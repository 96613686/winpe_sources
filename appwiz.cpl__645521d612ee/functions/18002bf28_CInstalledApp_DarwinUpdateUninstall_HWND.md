# CInstalledApp::_DarwinUpdateUninstall(HWND__ *)

- ea: `0x18002bf28`
- end: `0x18002bff4`
- name: `?_DarwinUpdateUninstall@CInstalledApp@@AEAAJPEAUHWND__@@@Z`
- size: `204`
- prototype: `int(CInstalledApp *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002b570`

## callees

- `0x18002bf28`
- `0x18004fad4`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002bf8b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002bf8b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bf68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bf68`
- `msi!__imp_MsiRemovePatchesW` at `0x18002bfad`
- `msi!__imp_MsiRemovePatchesW` at `0x18002bfad`

## pseudocode

```c
__int64 __fastcall CInstalledApp::_DarwinUpdateUninstall(const WCHAR *this, HWND a2)
{
  unsigned int v4; // ebx
  UINT v5; // eax
  WCHAR Buffer[256]; // [rsp+30h] [rbp-218h] BYREF

  LoadStringW(g_hinst, 0x98u, Buffer, 256);
  if ( ShellMessageBoxW(g_hinst, a2, Buffer, (LPCWSTR)0xB8, 0x34u) == 6 )
  {
    v4 = 0;
    v5 = MsiRemovePatchesW(this + 2098, this + 2666, INSTALLTYPE_SINGLE_INSTANCE, 0);
    if ( v5 )
    {
      _ARPErrorMessageBox(a2, v5);
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    return (unsigned int)-2147467260;
  }
  return v4;
}

```

## disassembly

```asm
0x18002bf28  mov     [rsp+arg_10], rbx
0x18002bf2d  mov     [rsp+arg_18], rsi
0x18002bf32  push    rdi
0x18002bf33  sub     rsp, 240h
0x18002bf3a  mov     rax, cs:__security_cookie
0x18002bf41  xor     rax, rsp
0x18002bf44  mov     [rsp+248h+var_18], rax
0x18002bf4c  mov     r9d, 100h; cchBufferMax
0x18002bf52  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x18002bf57  mov     rsi, rdx
0x18002bf5a  mov     rdi, rcx
0x18002bf5d  mov     rcx, cs:g_hinst; hInstance
0x18002bf64  lea     edx, [r9-68h]; uID
0x18002bf68  call    cs:__imp_LoadStringW
0x18002bf6e  mov     rcx, cs:g_hinst; hAppInst
0x18002bf75  lea     r8, [rsp+248h+Buffer]; lpcText
0x18002bf7a  mov     r9d, 0B8h; lpcTitle
0x18002bf80  mov     [rsp+248h+fuStyle], 34h ; '4'; fuStyle
0x18002bf88  mov     rdx, rsi; hWnd
0x18002bf8b  call    cs:__imp_ShellMessageBoxW
0x18002bf91  cmp     eax, 6
0x18002bf94  jnz     short loc_18002BFC8
0x18002bf96  lea     rdx, [rdi+14D4h]; szProductCode
0x18002bf9d  xor     r9d, r9d; szPropertyList
0x18002bfa0  lea     rcx, [rdi+1064h]; szPatchList
0x18002bfa7  xor     ebx, ebx
0x18002bfa9  lea     r8d, [rax-4]; eUninstallType
0x18002bfad  call    cs:__imp_MsiRemovePatchesW
0x18002bfb3  test    eax, eax
0x18002bfb5  jz      short loc_18002BFCD
0x18002bfb7  mov     edx, eax; dwMessageId
0x18002bfb9  mov     rcx, rsi; hWnd
0x18002bfbc  call    ?_ARPErrorMessageBox@@YAXPEAUHWND__@@K@Z; _ARPErrorMessageBox(HWND__ *,ulong)
0x18002bfc1  mov     ebx, 80004005h
0x18002bfc6  jmp     short loc_18002BFCD
0x18002bfc8  mov     ebx, 80004004h
0x18002bfcd  mov     eax, ebx
0x18002bfcf  mov     rcx, [rsp+248h+var_18]
0x18002bfd7  xor     rcx, rsp; StackCookie
0x18002bfda  call    __security_check_cookie
0x18002bfdf  lea     r11, [rsp+248h+var_8]
0x18002bfe7  mov     rbx, [r11+20h]
0x18002bfeb  mov     rsi, [r11+28h]
0x18002bfef  mov     rsp, r11
0x18002bff2  pop     rdi
0x18002bff3  retn
```
