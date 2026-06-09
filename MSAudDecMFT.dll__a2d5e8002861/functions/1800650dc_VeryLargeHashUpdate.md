# VeryLargeHashUpdate

- ea: `0x1800650dc`
- end: `0x18006540b`
- name: `VeryLargeHashUpdate`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18006400c`

## callees

- `0x180049260`
- `0x18004a5b0`
- `0x18004a8c0`
- `0x18004d320`
- `0x18004dd14`
- `0x1800650dc`

## pseudocode

```c
__int64 __fastcall VeryLargeHashUpdate(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rdx
  _BYTE *v12; // rcx
  __int64 v13; // rdx
  _BYTE *v14; // rcx
  _BYTE v16[4]; // [rsp+20h] [rbp-B9h] BYREF
  int v17; // [rsp+24h] [rbp-B5h]
  _BYTE v18[20]; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v19[20]; // [rsp+B4h] [rbp-25h] BYREF
  _BYTE v20[20]; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v21[20]; // [rsp+DCh] [rbp+3h] BYREF

  v17 = 0;
  memset_0(v16, 0, 0x7Cu);
  if ( !a3 )
    return 0;
  if ( !a1 )
    return 0;
  v6 = a2 >> 2;
  if ( !(_DWORD)v6 )
    return 0;
  v7 = (unsigned int)v6;
  v8 = a1 + v6;
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3, 20);
  SymCryptSha1Append(v16, a1, (unsigned int)v7);
  SymCryptSha1Append(v16, a3 + 20, 20);
  SymCryptSha1Append(v16, v8, (unsigned int)v7);
  SymCryptSha1Result(v16, v18);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3 + 20, 20);
  SymCryptSha1Append(v16, v8, (unsigned int)v7);
  SymCryptSha1Append(v16, a3, 20);
  SymCryptSha1Append(v16, a1, (unsigned int)v7);
  SymCryptSha1Result(v16, v19);
  v9 = v8 + v7;
  v10 = v8 + v7 + v7;
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3 + 40, 20);
  SymCryptSha1Append(v16, v9, (unsigned int)v7);
  SymCryptSha1Append(v16, a3 + 60, 20);
  SymCryptSha1Append(v16, v10, (unsigned int)v7);
  SymCryptSha1Result(v16, v20);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3 + 60, 20);
  SymCryptSha1Append(v16, v10, (unsigned int)v7);
  SymCryptSha1Append(v16, a3 + 40, 20);
  SymCryptSha1Append(v16, v9, (unsigned int)v7);
  SymCryptSha1Result(v16, v21);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v18, 20);
  SymCryptSha1Append(v16, v20, 20);
  SymCryptSha1Result(v16, a3);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v19, 20);
  SymCryptSha1Append(v16, v21, 20);
  SymCryptSha1Result(v16, a3 + 20);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v20, 20);
  SymCryptSha1Append(v16, v18, 20);
  SymCryptSha1Result(v16, a3 + 40);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v21, 20);
  SymCryptSha1Append(v16, v19, 20);
  SymCryptSha1Result(v16, a3 + 60);
  v11 = 128;
  v12 = v16;
  do
  {
    *v12++ = 0;
    --v11;
  }
  while ( v11 );
  v13 = 80;
  v14 = v18;
  do
  {
    *v14++ = 0;
    --v13;
  }
  while ( v13 );
  return 1;
}

```

## disassembly

```asm
0x1800650dc  mov     [rsp-8+arg_18], rbx
0x1800650e1  push    rbp
0x1800650e2  push    rsi
0x1800650e3  push    rdi
0x1800650e4  push    r12
0x1800650e6  push    r13
0x1800650e8  push    r14
0x1800650ea  push    r15
0x1800650ec  lea     rbp, [rsp-27h]
0x1800650f1  sub     rsp, 100h
0x1800650f8  mov     rax, cs:__security_cookie
0x1800650ff  xor     rax, rsp
0x180065102  mov     [rbp+57h+var_40], rax
0x180065106  xor     eax, eax
0x180065108  mov     r12, r8
0x18006510b  mov     ebx, edx
0x18006510d  mov     [rsp+130h+var_10C], eax
0x180065111  mov     rdi, rcx
0x180065114  xor     edx, edx; Val
0x180065116  lea     rcx, [rsp+130h+var_110]; void *
0x18006511b  lea     r8d, [rax+7Ch]; Size
0x18006511f  call    memset_0
0x180065124  test    r12, r12
0x180065127  jz      loc_1800653E1
0x18006512d  test    rdi, rdi
0x180065130  jz      loc_1800653E1
0x180065136  shr     ebx, 2
0x180065139  test    ebx, ebx
0x18006513b  jz      loc_1800653E1
0x180065141  mov     r14d, ebx
0x180065144  lea     rcx, [rsp+130h+var_110]
0x180065149  add     rbx, rdi
0x18006514c  lea     r13, [r12+14h]
0x180065151  call    SymCryptSha1Init
0x180065156  mov     esi, 14h
0x18006515b  lea     rcx, [rsp+130h+var_110]
0x180065160  mov     r8d, esi
0x180065163  mov     rdx, r12
0x180065166  call    SymCryptSha1Append
0x18006516b  mov     r8d, r14d
0x18006516e  lea     rcx, [rsp+130h+var_110]
0x180065173  mov     rdx, rdi
0x180065176  call    SymCryptSha1Append
0x18006517b  mov     r8d, esi
0x18006517e  lea     rcx, [rsp+130h+var_110]
0x180065183  mov     rdx, r13
0x180065186  call    SymCryptSha1Append
0x18006518b  mov     r8d, r14d
0x18006518e  lea     rcx, [rsp+130h+var_110]
0x180065193  mov     rdx, rbx
0x180065196  call    SymCryptSha1Append
0x18006519b  lea     rdx, [rbp+57h+var_90]
0x18006519f  lea     rcx, [rsp+130h+var_110]
0x1800651a4  call    SymCryptSha1Result
0x1800651a9  lea     rcx, [rsp+130h+var_110]
0x1800651ae  call    SymCryptSha1Init
0x1800651b3  mov     r8d, esi
0x1800651b6  lea     rcx, [rsp+130h+var_110]
0x1800651bb  mov     rdx, r13
0x1800651be  call    SymCryptSha1Append
0x1800651c3  mov     r8d, r14d
0x1800651c6  lea     rcx, [rsp+130h+var_110]
0x1800651cb  mov     rdx, rbx
0x1800651ce  call    SymCryptSha1Append
0x1800651d3  mov     r8d, esi
0x1800651d6  lea     rcx, [rsp+130h+var_110]
0x1800651db  mov     rdx, r12
0x1800651de  call    SymCryptSha1Append
0x1800651e3  mov     r8d, r14d
0x1800651e6  lea     rcx, [rsp+130h+var_110]
0x1800651eb  mov     rdx, rdi
0x1800651ee  call    SymCryptSha1Append
0x1800651f3  lea     rdx, [rbp+57h+var_7C]
0x1800651f7  lea     rcx, [rsp+130h+var_110]
0x1800651fc  call    SymCryptSha1Result
0x180065201  lea     rsi, [r13+14h]
0x180065205  lea     rdi, [rbx+r14]
0x180065209  lea     rcx, [rsp+130h+var_110]
0x18006520e  lea     r15, [rsi+14h]
0x180065212  lea     rbx, [rdi+r14]
0x180065216  call    SymCryptSha1Init
0x18006521b  mov     r8d, 14h
0x180065221  lea     rcx, [rsp+130h+var_110]
0x180065226  mov     rdx, rsi
0x180065229  call    SymCryptSha1Append
0x18006522e  mov     r8d, r14d
0x180065231  lea     rcx, [rsp+130h+var_110]
0x180065236  mov     rdx, rdi
0x180065239  call    SymCryptSha1Append
0x18006523e  mov     r8d, 14h
0x180065244  lea     rcx, [rsp+130h+var_110]
0x180065249  mov     rdx, r15
0x18006524c  call    SymCryptSha1Append
0x180065251  mov     r8d, r14d
0x180065254  lea     rcx, [rsp+130h+var_110]
0x180065259  mov     rdx, rbx
0x18006525c  call    SymCryptSha1Append
0x180065261  lea     rdx, [rbp+57h+var_68]
0x180065265  lea     rcx, [rsp+130h+var_110]
0x18006526a  call    SymCryptSha1Result
0x18006526f  lea     rcx, [rsp+130h+var_110]
0x180065274  call    SymCryptSha1Init
0x180065279  mov     r8d, 14h
0x18006527f  lea     rcx, [rsp+130h+var_110]
0x180065284  mov     rdx, r15
0x180065287  call    SymCryptSha1Append
0x18006528c  mov     r8d, r14d
0x18006528f  lea     rcx, [rsp+130h+var_110]
0x180065294  mov     rdx, rbx
0x180065297  call    SymCryptSha1Append
0x18006529c  mov     ebx, 14h
0x1800652a1  lea     rcx, [rsp+130h+var_110]
0x1800652a6  mov     r8d, ebx
0x1800652a9  mov     rdx, rsi
0x1800652ac  call    SymCryptSha1Append
0x1800652b1  mov     r8d, r14d
0x1800652b4  lea     rcx, [rsp+130h+var_110]
0x1800652b9  mov     rdx, rdi
0x1800652bc  call    SymCryptSha1Append
0x1800652c1  lea     rdx, [rbp+57h+var_54]
0x1800652c5  lea     rcx, [rsp+130h+var_110]
0x1800652ca  call    SymCryptSha1Result
0x1800652cf  lea     rcx, [rsp+130h+var_110]
0x1800652d4  call    SymCryptSha1Init
0x1800652d9  mov     r8d, ebx
0x1800652dc  lea     rdx, [rbp+57h+var_90]
0x1800652e0  lea     rcx, [rsp+130h+var_110]
0x1800652e5  call    SymCryptSha1Append
0x1800652ea  mov     r8d, ebx
0x1800652ed  lea     rdx, [rbp+57h+var_68]
0x1800652f1  lea     rcx, [rsp+130h+var_110]
0x1800652f6  call    SymCryptSha1Append
0x1800652fb  mov     rdx, r12
0x1800652fe  lea     rcx, [rsp+130h+var_110]
0x180065303  call    SymCryptSha1Result
0x180065308  lea     rcx, [rsp+130h+var_110]
0x18006530d  call    SymCryptSha1Init
0x180065312  mov     r8d, ebx
0x180065315  lea     rdx, [rbp+57h+var_7C]
0x180065319  lea     rcx, [rsp+130h+var_110]
0x18006531e  call    SymCryptSha1Append
0x180065323  mov     r8d, ebx
0x180065326  lea     rdx, [rbp+57h+var_54]
0x18006532a  lea     rcx, [rsp+130h+var_110]
0x18006532f  call    SymCryptSha1Append
0x180065334  mov     rdx, r13
0x180065337  lea     rcx, [rsp+130h+var_110]
0x18006533c  call    SymCryptSha1Result
0x180065341  lea     rcx, [rsp+130h+var_110]
0x180065346  call    SymCryptSha1Init
0x18006534b  mov     r8d, ebx
0x18006534e  lea     rdx, [rbp+57h+var_68]
0x180065352  lea     rcx, [rsp+130h+var_110]
0x180065357  call    SymCryptSha1Append
0x18006535c  mov     r8d, ebx
0x18006535f  lea     rdx, [rbp+57h+var_90]
0x180065363  lea     rcx, [rsp+130h+var_110]
0x180065368  call    SymCryptSha1Append
0x18006536d  mov     rdx, rsi
0x180065370  lea     rcx, [rsp+130h+var_110]
0x180065375  call    SymCryptSha1Result
0x18006537a  lea     rcx, [rsp+130h+var_110]
0x18006537f  call    SymCryptSha1Init
0x180065384  mov     r8d, ebx
0x180065387  lea     rdx, [rbp+57h+var_54]
0x18006538b  lea     rcx, [rsp+130h+var_110]
0x180065390  call    SymCryptSha1Append
0x180065395  mov     r8d, ebx
0x180065398  lea     rdx, [rbp+57h+var_7C]
0x18006539c  lea     rcx, [rsp+130h+var_110]
0x1800653a1  call    SymCryptSha1Append
0x1800653a6  mov     rdx, r15
0x1800653a9  lea     rcx, [rsp+130h+var_110]
0x1800653ae  call    SymCryptSha1Result
0x1800653b3  lea     edx, [rbx+6Ch]
0x1800653b6  lea     rcx, [rsp+130h+var_110]
0x1800653bb  mov     byte ptr [rcx], 0
0x1800653be  inc     rcx
0x1800653c1  sub     rdx, 1
0x1800653c5  jnz     short loc_1800653BB
0x1800653c7  mov     edx, 50h ; 'P'
0x1800653cc  lea     rcx, [rbp+57h+var_90]
0x1800653d0  mov     byte ptr [rcx], 0
0x1800653d3  inc     rcx
0x1800653d6  sub     rdx, 1
0x1800653da  jnz     short loc_1800653D0
0x1800653dc  lea     eax, [rdx+1]
0x1800653df  jmp     short loc_1800653E3
0x1800653e1  xor     eax, eax
0x1800653e3  mov     rcx, [rbp+57h+var_40]
0x1800653e7  xor     rcx, rsp; StackCookie
0x1800653ea  call    __security_check_cookie
0x1800653ef  mov     rbx, [rsp+130h+arg_18]
0x1800653f7  add     rsp, 100h
0x1800653fe  pop     r15
0x180065400  pop     r14
0x180065402  pop     r13
0x180065404  pop     r12
0x180065406  pop     rdi
0x180065407  pop     rsi
0x180065408  pop     rbp
0x180065409  retn
```
