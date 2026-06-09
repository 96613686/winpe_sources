# PiiSafeShellitemParsingName::GetShellitemNameType(ushort const *)

- ea: `0x180074738`
- end: `0x1800747f8`
- name: `?GetShellitemNameType@PiiSafeShellitemParsingName@@CA?AW4ShellItemParsingNameType@@PEBG@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180072b88`

## callees

- `0x180037780`
- `0x180074738`
- `0x180083464`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18007479f`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18007479f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800747b3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800747b3`

## pseudocode

```c
__int64 __fastcall PiiSafeShellitemParsingName::GetShellitemNameType(__int64 a1)
{
  wchar_t String2[12]; // [rsp+20h] [rbp-28h] BYREF

  wcscpy(String2, L"search-ms:");
  if ( !wcsncmp_0((const wchar_t *)a1, String2, 0xAu) )
    return 102;
  if ( PathIsURLW((LPCWSTR)a1) )
    return 100;
  if ( PathIsUNCW((LPCWSTR)a1) )
    return 101;
  if ( *(_WORD *)a1 == 58 && *(_WORD *)(a1 + 2) == 58 )
    return 11 - (unsigned int)(*(_WORD *)(a1 + 4) != 123);
  return 10;
}

```

## disassembly

```asm
0x180074738  push    rbp
0x18007473a  push    rbx
0x18007473b  push    rsi
0x18007473c  push    rdi
0x18007473d  mov     rbp, rsp
0x180074740  sub     rsp, 48h
0x180074744  mov     rax, cs:__security_cookie
0x18007474b  xor     rax, rsp
0x18007474e  mov     [rbp+var_10], rax
0x180074752  mov     esi, 65h ; 'e'
0x180074757  mov     dword ptr [rbp+String2], 650073h
0x18007475e  xor     eax, eax
0x180074760  mov     [rbp+var_24], 720061h
0x180074767  lea     rdx, [rbp+String2]; String2
0x18007476b  mov     [rbp+var_20], 680063h
0x180074772  mov     rbx, rcx
0x180074775  mov     [rbp+var_1C], 6D002Dh
0x18007477c  lea     r8d, [rsi-5Bh]; MaxCount
0x180074780  mov     [rbp+var_18], 3A0073h
0x180074787  lea     edi, [rsi-2Bh]
0x18007478a  mov     [rbp+var_14], ax
0x18007478e  call    wcsncmp_0
0x180074793  test    eax, eax
0x180074795  jnz     short loc_18007479C
0x180074797  lea     eax, [rsi+1]
0x18007479a  jmp     short loc_1800747E3
0x18007479c  mov     rcx, rbx; pszPath
0x18007479f  call    cs:__imp_PathIsURLW
0x1800747a5  test    eax, eax
0x1800747a7  jz      short loc_1800747B0
0x1800747a9  mov     eax, 64h ; 'd'
0x1800747ae  jmp     short loc_1800747E3
0x1800747b0  mov     rcx, rbx; pszPath
0x1800747b3  call    cs:__imp_PathIsUNCW
0x1800747b9  test    eax, eax
0x1800747bb  jz      short loc_1800747C1
0x1800747bd  mov     eax, esi
0x1800747bf  jmp     short loc_1800747E3
0x1800747c1  cmp     [rbx], di
0x1800747c4  jnz     short loc_1800747DE
0x1800747c6  cmp     [rbx+2], di
0x1800747ca  jnz     short loc_1800747DE
0x1800747cc  movzx   eax, word ptr [rbx+4]
0x1800747d0  sub     ax, 7Bh ; '{'
0x1800747d4  neg     ax
0x1800747d7  sbb     eax, eax
0x1800747d9  add     eax, 0Bh
0x1800747dc  jmp     short loc_1800747E3
0x1800747de  mov     eax, 0Ah
0x1800747e3  mov     rcx, [rbp+var_10]
0x1800747e7  xor     rcx, rsp; StackCookie
0x1800747ea  call    __security_check_cookie
0x1800747ef  add     rsp, 48h
0x1800747f3  pop     rdi
0x1800747f4  pop     rsi
0x1800747f5  pop     rbx
0x1800747f6  pop     rbp
0x1800747f7  retn
```
