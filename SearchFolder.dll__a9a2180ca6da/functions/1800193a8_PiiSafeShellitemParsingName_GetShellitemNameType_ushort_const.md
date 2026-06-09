# PiiSafeShellitemParsingName::GetShellitemNameType(ushort const *)

- ea: `0x1800193a8`
- end: `0x180019468`
- name: `?GetShellitemNameType@PiiSafeShellitemParsingName@@CA?AW4ShellItemParsingNameType@@PEBG@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006250`

## callees

- `0x180006900`
- `0x1800193a8`
- `0x18004faf4`

## import_xrefs

- `SHLWAPI!PathIsURLW` at `0x18001940f`
- `SHLWAPI!PathIsURLW` at `0x18001940f`
- `SHLWAPI!PathIsUNCW` at `0x180019423`
- `SHLWAPI!PathIsUNCW` at `0x180019423`

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
0x1800193a8  push    rbp
0x1800193aa  push    rbx
0x1800193ab  push    rsi
0x1800193ac  push    rdi
0x1800193ad  mov     rbp, rsp
0x1800193b0  sub     rsp, 48h
0x1800193b4  mov     rax, cs:__security_cookie
0x1800193bb  xor     rax, rsp
0x1800193be  mov     [rbp+var_10], rax
0x1800193c2  mov     esi, 65h ; 'e'
0x1800193c7  mov     dword ptr [rbp+String2], 650073h
0x1800193ce  xor     eax, eax
0x1800193d0  mov     [rbp+var_24], 720061h
0x1800193d7  lea     rdx, [rbp+String2]; String2
0x1800193db  mov     [rbp+var_20], 680063h
0x1800193e2  mov     rbx, rcx
0x1800193e5  mov     [rbp+var_1C], 6D002Dh
0x1800193ec  lea     r8d, [rsi-5Bh]; MaxCount
0x1800193f0  mov     [rbp+var_18], 3A0073h
0x1800193f7  lea     edi, [rsi-2Bh]
0x1800193fa  mov     [rbp+var_14], ax
0x1800193fe  call    wcsncmp_0
0x180019403  test    eax, eax
0x180019405  jnz     short loc_18001940C
0x180019407  lea     eax, [rsi+1]
0x18001940a  jmp     short loc_180019453
0x18001940c  mov     rcx, rbx; pszPath
0x18001940f  call    cs:__imp_PathIsURLW
0x180019415  test    eax, eax
0x180019417  jz      short loc_180019420
0x180019419  mov     eax, 64h ; 'd'
0x18001941e  jmp     short loc_180019453
0x180019420  mov     rcx, rbx; pszPath
0x180019423  call    cs:__imp_PathIsUNCW
0x180019429  test    eax, eax
0x18001942b  jz      short loc_180019431
0x18001942d  mov     eax, esi
0x18001942f  jmp     short loc_180019453
0x180019431  cmp     [rbx], di
0x180019434  jnz     short loc_18001944E
0x180019436  cmp     [rbx+2], di
0x18001943a  jnz     short loc_18001944E
0x18001943c  movzx   eax, word ptr [rbx+4]
0x180019440  sub     ax, 7Bh ; '{'
0x180019444  neg     ax
0x180019447  sbb     eax, eax
0x180019449  add     eax, 0Bh
0x18001944c  jmp     short loc_180019453
0x18001944e  mov     eax, 0Ah
0x180019453  mov     rcx, [rbp+var_10]
0x180019457  xor     rcx, rsp; StackCookie
0x18001945a  call    __security_check_cookie
0x18001945f  add     rsp, 48h
0x180019463  pop     rdi
0x180019464  pop     rsi
0x180019465  pop     rbx
0x180019466  pop     rbp
0x180019467  retn
```
