# WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)

- ea: `0x140058c04`
- end: `0x140058ec8`
- name: `?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z`
- size: `708`
- prototype: `int(struct _AUTOVERIFIER_IPT_SETTINGS *, unsigned int, HKEY, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14004c6e0`
- `0x14005014c`

## callees

- `0x14000551c`
- `0x140014ee4`
- `0x140014f14`
- `0x140058c04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058e0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058e0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058ead`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140058d4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140058de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140058d4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140058de6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140058c79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140058c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058c96`

## pseudocode

```c
__int64 __fastcall WerPluginWriteSettings(const BYTE *a1, unsigned int a2, HKEY a3, const wchar_t *a4)
{
  HKEY v5; // rdi
  HKEY *phkResult; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // rcx
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  const BYTE *v15; // rax
  const BYTE *v16; // r8
  unsigned __int64 v17; // rax
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  v5 = a3;
  if ( !a1 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942487LL;
  }
  if ( a4 )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegCreateKeyExW(v5, a4, 0, 0, 0, 2u, 0, phkResult, 0) || (v5 = hKey) == 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids, v10);
      }
      goto LABEL_25;
    }
  }
  v11 = 0;
  if ( !a2 )
  {
LABEL_24:
    v10 = 0;
    goto LABEL_25;
  }
  while ( 1 )
  {
    v12 = 568LL * v11;
    if ( !*(_DWORD *)&a1[v12 + 564] )
      goto LABEL_23;
    if ( *(_DWORD *)&a1[v12] == 1 )
      break;
    if ( *(_DWORD *)&a1[v12] == 4 && RegSetValueExW(v5, (LPCWSTR)&a1[v12 + 4], 0, 4u, &a1[v12 + 560], 4u) )
    {
      v10 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 21;
LABEL_19:
        WPP_SF_(*((_QWORD *)v13 + 2), v14, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
LABEL_23:
    if ( ++v11 >= a2 )
      goto LABEL_24;
  }
  v15 = *(const BYTE **)&a1[v12 + 536];
  v16 = *(const BYTE **)&a1[v12 + 528];
  if ( v16 == v15 )
    goto LABEL_23;
  v17 = (v15 - v16) >> 1;
  if ( v17 >= 0x7FFFFFFF )
  {
    v10 = -2147024362;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 22;
      goto LABEL_19;
    }
    goto LABEL_25;
  }
  if ( !RegSetValueExW(v5, (LPCWSTR)&a1[v12 + 4], 0, 1u, v16, 2 * v17 + 2) )
    goto LABEL_23;
  v10 = -2147467259;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 23;
    goto LABEL_19;
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x140058c04  mov     rax, rsp
0x140058c07  push    rbx
0x140058c08  push    rbp
0x140058c09  push    rsi
0x140058c0a  push    rdi
0x140058c0b  sub     rsp, 58h
0x140058c0f  mov     qword ptr [rax+8], 0
0x140058c17  mov     rsi, r9
0x140058c1a  mov     rdi, r8
0x140058c1d  mov     ebp, edx
0x140058c1f  mov     rbx, rcx
0x140058c22  test    rcx, rcx
0x140058c25  jz      loc_140058E72
0x140058c2b  test    r8, r8
0x140058c2e  jz      loc_140058E72
0x140058c34  test    r9, r9
0x140058c37  jz      loc_140058CEF
0x140058c3d  lea     rcx, [rax+8]
0x140058c41  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140058c46  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x140058c4f  xor     r9d, r9d; lpClass
0x140058c52  mov     [rsp+78h+phkResult], rax; phkResult
0x140058c57  xor     r8d, r8d; Reserved
0x140058c5a  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140058c63  mov     rdx, rsi; lpSubKey
0x140058c66  mov     [rsp+78h+samDesired], 2; samDesired
0x140058c6e  mov     rcx, rdi; hKey
0x140058c71  mov     [rsp+78h+dwOptions], 0; dwOptions
0x140058c79  call    cs:__imp_RegCreateKeyExW
0x140058c80  nop     dword ptr [rax+rax+00h]
0x140058c85  test    eax, eax
0x140058c87  jnz     short loc_140058C96
0x140058c89  mov     rdi, [rsp+78h+hKey]
0x140058c91  test    rdi, rdi
0x140058c94  jnz     short loc_140058CEF
0x140058c96  call    cs:__imp_GetLastError
0x140058c9d  nop     dword ptr [rax+rax+00h]
0x140058ca2  mov     ebx, eax
0x140058ca4  test    eax, eax
0x140058ca6  jle     short loc_140058CB1
0x140058ca8  movzx   ebx, ax
0x140058cab  or      ebx, 80070000h
0x140058cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140058cb8  lea     rax, WPP_GLOBAL_Control
0x140058cbf  cmp     rcx, rax
0x140058cc2  jz      loc_140058E02
0x140058cc8  test    byte ptr [rcx+1Ch], 1
0x140058ccc  jz      loc_140058E02
0x140058cd2  mov     rcx, [rcx+10h]
0x140058cd6  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x140058cdd  mov     edx, 14h
0x140058ce2  mov     r9d, ebx
0x140058ce5  call    WPP_SF_d
0x140058cea  jmp     loc_140058E02
0x140058cef  xor     esi, esi
0x140058cf1  test    ebp, ebp
0x140058cf3  jz      loc_140058E00
0x140058cf9  mov     eax, esi
0x140058cfb  imul    rcx, rax, 238h
0x140058d02  cmp     dword ptr [rcx+rbx+234h], 0
0x140058d0a  jz      loc_140058DF6
0x140058d10  mov     edx, [rcx+rbx]
0x140058d13  sub     edx, 1
0x140058d16  jz      loc_140058D9C
0x140058d1c  cmp     edx, 3
0x140058d1f  jnz     loc_140058DF6
0x140058d25  lea     rax, [rbx+230h]
0x140058d2c  mov     [rsp+78h+samDesired], 4; cbData
0x140058d34  add     rax, rcx
0x140058d37  lea     rdx, [rbx+4]
0x140058d3b  add     rdx, rcx; lpValueName
0x140058d3e  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x140058d43  mov     rcx, rdi; hKey
0x140058d46  mov     r9d, 4; dwType
0x140058d4c  xor     r8d, r8d; Reserved
0x140058d4f  call    cs:__imp_RegSetValueExW
0x140058d56  nop     dword ptr [rax+rax+00h]
0x140058d5b  test    eax, eax
0x140058d5d  jz      loc_140058DF6
0x140058d63  mov     ebx, 80004005h
0x140058d68  mov     rcx, cs:WPP_GLOBAL_Control
0x140058d6f  lea     rax, WPP_GLOBAL_Control
0x140058d76  cmp     rcx, rax
0x140058d79  jz      loc_140058E02
0x140058d7f  test    byte ptr [rcx+1Ch], 1
0x140058d83  jz      short loc_140058E02
0x140058d85  mov     edx, 15h
0x140058d8a  mov     rcx, [rcx+10h]
0x140058d8e  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x140058d95  call    WPP_SF_
0x140058d9a  jmp     short loc_140058E02
0x140058d9c  mov     rax, [rcx+rbx+218h]
0x140058da4  mov     r8, [rcx+rbx+210h]
0x140058dac  cmp     r8, rax
0x140058daf  jz      short loc_140058DF6
0x140058db1  sub     rax, r8
0x140058db4  sar     rax, 1
0x140058db7  cmp     rax, 7FFFFFFFh
0x140058dbd  jnb     loc_140058E4A
0x140058dc3  lea     eax, ds:2[rax*2]
0x140058dca  mov     r9d, 1; dwType
0x140058dd0  mov     [rsp+78h+samDesired], eax; cbData
0x140058dd4  lea     rdx, [rbx+4]
0x140058dd8  mov     qword ptr [rsp+78h+dwOptions], r8; lpData
0x140058ddd  add     rdx, rcx; lpValueName
0x140058de0  xor     r8d, r8d; Reserved
0x140058de3  mov     rcx, rdi; hKey
0x140058de6  call    cs:__imp_RegSetValueExW
0x140058ded  nop     dword ptr [rax+rax+00h]
0x140058df2  test    eax, eax
0x140058df4  jnz     short loc_140058E22
0x140058df6  inc     esi
0x140058df8  cmp     esi, ebp
0x140058dfa  jb      loc_140058CF9
0x140058e00  xor     ebx, ebx
0x140058e02  mov     rcx, [rsp+78h+hKey]; hKey
0x140058e0a  test    rcx, rcx
0x140058e0d  jz      short loc_140058E1B
0x140058e0f  call    cs:__imp_RegCloseKey
0x140058e16  nop     dword ptr [rax+rax+00h]
0x140058e1b  mov     eax, ebx
0x140058e1d  jmp     loc_140058EBE
0x140058e22  mov     ebx, 80004005h
0x140058e27  mov     rcx, cs:WPP_GLOBAL_Control
0x140058e2e  lea     rax, WPP_GLOBAL_Control
0x140058e35  cmp     rcx, rax
0x140058e38  jz      short loc_140058E02
0x140058e3a  test    byte ptr [rcx+1Ch], 1
0x140058e3e  jz      short loc_140058E02
0x140058e40  mov     edx, 17h
0x140058e45  jmp     loc_140058D8A
0x140058e4a  mov     ebx, 80070216h
0x140058e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058e56  lea     rax, WPP_GLOBAL_Control
0x140058e5d  cmp     rcx, rax
0x140058e60  jz      short loc_140058E02
0x140058e62  test    byte ptr [rcx+1Ch], 1
0x140058e66  jz      short loc_140058E02
0x140058e68  mov     edx, 16h
0x140058e6d  jmp     loc_140058D8A
0x140058e72  mov     rcx, cs:WPP_GLOBAL_Control
0x140058e79  lea     rax, WPP_GLOBAL_Control
0x140058e80  cmp     rcx, rax
0x140058e83  jz      short loc_140058EA0
0x140058e85  test    byte ptr [rcx+1Ch], 1
0x140058e89  jz      short loc_140058EA0
0x140058e8b  mov     rcx, [rcx+10h]
0x140058e8f  lea     r8, WPP_f02d492ef79f375c7527d8b7327187cd_Traceguids
0x140058e96  mov     edx, 13h
0x140058e9b  call    WPP_SF_
0x140058ea0  mov     rcx, [rsp+78h+hKey]; hKey
0x140058ea8  test    rcx, rcx
0x140058eab  jz      short loc_140058EB9
0x140058ead  call    cs:__imp_RegCloseKey
0x140058eb4  nop     dword ptr [rax+rax+00h]
0x140058eb9  mov     eax, 80070057h
0x140058ebe  add     rsp, 58h
0x140058ec2  pop     rdi
0x140058ec3  pop     rsi
0x140058ec4  pop     rbp
0x140058ec5  pop     rbx
0x140058ec6  retn
```
