# WaasMedic::CServiceHealthPlugin::FixRegistryKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SECURITY_ATTRIBUTES * const,WaasMedic::CRegKeyInformationFromXML const &)

- ea: `0x18004b3e8`
- end: `0x18004b759`
- name: `?FixRegistryKey@CServiceHealthPlugin@WaasMedic@@AEAAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAU_SECURITY_ATTRIBUTES@@AEBVCRegKeyInformationFromXML@2@@Z`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ca5c`

## callees

- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x180032408`
- `0x18004b3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b525`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b525`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b729`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b660`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b660`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b56e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b56e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b51d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b738`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b51d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b738`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004b451`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004b6f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004b451`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004b6f1`

## string_xrefs

- `0x18004b410`: `SeTakeOwnershipPrivilege`
- `0x18004b467`: `Failed to revert the thread token: 0%x08X`
- `0x18004b707`: `Failed to revert the thread token: 0%x08X`
- `0x18004b43c`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004b5a7`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004b4a5`: `SeSecurityPrivilege`
- `0x18004b4e5`: `SeBackupPrivilege`
- `0x18004b4c5`: `SeRestorePrivilege`
- `0x18004b5da`: `Key was missing, new key was created for %s`
- `0x18004b59b`: `Failed to create/open reg key for %ws.`

## pseudocode

```c
__int64 __fastcall WaasMedic::CServiceHealthPlugin::FixRegistryKey(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        __int64 a5)
{
  signed int v8; // ebx
  __int64 v9; // rdx
  DWORD LastError; // eax
  bool v12; // cc
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  __int64 *v15; // r8
  _QWORD *v16; // rdi
  _QWORD *i; // rbx
  const WCHAR *v18; // r14
  const BYTE *v19; // rax
  const WCHAR *v20; // rdx
  int v21; // eax
  __int64 *v22; // r9
  __int64 *v23; // r9
  DWORD v24; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  HANDLE hObject[2]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 dwDisposition; // [rsp+A0h] [rbp+30h] BYREF

  dwDisposition = a1;
  hKey = 0;
  *(_OWORD *)hObject = 0;
  v8 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
         (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
         L"SeTakeOwnershipPrivilege");
  if ( v8 < 0 )
  {
    v9 = 568;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)(unsigned int)v8,
      dwOptions[0]);
LABEL_4:
    if ( LOBYTE(hObject[1]) )
    {
      if ( RevertToSelf() )
      {
        LOBYTE(hObject[1]) = 0;
      }
      else
      {
        LastError = GetLastError();
        LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", LastError);
      }
    }
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v8;
  }
  v8 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
         (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
         L"SeSecurityPrivilege");
  if ( v8 < 0 )
  {
    v9 = 569;
    goto LABEL_3;
  }
  v8 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
         (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
         L"SeRestorePrivilege");
  if ( v8 < 0 )
  {
    v9 = 570;
    goto LABEL_3;
  }
  v8 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
         (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
         L"SeBackupPrivilege");
  if ( v8 < 0 )
  {
    v9 = 571;
    goto LABEL_3;
  }
  LODWORD(dwDisposition) = 0;
  v12 = *((_QWORD *)a3 + 3) <= 7u;
  hKey = 0;
  if ( v12 )
    v13 = a3;
  else
    v13 = *(const WCHAR **)a3;
  v14 = RegCreateKeyExW(*a2, v13, 0, 0, 4u, 0x20006u, a4, &hKey, (LPDWORD)&dwDisposition);
  v8 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const WCHAR **)a3;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
        (const char *)(unsigned int)v8,
        (int)"Failed to create/open reg key for %ws.",
        (const char *)a3);
    }
    goto LABEL_4;
  }
  if ( (_DWORD)dwDisposition == 1 )
  {
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v15 = (__int64 *)a3;
    else
      v15 = *(__int64 **)a3;
    LogLevelW(4u, L"Key was missing, new key was created for %s", v15);
  }
  v16 = *(_QWORD **)(a5 + 80);
  for ( i = (_QWORD *)*v16; i != v16; i = (_QWORD *)*i )
  {
    v18 = (const WCHAR *)i[2];
    switch ( *((_DWORD *)v18 + 8) )
    {
      case 1:
      case 2:
        v19 = (const BYTE *)*((_QWORD *)v18 + 12);
        break;
      case 3:
        v19 = (const BYTE *)*((_QWORD *)v18 + 10);
        break;
      case 4:
        v19 = (const BYTE *)(v18 + 38);
        break;
      case 7:
        v19 = (const BYTE *)*((_QWORD *)v18 + 11);
        break;
      default:
        v8 = -2147418113;
        v9 = 621;
        goto LABEL_3;
    }
    if ( *((_QWORD *)v18 + 3) <= 7u )
      v20 = (const WCHAR *)i[2];
    else
      v20 = *(const WCHAR **)v18;
    v21 = RegSetValueExW(hKey, v20, 0, *((_DWORD *)v18 + 8), v19, *((_DWORD *)v18 + 18));
    if ( v21 )
    {
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      if ( *((_QWORD *)a3 + 3) <= 7u )
        v22 = (__int64 *)a3;
      else
        v22 = *(__int64 **)a3;
      if ( *((_QWORD *)v18 + 3) > 7u )
        v18 = *(const WCHAR **)v18;
      dwOptions[0] = v21;
      LogLevelW(2u, L"Failed to set reg value %s under %s. ErrorCode = 0x%08x", v18, v22, *(_QWORD *)dwOptions);
    }
    else
    {
      if ( *((_QWORD *)a3 + 3) <= 7u )
        v23 = (__int64 *)a3;
      else
        v23 = *(__int64 **)a3;
      if ( *((_QWORD *)v18 + 3) > 7u )
        v18 = *(const WCHAR **)v18;
      LogLevelW(4u, L"Reg value %s under %s fixed successfully.", v18, v23);
    }
  }
  if ( LOBYTE(hObject[1]) )
  {
    if ( RevertToSelf() )
    {
      LOBYTE(hObject[1]) = 0;
    }
    else
    {
      v24 = GetLastError();
      LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v24);
    }
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18004b3e8  mov     [rsp-28h+arg_8], rbx
0x18004b3ed  mov     [rsp-28h+arg_10], rsi
0x18004b3f2  mov     [rsp-28h+dwDisposition], rcx
0x18004b3f7  push    rbp
0x18004b3f8  push    rdi
0x18004b3f9  push    r12
0x18004b3fb  push    r14
0x18004b3fd  push    r15
0x18004b3ff  mov     rbp, rsp
0x18004b402  sub     rsp, 70h
0x18004b406  mov     r15, rdx
0x18004b409  lea     rcx, [rbp+hObject]; this
0x18004b40d  xorps   xmm0, xmm0
0x18004b410  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x18004b417  xor     r12d, r12d
0x18004b41a  mov     r14, r9
0x18004b41d  mov     [rbp+hKey], r12
0x18004b421  mov     rsi, r8
0x18004b424  movups  xmmword ptr [rbp+hObject], xmm0
0x18004b428  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x18004b42d  mov     ebx, eax
0x18004b42f  test    eax, eax
0x18004b431  jns     short loc_18004B4A5
0x18004b433  mov     edx, 238h; void *
0x18004b438  mov     rcx, [rbp+28h]; this
0x18004b43c  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004b443  mov     r9d, ebx; char *
0x18004b446  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b44b  cmp     byte ptr [rbp+hObject+8], r12b
0x18004b44f  jz      short loc_18004B47B
0x18004b451  call    cs:__imp_RevertToSelf
0x18004b457  test    eax, eax
0x18004b459  jz      short loc_18004B461
0x18004b45b  mov     byte ptr [rbp+hObject+8], r12b
0x18004b45f  jmp     short loc_18004B47B
0x18004b461  call    cs:__imp_GetLastError
0x18004b467  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x18004b46e  mov     ecx, 2; unsigned __int8
0x18004b473  mov     r8d, eax
0x18004b476  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004b47b  mov     rcx, [rbp+hObject]; hObject
0x18004b47f  lea     rax, [rcx-1]
0x18004b483  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004b487  ja      short loc_18004B48F
0x18004b489  call    cs:__imp_CloseHandle
0x18004b48f  mov     rcx, [rbp+hKey]; hKey
0x18004b493  test    rcx, rcx
0x18004b496  jz      short loc_18004B49E
0x18004b498  call    cs:__imp_RegCloseKey
0x18004b49e  mov     eax, ebx
0x18004b4a0  jmp     loc_18004B740
0x18004b4a5  lea     rdx, aSesecuritypriv; "SeSecurityPrivilege"
0x18004b4ac  lea     rcx, [rbp+hObject]; this
0x18004b4b0  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x18004b4b5  mov     ebx, eax
0x18004b4b7  test    eax, eax
0x18004b4b9  jns     short loc_18004B4C5
0x18004b4bb  mov     edx, 239h
0x18004b4c0  jmp     loc_18004B438
0x18004b4c5  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x18004b4cc  lea     rcx, [rbp+hObject]; this
0x18004b4d0  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x18004b4d5  mov     ebx, eax
0x18004b4d7  test    eax, eax
0x18004b4d9  jns     short loc_18004B4E5
0x18004b4db  mov     edx, 23Ah
0x18004b4e0  jmp     loc_18004B438
0x18004b4e5  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x18004b4ec  lea     rcx, [rbp+hObject]; this
0x18004b4f0  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x18004b4f5  mov     ebx, eax
0x18004b4f7  test    eax, eax
0x18004b4f9  jns     short loc_18004B505
0x18004b4fb  mov     edx, 23Bh
0x18004b500  jmp     loc_18004B438
0x18004b505  mov     rdi, [rbp+hKey]
0x18004b509  mov     dword ptr [rbp+dwDisposition], r12d
0x18004b50d  test    rdi, rdi
0x18004b510  jz      short loc_18004B52B
0x18004b512  call    cs:__imp_GetLastError
0x18004b518  mov     rcx, rdi; hKey
0x18004b51b  mov     ebx, eax
0x18004b51d  call    cs:__imp_RegCloseKey
0x18004b523  mov     ecx, ebx; dwErrCode
0x18004b525  call    cs:__imp_SetLastError
0x18004b52b  cmp     qword ptr [rsi+18h], 7
0x18004b530  mov     [rbp+hKey], r12
0x18004b534  jbe     short loc_18004B53B
0x18004b536  mov     rdx, [rsi]
0x18004b539  jmp     short loc_18004B53E
0x18004b53b  mov     rdx, rsi; lpSubKey
0x18004b53e  mov     rcx, [r15]; hKey
0x18004b541  lea     rax, [rbp+dwDisposition]
0x18004b545  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18004b54a  xor     r9d, r9d; lpClass
0x18004b54d  lea     rax, [rbp+hKey]
0x18004b551  xor     r8d, r8d; Reserved
0x18004b554  mov     [rsp+70h+phkResult], rax; phkResult
0x18004b559  mov     [rsp+70h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18004b55e  mov     [rsp+70h+samDesired], 20006h; samDesired
0x18004b566  mov     [rsp+70h+dwOptions], 4; dwOptions
0x18004b56e  call    cs:__imp_RegCreateKeyExW
0x18004b574  mov     ebx, eax
0x18004b576  test    eax, eax
0x18004b578  jz      short loc_18004B5C5
0x18004b57a  jle     short loc_18004B585
0x18004b57c  movzx   ebx, ax
0x18004b57f  or      ebx, 80070000h
0x18004b585  test    ebx, ebx
0x18004b587  jns     loc_18004B44B
0x18004b58d  cmp     qword ptr [rsi+18h], 7
0x18004b592  jbe     short loc_18004B597
0x18004b594  mov     rsi, [rsi]
0x18004b597  mov     rcx, [rbp+28h]; this
0x18004b59b  lea     rax, aFailedToCreate_2; "Failed to create/open reg key for %ws."
0x18004b5a2  mov     qword ptr [rsp+70h+samDesired], rsi; char *
0x18004b5a7  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004b5ae  mov     r9d, ebx; char *
0x18004b5b1  mov     qword ptr [rsp+70h+dwOptions], rax; int
0x18004b5b6  mov     edx, 249h; void *
0x18004b5bb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b5c0  jmp     loc_18004B44B
0x18004b5c5  cmp     dword ptr [rbp+dwDisposition], 1
0x18004b5c9  jnz     short loc_18004B5EB
0x18004b5cb  cmp     qword ptr [rsi+18h], 7
0x18004b5d0  jbe     short loc_18004B5D7
0x18004b5d2  mov     r8, [rsi]
0x18004b5d5  jmp     short loc_18004B5DA
0x18004b5d7  mov     r8, rsi
0x18004b5da  lea     rdx, aKeyWasMissingN; "Key was missing, new key was created fo"...
0x18004b5e1  mov     ecx, 4; unsigned __int8
0x18004b5e6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004b5eb  mov     rdi, [rbp+arg_20]
0x18004b5ef  mov     rdi, [rdi+50h]
0x18004b5f3  mov     rbx, [rdi]
0x18004b5f6  cmp     rbx, rdi
0x18004b5f9  jz      loc_18004B6EB
0x18004b5ff  mov     r14, [rbx+10h]
0x18004b603  mov     r9d, [r14+20h]; dwType
0x18004b607  mov     eax, r9d
0x18004b60a  sub     eax, 1
0x18004b60d  jz      short loc_18004B639
0x18004b60f  sub     eax, 1
0x18004b612  jz      short loc_18004B639
0x18004b614  sub     eax, 1
0x18004b617  jz      short loc_18004B633
0x18004b619  sub     eax, 1
0x18004b61c  jz      short loc_18004B62D
0x18004b61e  cmp     eax, 3
0x18004b621  jnz     loc_18004B6DC
0x18004b627  mov     rax, [r14+58h]
0x18004b62b  jmp     short loc_18004B63D
0x18004b62d  lea     rax, [r14+4Ch]
0x18004b631  jmp     short loc_18004B63D
0x18004b633  mov     rax, [r14+50h]
0x18004b637  jmp     short loc_18004B63D
0x18004b639  mov     rax, [r14+60h]
0x18004b63d  cmp     qword ptr [r14+18h], 7
0x18004b642  mov     ecx, [r14+48h]
0x18004b646  jbe     short loc_18004B64D
0x18004b648  mov     rdx, [r14]
0x18004b64b  jmp     short loc_18004B650
0x18004b64d  mov     rdx, r14; lpValueName
0x18004b650  mov     [rsp+70h+samDesired], ecx; cbData
0x18004b654  xor     r8d, r8d; Reserved
0x18004b657  mov     rcx, [rbp+hKey]; hKey
0x18004b65b  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18004b660  call    cs:__imp_RegSetValueExW
0x18004b666  test    eax, eax
0x18004b668  jz      short loc_18004B6A7
0x18004b66a  jle     short loc_18004B674
0x18004b66c  movzx   eax, ax
0x18004b66f  or      eax, 80070000h
0x18004b674  cmp     qword ptr [rsi+18h], 7
0x18004b679  jbe     short loc_18004B680
0x18004b67b  mov     r9, [rsi]
0x18004b67e  jmp     short loc_18004B683
0x18004b680  mov     r9, rsi
0x18004b683  cmp     qword ptr [r14+18h], 7
0x18004b688  jbe     short loc_18004B68D
0x18004b68a  mov     r14, [r14]
0x18004b68d  mov     r8, r14
0x18004b690  mov     [rsp+70h+dwOptions], eax
0x18004b694  lea     rdx, aFailedToSetReg; "Failed to set reg value %s under %s. Er"...
0x18004b69b  mov     ecx, 2; unsigned __int8
0x18004b6a0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004b6a5  jmp     short loc_18004B6D4
0x18004b6a7  cmp     qword ptr [rsi+18h], 7
0x18004b6ac  jbe     short loc_18004B6B3
0x18004b6ae  mov     r9, [rsi]
0x18004b6b1  jmp     short loc_18004B6B6
0x18004b6b3  mov     r9, rsi
0x18004b6b6  cmp     qword ptr [r14+18h], 7
0x18004b6bb  jbe     short loc_18004B6C0
0x18004b6bd  mov     r14, [r14]
0x18004b6c0  mov     r8, r14
0x18004b6c3  lea     rdx, aRegValueSUnder; "Reg value %s under %s fixed successfull"...
0x18004b6ca  mov     ecx, 4; unsigned __int8
0x18004b6cf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004b6d4  mov     rbx, [rbx]
0x18004b6d7  jmp     loc_18004B5F6
0x18004b6dc  mov     ebx, 8000FFFFh
0x18004b6e1  mov     edx, 26Dh
0x18004b6e6  jmp     loc_18004B438
0x18004b6eb  cmp     byte ptr [rbp+hObject+8], r12b
0x18004b6ef  jz      short loc_18004B71B
0x18004b6f1  call    cs:__imp_RevertToSelf
0x18004b6f7  test    eax, eax
0x18004b6f9  jz      short loc_18004B701
0x18004b6fb  mov     byte ptr [rbp+hObject+8], r12b
0x18004b6ff  jmp     short loc_18004B71B
0x18004b701  call    cs:__imp_GetLastError
0x18004b707  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x18004b70e  mov     ecx, 2; unsigned __int8
0x18004b713  mov     r8d, eax
0x18004b716  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004b71b  mov     rcx, [rbp+hObject]; hObject
0x18004b71f  lea     rax, [rcx-1]
0x18004b723  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004b727  ja      short loc_18004B72F
0x18004b729  call    cs:__imp_CloseHandle
0x18004b72f  mov     rcx, [rbp+hKey]; hKey
0x18004b733  test    rcx, rcx
0x18004b736  jz      short loc_18004B73E
0x18004b738  call    cs:__imp_RegCloseKey
0x18004b73e  xor     eax, eax
0x18004b740  lea     r11, [rsp+70h+var_s0]
0x18004b745  mov     rbx, [r11+38h]
0x18004b749  mov     rsi, [r11+40h]
0x18004b74d  mov     rsp, r11
0x18004b750  pop     r15
0x18004b752  pop     r14
0x18004b754  pop     r12
0x18004b756  pop     rdi
0x18004b757  pop     rbp
0x18004b758  retn
```
