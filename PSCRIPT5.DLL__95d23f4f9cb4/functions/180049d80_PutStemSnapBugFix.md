# PutStemSnapBugFix

- ea: `0x180049d80`
- end: `0x180049e0c`
- name: `PutStemSnapBugFix`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004c470`

## callees

- `0x180049b2c`
- `0x180049b98`
- `0x180049d80`
- `0x180049e14`

## string_xrefs

- `0x180049da7`: `\n systemdict /internaldict known\n{1183615869 systemdict /internaldict get exec\n/StemSnapLength 2 copy known {get `

## pseudocode

```c
__int64 __fastcall PutStemSnapBugFix(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v4; // ebx
  __int64 i; // r10

  v4 = 0;
  for ( i = 0; (int)i < a4; i = (unsigned int)(i + 1) )
    v4 += *(_DWORD *)(a3 + 4 * i);
  PutString(
    a1,
    "\r\n"
    " systemdict /internaldict known\r\n"
    "{1183615869 systemdict /internaldict get exec\r\n"
    "/StemSnapLength 2 copy known {get ");
  PutLongNumber(a1, (unsigned int)a4);
  PutString(a1, " lt} {pop pop true} ifelse}\r\n{true} ifelse {pop [");
  PutNumber(a1, a2, 0);
  PutString(a1, " ");
  PutNumber(a1, v4, 0);
  return PutString(a1, "]} if def\r\n");
}

```

## disassembly

```asm
0x180049d80  push    rbx
0x180049d82  push    rbp
0x180049d83  push    rsi
0x180049d84  push    rdi
0x180049d85  sub     rsp, 28h
0x180049d89  xor     ebx, ebx
0x180049d8b  xor     r10d, r10d
0x180049d8e  mov     edi, r9d
0x180049d91  mov     ebp, edx
0x180049d93  mov     rsi, rcx
0x180049d96  test    r9d, r9d
0x180049d99  jle     short loc_180049DA7
0x180049d9b  add     ebx, [r8+r10*4]
0x180049d9f  inc     r10d
0x180049da2  cmp     r10d, edi
0x180049da5  jl      short loc_180049D9B
0x180049da7  lea     rdx, aSystemdictInte_0; "\r\n systemdict /internaldict known\r\n"...
0x180049dae  call    PutString
0x180049db3  mov     edx, edi
0x180049db5  mov     rcx, rsi
0x180049db8  call    PutLongNumber
0x180049dbd  lea     rdx, aLtPopPopTrueIf; " lt} {pop pop true} ifelse}\r\n{true} i"...
0x180049dc4  mov     rcx, rsi
0x180049dc7  call    PutString
0x180049dcc  xor     r8d, r8d
0x180049dcf  mov     edx, ebp
0x180049dd1  mov     rcx, rsi
0x180049dd4  call    PutNumber
0x180049dd9  lea     rdx, asc_180062A20; " "
0x180049de0  mov     rcx, rsi
0x180049de3  call    PutString
0x180049de8  xor     r8d, r8d
0x180049deb  mov     edx, ebx
0x180049ded  mov     rcx, rsi
0x180049df0  call    PutNumber
0x180049df5  lea     rdx, aIfDef; "]} if def\r\n"
0x180049dfc  mov     rcx, rsi
0x180049dff  add     rsp, 28h
0x180049e03  pop     rdi
0x180049e04  pop     rsi
0x180049e05  pop     rbp
0x180049e06  pop     rbx
0x180049e07  jmp     PutString
```
