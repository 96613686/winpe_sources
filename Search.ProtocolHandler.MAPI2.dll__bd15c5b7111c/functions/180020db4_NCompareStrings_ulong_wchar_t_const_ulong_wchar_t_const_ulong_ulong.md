# NCompareStrings(ulong,wchar_t const *,ulong,wchar_t const *,ulong,ulong)

- ea: `0x180020db4`
- end: `0x180020e3c`
- name: `?NCompareStrings@@YAHKPEB_WK0KK@Z`
- size: `136`
- prototype: `int(unsigned int, const wchar_t *, unsigned int, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a0d0`

## callees

- `0x180020db4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180020e1d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180020e1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020df8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020df8`

## pseudocode

```c
__int64 __fastcall NCompareStrings(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *lpString2,
        unsigned int a5,
        unsigned int cchCount1)
{
  int v6; // edi
  int cchCount2; // ebx
  int v10; // eax

  v6 = a3;
  cchCount2 = a5;
  if ( a3 >= cchCount1 )
    v6 = cchCount1;
  if ( a5 >= cchCount1 )
    cchCount2 = cchCount1;
  v10 = CompareStringW(0x800u, 1u, a2, v6, lpString2, cchCount2);
  switch ( v10 )
  {
    case 1:
      return 0xFFFFFFFFLL;
    case 2:
      return 0;
    case 3:
      return 1;
  }
  if ( v6 < cchCount2 )
    cchCount2 = v6;
  return _o__wcsnicmp(a2, lpString2, cchCount2);
}

```

## disassembly

```asm
0x180020db4  push    rbx
0x180020db6  push    rbp
0x180020db7  push    rsi
0x180020db8  push    rdi
0x180020db9  sub     rsp, 38h
0x180020dbd  mov     eax, [rsp+58h+cchCount1]
0x180020dc4  mov     edi, r8d
0x180020dc7  mov     ebx, [rsp+58h+arg_20]
0x180020dce  cmp     r8d, eax
0x180020dd1  mov     rsi, r9
0x180020dd4  mov     rbp, rdx
0x180020dd7  cmovnb  edi, eax
0x180020dda  mov     r8, rdx; lpString1
0x180020ddd  cmp     ebx, eax
0x180020ddf  mov     edx, 1; dwCmpFlags
0x180020de4  mov     ecx, 800h; Locale
0x180020de9  cmovnb  ebx, eax
0x180020dec  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180020df0  mov     [rsp+58h+lpString2], r9; lpString2
0x180020df5  mov     r9d, edi; cchCount1
0x180020df8  call    cs:__imp_CompareStringW
0x180020dfe  mov     ecx, eax
0x180020e00  sub     ecx, 1
0x180020e03  jz      short loc_180020E30
0x180020e05  sub     ecx, 1
0x180020e08  jz      short loc_180020E2C
0x180020e0a  cmp     ecx, 1
0x180020e0d  jz      short loc_180020E25
0x180020e0f  cmp     edi, ebx
0x180020e11  mov     rdx, rsi
0x180020e14  mov     rcx, rbp
0x180020e17  cmovl   ebx, edi
0x180020e1a  movsxd  r8, ebx
0x180020e1d  call    cs:__imp__o__wcsnicmp
0x180020e23  jmp     short loc_180020E33
0x180020e25  mov     eax, 1
0x180020e2a  jmp     short loc_180020E33
0x180020e2c  xor     eax, eax
0x180020e2e  jmp     short loc_180020E33
0x180020e30  or      eax, 0FFFFFFFFh
0x180020e33  add     rsp, 38h
0x180020e37  pop     rdi
0x180020e38  pop     rsi
0x180020e39  pop     rbp
0x180020e3a  pop     rbx
0x180020e3b  retn
```
