# CInstalledApp::_DarwinAppUninstall(HWND__ *)

- ea: `0x18002bdd8`
- end: `0x18002bf22`
- name: `?_DarwinAppUninstall@CInstalledApp@@AEAAJPEAUHWND__@@@Z`
- size: `330`
- prototype: `int(CInstalledApp *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18002b570`

## callees

- `0x180007960`
- `0x18002bdd8`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!__imp_SHMessageBoxCheckW` at `0x18002be91`
- `SHLWAPI!__imp_SHMessageBoxCheckW` at `0x18002be91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bedc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bedc`
- `msi!__imp_MsiConfigureProductW` at `0x18002beb6`
- `msi!__imp_MsiConfigureProductW` at `0x18002beb6`
- `msi!__imp_MsiSetInternalUI` at `0x18002bea1`
- `msi!__imp_MsiSetInternalUI` at `0x18002bec2`
- `msi!__imp_MsiSetInternalUI` at `0x18002bea1`
- `msi!__imp_MsiSetInternalUI` at `0x18002bec2`

## pseudocode

```c
__int64 __fastcall CInstalledApp::_DarwinAppUninstall(const WCHAR *this, HWND a2)
{
  signed int v4; // edi
  int v5; // eax
  INSTALLUILEVEL v6; // ebx
  signed int LastError; // eax
  WCHAR Buffer[256]; // [rsp+30h] [rbp-818h] BYREF
  WCHAR pszCaption[256]; // [rsp+230h] [rbp-618h] BYREF
  WCHAR pszText[512]; // [rsp+430h] [rbp-418h] BYREF

  LoadStringW(g_hinst, 0x3025u, Buffer, 256);
  v4 = StringCchPrintfW(pszText, 0x200u, Buffer, this + 18);
  if ( v4 >= 0 )
  {
    LoadStringW(g_hinst, 0x3027u, pszCaption, 256);
    v5 = SHMessageBoxCheckW(a2, pszText, pszCaption, 0x134u, 6, L"{948e51fb-0a48-44f0-86ac-33c36def540c}");
    if ( v5 == 6 )
    {
      v6 = MsiSetInternalUI(INSTALLUILEVEL_BASIC, 0);
      v4 = MsiConfigureProductW(this + 2098, 0, INSTALLSTATE_ABSENT);
      MsiSetInternalUI(v6, 0);
      if ( v4 > 0 )
      {
        v4 = (unsigned __int16)v4;
LABEL_5:
        v4 |= 0x80070000;
      }
    }
    else
    {
      if ( v5 != -1 )
        return (unsigned int)-2147467260;
      LastError = GetLastError();
      v4 = LastError;
      if ( !LastError )
        return (unsigned int)-2147467259;
      if ( LastError > 0 )
      {
        v4 = (unsigned __int16)LastError;
        goto LABEL_5;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002bdd8  mov     [rsp+arg_10], rbx
0x18002bddd  mov     [rsp+arg_18], rsi
0x18002bde2  push    rdi
0x18002bde3  sub     rsp, 840h
0x18002bdea  mov     rax, cs:__security_cookie
0x18002bdf1  xor     rax, rsp
0x18002bdf4  mov     [rsp+848h+var_18], rax
0x18002bdfc  mov     rbx, rdx
0x18002bdff  lea     r8, [rsp+848h+Buffer]; lpBuffer
0x18002be04  mov     rsi, rcx
0x18002be07  mov     edx, 3025h; uID
0x18002be0c  mov     rcx, cs:g_hinst; hInstance
0x18002be13  mov     r9d, 100h; cchBufferMax
0x18002be19  call    cs:__imp_LoadStringW
0x18002be1f  lea     r9, [rsi+24h]
0x18002be23  mov     edx, 200h; unsigned __int64
0x18002be28  lea     r8, [rsp+848h+Buffer]; unsigned __int16 *
0x18002be2d  lea     rcx, [rsp+848h+pszText]; unsigned __int16 *
0x18002be35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002be3a  mov     edi, eax
0x18002be3c  test    eax, eax
0x18002be3e  js      loc_18002BEFB
0x18002be44  mov     rcx, cs:g_hinst; hInstance
0x18002be4b  lea     r8, [rsp+848h+pszCaption]; lpBuffer
0x18002be53  mov     r9d, 100h; cchBufferMax
0x18002be59  mov     edx, 3027h; uID
0x18002be5e  call    cs:__imp_LoadStringW
0x18002be64  lea     rax, pszRegVal; "{948e51fb-0a48-44f0-86ac-33c36def540c}"
0x18002be6b  mov     r9d, 134h; uType
0x18002be71  mov     [rsp+848h+pszRegVal], rax; pszRegVal
0x18002be76  lea     r8, [rsp+848h+pszCaption]; pszCaption
0x18002be7e  lea     rdx, [rsp+848h+pszText]; pszText
0x18002be86  mov     [rsp+848h+iDefault], 6; iDefault
0x18002be8e  mov     rcx, rbx; hwnd
0x18002be91  call    cs:__imp_SHMessageBoxCheckW
0x18002be97  cmp     eax, 6
0x18002be9a  jnz     short loc_18002BED7
0x18002be9c  xor     edx, edx; phWnd
0x18002be9e  lea     ecx, [rax-3]; dwUILevel
0x18002bea1  call    cs:__imp_MsiSetInternalUI
0x18002bea7  xor     edx, edx; iInstallLevel
0x18002bea9  lea     rcx, [rsi+1064h]; szProduct
0x18002beb0  mov     ebx, eax
0x18002beb2  lea     r8d, [rdx+2]; eInstallState
0x18002beb6  call    cs:__imp_MsiConfigureProductW
0x18002bebc  xor     edx, edx; phWnd
0x18002bebe  mov     ecx, ebx; dwUILevel
0x18002bec0  mov     edi, eax
0x18002bec2  call    cs:__imp_MsiSetInternalUI
0x18002bec8  test    edi, edi
0x18002beca  jle     short loc_18002BEFB
0x18002becc  movzx   edi, di
0x18002becf  or      edi, 80070000h
0x18002bed5  jmp     short loc_18002BEFB
0x18002bed7  cmp     eax, 0FFFFFFFFh
0x18002beda  jnz     short loc_18002BEF6
0x18002bedc  call    cs:__imp_GetLastError
0x18002bee2  mov     edi, eax
0x18002bee4  test    eax, eax
0x18002bee6  jz      short loc_18002BEEF
0x18002bee8  jle     short loc_18002BEFB
0x18002beea  movzx   edi, ax
0x18002beed  jmp     short loc_18002BECF
0x18002beef  mov     edi, 80004005h
0x18002bef4  jmp     short loc_18002BEFB
0x18002bef6  mov     edi, 80004004h
0x18002befb  mov     eax, edi
0x18002befd  mov     rcx, [rsp+848h+var_18]
0x18002bf05  xor     rcx, rsp; StackCookie
0x18002bf08  call    __security_check_cookie
0x18002bf0d  lea     r11, [rsp+848h+var_8]
0x18002bf15  mov     rbx, [r11+20h]
0x18002bf19  mov     rsi, [r11+28h]
0x18002bf1d  mov     rsp, r11
0x18002bf20  pop     rdi
0x18002bf21  retn
```
