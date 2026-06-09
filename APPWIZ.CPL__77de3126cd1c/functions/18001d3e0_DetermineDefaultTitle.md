# DetermineDefaultTitle

- ea: `0x18001d3e0`
- end: `0x18001d4e7`
- name: `DetermineDefaultTitle`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001c5cc`
- `0x18005557c`

## callees

- `0x18000791c`
- `0x18001d3e0`
- `0x1800582e0`

## import_xrefs

- `SHELL32!__imp_SHGetNewLinkInfoW` at `0x18001d441`
- `SHELL32!__imp_SHGetNewLinkInfoW` at `0x18001d441`
- `SHLWAPI!PathFindFileNameW` at `0x18001d450`
- `SHLWAPI!PathFindFileNameW` at `0x18001d450`
- `SHLWAPI!PathFindExtensionW` at `0x18001d461`
- `SHLWAPI!PathFindExtensionW` at `0x18001d461`

## pseudocode

```c
BOOL __fastcall DetermineDefaultTitle(__int64 a1)
{
  int v2; // eax
  BOOL result; // eax
  const WCHAR *FileNameW; // rax
  const unsigned __int16 *v5; // rdi
  LPWSTR ExtensionW; // rax
  int v7; // r11d
  const unsigned __int16 *v8; // r8
  BOOL pfMustCopy; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszName[264]; // [rsp+40h] [rbp-228h] BYREF

  *(_DWORD *)(a1 + 8) &= ~0x200u;
  v2 = *(_DWORD *)(a1 + 8) & 0x10000000;
  pfMustCopy = 0;
  result = SHGetNewLinkInfoW((LPCWSTR)(a1 + (v2 != 0 ? 532LL : 12LL)), *(LPCWSTR *)(a1 + 2624), pszName, &pfMustCopy, 0);
  if ( result )
  {
    FileNameW = PathFindFileNameW(pszName);
    v5 = FileNameW;
    if ( FileNameW )
    {
      ExtensionW = PathFindExtensionW(FileNameW);
      if ( *ExtensionW )
        *ExtensionW = 0;
    }
    StringCchCopyW((unsigned __int16 *)(a1 + 1572), 0x104u, v5);
    v7 = *(_DWORD *)(a1 + 8);
    if ( (v7 & 4) != 0 )
    {
      v8 = L".pif";
    }
    else
    {
      if ( pfMustCopy )
        *(_DWORD *)(a1 + 8) = v7 | 0x200;
      v8 = L".lnk";
    }
    StringCchCopyW((unsigned __int16 *)(a1 + 3312), 0x104u, v8);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001d3e0  mov     [rsp+arg_8], rbx
0x18001d3e5  mov     [rsp+arg_10], rsi
0x18001d3ea  push    rdi
0x18001d3eb  sub     rsp, 260h
0x18001d3f2  mov     rax, cs:__security_cookie
0x18001d3f9  xor     rax, rsp
0x18001d3fc  mov     [rsp+268h+var_18], rax
0x18001d404  btr     dword ptr [rcx+8], 9
0x18001d409  lea     r9, [rsp+268h+pfMustCopy]; pfMustCopy
0x18001d40e  mov     eax, [rcx+8]
0x18001d411  lea     r8, [rsp+268h+pszName]; pszName
0x18001d416  mov     rbx, rcx
0x18001d419  xor     esi, esi
0x18001d41b  and     eax, 10000000h
0x18001d420  mov     [rsp+268h+pfMustCopy], esi
0x18001d424  neg     eax
0x18001d426  mov     [rsp+268h+uFlags], esi; uFlags
0x18001d42a  mov     rdx, [rbx+0A40h]; pszDir
0x18001d431  sbb     rcx, rcx
0x18001d434  and     ecx, 208h
0x18001d43a  add     rcx, 0Ch
0x18001d43e  add     rcx, rbx; pszLinkTo
0x18001d441  call    cs:__imp_SHGetNewLinkInfoW
0x18001d447  test    eax, eax
0x18001d449  jz      short loc_18001D4C2
0x18001d44b  lea     rcx, [rsp+268h+pszName]; pszPath
0x18001d450  call    cs:__imp_PathFindFileNameW
0x18001d456  mov     rdi, rax
0x18001d459  test    rax, rax
0x18001d45c  jz      short loc_18001D46F
0x18001d45e  mov     rcx, rax; pszPath
0x18001d461  call    cs:__imp_PathFindExtensionW
0x18001d467  cmp     [rax], si
0x18001d46a  jz      short loc_18001D46F
0x18001d46c  mov     [rax], si
0x18001d46f  mov     r8, rdi; unsigned __int16 *
0x18001d472  lea     rcx, [rbx+624h]; unsigned __int16 *
0x18001d479  mov     edi, 104h
0x18001d47e  mov     edx, edi; unsigned __int64
0x18001d480  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d485  mov     r11d, [rbx+8]
0x18001d489  test    r11b, 4
0x18001d48d  jnz     short loc_18001D4A7
0x18001d48f  cmp     [rsp+268h+pfMustCopy], esi
0x18001d493  jz      short loc_18001D49E
0x18001d495  bts     r11d, 9
0x18001d49a  mov     [rbx+8], r11d
0x18001d49e  lea     r8, c_szLNK; ".lnk"
0x18001d4a5  jmp     short loc_18001D4AE
0x18001d4a7  lea     r8, c_szPIF; ".pif"
0x18001d4ae  mov     rdx, rdi; unsigned __int64
0x18001d4b1  lea     rcx, [rbx+0CF0h]; unsigned __int16 *
0x18001d4b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d4bd  mov     eax, 1
0x18001d4c2  mov     rcx, [rsp+268h+var_18]
0x18001d4ca  xor     rcx, rsp; StackCookie
0x18001d4cd  call    __security_check_cookie
0x18001d4d2  lea     r11, [rsp+268h+var_8]
0x18001d4da  mov     rbx, [r11+18h]
0x18001d4de  mov     rsi, [r11+20h]
0x18001d4e2  mov     rsp, r11
0x18001d4e5  pop     rdi
0x18001d4e6  retn
```
