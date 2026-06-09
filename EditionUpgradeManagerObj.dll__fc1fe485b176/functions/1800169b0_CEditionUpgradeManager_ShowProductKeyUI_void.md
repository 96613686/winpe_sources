# CEditionUpgradeManager::ShowProductKeyUI(void)

- ea: `0x1800169b0`
- end: `0x180016aee`
- name: `?ShowProductKeyUI@CEditionUpgradeManager@@UEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800026b4`
- `0x1800090dc`
- `0x180009480`
- `0x1800169b0`
- `0x180018cec`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ab8`
- `SHELL32!SHGetIDListFromObject` at `0x180016a32`
- `SHELL32!SHGetIDListFromObject` at `0x180016a32`
- `SHELL32!SHCreateItemInKnownFolder` at `0x180016a1e`
- `SHELL32!SHCreateItemInKnownFolder` at `0x180016a1e`
- `SHELL32!ShellExecuteExW` at `0x180016a79`
- `SHELL32!ShellExecuteExW` at `0x180016a79`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::ShowProductKeyUI(CEditionUpgradeManager *this)
{
  PCWSTR v1; // rcx
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  const WCHAR *v5; // rax
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-19h] BYREF
  DWORD pdwValue; // [rsp+B8h] [rbp+6Fh] BYREF
  LPITEMIDLIST ppidl; // [rsp+C0h] [rbp+77h] BYREF
  IUnknown *punk; // [rsp+C8h] [rbp+7Fh] BYREF

  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  punk = 0;
  ppidl = 0;
  pdwValue = 0;
  v2 = SLGetWindowsInformationDWORD(v1, &pdwValue);
  v3 = v2;
  if ( v2 < 0
    || (v2 = SHCreateItemInKnownFolder(
               &FOLDERID_AppsFolder,
               0,
               L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               (void **)&punk),
        v3 = v2,
        v2 < 0)
    || (v2 = SHGetIDListFromObject(punk, &ppidl), v3 = v2, v2 < 0) )
  {
    v4 = (unsigned int)v2;
LABEL_13:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_14;
  }
  pExecInfo.lpIDList = ppidl;
  v5 = L"page=SettingsPageActivate&target=SystemSettings_Activation_ActivatedChangePK&invoke=true";
  if ( pdwValue != 1 )
    v5 = L"page=SettingsPageActivate&target=SystemSettings_Activation_ChangePK&invoke=true";
  pExecInfo.cbSize = 112;
  pExecInfo.lpParameters = v5;
  pExecInfo.fMask = 33555468;
  pExecInfo.nShow = 1;
  if ( !ShellExecuteExW(&pExecInfo) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    v4 = v3;
    goto LABEL_13;
  }
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( ppidl )
  {
    CoTaskMemFree(ppidl);
    ppidl = 0;
  }
  if ( punk )
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  return v3;
}

```

## disassembly

```asm
0x1800169b0  mov     [rsp-8+arg_0], rbx
0x1800169b5  push    rbp
0x1800169b6  lea     rbp, [rsp-57h]
0x1800169bb  sub     rsp, 0A0h
0x1800169c2  xor     edx, edx; Val
0x1800169c4  lea     rcx, [rbp+57h+pExecInfo]; void *
0x1800169c8  lea     r8d, [rdx+70h]; Size
0x1800169cc  call    memset_0
0x1800169d1  lea     rdx, [rbp+57h+pdwValue]; pdwValue
0x1800169d5  mov     [rbp+57h+punk], 0
0x1800169dd  mov     [rbp+57h+ppidl], 0
0x1800169e5  mov     [rbp+57h+pdwValue], 0
0x1800169ec  call    SLGetWindowsInformationDWORD
0x1800169f1  mov     ebx, eax
0x1800169f3  test    eax, eax
0x1800169f5  jns     short loc_1800169FE
0x1800169f7  mov     ecx, eax
0x1800169f9  jmp     loc_180016AA3
0x1800169fe  lea     rax, [rbp+57h+punk]
0x180016a02  xor     edx, edx; dwKFFlags
0x180016a04  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180016a0b  mov     [rsp+0A0h+ppv], rax; ppv
0x180016a10  lea     r8, pszItem; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x180016a17  lea     rcx, FOLDERID_AppsFolder; kfid
0x180016a1e  call    cs:__imp_SHCreateItemInKnownFolder
0x180016a24  mov     ebx, eax
0x180016a26  test    eax, eax
0x180016a28  js      short loc_1800169F7
0x180016a2a  mov     rcx, [rbp+57h+punk]; punk
0x180016a2e  lea     rdx, [rbp+57h+ppidl]; ppidl
0x180016a32  call    cs:__imp_SHGetIDListFromObject
0x180016a38  mov     ebx, eax
0x180016a3a  test    eax, eax
0x180016a3c  js      short loc_1800169F7
0x180016a3e  mov     rax, [rbp+57h+ppidl]
0x180016a42  lea     rcx, aPageSettingspa; "page=SettingsPageActivate&target=System"...
0x180016a49  cmp     [rbp+57h+pdwValue], 1
0x180016a4d  mov     [rbp+57h+pExecInfo.lpIDList], rax
0x180016a51  lea     rax, aPageSettingspa_0; "page=SettingsPageActivate&target=System"...
0x180016a58  cmovnz  rax, rcx
0x180016a5c  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180016a63  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180016a67  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x180016a6b  mov     [rbp+57h+pExecInfo.fMask], 200040Ch
0x180016a72  mov     [rbp+57h+pExecInfo.nShow], 1
0x180016a79  call    cs:__imp_ShellExecuteExW
0x180016a7f  test    eax, eax
0x180016a81  jnz     short loc_180016AA8
0x180016a83  call    cs:__imp_GetLastError
0x180016a89  mov     ebx, eax
0x180016a8b  test    eax, eax
0x180016a8d  jnz     short loc_180016A96
0x180016a8f  mov     ebx, 80004005h
0x180016a94  jmp     short loc_180016AA1
0x180016a96  jle     short loc_180016AA1
0x180016a98  movzx   ebx, ax
0x180016a9b  or      ebx, 80070000h
0x180016aa1  mov     ecx, ebx
0x180016aa3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016aa8  mov     ecx, ebx
0x180016aaa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016aaf  mov     rcx, [rbp+57h+ppidl]; pv
0x180016ab3  test    rcx, rcx
0x180016ab6  jz      short loc_180016AC6
0x180016ab8  call    cs:__imp_CoTaskMemFree
0x180016abe  mov     [rbp+57h+ppidl], 0
0x180016ac6  mov     rcx, [rbp+57h+punk]
0x180016aca  test    rcx, rcx
0x180016acd  jz      short loc_180016ADB
0x180016acf  mov     rax, [rcx]
0x180016ad2  mov     rax, [rax+10h]
0x180016ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016adb  mov     eax, ebx
0x180016add  mov     rbx, [rsp+0A0h+arg_0]
0x180016ae5  add     rsp, 0A0h
0x180016aec  pop     rbp
0x180016aed  retn
```
