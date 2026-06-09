# GetSearchRegistrationEndpoint

- ea: `0x1800b75c4`
- end: `0x1800b7951`
- name: `GetSearchRegistrationEndpoint`
- size: `909`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800be6d0`
- `0x180119e9c`
- `0x18011d038`

## callees

- `0x18000f880`
- `0x18002dc6c`
- `0x180056b90`
- `0x1800b3224`
- `0x1800b75c4`
- `0x1800b837c`
- `0x1800f8f24`
- `0x18010bfd4`
- `0x1801244c0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7912`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b7745`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b7745`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b763b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b763b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b75ff`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b75ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b791c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b7926`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b791c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b7926`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800b7692`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800b7692`

## string_xrefs

- `0x1800b7615`: `onecoreuap\base\appmodel\search\mssrch\dll\searchlifetimemanager.cpp`
- `0x1800b7650`: `onecoreuap\base\appmodel\search\mssrch\dll\searchlifetimemanager.cpp`
- `0x1800b777c`: `onecoreuap\base\appmodel\search\mssrch\dll\searchlifetimemanager.cpp`
- `0x1800b77ea`: `onecoreuap\base\appmodel\search\mssrch\dll\searchlifetimemanager.cpp`
- `0x1800b783b`: `onecoreuap\base\appmodel\search\mssrch\dll\searchlifetimemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetSearchRegistrationEndpoint(_QWORD *a1, _BYTE *a2)
{
  SC_HANDLE v4; // rax
  const char *v5; // r9
  SC_HANDLE v6; // rdi
  unsigned int LastError; // ebx
  SC_HANDLE v8; // rbx
  const char *v9; // r9
  __int64 v10; // rdx
  const wchar_t *v11; // rcx
  int v12; // esi
  HRESULT v13; // esi
  int v14; // ecx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  int v20; // eax
  __int64 v22; // rcx
  LPVOID v23; // rcx
  int pcbBytesNeeded; // [rsp+20h] [rbp-59h]
  LPVOID ppv; // [rsp+30h] [rbp-49h] BYREF
  SC_HANDLE v26; // [rsp+38h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-39h] BYREF
  __int64 v28; // [rsp+48h] [rbp-31h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-29h] BYREF
  DWORD v30; // [rsp+58h] [rbp-21h] BYREF
  SC_HANDLE v31; // [rsp+60h] [rbp-19h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-11h]
  HKEY v33; // [rsp+70h] [rbp-9h] BYREF
  char v34; // [rsp+78h] [rbp-1h]
  BYTE Buffer[16]; // [rsp+80h] [rbp+7h] BYREF
  __int128 v36; // [rsp+90h] [rbp+17h]
  int v37; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v4 = OpenSCManagerW(0, 0, 1u);
  v6 = v4;
  v31 = v4;
  if ( !v4 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x23,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\searchlifetimemanager.cpp",
                  v5);
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v31);
    return LastError;
  }
  v8 = OpenServiceW(v4, L"wsearch", 4u);
  v26 = v8;
  if ( !v8 )
  {
    v10 = 38;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\searchlifetimemanager.cpp",
                  v9);
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
    goto LABEL_25;
  }
  *(_OWORD *)Buffer = 0;
  v36 = 0;
  v37 = 0;
  v30 = 0;
  if ( !QueryServiceStatusEx(v8, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v30) )
  {
    v10 = 43;
    goto LABEL_5;
  }
  if ( *(_DWORD *)&Buffer[4] != 4 )
  {
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
    LastError = 0;
    goto LABEL_25;
  }
  hKey = 0;
  p_hKey = &hKey;
  v33 = 0;
  v34 = 1;
  v12 = WSearchRegOpenKeyEx(
          v11,
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows Search\\SearchIdle",
          (unsigned int)v9,
          1u,
          &v33);
  if ( v34 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      p_hKey,
      v33);
  if ( !v12 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_9;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v13 = CoCreateInstance(
          &GUID_b52d54bb_4818_4eb9_aa80_f9eacd371df8,
          0,
          4u,
          &GUID_993eceb0_6f1b_49fe_8ba2_21b6a5317de1,
          &ppv);
  if ( (unsigned int)(v13 + 2147023843) <= 0x11 && (v14 = 164001, _bittest(&v14, v13 + 2147023843))
    || v13 == -2147023653 )
  {
    v23 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
    }
    if ( hKey )
      RegCloseKey(hKey);
    CloseServiceHandle(v8);
    CloseServiceHandle(v6);
  }
  else
  {
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\searchlifetimemanager.cpp",
        (const char *)(unsigned int)v13,
        pcbBytesNeeded);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
      LastError = v13;
      goto LABEL_25;
    }
    v29 = 0;
    v15 = ppv;
    v16 = *(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)ppv + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v17 = v16(v15, &v29);
    LastError = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\searchlifetimemanager.cpp",
        (const char *)(unsigned int)v17,
        pcbBytesNeeded);
LABEL_23:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_24;
    }
    v28 = 0;
    v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
    v19 = **v29;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v20 = v19(v18, &GUID_6a4eb77f_114c_4ff0_9aa8_9e159df6c137, &v28);
    LastError = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\searchlifetimemanager.cpp",
        (const char *)(unsigned int)v20,
        pcbBytesNeeded);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      goto LABEL_23;
    }
    v22 = v28;
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      v22 = v28;
    }
    *a1 = v22;
    *a2 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v31);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b75c4  mov     [rsp-8+arg_10], rbx
0x1800b75c9  push    rbp
0x1800b75ca  push    rsi
0x1800b75cb  push    rdi
0x1800b75cc  push    r14
0x1800b75ce  push    r15
0x1800b75d0  lea     rbp, [rsp-37h]
0x1800b75d5  sub     rsp, 0B0h
0x1800b75dc  mov     rax, cs:__security_cookie
0x1800b75e3  xor     rax, rsp
0x1800b75e6  mov     [rbp+57h+var_28], rax
0x1800b75ea  mov     r14, rdx
0x1800b75ed  mov     r15, rcx
0x1800b75f0  mov     byte ptr [rdx], 0
0x1800b75f3  mov     esi, 1
0x1800b75f8  mov     r8d, esi; dwDesiredAccess
0x1800b75fb  xor     edx, edx; lpDatabaseName
0x1800b75fd  xor     ecx, ecx; lpMachineName
0x1800b75ff  call    cs:__imp_OpenSCManagerW
0x1800b7605  mov     rdi, rax
0x1800b7608  mov     [rbp+57h+var_70], rax
0x1800b760c  test    rax, rax
0x1800b760f  jnz     short loc_1800B762B
0x1800b7611  mov     rcx, [rbp+5Fh]; this
0x1800b7615  lea     r8, aOnecoreuapBase_160; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800b761c  lea     edx, [rsi+22h]; void *
0x1800b761f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b7624  mov     ebx, eax
0x1800b7626  jmp     loc_1800B787E
0x1800b762b  mov     r8d, 4; dwDesiredAccess
0x1800b7631  lea     rdx, ServiceName; "wsearch"
0x1800b7638  mov     rcx, rdi; hSCManager
0x1800b763b  call    cs:__imp_OpenServiceW
0x1800b7641  mov     rbx, rax
0x1800b7644  mov     [rbp+57h+var_98], rax
0x1800b7648  test    rax, rax
0x1800b764b  jnz     short loc_1800B7667
0x1800b764d  lea     edx, [rax+26h]; void *
0x1800b7650  lea     r8, aOnecoreuapBase_160; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800b7657  mov     rcx, [rbp+5Fh]; this
0x1800b765b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b7660  mov     ebx, eax
0x1800b7662  jmp     loc_1800B7874
0x1800b7667  xorps   xmm0, xmm0
0x1800b766a  xor     eax, eax
0x1800b766c  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800b7670  movups  [rbp+57h+var_40], xmm0
0x1800b7674  mov     [rbp+57h+var_30], eax
0x1800b7677  mov     [rbp+57h+var_78], eax
0x1800b767a  lea     rax, [rbp+57h+var_78]
0x1800b767e  mov     [rsp+0D0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800b7683  mov     r9d, 24h ; '$'; cbBufSize
0x1800b7689  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800b768d  xor     edx, edx; InfoLevel
0x1800b768f  mov     rcx, rbx; hService
0x1800b7692  call    cs:__imp_QueryServiceStatusEx
0x1800b7698  test    eax, eax
0x1800b769a  jnz     short loc_1800B76A1
0x1800b769c  lea     edx, [rax+2Bh]
0x1800b769f  jmp     short loc_1800B7650
0x1800b76a1  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x1800b76a5  jz      short loc_1800B76B7
0x1800b76a7  lea     rcx, [rbp+57h+var_98]
0x1800b76ab  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b76b0  xor     ebx, ebx
0x1800b76b2  jmp     loc_1800B787E
0x1800b76b7  mov     [rbp+57h+hKey], 0
0x1800b76bf  lea     rax, [rbp+57h+hKey]
0x1800b76c3  mov     [rbp+57h+var_68], rax
0x1800b76c7  mov     [rbp+57h+var_60], 0
0x1800b76cf  mov     [rbp+57h+var_58], sil
0x1800b76d3  lea     rax, [rbp+57h+var_60]
0x1800b76d7  mov     [rsp+0D0h+var_A8], rax; HKEY *
0x1800b76dc  mov     dword ptr [rsp+0D0h+pcbBytesNeeded], esi; unsigned int
0x1800b76e0  lea     r8, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x1800b76e7  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800b76ee  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800b76f3  mov     esi, eax
0x1800b76f5  cmp     [rbp+57h+var_58], 0
0x1800b76f9  jz      short loc_1800B7708
0x1800b76fb  mov     rdx, [rbp+57h+var_60]
0x1800b76ff  mov     rcx, [rbp+57h+var_68]
0x1800b7703  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b7708  test    esi, esi
0x1800b770a  jnz     short loc_1800B7717
0x1800b770c  lea     rcx, [rbp+57h+hKey]
0x1800b7710  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b7715  jmp     short loc_1800B76A7
0x1800b7717  mov     [rbp+57h+ppv], 0
0x1800b771f  lea     rcx, [rbp+57h+ppv]
0x1800b7723  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7728  lea     rax, [rbp+57h+ppv]
0x1800b772c  mov     [rsp+0D0h+pcbBytesNeeded], rax; int
0x1800b7731  lea     r9, _GUID_993eceb0_6f1b_49fe_8ba2_21b6a5317de1; riid
0x1800b7738  xor     edx, edx; pUnkOuter
0x1800b773a  lea     r8d, [rdx+4]; dwClsContext
0x1800b773e  lea     rcx, _GUID_b52d54bb_4818_4eb9_aa80_f9eacd371df8; rclsid
0x1800b7745  call    cs:__imp_CoCreateInstance
0x1800b774b  mov     esi, eax
0x1800b774d  add     eax, 7FF8FBE3h
0x1800b7752  cmp     eax, 11h
0x1800b7755  ja      short loc_1800B7765
0x1800b7757  mov     ecx, 280A1h
0x1800b775c  bt      ecx, eax
0x1800b775f  jb      loc_1800B78EB
0x1800b7765  cmp     esi, 800704DBh
0x1800b776b  jz      loc_1800B78EB
0x1800b7771  test    esi, esi
0x1800b7773  jns     short loc_1800B77B2
0x1800b7775  mov     rcx, [rbp+5Fh]; this
0x1800b7779  mov     r9d, esi; char *
0x1800b777c  lea     r8, aOnecoreuapBase_160; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800b7783  mov     edx, 47h ; 'G'; void *
0x1800b7788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b778d  nop
0x1800b778e  lea     rcx, [rbp+57h+ppv]
0x1800b7792  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7797  nop
0x1800b7798  lea     rcx, [rbp+57h+hKey]
0x1800b779c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b77a1  nop
0x1800b77a2  lea     rcx, [rbp+57h+var_98]
0x1800b77a6  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b77ab  mov     ebx, esi
0x1800b77ad  jmp     loc_1800B787E
0x1800b77b2  mov     [rbp+57h+var_80], 0
0x1800b77ba  mov     rdi, [rbp+57h+ppv]
0x1800b77be  mov     rax, [rdi]
0x1800b77c1  mov     rbx, [rax+20h]
0x1800b77c5  lea     rcx, [rbp+57h+var_80]
0x1800b77c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b77ce  lea     rdx, [rbp+57h+var_80]
0x1800b77d2  mov     rcx, rdi
0x1800b77d5  mov     rax, rbx
0x1800b77d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b77dd  mov     ebx, eax
0x1800b77df  test    eax, eax
0x1800b77e1  jns     short loc_1800B77FD
0x1800b77e3  mov     rcx, [rbp+5Fh]; this
0x1800b77e7  mov     r9d, eax; char *
0x1800b77ea  lea     r8, aOnecoreuapBase_160; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800b77f1  mov     edx, 4Ah ; 'J'; void *
0x1800b77f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b77fb  jmp     short loc_1800B7856
0x1800b77fd  mov     [rbp+57h+var_88], 0
0x1800b7805  mov     rbx, [rbp+57h+var_80]
0x1800b7809  mov     rax, [rbx]
0x1800b780c  mov     rdi, [rax]
0x1800b780f  lea     rcx, [rbp+57h+var_88]
0x1800b7813  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7818  lea     r8, [rbp+57h+var_88]
0x1800b781c  lea     rdx, _GUID_6a4eb77f_114c_4ff0_9aa8_9e159df6c137
0x1800b7823  mov     rcx, rbx
0x1800b7826  mov     rax, rdi
0x1800b7829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b782e  mov     ebx, eax
0x1800b7830  test    eax, eax
0x1800b7832  jns     short loc_1800B788E
0x1800b7834  mov     rcx, [rbp+5Fh]; this
0x1800b7838  mov     r9d, eax; char *
0x1800b783b  lea     r8, aOnecoreuapBase_160; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800b7842  mov     edx, 4Dh ; 'M'; void *
0x1800b7847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b784c  lea     rcx, [rbp+57h+var_88]
0x1800b7850  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7855  nop
0x1800b7856  lea     rcx, [rbp+57h+var_80]
0x1800b785a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b785f  nop
0x1800b7860  lea     rcx, [rbp+57h+ppv]
0x1800b7864  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b7869  nop
0x1800b786a  lea     rcx, [rbp+57h+hKey]
0x1800b786e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b7873  nop
0x1800b7874  lea     rcx, [rbp+57h+var_98]
0x1800b7878  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b787d  nop
0x1800b787e  lea     rcx, [rbp+57h+var_70]
0x1800b7882  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b7887  mov     eax, ebx
0x1800b7889  jmp     loc_1800B792E
0x1800b788e  mov     rcx, [rbp+57h+var_88]
0x1800b7892  test    rcx, rcx
0x1800b7895  jz      short loc_1800B78A7
0x1800b7897  mov     rax, [rcx]
0x1800b789a  mov     rax, [rax+8]
0x1800b789e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b78a3  mov     rcx, [rbp+57h+var_88]
0x1800b78a7  mov     [r15], rcx
0x1800b78aa  mov     byte ptr [r14], 1
0x1800b78ae  lea     rcx, [rbp+57h+var_88]
0x1800b78b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b78b7  nop
0x1800b78b8  lea     rcx, [rbp+57h+var_80]
0x1800b78bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b78c1  nop
0x1800b78c2  lea     rcx, [rbp+57h+ppv]
0x1800b78c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b78cb  nop
0x1800b78cc  lea     rcx, [rbp+57h+hKey]
0x1800b78d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b78d5  nop
0x1800b78d6  lea     rcx, [rbp+57h+var_98]
0x1800b78da  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b78df  nop
0x1800b78e0  lea     rcx, [rbp+57h+var_70]
0x1800b78e4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b78e9  jmp     short loc_1800B792C
0x1800b78eb  mov     rcx, [rbp+57h+ppv]
0x1800b78ef  test    rcx, rcx
0x1800b78f2  jz      short loc_1800B7909
0x1800b78f4  mov     [rbp+57h+ppv], 0
0x1800b78fc  mov     rax, [rcx]
0x1800b78ff  mov     rax, [rax+10h]
0x1800b7903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7908  nop
0x1800b7909  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b790d  test    rcx, rcx
0x1800b7910  jz      short loc_1800B7919
0x1800b7912  call    cs:__imp_RegCloseKey
0x1800b7918  nop
0x1800b7919  mov     rcx, rbx; hSCObject
0x1800b791c  call    cs:__imp_CloseServiceHandle
0x1800b7922  nop
0x1800b7923  mov     rcx, rdi; hSCObject
0x1800b7926  call    cs:__imp_CloseServiceHandle
0x1800b792c  xor     eax, eax
0x1800b792e  mov     rcx, [rbp+57h+var_28]
0x1800b7932  xor     rcx, rsp; StackCookie
0x1800b7935  call    __security_check_cookie
0x1800b793a  mov     rbx, [rsp+0D0h+arg_10]
0x1800b7942  add     rsp, 0B0h
0x1800b7949  pop     r15
0x1800b794b  pop     r14
0x1800b794d  pop     rdi
0x1800b794e  pop     rsi
0x1800b794f  pop     rbp
0x1800b7950  retn
```
