# CApplicationFrame::GetLogoLoaderThemeOption(void)

- ea: `0x180039b04`
- end: `0x180039b7d`
- name: `?GetLogoLoaderThemeOption@CApplicationFrame@@AEAA?AW4TileThemeSelector@VisualCache@UnifiedTile@Shell@WindowsInternal@winrt@@XZ`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000471c`

## callees

- `0x180039b04`

## import_xrefs

- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x180039b6b`
- `UxTheme!__imp_ShouldAppsUseDarkMode` at `0x180039b6b`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180039b3d`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180039b3d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039b27`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039b27`

## pseudocode

```c
__int64 CApplicationFrame::GetLogoLoaderThemeOption()
{
  DWORD SysColor; // eax
  int pvParam; // [rsp+20h] [rbp-18h] BYREF
  __int64 v3; // [rsp+24h] [rbp-14h]
  int v4; // [rsp+2Ch] [rbp-Ch]

  pvParam = 16;
  v3 = 0;
  v4 = 0;
  if ( !SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) || (v3 & 1) == 0 )
    return 4 - (unsigned int)((unsigned __int8)ShouldAppsUseDarkMode() != 0);
  SysColor = GetSysColor(5);
  return (unsigned int)(BYTE2(SysColor) + 5 * BYTE1(SysColor) + 2 * (unsigned int)(unsigned __int8)SysColor > 0x400) + 1;
}

```

## disassembly

```asm
0x180039b04  sub     rsp, 38h
0x180039b08  mov     edx, 10h; uiParam
0x180039b0d  lea     r8, [rsp+38h+pvParam]; pvParam
0x180039b12  xor     eax, eax
0x180039b14  mov     [rsp+38h+pvParam], edx
0x180039b18  xor     r9d, r9d; fWinIni
0x180039b1b  mov     [rsp+38h+var_14], rax
0x180039b20  mov     [rsp+38h+var_C], eax
0x180039b24  lea     ecx, [rdx+32h]; uiAction
0x180039b27  call    cs:__imp_SystemParametersInfoW
0x180039b2d  test    eax, eax
0x180039b2f  jz      short loc_180039B6B
0x180039b31  test    byte ptr [rsp+38h+var_14], 1
0x180039b36  jz      short loc_180039B6B
0x180039b38  mov     ecx, 5; nIndex
0x180039b3d  call    cs:__imp_GetSysColor
0x180039b43  movzx   ecx, ax
0x180039b46  shr     ecx, 8
0x180039b49  lea     edx, [rcx+rcx*4]
0x180039b4c  mov     ecx, eax
0x180039b4e  shr     ecx, 10h
0x180039b51  movzx   eax, al
0x180039b54  movzx   ecx, cl
0x180039b57  add     edx, ecx
0x180039b59  lea     ecx, [rdx+rax*2]
0x180039b5c  xor     eax, eax
0x180039b5e  cmp     ecx, 400h
0x180039b64  setnbe  al
0x180039b67  inc     eax
0x180039b69  jmp     short loc_180039B78
0x180039b6b  call    cs:__imp_ShouldAppsUseDarkMode
0x180039b71  neg     al
0x180039b73  sbb     eax, eax
0x180039b75  add     eax, 4
0x180039b78  add     rsp, 38h
0x180039b7c  retn
```
