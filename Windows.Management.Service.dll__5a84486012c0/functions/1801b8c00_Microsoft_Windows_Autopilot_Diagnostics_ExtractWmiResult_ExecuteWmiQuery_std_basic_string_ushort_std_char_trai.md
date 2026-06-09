# Microsoft::Windows::Autopilot::Diagnostics::ExtractWmiResult::ExecuteWmiQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::com_ptr_t<IEnumWbemClassObject,wil::err_returncode_policy> &)

- ea: `0x1801b8c00`
- end: `0x1801b90df`
- name: `?ExecuteWmiQuery@ExtractWmiResult@Diagnostics@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$com_ptr_t@UIEnumWbemClassObject@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `1247`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b92e8`

## callees

- `0x180067a54`
- `0x18006defc`
- `0x18008019c`
- `0x1800841e8`
- `0x18008939c`
- `0x1801b8c00`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801b8dfe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801b8fef`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801b8dfe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801b8fef`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1801b8c48`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1801b8c48`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b8cb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b8cb3`

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
0x1801b8c00  mov     rax, rsp
0x1801b8c03  mov     [rax+8], rbx
0x1801b8c07  mov     [rax+10h], rsi
0x1801b8c0b  push    rdi
0x1801b8c0c  push    r12
0x1801b8c0e  push    r13
0x1801b8c10  push    r14
0x1801b8c12  push    r15
0x1801b8c14  sub     rsp, 80h
0x1801b8c1b  mov     rsi, rdx
0x1801b8c1e  mov     r15, rcx
0x1801b8c21  xor     r13d, r13d
0x1801b8c24  mov     [rax-68h], r13
0x1801b8c28  mov     [rax-70h], r13d
0x1801b8c2c  mov     [rax-78h], r13
0x1801b8c30  lea     r12d, [r13+3]
0x1801b8c34  mov     [rax-80h], r12d
0x1801b8c38  mov     [rsp+0A8h+dwAuthnLevel], r13d; int
0x1801b8c3d  xor     r9d, r9d; pReserved1
0x1801b8c40  xor     r8d, r8d; asAuthSvc
0x1801b8c43  or      edx, 0FFFFFFFFh; cAuthSvc
0x1801b8c46  xor     ecx, ecx; pSecDesc
0x1801b8c48  call    cs:__imp_CoInitializeSecurity
0x1801b8c4e  mov     ebx, eax
0x1801b8c50  mov     eax, 80000000h
0x1801b8c55  lea     ecx, [rbx+rax]
0x1801b8c58  test    eax, ecx
0x1801b8c5a  jnz     short loc_1801B8C86
0x1801b8c5c  cmp     ebx, 80010119h
0x1801b8c62  jz      short loc_1801B8C86
0x1801b8c64  mov     rcx, [rsp+0A8h]; this
0x1801b8c6c  mov     r9d, ebx; char *
0x1801b8c6f  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b8c76  lea     edx, [r13+4Ch]; void *
0x1801b8c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b8c7f  mov     eax, ebx
0x1801b8c81  jmp     loc_1801B90C1
0x1801b8c86  mov     [rsp+0A8h+ppv], r13
0x1801b8c8e  lea     rax, [rsp+0A8h+ppv]
0x1801b8c96  mov     qword ptr [rsp+0A8h+dwAuthnLevel], rax; int
0x1801b8c9b  lea     r9, IID_IWbemLocator; riid
0x1801b8ca2  mov     edi, 1
0x1801b8ca7  mov     r8d, edi; dwClsContext
0x1801b8caa  xor     edx, edx; pUnkOuter
0x1801b8cac  lea     rcx, CLSID_WbemLocator; rclsid
0x1801b8cb3  call    cs:__imp_CoCreateInstance
0x1801b8cb9  mov     ebx, eax
0x1801b8cbb  test    eax, eax
0x1801b8cbd  jns     short loc_1801B8CEE
0x1801b8cbf  mov     rcx, [rsp+0A8h]; this
0x1801b8cc7  mov     r9d, eax; char *
0x1801b8cca  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b8cd1  lea     edx, [rdi+4Eh]; void *
0x1801b8cd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b8cd9  nop
0x1801b8cda  lea     rcx, [rsp+0A8h+ppv]
0x1801b8ce2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8ce7  mov     eax, ebx
0x1801b8ce9  jmp     loc_1801B90C1
0x1801b8cee  mov     [rsp+0A8h+pProxy], r13
0x1801b8cf6  mov     rbx, [rsp+0A8h+ppv]
0x1801b8cfe  mov     rax, [rbx]
0x1801b8d01  mov     r14, [rax+18h]
0x1801b8d05  mov     [rsp+0A8h+pProxy], r13
0x1801b8d0d  lea     rdx, aRootCimv2; "ROOT\\CIMV2"
0x1801b8d14  lea     rcx, [rsp+0A8h+var_40]
0x1801b8d19  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801b8d1e  nop
0x1801b8d1f  lea     rcx, [rsp+0A8h+pProxy]
0x1801b8d27  mov     [rsp+0A8h+var_68], rcx
0x1801b8d2c  mov     qword ptr [rsp+0A8h+dwCapabilities], r13
0x1801b8d31  mov     [rsp+0A8h+pAuthInfo], r13
0x1801b8d36  mov     [rsp+0A8h+dwImpLevel], r13d
0x1801b8d3b  mov     qword ptr [rsp+0A8h+dwAuthnLevel], r13; int
0x1801b8d40  xor     r9d, r9d
0x1801b8d43  xor     r8d, r8d
0x1801b8d46  mov     rdx, [rax]
0x1801b8d49  mov     rcx, rbx
0x1801b8d4c  mov     rax, r14
0x1801b8d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8d54  mov     ebx, eax
0x1801b8d56  lea     rcx, [rsp+0A8h+var_40]
0x1801b8d5b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b8d60  test    ebx, ebx
0x1801b8d62  jns     short loc_1801B8DA3
0x1801b8d64  mov     rcx, [rsp+0A8h]; this
0x1801b8d6c  mov     r9d, ebx; char *
0x1801b8d6f  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b8d76  mov     edx, 5Ah ; 'Z'; void *
0x1801b8d7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b8d80  nop
0x1801b8d81  lea     rcx, [rsp+0A8h+pProxy]
0x1801b8d89  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8d8e  nop
0x1801b8d8f  lea     rcx, [rsp+0A8h+ppv]
0x1801b8d97  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8d9c  mov     eax, ebx
0x1801b8d9e  jmp     loc_1801B90C1
0x1801b8da3  mov     [rsp+0A8h+var_48], r13
0x1801b8da8  mov     rcx, [rsp+0A8h+pProxy]
0x1801b8db0  mov     rax, [rcx]
0x1801b8db3  mov     [rsp+0A8h+var_48], r13
0x1801b8db8  lea     r8, [rsp+0A8h+var_48]
0x1801b8dbd  lea     rdx, IID_IClientSecurity
0x1801b8dc4  mov     rax, [rax]
0x1801b8dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8dcc  cmp     eax, 80004002h
0x1801b8dd1  jz      loc_1801B8E57
0x1801b8dd7  mov     [rsp+0A8h+dwCapabilities], r13d; dwCapabilities
0x1801b8ddc  mov     [rsp+0A8h+pAuthInfo], r13; pAuthInfo
0x1801b8de1  mov     [rsp+0A8h+dwImpLevel], r12d; dwImpLevel
0x1801b8de6  mov     [rsp+0A8h+dwAuthnLevel], r12d; int
0x1801b8deb  xor     r9d, r9d; pServerPrincName
0x1801b8dee  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1801b8df2  lea     edx, [r9+0Ah]; dwAuthnSvc
0x1801b8df6  mov     rcx, [rsp+0A8h+pProxy]; pProxy
0x1801b8dfe  call    cs:__imp_CoSetProxyBlanket
0x1801b8e04  mov     ebx, eax
0x1801b8e06  test    eax, eax
0x1801b8e08  jns     short loc_1801B8E54
0x1801b8e0a  mov     rcx, [rsp+0A8h]; this
0x1801b8e12  mov     r9d, eax; char *
0x1801b8e15  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b8e1c  mov     edx, 74h ; 't'; void *
0x1801b8e21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b8e26  nop
0x1801b8e27  lea     rcx, [rsp+0A8h+var_48]
0x1801b8e2c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8e31  nop
0x1801b8e32  lea     rcx, [rsp+0A8h+pProxy]
0x1801b8e3a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8e3f  nop
0x1801b8e40  lea     rcx, [rsp+0A8h+ppv]
0x1801b8e48  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8e4d  mov     eax, ebx
0x1801b8e4f  jmp     loc_1801B90C1
0x1801b8e54  mov     dil, r13b
0x1801b8e57  mov     [rsp+0A8h+var_50], r13
0x1801b8e5c  mov     rbx, [rsp+0A8h+pProxy]
0x1801b8e64  mov     rax, [rbx]
0x1801b8e67  mov     r12, [rax+0A0h]
0x1801b8e6e  mov     [rsp+0A8h+var_50], r13
0x1801b8e73  mov     rcx, r15
0x1801b8e76  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b8e7b  mov     rdx, rax
0x1801b8e7e  lea     rcx, [rsp+0A8h+var_38]
0x1801b8e83  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801b8e88  nop
0x1801b8e89  mov     r14, [rax]
0x1801b8e8c  lea     rdx, aWql; "WQL"
0x1801b8e93  lea     rcx, [rsp+0A8h+var_40]
0x1801b8e98  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801b8e9d  nop
0x1801b8e9e  lea     rcx, [rsp+0A8h+var_50]
0x1801b8ea3  mov     qword ptr [rsp+0A8h+dwImpLevel], rcx
0x1801b8ea8  mov     qword ptr [rsp+0A8h+dwAuthnLevel], r13; int
0x1801b8ead  mov     r9d, 30h ; '0'
0x1801b8eb3  mov     r8, r14
0x1801b8eb6  mov     rdx, [rax]
0x1801b8eb9  mov     rcx, rbx
0x1801b8ebc  mov     rax, r12
0x1801b8ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8ec4  mov     ebx, eax
0x1801b8ec6  lea     rcx, [rsp+0A8h+var_40]
0x1801b8ecb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b8ed0  nop
0x1801b8ed1  lea     rcx, [rsp+0A8h+var_38]
0x1801b8ed6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b8edb  test    ebx, ebx
0x1801b8edd  jns     short loc_1801B8F34
0x1801b8edf  mov     rcx, [rsp+0A8h]; this
0x1801b8ee7  mov     r9d, ebx; char *
0x1801b8eea  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b8ef1  mov     edx, 7Dh ; '}'; void *
0x1801b8ef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b8efb  nop
0x1801b8efc  lea     rcx, [rsp+0A8h+var_50]
0x1801b8f01  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f06  nop
0x1801b8f07  lea     rcx, [rsp+0A8h+var_48]
0x1801b8f0c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f11  nop
0x1801b8f12  lea     rcx, [rsp+0A8h+pProxy]
0x1801b8f1a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f1f  nop
0x1801b8f20  lea     rcx, [rsp+0A8h+ppv]
0x1801b8f28  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f2d  mov     eax, ebx
0x1801b8f2f  jmp     loc_1801B90C1
0x1801b8f34  mov     [rsp+0A8h+var_58], r13
0x1801b8f39  mov     rcx, [rsp+0A8h+var_50]
0x1801b8f3e  mov     rax, [rcx]
0x1801b8f41  mov     [rsp+0A8h+var_58], r13
0x1801b8f46  lea     r8, [rsp+0A8h+var_58]
0x1801b8f4b  lea     rdx, IID_IEnumWbemClassObject
0x1801b8f52  mov     rax, [rax]
0x1801b8f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8f5a  mov     ebx, eax
0x1801b8f5c  test    eax, eax
0x1801b8f5e  jns     short loc_1801B8FC0
0x1801b8f60  mov     rcx, [rsp+0A8h]; this
0x1801b8f68  mov     r9d, eax; char *
0x1801b8f6b  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b8f72  mov     edx, 80h; void *
0x1801b8f77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b8f7c  nop
0x1801b8f7d  lea     rcx, [rsp+0A8h+var_58]
0x1801b8f82  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f87  nop
0x1801b8f88  lea     rcx, [rsp+0A8h+var_50]
0x1801b8f8d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f92  nop
0x1801b8f93  lea     rcx, [rsp+0A8h+var_48]
0x1801b8f98  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8f9d  nop
0x1801b8f9e  lea     rcx, [rsp+0A8h+pProxy]
0x1801b8fa6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8fab  nop
0x1801b8fac  lea     rcx, [rsp+0A8h+ppv]
0x1801b8fb4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b8fb9  mov     eax, ebx
0x1801b8fbb  jmp     loc_1801B90C1
0x1801b8fc0  test    dil, dil
0x1801b8fc3  jnz     loc_1801B9058
0x1801b8fc9  mov     [rsp+0A8h+dwCapabilities], r13d; dwCapabilities
0x1801b8fce  mov     [rsp+0A8h+pAuthInfo], r13; pAuthInfo
0x1801b8fd3  mov     eax, 3
0x1801b8fd8  mov     [rsp+0A8h+dwImpLevel], eax; dwImpLevel
0x1801b8fdc  mov     [rsp+0A8h+dwAuthnLevel], eax; int
0x1801b8fe0  xor     r9d, r9d; pServerPrincName
0x1801b8fe3  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1801b8fe7  lea     edx, [rax+7]; dwAuthnSvc
0x1801b8fea  mov     rcx, [rsp+0A8h+var_58]; pProxy
0x1801b8fef  call    cs:__imp_CoSetProxyBlanket
0x1801b8ff5  mov     ebx, eax
0x1801b8ff7  test    eax, eax
0x1801b8ff9  jns     short loc_1801B9058
0x1801b8ffb  mov     rcx, [rsp+0A8h]; this
0x1801b9003  mov     r9d, eax; char *
0x1801b9006  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b900d  mov     edx, 8Dh; void *
0x1801b9012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b9017  nop
0x1801b9018  lea     rcx, [rsp+0A8h+var_58]
0x1801b901d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b9022  nop
0x1801b9023  lea     rcx, [rsp+0A8h+var_50]
0x1801b9028  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b902d  nop
0x1801b902e  lea     rcx, [rsp+0A8h+var_48]
0x1801b9033  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b9038  nop
0x1801b9039  lea     rcx, [rsp+0A8h+pProxy]
0x1801b9041  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b9046  nop
0x1801b9047  lea     rcx, [rsp+0A8h+ppv]
0x1801b904f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b9054  mov     eax, ebx
0x1801b9056  jmp     short loc_1801B90C1
0x1801b9058  mov     rax, [rsp+0A8h+var_58]
0x1801b905d  mov     [rsp+0A8h+var_58], r13
0x1801b9062  mov     rcx, [rsi]
0x1801b9065  mov     [rsi], rax
0x1801b9068  test    rcx, rcx
0x1801b906b  jz      short loc_1801B907A
0x1801b906d  mov     rax, [rcx]
0x1801b9070  mov     rax, [rax+10h]
0x1801b9074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9079  nop
0x1801b907a  lea     rcx, [rsp+0A8h+var_58]
0x1801b907f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b9084  nop
0x1801b9085  lea     rcx, [rsp+0A8h+var_50]
0x1801b908a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b908f  nop
0x1801b9090  lea     rcx, [rsp+0A8h+var_48]
0x1801b9095  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b909a  nop
0x1801b909b  lea     rcx, [rsp+0A8h+pProxy]
0x1801b90a3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b90a8  nop
0x1801b90a9  lea     rcx, [rsp+0A8h+ppv]
0x1801b90b1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801b90b6  xor     eax, eax
0x1801b90b8  jmp     short loc_1801B90C1
0x1801b90ba  mov     eax, dword ptr [rsp+0A8h+pProxy]
0x1801b90c1  lea     r11, [rsp+0A8h+var_28]
0x1801b90c9  mov     rbx, [r11+30h]
0x1801b90cd  mov     rsi, [r11+38h]
0x1801b90d1  mov     rsp, r11
0x1801b90d4  pop     r15
0x1801b90d6  pop     r14
0x1801b90d8  pop     r13
0x1801b90da  pop     r12
0x1801b90dc  pop     rdi
0x1801b90dd  retn
```
