# CompareInvariantIgnoreCase(wchar_t const *,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x180008780`
- end: `0x1800087df`
- name: `?CompareInvariantIgnoreCase@@YAHPEB_W_K01@Z`
- size: `95`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, unsigned __int64 cchCount1, PCNZWCH lpString2, unsigned __int64 cchCount2)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008608`
- `0x180068e64`
- `0x18007625c`

## callees

- `0x180008780`
- `0x18009e420`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800087ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800087ba`

## pseudocode

```c
__int64 __fastcall CompareInvariantIgnoreCase(
        PCNZWCH lpString1,
        unsigned __int64 cchCount1,
        PCNZWCH lpString2,
        unsigned __int64 cchCount2)
{
  if ( !lpString1 )
    return (unsigned int)-(lpString2 != 0);
  if ( !lpString2 )
    return 1;
  if ( cchCount2 > 0x7FFFFFFF || cchCount1 > 0x7FFFFFFF )
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(lpString1, cchCount1, lpString2, cchCount2);
  return (unsigned int)(CompareStringW(0x7Fu, 1u, lpString1, cchCount1, lpString2, cchCount2) - 2);
}

```

## disassembly

```asm
0x180008780  sub     rsp, 38h
0x180008784  test    rcx, rcx
0x180008787  jz      short loc_1800087C8
0x180008789  test    r8, r8
0x18000878c  jz      short loc_1800087D2
0x18000878e  cmp     r9, 7FFFFFFFh
0x180008795  ja      short loc_1800087D9
0x180008797  cmp     rdx, 7FFFFFFFh
0x18000879e  ja      short loc_1800087D9
0x1800087a0  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800087a5  mov     r9d, edx; cchCount1
0x1800087a8  mov     [rsp+38h+lpString2], r8; lpString2
0x1800087ad  mov     edx, 1; dwCmpFlags
0x1800087b2  mov     r8, rcx; lpString1
0x1800087b5  mov     ecx, 7Fh; Locale
0x1800087ba  call    cs:__imp_CompareStringW
0x1800087c0  sub     eax, 2
0x1800087c3  add     rsp, 38h
0x1800087c7  retn
0x1800087c8  neg     r8
0x1800087cb  sbb     eax, eax
0x1800087cd  add     rsp, 38h
0x1800087d1  retn
0x1800087d2  mov     eax, 1
0x1800087d7  jmp     short loc_1800087C3
0x1800087d9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
