# Microsoft::Windows::Autopilot::Diagnostics::ExtractWmiResult::ExecuteWmiQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::com_ptr_t<IEnumWbemClassObject,wil::err_returncode_policy> &)

- ea: `0x1801be6f4`
- end: `0x1801bebeb`
- name: `?ExecuteWmiQuery@ExtractWmiResult@Diagnostics@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$com_ptr_t@UIEnumWbemClassObject@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `1271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801bedf4`

## callees

- `0x180067e54`
- `0x18006e43c`
- `0x180080bac`
- `0x180084d5c`
- `0x18008a26c`
- `0x1801be6f4`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801be8fe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801beaf5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801be8fe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801beaf5`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1801be73c`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1801be73c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801be7ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801be7ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Windows::Autopilot::Diagnostics::ExtractWmiResult::ExecuteWmiQuery(
        __int64 a1,
        IUnknown **a2)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  char v6; // di
  HRESULT v7; // eax
  unsigned int v8; // ebx
  LPVOID v9; // rbx
  __int64 (__fastcall *v10)(LPVOID, _QWORD, _QWORD, _QWORD); // r14
  _QWORD *bstr; // rax
  int v12; // ebx
  const char *v13; // r9
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT v15; // eax
  unsigned int v16; // ebx
  IUnknown *v17; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r12
  __int64 v19; // rdx
  __int64 v20; // r14
  _QWORD *v21; // rax
  int v22; // ebx
  __int64 (__fastcall **v23)(_QWORD, GUID *, IUnknown **); // rax
  int v24; // eax
  unsigned int v25; // ebx
  HRESULT v26; // eax
  unsigned int v27; // ebx
  IUnknown *v28; // rax
  IUnknown *v29; // rcx
  int dwAuthnLevel; // [rsp+20h] [rbp-88h]
  int dwAuthnLevela; // [rsp+20h] [rbp-88h]
  int dwAuthnLevelb; // [rsp+20h] [rbp-88h]
  int dwAuthnLevelc; // [rsp+20h] [rbp-88h]
  IUnknown *v34; // [rsp+50h] [rbp-58h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, IUnknown **); // [rsp+58h] [rbp-50h] BYREF
  __int64 v36; // [rsp+60h] [rbp-48h] BYREF
  char v37[8]; // [rsp+68h] [rbp-40h] BYREF
  _BYTE v38[16]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  IUnknown *pProxy; // [rsp+C0h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+20h] BYREF

  v4 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417831 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawdata\\ex"
                    "tractwmiresult.cpp",
      (const char *)v4,
      dwAuthnLevel);
    return v4;
  }
  ppv = 0;
  v6 = 1;
  v7 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawdata\\ex"
                    "tractwmiresult.cpp",
      (const char *)(unsigned int)v7,
      dwAuthnLevela);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
    return v8;
  }
  pProxy = 0;
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL);
  pProxy = 0;
  try
  {
    bstr = (_QWORD *)wil::make_bstr(v37, L"ROOT\\CIMV2");
    v12 = v10(v9, *bstr, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v37);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawdata\\"
                      "extractwmiresult.cpp",
        (const char *)(unsigned int)v12,
        0);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&pProxy);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
      return (unsigned int)v12;
    }
    v36 = 0;
    lpVtbl = pProxy->lpVtbl;
    v36 = 0;
    if ( ((unsigned __int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           pProxy,
           &IID_IClientSecurity,
           &v36) != -2147467262 )
    {
      v15 = CoSetProxyBlanket(pProxy, 0xAu, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawdata"
                        "\\extractwmiresult.cpp",
          (const char *)(unsigned int)v15,
          dwAuthnLevelb);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v36);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&pProxy);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
        return v16;
      }
      v6 = 0;
    }
    v35 = 0;
    v17 = pProxy;
    Release = pProxy->lpVtbl[6].Release;
    v35 = 0;
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v20 = *(_QWORD *)wil::make_bstr(v38, v19);
    v21 = (_QWORD *)wil::make_bstr(v37, L"WQL");
    v22 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, __int64))Release)(v17, *v21, v20, 48);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v38);
    if ( v22 >= 0 )
    {
      v34 = 0;
      v23 = *v35;
      v34 = 0;
      v24 = (*v23)(v35, &IID_IEnumWbemClassObject, &v34);
      v25 = v24;
      if ( v24 >= 0 )
      {
        if ( v6 || (v26 = CoSetProxyBlanket(v34, 0xAu, 0xFFFFFFFF, 0, 3u, 3u, 0, 0), v27 = v26, v26 >= 0) )
        {
          v28 = v34;
          v34 = 0;
          v29 = *a2;
          *a2 = v28;
          if ( v29 )
            ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v34);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v35);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v36);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&pProxy);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawda"
                          "ta\\extractwmiresult.cpp",
            (const char *)(unsigned int)v26,
            dwAuthnLevelc);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v34);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v35);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v36);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&pProxy);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
          result = v27;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawdata"
                        "\\extractwmiresult.cpp",
          (const char *)(unsigned int)v24,
          0);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v34);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v35);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v36);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&pProxy);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
        result = v25;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\extractrawdata\\"
                      "extractwmiresult.cpp",
        (const char *)(unsigned int)v22,
        0);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v35);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v36);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&pProxy);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&ppv);
      result = (unsigned int)v22;
    }
  }
  catch ( ... )
  {
    LODWORD(pProxy) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x94,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\diagnosticanalysisframework\\lib\\"
                                      "extractrawdata\\extractwmiresult.cpp",
                        v13);
    return (unsigned int)pProxy;
  }
  return result;
}

```

## disassembly

```asm
0x1801be6f4  mov     rax, rsp
0x1801be6f7  mov     [rax+8], rbx
0x1801be6fb  mov     [rax+10h], rsi
0x1801be6ff  push    rdi
0x1801be700  push    r12
0x1801be702  push    r13
0x1801be704  push    r14
0x1801be706  push    r15
0x1801be708  sub     rsp, 80h
0x1801be70f  mov     rsi, rdx
0x1801be712  mov     r15, rcx
0x1801be715  xor     r13d, r13d
0x1801be718  mov     [rax-68h], r13
0x1801be71c  mov     [rax-70h], r13d
0x1801be720  mov     [rax-78h], r13
0x1801be724  lea     r12d, [r13+3]
0x1801be728  mov     [rax-80h], r12d
0x1801be72c  mov     [rsp+0A8h+dwAuthnLevel], r13d; int
0x1801be731  xor     r9d, r9d; pReserved1
0x1801be734  xor     r8d, r8d; asAuthSvc
0x1801be737  or      edx, 0FFFFFFFFh; cAuthSvc
0x1801be73a  xor     ecx, ecx; pSecDesc
0x1801be73c  call    cs:__imp_CoInitializeSecurity
0x1801be743  nop     dword ptr [rax+rax+00h]
0x1801be748  mov     ebx, eax
0x1801be74a  mov     eax, 80000000h
0x1801be74f  lea     ecx, [rbx+rax]
0x1801be752  test    eax, ecx
0x1801be754  jnz     short loc_1801BE780
0x1801be756  cmp     ebx, 80010119h
0x1801be75c  jz      short loc_1801BE780
0x1801be75e  mov     rcx, [rsp+0A8h]; this
0x1801be766  mov     r9d, ebx; char *
0x1801be769  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801be770  lea     edx, [r13+4Ch]; void *
0x1801be774  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801be779  mov     eax, ebx
0x1801be77b  jmp     loc_1801BEBCD
0x1801be780  mov     [rsp+0A8h+ppv], r13
0x1801be788  lea     rax, [rsp+0A8h+ppv]
0x1801be790  mov     qword ptr [rsp+0A8h+dwAuthnLevel], rax; int
0x1801be795  lea     r9, IID_IWbemLocator; riid
0x1801be79c  mov     edi, 1
0x1801be7a1  mov     r8d, edi; dwClsContext
0x1801be7a4  xor     edx, edx; pUnkOuter
0x1801be7a6  lea     rcx, CLSID_WbemLocator; rclsid
0x1801be7ad  call    cs:__imp_CoCreateInstance
0x1801be7b4  nop     dword ptr [rax+rax+00h]
0x1801be7b9  mov     ebx, eax
0x1801be7bb  test    eax, eax
0x1801be7bd  jns     short loc_1801BE7EE
0x1801be7bf  mov     rcx, [rsp+0A8h]; this
0x1801be7c7  mov     r9d, eax; char *
0x1801be7ca  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801be7d1  lea     edx, [rdi+4Eh]; void *
0x1801be7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801be7d9  nop
0x1801be7da  lea     rcx, [rsp+0A8h+ppv]
0x1801be7e2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801be7e7  mov     eax, ebx
0x1801be7e9  jmp     loc_1801BEBCD
0x1801be7ee  mov     [rsp+0A8h+pProxy], r13
0x1801be7f6  mov     rbx, [rsp+0A8h+ppv]
0x1801be7fe  mov     rax, [rbx]
0x1801be801  mov     r14, [rax+18h]
0x1801be805  mov     [rsp+0A8h+pProxy], r13
0x1801be80d  lea     rdx, aRootCimv2; "ROOT\\CIMV2"
0x1801be814  lea     rcx, [rsp+0A8h+var_40]
0x1801be819  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801be81e  nop
0x1801be81f  lea     rcx, [rsp+0A8h+pProxy]
0x1801be827  mov     [rsp+0A8h+var_68], rcx
0x1801be82c  mov     qword ptr [rsp+0A8h+dwCapabilities], r13
0x1801be831  mov     [rsp+0A8h+pAuthInfo], r13
0x1801be836  mov     [rsp+0A8h+dwImpLevel], r13d
0x1801be83b  mov     qword ptr [rsp+0A8h+dwAuthnLevel], r13; int
0x1801be840  xor     r9d, r9d
0x1801be843  xor     r8d, r8d
0x1801be846  mov     rdx, [rax]
0x1801be849  mov     rcx, rbx
0x1801be84c  mov     rax, r14
0x1801be84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be854  mov     ebx, eax
0x1801be856  lea     rcx, [rsp+0A8h+var_40]
0x1801be85b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801be860  test    ebx, ebx
0x1801be862  jns     short loc_1801BE8A3
0x1801be864  mov     rcx, [rsp+0A8h]; this
0x1801be86c  mov     r9d, ebx; char *
0x1801be86f  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801be876  mov     edx, 5Ah ; 'Z'; void *
0x1801be87b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801be880  nop
0x1801be881  lea     rcx, [rsp+0A8h+pProxy]
0x1801be889  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801be88e  nop
0x1801be88f  lea     rcx, [rsp+0A8h+ppv]
0x1801be897  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801be89c  mov     eax, ebx
0x1801be89e  jmp     loc_1801BEBCD
0x1801be8a3  mov     [rsp+0A8h+var_48], r13
0x1801be8a8  mov     rcx, [rsp+0A8h+pProxy]
0x1801be8b0  mov     rax, [rcx]
0x1801be8b3  mov     [rsp+0A8h+var_48], r13
0x1801be8b8  lea     r8, [rsp+0A8h+var_48]
0x1801be8bd  lea     rdx, IID_IClientSecurity
0x1801be8c4  mov     rax, [rax]
0x1801be8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be8cc  cmp     eax, 80004002h
0x1801be8d1  jz      loc_1801BE95D
0x1801be8d7  mov     [rsp+0A8h+dwCapabilities], r13d; dwCapabilities
0x1801be8dc  mov     [rsp+0A8h+pAuthInfo], r13; pAuthInfo
0x1801be8e1  mov     [rsp+0A8h+dwImpLevel], r12d; dwImpLevel
0x1801be8e6  mov     [rsp+0A8h+dwAuthnLevel], r12d; int
0x1801be8eb  xor     r9d, r9d; pServerPrincName
0x1801be8ee  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1801be8f2  lea     edx, [r9+0Ah]; dwAuthnSvc
0x1801be8f6  mov     rcx, [rsp+0A8h+pProxy]; pProxy
0x1801be8fe  call    cs:__imp_CoSetProxyBlanket
0x1801be905  nop     dword ptr [rax+rax+00h]
0x1801be90a  mov     ebx, eax
0x1801be90c  test    eax, eax
0x1801be90e  jns     short loc_1801BE95A
0x1801be910  mov     rcx, [rsp+0A8h]; this
0x1801be918  mov     r9d, eax; char *
0x1801be91b  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801be922  mov     edx, 74h ; 't'; void *
0x1801be927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801be92c  nop
0x1801be92d  lea     rcx, [rsp+0A8h+var_48]
0x1801be932  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801be937  nop
0x1801be938  lea     rcx, [rsp+0A8h+pProxy]
0x1801be940  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801be945  nop
0x1801be946  lea     rcx, [rsp+0A8h+ppv]
0x1801be94e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801be953  mov     eax, ebx
0x1801be955  jmp     loc_1801BEBCD
0x1801be95a  mov     dil, r13b
0x1801be95d  mov     [rsp+0A8h+var_50], r13
0x1801be962  mov     rbx, [rsp+0A8h+pProxy]
0x1801be96a  mov     rax, [rbx]
0x1801be96d  mov     r12, [rax+0A0h]
0x1801be974  mov     [rsp+0A8h+var_50], r13
0x1801be979  mov     rcx, r15
0x1801be97c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801be981  mov     rdx, rax
0x1801be984  lea     rcx, [rsp+0A8h+var_38]
0x1801be989  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801be98e  nop
0x1801be98f  mov     r14, [rax]
0x1801be992  lea     rdx, aWql; "WQL"
0x1801be999  lea     rcx, [rsp+0A8h+var_40]
0x1801be99e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801be9a3  nop
0x1801be9a4  lea     rcx, [rsp+0A8h+var_50]
0x1801be9a9  mov     qword ptr [rsp+0A8h+dwImpLevel], rcx
0x1801be9ae  mov     qword ptr [rsp+0A8h+dwAuthnLevel], r13; int
0x1801be9b3  mov     r9d, 30h ; '0'
0x1801be9b9  mov     r8, r14
0x1801be9bc  mov     rdx, [rax]
0x1801be9bf  mov     rcx, rbx
0x1801be9c2  mov     rax, r12
0x1801be9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be9ca  mov     ebx, eax
0x1801be9cc  lea     rcx, [rsp+0A8h+var_40]
0x1801be9d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801be9d6  nop
0x1801be9d7  lea     rcx, [rsp+0A8h+var_38]
0x1801be9dc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801be9e1  test    ebx, ebx
0x1801be9e3  jns     short loc_1801BEA3A
0x1801be9e5  mov     rcx, [rsp+0A8h]; this
0x1801be9ed  mov     r9d, ebx; char *
0x1801be9f0  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801be9f7  mov     edx, 7Dh ; '}'; void *
0x1801be9fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bea01  nop
0x1801bea02  lea     rcx, [rsp+0A8h+var_50]
0x1801bea07  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bea0c  nop
0x1801bea0d  lea     rcx, [rsp+0A8h+var_48]
0x1801bea12  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bea17  nop
0x1801bea18  lea     rcx, [rsp+0A8h+pProxy]
0x1801bea20  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bea25  nop
0x1801bea26  lea     rcx, [rsp+0A8h+ppv]
0x1801bea2e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bea33  mov     eax, ebx
0x1801bea35  jmp     loc_1801BEBCD
0x1801bea3a  mov     [rsp+0A8h+var_58], r13
0x1801bea3f  mov     rcx, [rsp+0A8h+var_50]
0x1801bea44  mov     rax, [rcx]
0x1801bea47  mov     [rsp+0A8h+var_58], r13
0x1801bea4c  lea     r8, [rsp+0A8h+var_58]
0x1801bea51  lea     rdx, IID_IEnumWbemClassObject
0x1801bea58  mov     rax, [rax]
0x1801bea5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bea60  mov     ebx, eax
0x1801bea62  test    eax, eax
0x1801bea64  jns     short loc_1801BEAC6
0x1801bea66  mov     rcx, [rsp+0A8h]; this
0x1801bea6e  mov     r9d, eax; char *
0x1801bea71  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801bea78  mov     edx, 80h; void *
0x1801bea7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bea82  nop
0x1801bea83  lea     rcx, [rsp+0A8h+var_58]
0x1801bea88  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bea8d  nop
0x1801bea8e  lea     rcx, [rsp+0A8h+var_50]
0x1801bea93  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bea98  nop
0x1801bea99  lea     rcx, [rsp+0A8h+var_48]
0x1801bea9e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beaa3  nop
0x1801beaa4  lea     rcx, [rsp+0A8h+pProxy]
0x1801beaac  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beab1  nop
0x1801beab2  lea     rcx, [rsp+0A8h+ppv]
0x1801beaba  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beabf  mov     eax, ebx
0x1801beac1  jmp     loc_1801BEBCD
0x1801beac6  test    dil, dil
0x1801beac9  jnz     loc_1801BEB64
0x1801beacf  mov     [rsp+0A8h+dwCapabilities], r13d; dwCapabilities
0x1801bead4  mov     [rsp+0A8h+pAuthInfo], r13; pAuthInfo
0x1801bead9  mov     eax, 3
0x1801beade  mov     [rsp+0A8h+dwImpLevel], eax; dwImpLevel
0x1801beae2  mov     [rsp+0A8h+dwAuthnLevel], eax; int
0x1801beae6  xor     r9d, r9d; pServerPrincName
0x1801beae9  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1801beaed  lea     edx, [rax+7]; dwAuthnSvc
0x1801beaf0  mov     rcx, [rsp+0A8h+var_58]; pProxy
0x1801beaf5  call    cs:__imp_CoSetProxyBlanket
0x1801beafc  nop     dword ptr [rax+rax+00h]
0x1801beb01  mov     ebx, eax
0x1801beb03  test    eax, eax
0x1801beb05  jns     short loc_1801BEB64
0x1801beb07  mov     rcx, [rsp+0A8h]; this
0x1801beb0f  mov     r9d, eax; char *
0x1801beb12  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801beb19  mov     edx, 8Dh; void *
0x1801beb1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801beb23  nop
0x1801beb24  lea     rcx, [rsp+0A8h+var_58]
0x1801beb29  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb2e  nop
0x1801beb2f  lea     rcx, [rsp+0A8h+var_50]
0x1801beb34  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb39  nop
0x1801beb3a  lea     rcx, [rsp+0A8h+var_48]
0x1801beb3f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb44  nop
0x1801beb45  lea     rcx, [rsp+0A8h+pProxy]
0x1801beb4d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb52  nop
0x1801beb53  lea     rcx, [rsp+0A8h+ppv]
0x1801beb5b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb60  mov     eax, ebx
0x1801beb62  jmp     short loc_1801BEBCD
0x1801beb64  mov     rax, [rsp+0A8h+var_58]
0x1801beb69  mov     [rsp+0A8h+var_58], r13
0x1801beb6e  mov     rcx, [rsi]
0x1801beb71  mov     [rsi], rax
0x1801beb74  test    rcx, rcx
0x1801beb77  jz      short loc_1801BEB86
0x1801beb79  mov     rax, [rcx]
0x1801beb7c  mov     rax, [rax+10h]
0x1801beb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801beb85  nop
0x1801beb86  lea     rcx, [rsp+0A8h+var_58]
0x1801beb8b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb90  nop
0x1801beb91  lea     rcx, [rsp+0A8h+var_50]
0x1801beb96  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beb9b  nop
0x1801beb9c  lea     rcx, [rsp+0A8h+var_48]
0x1801beba1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801beba6  nop
0x1801beba7  lea     rcx, [rsp+0A8h+pProxy]
0x1801bebaf  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bebb4  nop
0x1801bebb5  lea     rcx, [rsp+0A8h+ppv]
0x1801bebbd  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801bebc2  xor     eax, eax
0x1801bebc4  jmp     short loc_1801BEBCD
0x1801bebc6  mov     eax, dword ptr [rsp+0A8h+pProxy]
0x1801bebcd  lea     r11, [rsp+0A8h+var_28]
0x1801bebd5  mov     rbx, [r11+30h]
0x1801bebd9  mov     rsi, [r11+38h]
0x1801bebdd  mov     rsp, r11
0x1801bebe0  pop     r15
0x1801bebe2  pop     r14
0x1801bebe4  pop     r13
0x1801bebe6  pop     r12
0x1801bebe8  pop     rdi
0x1801bebe9  retn
  ... truncated ...
```
