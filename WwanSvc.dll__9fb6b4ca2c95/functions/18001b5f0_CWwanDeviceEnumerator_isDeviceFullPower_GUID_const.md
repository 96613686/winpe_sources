# CWwanDeviceEnumerator::isDeviceFullPower(_GUID const &)

- ea: `0x18001b5f0`
- end: `0x18001b921`
- name: `?isDeviceFullPower@CWwanDeviceEnumerator@@SA_NAEBU_GUID@@@Z`
- size: `817`
- prototype: `bool __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18002c7a8`

## callees

- `0x1800085d0`
- `0x180008b30`
- `0x180012300`
- `0x180014f1c`
- `0x180019d28`
- `0x180019d4c`
- `0x180019d70`
- `0x180019db8`
- `0x180019f48`
- `0x18001a0dc`
- `0x18001b5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b7c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b7c1`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001b700`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001b75d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001b700`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001b75d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001b6d2`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001b6d2`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001b684`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001b684`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001b629`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001b629`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18001b77f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18001b77f`

## string_xrefs

- `0x18001b642`: `DevObjCreateDeviceInfoList Failure %x, continue for the best effort`
- `0x18001b84a`: `CreateFile for %s failed 0x%x`

## pseudocode

```c
bool __fastcall CWwanDeviceEnumerator::isDeviceFullPower(const struct _GUID *a1)
{
  __int64 DeviceInfoList; // rax
  __int64 v3; // rbx
  DWORD LastError; // eax
  const unsigned __int16 *v5; // r8
  unsigned int i; // r14d
  _DWORD *v7; // rax
  const WCHAR *v8; // rdi
  int v9; // r8d
  char *FileW; // rax
  __int64 v11; // rbx
  bool v12; // bl
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-A9h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-A9h]
  unsigned __int64 v19; // [rsp+40h] [rbp-89h] BYREF
  _DWORD *v20; // [rsp+48h] [rbp-81h] BYREF
  __int64 v21; // [rsp+50h] [rbp-79h] BYREF
  char *v22; // [rsp+58h] [rbp-71h] BYREF
  __int64 v23; // [rsp+60h] [rbp-69h] BYREF
  _OWORD v24[2]; // [rsp+68h] [rbp-61h] BYREF
  WCHAR pszSrch[40]; // [rsp+90h] [rbp-39h] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v23 = DeviceInfoList;
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v5 = L"DevObjCreateDeviceInfoList Failure %x, continue for the best effort";
LABEL_3:
    WwanLog::Error("CWwanDeviceEnumerator::isDeviceFullPower", 0, v5, LastError);
    goto LABEL_25;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_NET, 0, 18, 0, 0) )
  {
    LastError = GetLastError();
    v5 = L"DevObjGetClassDevs Failure %x, continue for the best effort";
    goto LABEL_3;
  }
  LODWORD(v19) = 0;
  memset(v24, 0, sizeof(v24));
  LODWORD(v24[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v3, 0, &GUID_DEVINTERFACE_NET, i, v24); ++i )
  {
    DevObjGetDeviceInterfaceDetail(v3, v24, 0, 0, &v19, 0);
    if ( GetLastError() != 122 )
    {
      v14 = GetLastError();
      WwanLog::Error(
        "CWwanDeviceEnumerator::isDeviceFullPower",
        a1,
        L"DevObjGetDeviceInterfaceDetail failed - errorCode:%x",
        v14);
      goto LABEL_25;
    }
    v7 = operator new[]((unsigned int)v19, (const struct std::nothrow_t *)std::nothrow);
    v20 = v7;
    v8 = (const WCHAR *)v7;
    if ( !v7 )
    {
      dwCreationDisposition[0] = GetLastError();
      WwanLog::Error(
        "CWwanDeviceEnumerator::isDeviceFullPower",
        a1,
        L"Memory allocation for DO_DEVICE_INTERFACE_DETAIL_DATA(length:%d) failed - errorCode:%x",
        (unsigned int)v19,
        *(_QWORD *)dwCreationDisposition);
      goto LABEL_21;
    }
    *v7 = 8;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v3, v24, v7, (unsigned int)v19, 0, 0) )
    {
      v13 = GetLastError();
      WwanLog::Error(
        "CWwanDeviceEnumerator::isDeviceFullPower",
        a1,
        L"DevObjGetDeviceInterfaceDetail failed - errorCode:%x",
        v13);
LABEL_21:
      std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(&v20);
      goto LABEL_25;
    }
    GuidToString(a1, pszSrch, v9);
    if ( StrStrIW(v8 + 2, pszSrch) )
    {
      FileW = (char *)CreateFileW(v8 + 2, 0, 0, 0, 3u, 0x80u, 0);
      v22 = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        dwCreationDispositiona[0] = GetLastError();
        WwanLog::Error(
          "CWwanDeviceEnumerator::isDeviceFullPower",
          a1,
          L"CreateFile for %s failed 0x%x",
          v8 + 2,
          *(_QWORD *)dwCreationDispositiona);
      }
      else
      {
        CWwanDeviceEnumerator::NdisWmipGetPowerManagmentInfoAdapter(&v21, FileW);
        v11 = v21;
        if ( v21 )
        {
          WwanLog::Info(
            "CWwanDeviceEnumerator::isDeviceFullPower",
            a1,
            L"Current device power state in NDIS is %d",
            *(unsigned int *)(v21 + 536));
          v12 = *(_DWORD *)(v11 + 536) == 1;
          std::unique_ptr<_NDIS_INTERFACE_POWER_INFO>::~unique_ptr<_NDIS_INTERFACE_POWER_INFO>(&v21);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
          std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(&v20);
          goto LABEL_26;
        }
        std::unique_ptr<_NDIS_INTERFACE_POWER_INFO>::~unique_ptr<_NDIS_INTERFACE_POWER_INFO>(&v21);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
      goto LABEL_21;
    }
    std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(&v20);
  }
  GetLastError();
  v15 = GetLastError();
  WwanLog::Info(
    "CWwanDeviceEnumerator::isDeviceFullPower",
    a1,
    L"DevObjEnumDeviceInterfaces failed - errorCode:%x",
    v15);
LABEL_25:
  v12 = 0;
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
  return v12;
}

```

## disassembly

```asm
0x18001b5f0  push    rbp
0x18001b5f2  push    rbx
0x18001b5f3  push    rsi
0x18001b5f4  push    rdi
0x18001b5f5  push    r14
0x18001b5f7  push    r15
0x18001b5f9  lea     rbp, [rsp-2Fh]
0x18001b5fe  sub     rsp, 0F8h
0x18001b605  mov     rax, cs:__security_cookie
0x18001b60c  xor     rax, rsp
0x18001b60f  mov     [rbp+57h+var_40], rax
0x18001b613  mov     rsi, rcx
0x18001b616  mov     qword ptr [rsp+120h+dwCreationDisposition], 0
0x18001b61f  xor     ecx, ecx
0x18001b621  xor     r9d, r9d
0x18001b624  xor     r8d, r8d
0x18001b627  xor     edx, edx
0x18001b629  call    cs:__imp_DevObjCreateDeviceInfoList
0x18001b62f  mov     [rbp+57h+var_C0], rax
0x18001b633  mov     rbx, rax
0x18001b636  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b63a  jnz     short loc_18001B65F
0x18001b63c  call    cs:__imp_GetLastError
0x18001b642  lea     r8, aDevobjcreatede; "DevObjCreateDeviceInfoList Failure %x, "...
0x18001b649  xor     edx, edx; struct _GUID *
0x18001b64b  mov     r9d, eax
0x18001b64e  lea     rcx, aCwwandeviceenu_11; "CWwanDeviceEnumerator::isDeviceFullPowe"...
0x18001b655  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b65a  jmp     loc_18001B8F8
0x18001b65f  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], 0
0x18001b668  lea     rdx, GUID_DEVINTERFACE_NET
0x18001b66f  mov     r9d, 12h
0x18001b675  mov     qword ptr [rsp+120h+dwCreationDisposition], 0
0x18001b67e  xor     r8d, r8d
0x18001b681  mov     rcx, rbx
0x18001b684  call    cs:__imp_DevObjGetClassDevs
0x18001b68a  test    eax, eax
0x18001b68c  jnz     short loc_18001B69D
0x18001b68e  call    cs:__imp_GetLastError
0x18001b694  lea     r8, aDevobjgetclass; "DevObjGetClassDevs Failure %x, continue"...
0x18001b69b  jmp     short loc_18001B649
0x18001b69d  xorps   xmm0, xmm0
0x18001b6a0  mov     dword ptr [rsp+120h+var_E0], 0
0x18001b6a8  movups  [rbp+57h+var_B8], xmm0
0x18001b6ac  mov     dword ptr [rbp+57h+var_B8], 20h ; ' '
0x18001b6b3  xor     r14d, r14d
0x18001b6b6  movups  [rbp+57h+var_A8], xmm0
0x18001b6ba  lea     rax, [rbp+57h+var_B8]
0x18001b6be  mov     r9d, r14d
0x18001b6c1  lea     r8, GUID_DEVINTERFACE_NET
0x18001b6c8  mov     qword ptr [rsp+120h+dwCreationDisposition], rax
0x18001b6cd  xor     edx, edx
0x18001b6cf  mov     rcx, rbx
0x18001b6d2  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18001b6d8  test    eax, eax
0x18001b6da  jz      loc_18001B8D3
0x18001b6e0  lea     rax, [rsp+120h+var_E0]
0x18001b6e5  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], 0
0x18001b6ee  xor     r9d, r9d
0x18001b6f1  mov     qword ptr [rsp+120h+dwCreationDisposition], rax
0x18001b6f6  xor     r8d, r8d
0x18001b6f9  lea     rdx, [rbp+57h+var_B8]
0x18001b6fd  mov     rcx, rbx
0x18001b700  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001b706  call    cs:__imp_GetLastError
0x18001b70c  cmp     eax, 7Ah ; 'z'
0x18001b70f  jnz     loc_18001B8BE
0x18001b715  mov     ecx, dword ptr [rsp+120h+var_E0]; unsigned __int64
0x18001b719  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b720  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b725  mov     [rsp+120h+var_D8], rax
0x18001b72a  mov     rdi, rax
0x18001b72d  test    rax, rax
0x18001b730  jz      loc_18001B897
0x18001b736  mov     dword ptr [rax], 8
0x18001b73c  lea     rdx, [rbp+57h+var_B8]
0x18001b740  mov     r9d, dword ptr [rsp+120h+var_E0]
0x18001b745  mov     r8, rax
0x18001b748  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], 0
0x18001b751  mov     rcx, rbx
0x18001b754  mov     qword ptr [rsp+120h+dwCreationDisposition], 0
0x18001b75d  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001b763  test    eax, eax
0x18001b765  jz      loc_18001B86C
0x18001b76b  lea     rdx, [rbp+57h+pszSrch]; unsigned __int16 *
0x18001b76f  mov     rcx, rsi; struct _GUID *
0x18001b772  call    ?GuidToString@@YAHPEBU_GUID@@PEAGH@Z; GuidToString(_GUID const *,ushort *,int)
0x18001b777  lea     rcx, [rdi+4]; pszFirst
0x18001b77b  lea     rdx, [rbp+57h+pszSrch]; pszSrch
0x18001b77f  call    cs:__imp_StrStrIW
0x18001b785  test    rax, rax
0x18001b788  jnz     short loc_18001B79C
0x18001b78a  inc     r14d
0x18001b78d  lea     rcx, [rsp+120h+var_D8]
0x18001b792  call    ??1?$unique_ptr@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@U?$default_delete@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(void)
0x18001b797  jmp     loc_18001B6BA
0x18001b79c  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x18001b7a5  lea     rcx, [rdi+4]; lpFileName
0x18001b7a9  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001b7b1  xor     r9d, r9d; lpSecurityAttributes
0x18001b7b4  xor     r8d, r8d; dwShareMode
0x18001b7b7  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b7bf  xor     edx, edx; dwDesiredAccess
0x18001b7c1  call    cs:__imp_CreateFileW
0x18001b7c7  mov     [rbp+57h+var_C8], rax
0x18001b7cb  lea     rcx, [rax-1]
0x18001b7cf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001b7d3  ja      short loc_18001B83D
0x18001b7d5  mov     rdx, rax
0x18001b7d8  lea     rcx, [rbp+57h+var_D0]
0x18001b7dc  call    ?NdisWmipGetPowerManagmentInfoAdapter@CWwanDeviceEnumerator@@CA?AV?$unique_ptr@U_NDIS_INTERFACE_POWER_INFO@@U?$default_delete@U_NDIS_INTERFACE_POWER_INFO@@@std@@@std@@PEAX@Z; CWwanDeviceEnumerator::NdisWmipGetPowerManagmentInfoAdapter(void *)
0x18001b7e1  mov     rbx, [rbp+57h+var_D0]
0x18001b7e5  test    rbx, rbx
0x18001b7e8  jz      short loc_18001B832
0x18001b7ea  mov     r9d, [rbx+218h]
0x18001b7f1  lea     r8, aCurrentDeviceP_0; "Current device power state in NDIS is %"...
0x18001b7f8  mov     rdx, rsi; struct _GUID *
0x18001b7fb  lea     rcx, aCwwandeviceenu_11; "CWwanDeviceEnumerator::isDeviceFullPowe"...
0x18001b802  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001b807  cmp     dword ptr [rbx+218h], 1
0x18001b80e  lea     rcx, [rbp+57h+var_D0]
0x18001b812  setz    bl
0x18001b815  call    ??1?$unique_ptr@U_NDIS_INTERFACE_POWER_INFO@@U?$default_delete@U_NDIS_INTERFACE_POWER_INFO@@@std@@@std@@QEAA@XZ; std::unique_ptr<_NDIS_INTERFACE_POWER_INFO>::~unique_ptr<_NDIS_INTERFACE_POWER_INFO>(void)
0x18001b81a  lea     rcx, [rbp+57h+var_C8]
0x18001b81e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b823  lea     rcx, [rsp+120h+var_D8]
0x18001b828  call    ??1?$unique_ptr@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@U?$default_delete@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(void)
0x18001b82d  jmp     loc_18001B8FA
0x18001b832  lea     rcx, [rbp+57h+var_D0]
0x18001b836  call    ??1?$unique_ptr@U_NDIS_INTERFACE_POWER_INFO@@U?$default_delete@U_NDIS_INTERFACE_POWER_INFO@@@std@@@std@@QEAA@XZ; std::unique_ptr<_NDIS_INTERFACE_POWER_INFO>::~unique_ptr<_NDIS_INTERFACE_POWER_INFO>(void)
0x18001b83b  jmp     short loc_18001B861
0x18001b83d  call    cs:__imp_GetLastError
0x18001b843  lea     r9, [rdi+4]
0x18001b847  mov     rdx, rsi; struct _GUID *
0x18001b84a  lea     r8, aCreatefileForS; "CreateFile for %s failed 0x%x"
0x18001b851  mov     [rsp+120h+dwCreationDisposition], eax
0x18001b855  lea     rcx, aCwwandeviceenu_11; "CWwanDeviceEnumerator::isDeviceFullPowe"...
0x18001b85c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b861  lea     rcx, [rbp+57h+var_C8]
0x18001b865  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b86a  jmp     short loc_18001B88B
0x18001b86c  call    cs:__imp_GetLastError
0x18001b872  lea     r8, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail failed -"...
0x18001b879  mov     rdx, rsi; struct _GUID *
0x18001b87c  mov     r9d, eax
0x18001b87f  lea     rcx, aCwwandeviceenu_11; "CWwanDeviceEnumerator::isDeviceFullPowe"...
0x18001b886  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b88b  lea     rcx, [rsp+120h+var_D8]
0x18001b890  call    ??1?$unique_ptr@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@U?$default_delete@U_DO_DEVICE_INTERFACE_DETAIL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>::~unique_ptr<_DO_DEVICE_INTERFACE_DETAIL_DATA>(void)
0x18001b895  jmp     short loc_18001B8F8
0x18001b897  call    cs:__imp_GetLastError
0x18001b89d  mov     r9d, dword ptr [rsp+120h+var_E0]
0x18001b8a2  lea     r8, aMemoryAllocati_1; "Memory allocation for DO_DEVICE_INTERFA"...
0x18001b8a9  mov     rdx, rsi; struct _GUID *
0x18001b8ac  mov     [rsp+120h+dwCreationDisposition], eax
0x18001b8b0  lea     rcx, aCwwandeviceenu_11; "CWwanDeviceEnumerator::isDeviceFullPowe"...
0x18001b8b7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b8bc  jmp     short loc_18001B88B
0x18001b8be  call    cs:__imp_GetLastError
0x18001b8c4  lea     r8, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail failed -"...
0x18001b8cb  mov     rdx, rsi
0x18001b8ce  jmp     loc_18001B64B
0x18001b8d3  call    cs:__imp_GetLastError
0x18001b8d9  call    cs:__imp_GetLastError
0x18001b8df  lea     r8, aDevobjenumdevi_1; "DevObjEnumDeviceInterfaces failed - err"...
0x18001b8e6  mov     rdx, rsi; struct _GUID *
0x18001b8e9  mov     r9d, eax
0x18001b8ec  lea     rcx, aCwwandeviceenu_11; "CWwanDeviceEnumerator::isDeviceFullPowe"...
0x18001b8f3  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001b8f8  xor     ebx, ebx
0x18001b8fa  lea     rcx, [rbp+57h+var_C0]
0x18001b8fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b903  mov     al, bl
0x18001b905  mov     rcx, [rbp+57h+var_40]
0x18001b909  xor     rcx, rsp; StackCookie
0x18001b90c  call    __security_check_cookie
0x18001b911  add     rsp, 0F8h
0x18001b918  pop     r15
0x18001b91a  pop     r14
0x18001b91c  pop     rdi
0x18001b91d  pop     rsi
0x18001b91e  pop     rbx
0x18001b91f  pop     rbp
0x18001b920  retn
```
