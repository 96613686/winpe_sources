# T42UpdateCIDMap

- ea: `0x18003fbb0`
- end: `0x18003fc66`
- name: `T42UpdateCIDMap`
- size: `182`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003c508`

## callees

- `0x1800055e0`
- `0x18003858c`
- `0x180038968`
- `0x1800389cc`
- `0x18003fbb0`

## string_xrefs

- `0x18003fc2e`: ` /%s UpdateCIDMap`

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
  __int64 v8; // r9
  __int64 v9; // r8
  unsigned __int16 v10; // bx

  StringCchPrintfA(pszDest, 0x80u, "%ld ", 2 * a3);
  if ( pszDest )
  {
    if ( !*pszDest )
      goto LABEL_6;
    v9 = -1;
    do
      ++v9;
    while ( pszDest[v9] );
    LOBYTE(v8) = 1;
    v10 = StrmPutBytes(a5, pszDest, v9, v8);
    if ( !v10 )
LABEL_6:
      v10 = StrmPutWordAsciiHex(a5, a2);
  }
  else
  {
    v10 = 5;
  }
  StringCchPrintfA(pszDest, 0x80u, " /%s UpdateCIDMap", a4);
  if ( !v10 )
    return (unsigned __int16)StrmPutStringEOL(a5, pszDest);
  return v10;
}

```

## disassembly

```asm
0x18003fbb0  push    rbx
0x18003fbb2  push    rbp
0x18003fbb3  push    rdi
0x18003fbb4  push    r14
0x18003fbb6  push    r15
0x18003fbb8  sub     rsp, 20h
0x18003fbbc  mov     rdi, [rsp+48h+pszDest]
0x18003fbc1  mov     r14, r9
0x18003fbc4  movzx   r9d, r8w
0x18003fbc8  movzx   ebp, dx
0x18003fbcb  add     r9d, r9d
0x18003fbce  lea     r8, aLd; "%ld "
0x18003fbd5  mov     edx, 80h; cchDest
0x18003fbda  mov     rcx, rdi; pszDest
0x18003fbdd  call    StringCchPrintfA
0x18003fbe2  xor     r15d, r15d
0x18003fbe5  test    rdi, rdi
0x18003fbe8  jz      short loc_18003FC26
0x18003fbea  cmp     [rdi], r15b
0x18003fbed  jz      short loc_18003FC14
0x18003fbef  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003fbf3  inc     r8
0x18003fbf6  cmp     [rdi+r8], r15b
0x18003fbfa  jnz     short loc_18003FBF3
0x18003fbfc  mov     rcx, [rsp+48h+arg_20]
0x18003fc01  mov     r9b, 1
0x18003fc04  mov     rdx, rdi
0x18003fc07  call    StrmPutBytes
0x18003fc0c  movzx   ebx, ax
0x18003fc0f  test    ax, ax
0x18003fc12  jnz     short loc_18003FC2B
0x18003fc14  mov     rcx, [rsp+48h+arg_20]
0x18003fc19  movzx   edx, bp
0x18003fc1c  call    StrmPutWordAsciiHex
0x18003fc21  movzx   ebx, ax
0x18003fc24  jmp     short loc_18003FC2B
0x18003fc26  mov     ebx, 5
0x18003fc2b  mov     r9, r14
0x18003fc2e  lea     r8, aSUpdatecidmap; " /%s UpdateCIDMap"
0x18003fc35  mov     edx, 80h; cchDest
0x18003fc3a  mov     rcx, rdi; pszDest
0x18003fc3d  call    StringCchPrintfA
0x18003fc42  test    bx, bx
0x18003fc45  jnz     short loc_18003FC57
0x18003fc47  mov     rcx, [rsp+48h+arg_20]
0x18003fc4c  mov     rdx, rdi
0x18003fc4f  call    StrmPutStringEOL
0x18003fc54  movzx   ebx, ax
0x18003fc57  movzx   eax, bx
0x18003fc5a  add     rsp, 20h
0x18003fc5e  pop     r15
0x18003fc60  pop     r14
0x18003fc62  pop     rdi
0x18003fc63  pop     rbp
0x18003fc64  pop     rbx
0x18003fc65  retn
```
