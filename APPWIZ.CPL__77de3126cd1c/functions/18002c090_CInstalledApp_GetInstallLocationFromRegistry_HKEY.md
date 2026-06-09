# CInstalledApp::_GetInstallLocationFromRegistry(HKEY__ *)

- ea: `0x18002c090`
- end: `0x18002c10c`
- name: `?_GetInstallLocationFromRegistry@CInstalledApp@@AEAAXPEAUHKEY__@@@Z`
- size: `124`
- prototype: `void(CInstalledApp *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180029da8`
- `0x18002a058`

## callees

- `0x18002c090`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18002c0da`
- `SHCORE!SHQueryValueExW` at `0x18002c0da`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18002c0e5`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18002c0e5`
- `SHLWAPI!PathRemoveBackslashW` at `0x18002c0ee`
- `SHLWAPI!PathRemoveBackslashW` at `0x18002c0ee`

## string_xrefs

- `0x18002c0d3`: `InstallLocation`

## pseudocode

```c
void __fastcall CInstalledApp::_GetInstallLocationFromRegistry(CInstalledApp *this, HKEY a2)
{
  WCHAR *v2; // rdi
  LSTATUS v4; // ebx
  DWORD v5; // [rsp+40h] [rbp+8h] BYREF
  DWORD v6; // [rsp+50h] [rbp+18h] BYREF

  v2 = (WCHAR *)((char *)this + 3676);
  v6 = 0;
  v5 = 520;
  v4 = SHQueryValueExW(a2, L"InstallLocation", 0, &v6, (char *)this + 3676, &v5);
  PathUnquoteSpacesW(v2);
  PathRemoveBackslashW(v2);
  if ( !v4 )
    *((_DWORD *)this + 6) |= 0x20u;
}

```

## disassembly

```asm
0x18002c090  mov     r11, rsp
0x18002c093  mov     [r11+10h], rbx
0x18002c097  mov     [r11+20h], rsi
0x18002c09b  push    rdi
0x18002c09c  sub     rsp, 30h
0x18002c0a0  lea     rdi, [rcx+0E5Ch]
0x18002c0a7  mov     [rsp+38h+arg_10], 0
0x18002c0af  mov     rsi, rcx
0x18002c0b2  mov     [rsp+38h+arg_0], 208h
0x18002c0ba  lea     rcx, [r11+8]
0x18002c0be  mov     rax, rdx
0x18002c0c1  mov     [r11-10h], rcx
0x18002c0c5  lea     r9, [r11+18h]; pdwType
0x18002c0c9  mov     rcx, rax; hkey
0x18002c0cc  mov     [r11-18h], rdi
0x18002c0d0  xor     r8d, r8d; pdwReserved
0x18002c0d3  lea     rdx, aInstalllocatio; "InstallLocation"
0x18002c0da  call    cs:__imp_SHQueryValueExW
0x18002c0e0  mov     rcx, rdi; lpsz
0x18002c0e3  mov     ebx, eax
0x18002c0e5  call    cs:__imp_PathUnquoteSpacesW
0x18002c0eb  mov     rcx, rdi; pszPath
0x18002c0ee  call    cs:__imp_PathRemoveBackslashW
0x18002c0f4  test    ebx, ebx
0x18002c0f6  jnz     short loc_18002C0FC
0x18002c0f8  or      dword ptr [rsi+18h], 20h
0x18002c0fc  mov     rbx, [rsp+38h+arg_8]
0x18002c101  mov     rsi, [rsp+38h+arg_18]
0x18002c106  add     rsp, 30h
0x18002c10a  pop     rdi
0x18002c10b  retn
```
