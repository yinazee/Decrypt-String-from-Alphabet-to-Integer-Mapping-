# Decrypt-String-from-Alphabet-to-Integer-Mapping-
Leetcode Challege - Javascript

// var freqAlphabets = function(s) {
//         const obj = {
//         ‘a’: ‘1’,
//         ‘b’: ‘2’,
//         ‘c’: ‘3’,
//         ‘d’: ‘4’,
//         ‘e’: ‘5’,
//         ‘f’: ‘6’,
//         ‘g’: ‘7’,
//         ‘h’: ‘8’,
//         ‘i’: ‘9’,
//         ‘j’: ‘10’,
//         ‘k’: ‘11’,
//         ‘l’: ‘12’,
//         ‘m’: ‘13’,
//         ‘n’: ‘14’,
//         ‘o’: ‘15’,
//         ‘p’: ‘16’,
//         ‘q’: ‘17’,
//         ‘r’: ‘18’,
//         ‘s’: ‘19’,
//         ‘t’: ‘20’,
//         ‘u’: ‘21’,
//         ‘v’: ‘22’,
//         ‘w’: ‘23’,
//         ‘x’: ‘24’,
//         ‘y’: ‘25’,
//         ‘z’: ‘26’,
//         }
//     // flip the key values pairs because I wrote it backwards T_T
//     let cipher = {}
//     for (const key in obj) {
//         cipher[obj[key]] = key;
//     }
//     let string = ‘’ // bakj [‘b’, ...] jkab
//     for (let i = s.length - 1; i > -1; i--) {
//         let current;
//         if (s[i] === ‘#’) {
//             current = s[i-2] + s[i-1]; // ‘10’
//             i = i - 2
//         } else { // is single digit
//             // set current to letter equivalent
//             current = s[i]
//         }
//         // append current to string
//         string += cipher[current];
//     }
//     return string.split(‘’).reverse().join(‘’);
// };

var freqAlphabets = function(s) {
    const CHAR_CODE_OFFSET = 96;
    let solStr = ''; 
    
    for (let i = 0; i < s.length; i++) {
        let currNumber = s[i];
        
        if (s[i + 2] === '#') {
            currNumber = s.slice(i, i + 2);
            i += 2;
        }
            
        solStr += String.fromCharCode(parseInt(currNumber) + CHAR_CODE_OFFSET);
    }
    
    return solStr;
};





