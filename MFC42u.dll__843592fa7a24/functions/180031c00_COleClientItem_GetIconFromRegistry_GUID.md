# COleClientItem::GetIconFromRegistry(_GUID &)

- ea: `0x180031c00`
- end: `0x180031eeb`
- name: `?GetIconFromRegistry@COleClientItem@@SAPEAUHICON__@@AEAU_GUID@@@Z`
- size: `747`
- prototype: `HICON __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180031b90`

## callees

- `0x18000c950`
- `0x180013330`
- `0x180019290`
- `0x180031c00`
- `0x180080924`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031d9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031db1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031eb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031d9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031db1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031eb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031c9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031cd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031cfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031df1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031e1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031c9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031cd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031cfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031df1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031e1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031d35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031e54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031d35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031e54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ebe`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180031c64`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180031c64`
- `SHELL32!ExtractIconW` at `0x180031d71`
- `SHELL32!ExtractIconW` at `0x180031e90`
- `SHELL32!ExtractIconW` at `0x180031d71`
- `SHELL32!ExtractIconW` at `0x180031e90`

## string_xrefs

- `0x180031c8c`: `clsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HICON __fastcall COleClientItem::GetIconFromRegistry(struct _GUID *a1)
{
  HICON IconW; // rbx
  struct AFX_MODULE_STATE *ModuleState; // rax
  struct AFX_MODULE_STATE *v4; // rax
  UINT nIconIndex; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v7; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[528]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszExeFileName[264]; // [rsp+280h] [rbp+180h] BYREF

  lpsz = 0;
  Type = 0;
  phkResult = 0;
  v7 = 0;
  hKey = 0;
  nIconIndex = 0;
  if ( StringFromCLSID(a1, &lpsz) < 0 )
    return 0;
  IconW = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"clsid", 0, 0x20019u, &hKey) )
    goto LABEL_22;
  CString::CString((CString *)lpSubKey, lpsz);
  if ( !RegOpenKeyExW(hKey, lpSubKey[0], 0, 0x20019u, &phkResult) )
  {
    if ( !RegOpenKeyExW(phkResult, L"DefaultIcon", 0, 0x20019u, &v7) )
    {
      cbData = 522;
      if ( !RegQueryValueExW(v7, 0, 0, &Type, Data, &cbData) )
      {
        AfxGetIconInfo(Data, pszExeFileName, &nIconIndex);
        ModuleState = AfxGetModuleState();
        IconW = ExtractIconW(*(HINSTANCE *)(*((_QWORD *)ModuleState + 1) + 200LL), pszExeFileName, nIconIndex);
        if ( IconW == (HICON)1 )
          IconW = 0;
      }
      RegCloseKey(v7);
      v7 = 0;
    }
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  RegCloseKey(hKey);
  hKey = 0;
  CString::~CString((CString *)lpSubKey);
  if ( !IconW )
  {
LABEL_22:
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"DocShortcut", 0, 0x20019u, &phkResult) )
    {
      if ( !RegOpenKeyExW(phkResult, L"DefaultIcon", 0, 0x20019u, &v7) )
      {
        cbData = 522;
        if ( !RegQueryValueExW(v7, 0, 0, &Type, Data, &cbData) )
        {
          AfxGetIconInfo(Data, pszExeFileName, &nIconIndex);
          v4 = AfxGetModuleState();
          IconW = ExtractIconW(*(HINSTANCE *)(*((_QWORD *)v4 + 1) + 200LL), pszExeFileName, nIconIndex);
          if ( IconW == (HICON)1 )
            IconW = 0;
        }
        RegCloseKey(v7);
      }
      RegCloseKey(phkResult);
    }
  }
  CoTaskMemFree(lpsz);
  return IconW;
}

```

## disassembly

```asm
0x180031c00  mov     [rsp-8+arg_8], rbx
0x180031c05  mov     [rsp-8+arg_10], rsi
0x180031c0a  push    rbp
0x180031c0b  lea     rbp, [rsp-3A0h]
0x180031c13  sub     rsp, 4A0h
0x180031c1a  mov     rax, cs:__security_cookie
0x180031c21  xor     rax, rsp
0x180031c24  mov     [rbp+3A0h+var_10], rax
0x180031c2b  mov     [rsp+4A0h+lpsz], 0
0x180031c34  mov     [rsp+4A0h+Type], 0
0x180031c3c  mov     [rsp+4A0h+var_460], 0
0x180031c45  mov     [rsp+4A0h+var_468], 0
0x180031c4e  mov     [rsp+4A0h+hKey], 0
0x180031c57  mov     [rsp+4A0h+nIconIndex], 0
0x180031c5f  lea     rdx, [rsp+4A0h+lpsz]; lplpsz
0x180031c64  call    cs:__imp_StringFromCLSID
0x180031c6a  test    eax, eax
0x180031c6c  jns     short loc_180031C75
0x180031c6e  xor     eax, eax
0x180031c70  jmp     loc_180031EC7
0x180031c75  xor     ebx, ebx
0x180031c77  lea     rax, [rsp+4A0h+hKey]
0x180031c7c  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180031c81  mov     esi, 20019h
0x180031c86  mov     r9d, esi; samDesired
0x180031c89  xor     r8d, r8d; ulOptions
0x180031c8c  lea     rdx, aClsid; "clsid"
0x180031c93  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180031c9a  call    cs:__imp_RegOpenKeyExW
0x180031ca0  test    eax, eax
0x180031ca2  jnz     loc_180031DD3
0x180031ca8  mov     rdx, [rsp+4A0h+lpsz]; unsigned __int16 *
0x180031cad  lea     rcx, [rsp+4A0h+lpSubKey]; this
0x180031cb2  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180031cb7  nop
0x180031cb8  lea     rax, [rsp+4A0h+var_460]
0x180031cbd  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180031cc2  mov     r9d, esi; samDesired
0x180031cc5  xor     r8d, r8d; ulOptions
0x180031cc8  mov     rdx, [rsp+4A0h+lpSubKey]; lpSubKey
0x180031ccd  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180031cd2  call    cs:__imp_RegOpenKeyExW
0x180031cd8  test    eax, eax
0x180031cda  jnz     loc_180031DAC
0x180031ce0  lea     rax, [rsp+4A0h+var_468]
0x180031ce5  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180031cea  mov     r9d, esi; samDesired
0x180031ced  xor     r8d, r8d; ulOptions
0x180031cf0  lea     rdx, aDefaulticon; "DefaultIcon"
0x180031cf7  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180031cfc  call    cs:__imp_RegOpenKeyExW
0x180031d02  test    eax, eax
0x180031d04  jnz     loc_180031D98
0x180031d0a  mov     [rsp+4A0h+cbData], 20Ah
0x180031d12  lea     rax, [rsp+4A0h+cbData]
0x180031d17  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180031d1c  lea     rax, [rsp+4A0h+Data]
0x180031d21  mov     [rsp+4A0h+phkResult], rax; lpData
0x180031d26  lea     r9, [rsp+4A0h+Type]; lpType
0x180031d2b  xor     r8d, r8d; lpReserved
0x180031d2e  xor     edx, edx; lpValueName
0x180031d30  mov     rcx, [rsp+4A0h+var_468]; hKey
0x180031d35  call    cs:__imp_RegQueryValueExW
0x180031d3b  test    eax, eax
0x180031d3d  jnz     short loc_180031D84
0x180031d3f  lea     r8, [rsp+4A0h+nIconIndex]
0x180031d44  lea     rdx, [rbp+3A0h+pszExeFileName]
0x180031d4b  lea     rcx, [rsp+4A0h+Data]
0x180031d50  call    AfxGetIconInfo
0x180031d55  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180031d5a  mov     rcx, [rax+8]
0x180031d5e  mov     r8d, [rsp+4A0h+nIconIndex]; nIconIndex
0x180031d63  lea     rdx, [rbp+3A0h+pszExeFileName]; pszExeFileName
0x180031d6a  mov     rcx, [rcx+0C8h]; hInst
0x180031d71  call    cs:__imp_ExtractIconW
0x180031d77  mov     rbx, rax
0x180031d7a  xor     eax, eax
0x180031d7c  cmp     rbx, 1
0x180031d80  cmovz   rbx, rax
0x180031d84  mov     rcx, [rsp+4A0h+var_468]; hKey
0x180031d89  call    cs:__imp_RegCloseKey
0x180031d8f  mov     [rsp+4A0h+var_468], 0
0x180031d98  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180031d9d  call    cs:__imp_RegCloseKey
0x180031da3  mov     [rsp+4A0h+var_460], 0
0x180031dac  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180031db1  call    cs:__imp_RegCloseKey
0x180031db7  mov     [rsp+4A0h+hKey], 0
0x180031dc0  lea     rcx, [rsp+4A0h+lpSubKey]; this
0x180031dc5  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180031dca  test    rbx, rbx
0x180031dcd  jnz     loc_180031EB9
0x180031dd3  lea     rax, [rsp+4A0h+var_460]
0x180031dd8  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180031ddd  mov     r9d, esi; samDesired
0x180031de0  xor     r8d, r8d; ulOptions
0x180031de3  lea     rdx, aDocshortcut; "DocShortcut"
0x180031dea  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180031df1  call    cs:__imp_RegOpenKeyExW
0x180031df7  test    eax, eax
0x180031df9  jnz     loc_180031EB9
0x180031dff  lea     rax, [rsp+4A0h+var_468]
0x180031e04  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180031e09  mov     r9d, esi; samDesired
0x180031e0c  xor     r8d, r8d; ulOptions
0x180031e0f  lea     rdx, aDefaulticon; "DefaultIcon"
0x180031e16  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180031e1b  call    cs:__imp_RegOpenKeyExW
0x180031e21  test    eax, eax
0x180031e23  jnz     loc_180031EAE
0x180031e29  mov     [rsp+4A0h+cbData], 20Ah
0x180031e31  lea     rax, [rsp+4A0h+cbData]
0x180031e36  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180031e3b  lea     rax, [rsp+4A0h+Data]
0x180031e40  mov     [rsp+4A0h+phkResult], rax; lpData
0x180031e45  lea     r9, [rsp+4A0h+Type]; lpType
0x180031e4a  xor     r8d, r8d; lpReserved
0x180031e4d  xor     edx, edx; lpValueName
0x180031e4f  mov     rcx, [rsp+4A0h+var_468]; hKey
0x180031e54  call    cs:__imp_RegQueryValueExW
0x180031e5a  test    eax, eax
0x180031e5c  jnz     short loc_180031EA3
0x180031e5e  lea     r8, [rsp+4A0h+nIconIndex]
0x180031e63  lea     rdx, [rbp+3A0h+pszExeFileName]
0x180031e6a  lea     rcx, [rsp+4A0h+Data]
0x180031e6f  call    AfxGetIconInfo
0x180031e74  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180031e79  mov     rcx, [rax+8]
0x180031e7d  mov     r8d, [rsp+4A0h+nIconIndex]; nIconIndex
0x180031e82  lea     rdx, [rbp+3A0h+pszExeFileName]; pszExeFileName
0x180031e89  mov     rcx, [rcx+0C8h]; hInst
0x180031e90  call    cs:__imp_ExtractIconW
0x180031e96  mov     rbx, rax
0x180031e99  xor     ecx, ecx
0x180031e9b  cmp     rax, 1
0x180031e9f  cmovz   rbx, rcx
0x180031ea3  mov     rcx, [rsp+4A0h+var_468]; hKey
0x180031ea8  call    cs:__imp_RegCloseKey
0x180031eae  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180031eb3  call    cs:__imp_RegCloseKey
0x180031eb9  mov     rcx, [rsp+4A0h+lpsz]; pv
0x180031ebe  call    cs:__imp_CoTaskMemFree
0x180031ec4  mov     rax, rbx
0x180031ec7  mov     rcx, [rbp+3A0h+var_10]
0x180031ece  xor     rcx, rsp; StackCookie
0x180031ed1  call    __security_check_cookie
0x180031ed6  lea     r11, [rsp+4A0h+var_s0]
0x180031ede  mov     rbx, [r11+18h]
0x180031ee2  mov     rsi, [r11+20h]
0x180031ee6  mov     rsp, r11
0x180031ee9  pop     rbp
0x180031eea  retn
```
