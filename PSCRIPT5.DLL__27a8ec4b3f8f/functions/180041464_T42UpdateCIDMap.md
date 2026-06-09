# T42UpdateCIDMap

- ea: `0x180041464`
- end: `0x18004151b`
- name: `T42UpdateCIDMap`
- size: `183`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, const char *, __int64, STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003ddc0`

## callees

- `0x180005670`
- `0x180039e10`
- `0x18003a1f4`
- `0x18003a25c`
- `0x180041464`

## string_xrefs

- `0x1800414e2`: ` /%s UpdateCIDMap`

## pseudocode

```c
__int64 __fastcall T42UpdateCIDMap(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        const char *a4,
        __int64 a5,
        STRSAFE_LPSTR pszDest)
{
  __int64 v8; // r8
  unsigned __int16 v9; // bx

  StringCchPrintfA(pszDest, 0x80u, "%ld ", 2 * a3);
  if ( pszDest )
  {
    if ( !*pszDest )
      goto LABEL_6;
    v8 = -1;
    do
      ++v8;
    while ( pszDest[v8] );
    v9 = StrmPutBytes(a5, (__int64)pszDest, v8, 1);
    if ( !v9 )
LABEL_6:
      v9 = StrmPutWordAsciiHex(a5, a2);
  }
  else
  {
    v9 = 5;
  }
  StringCchPrintfA(pszDest, 0x80u, " /%s UpdateCIDMap", a4);
  if ( !v9 )
    return (unsigned __int16)StrmPutStringEOL(a5, pszDest);
  return v9;
}

```

## disassembly

```asm
0x180041464  push    rbx
0x180041466  push    rbp
0x180041467  push    rdi
0x180041468  push    r14
0x18004146a  push    r15
0x18004146c  sub     rsp, 20h
0x180041470  mov     rdi, [rsp+48h+pszDest]
0x180041475  mov     r14, r9
0x180041478  movzx   r9d, r8w
0x18004147c  movzx   ebp, dx
0x18004147f  add     r9d, r9d
0x180041482  lea     r8, aLd; "%ld "
0x180041489  mov     edx, 80h; cchDest
0x18004148e  mov     rcx, rdi; pszDest
0x180041491  call    StringCchPrintfA
0x180041496  xor     r15d, r15d
0x180041499  test    rdi, rdi
0x18004149c  jz      short loc_1800414DA
0x18004149e  cmp     [rdi], r15b
0x1800414a1  jz      short loc_1800414C8
0x1800414a3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800414a7  inc     r8
0x1800414aa  cmp     [rdi+r8], r15b
0x1800414ae  jnz     short loc_1800414A7
0x1800414b0  mov     rcx, [rsp+48h+arg_20]
0x1800414b5  mov     r9b, 1
0x1800414b8  mov     rdx, rdi
0x1800414bb  call    StrmPutBytes
0x1800414c0  movzx   ebx, ax
0x1800414c3  test    ax, ax
0x1800414c6  jnz     short loc_1800414DF
0x1800414c8  mov     rcx, [rsp+48h+arg_20]
0x1800414cd  movzx   edx, bp
0x1800414d0  call    StrmPutWordAsciiHex
0x1800414d5  movzx   ebx, ax
0x1800414d8  jmp     short loc_1800414DF
0x1800414da  mov     ebx, 5
0x1800414df  mov     r9, r14
0x1800414e2  lea     r8, aSUpdatecidmap; " /%s UpdateCIDMap"
0x1800414e9  mov     edx, 80h; cchDest
0x1800414ee  mov     rcx, rdi; pszDest
0x1800414f1  call    StringCchPrintfA
0x1800414f6  test    bx, bx
0x1800414f9  jnz     short loc_18004150B
0x1800414fb  mov     rcx, [rsp+48h+arg_20]
0x180041500  mov     rdx, rdi
0x180041503  call    StrmPutStringEOL
0x180041508  movzx   ebx, ax
0x18004150b  movzx   eax, bx
0x18004150e  add     rsp, 20h
0x180041512  pop     r15
0x180041514  pop     r14
0x180041516  pop     rdi
0x180041517  pop     rbp
0x180041518  pop     rbx
0x180041519  retn
```
