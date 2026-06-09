# PutStemSnapBugFix

- ea: `0x18004b5fc`
- end: `0x18004b688`
- name: `PutStemSnapBugFix`
- size: `140`
- prototype: `__int64 __fastcall(__int64, int, __int64, signed int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004dcf8`

## callees

- `0x18004b3a4`
- `0x18004b410`
- `0x18004b5fc`
- `0x18004b690`

## string_xrefs

- `0x18004b623`: `\n systemdict /internaldict known\n{1183615869 systemdict /internaldict get exec\n/StemSnapLength 2 copy known {get `

## pseudocode

```c
__int64 __fastcall PutStemSnapBugFix(__int64 a1, int a2, __int64 a3, signed int a4)
{
  int v4; // ebx
  __int64 i; // r10

  v4 = 0;
  for ( i = 0; (int)i < a4; i = (unsigned int)(i + 1) )
    v4 += *(_DWORD *)(a3 + 4 * i);
  PutString(
    a1,
    (__int64)"\r\n"
             " systemdict /internaldict known\r\n"
             "{1183615869 systemdict /internaldict get exec\r\n"
             "/StemSnapLength 2 copy known {get ");
  PutLongNumber(a1, a4);
  PutString(a1, (__int64)" lt} {pop pop true} ifelse}\r\n{true} ifelse {pop [");
  PutNumber(a1, a2, 0);
  PutString(a1, (__int64)" ");
  PutNumber(a1, v4, 0);
  return PutString(a1, (__int64)"]} if def\r\n");
}

```

## disassembly

```asm
0x18004b5fc  push    rbx
0x18004b5fe  push    rbp
0x18004b5ff  push    rsi
0x18004b600  push    rdi
0x18004b601  sub     rsp, 28h
0x18004b605  xor     ebx, ebx
0x18004b607  xor     r10d, r10d
0x18004b60a  mov     edi, r9d
0x18004b60d  mov     ebp, edx
0x18004b60f  mov     rsi, rcx
0x18004b612  test    r9d, r9d
0x18004b615  jle     short loc_18004B623
0x18004b617  add     ebx, [r8+r10*4]
0x18004b61b  inc     r10d
0x18004b61e  cmp     r10d, edi
0x18004b621  jl      short loc_18004B617
0x18004b623  lea     rdx, aSystemdictInte_0; "\r\n systemdict /internaldict known\r\n"...
0x18004b62a  call    PutString
0x18004b62f  mov     edx, edi
0x18004b631  mov     rcx, rsi
0x18004b634  call    PutLongNumber
0x18004b639  lea     rdx, aLtPopPopTrueIf; " lt} {pop pop true} ifelse}\r\n{true} i"...
0x18004b640  mov     rcx, rsi
0x18004b643  call    PutString
0x18004b648  xor     r8d, r8d
0x18004b64b  mov     edx, ebp
0x18004b64d  mov     rcx, rsi
0x18004b650  call    PutNumber
0x18004b655  lea     rdx, asc_180064A10; " "
0x18004b65c  mov     rcx, rsi
0x18004b65f  call    PutString
0x18004b664  xor     r8d, r8d
0x18004b667  mov     edx, ebx
0x18004b669  mov     rcx, rsi
0x18004b66c  call    PutNumber
0x18004b671  lea     rdx, aIfDef; "]} if def\r\n"
0x18004b678  mov     rcx, rsi
0x18004b67b  add     rsp, 28h
0x18004b67f  pop     rdi
0x18004b680  pop     rsi
0x18004b681  pop     rbp
0x18004b682  pop     rbx
0x18004b683  jmp     PutString
```
