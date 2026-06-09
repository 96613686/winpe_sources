# GidsHandlerRpcBind

- ea: `0x18001672c`
- end: `0x180016b2b`
- name: `GidsHandlerRpcBind`
- size: `1023`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016b34`
- `0x1800315b8`
- `0x1800316ec`
- `0x1800317f4`

## callees

- `0x18000139c`
- `0x1800013c8`
- `0x18000142c`
- `0x180014e44`
- `0x180015044`
- `0x18001672c`
- `0x18001be80`
- `0x1800319c0`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001679a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001679a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001686e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ae5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016afb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001686e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ae5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016afb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800168a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800168a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001680b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001680b`
- `RPCRT4!RpcBindingCreateW` at `0x1800169d2`
- `RPCRT4!RpcBindingCreateW` at `0x1800169d2`
- `RPCRT4!RpcBindingBind` at `0x180016a35`
- `RPCRT4!RpcBindingBind` at `0x180016a35`

## string_xrefs

- `0x18001678c`: `System\CurrentControlSet\Services\NgcCtnrSvc\Parameters`
- `0x180016785`: `VscHandlerPath`
- `0x1800167b9`: `ds\security\ngc\ctnrsvc\client\gids\ngcgidshandlerclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GidsHandlerRpcBind(_QWORD *a1)
{
  unsigned int ValueW; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  __int64 v5; // rdx
  int LastError; // ebx
  BOOL v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  HLOCAL v12; // rcx
  BOOL v13; // ebx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  HLOCAL v17; // rcx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned int i; // esi
  RPC_STATUS v22; // eax
  __int64 v23; // rbx
  unsigned int v24; // edi
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // ebx
  int v29; // eax
  RPC_BINDING_HANDLE v30; // rax
  HLOCAL v31; // rcx
  bool v32; // zf
  HLOCAL v33; // rcx
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  void **v38; // [rsp+58h] [rbp-A8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD v41; // [rsp+6Ch] [rbp-94h] BYREF
  HLOCAL *p_hMem; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  char v44; // [rsp+80h] [rbp-80h]
  _DWORD v45[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+94h] [rbp-6Ch]
  int v47; // [rsp+9Ch] [rbp-64h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  HLOCAL v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  HLOCAL v51; // [rsp+B8h] [rbp-48h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+C0h] [rbp-40h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+E8h] [rbp-18h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v41 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\NgcCtnrSvc\\Parameters",
             L"VscHandlerPath",
             2u,
             &v41,
             0,
             &pcbData);
  if ( ValueW )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, v3, v4, (const char *)ValueW, pdwType);
    v5 = 84;
LABEL_3:
    LastError = -2147024846;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"ds\\security\\ngc\\ctnrsvc\\client\\gids\\ngcgidshandlerclient.cpp",
      (const char *)0x80070032LL,
      pdwType);
    return (unsigned int)LastError;
  }
  if ( !pcbData )
  {
    v5 = 89;
    goto LABEL_3;
  }
  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v44 = 1;
  v8 = ConvertStringSidToSidW(L"LS", &Sid);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v8 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_18004B048 > 2 )
    {
      LODWORD(v37) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&dword_180042CBC,
        v10,
        v11,
        (__int64)&v37);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
    v12 = hMem;
    hMem = 0;
    if ( v12 )
      LocalFree(v12);
    return (unsigned int)LastError;
  }
  v36 = 0;
  p_hMem = &v36;
  Sid = 0;
  v44 = 1;
  v13 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GR;;;S-1-5-80-2381253463-2694003897-3435975801-3559003598-683041300)",
          1u,
          &Sid,
          0);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v13 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_18004B048 > 2 )
    {
      LODWORD(v37) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&unk_180042C70,
        v15,
        v16,
        (__int64)&v37);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_19:
    v17 = v36;
    v36 = 0;
    if ( v17 )
      LocalFree(v17);
    goto LABEL_12;
  }
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  v45[0] = 5;
  v45[1] = 17;
  v45[2] = 1;
  v46 = 2;
  v47 = 0;
  v48 = 0;
  v49 = hMem;
  v50 = 1;
  v51 = v36;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v45;
  *(_QWORD *)&Options.Version = 1;
  *(_QWORD *)&Options.ComTimeout = 5;
  v38 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  Binding = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v38);
  LastError = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( LastError )
  {
    if ( (unsigned int)dword_18004B048 > 2 )
    {
      LODWORD(v37) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)&byte_180042C47,
        v19,
        v20,
        (__int64)&v37);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v38 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v38);
    goto LABEL_19;
  }
  for ( i = 0; i < 0x14; ++i )
  {
    v22 = RpcBindingBind(0, Binding, qword_18003AA30);
    v23 = v22;
    if ( v22 > 0 )
    {
      v24 = (unsigned __int16)v22 | 0x80070000;
    }
    else
    {
      v24 = v22;
      if ( !v22 )
        break;
    }
    if ( (unsigned int)dword_18004B048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x200000000000LL) )
    {
      v37 = v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v25,
        (unsigned int)byte_180042C1D,
        v26,
        v27,
        (__int64)&v37);
    }
    v28 = v23 + 2147023179;
    if ( v28 > 0xA )
      goto LABEL_39;
    v29 = 1601;
    if ( !_bittest(&v29, v28) )
      goto LABEL_39;
  }
  v30 = Binding;
  Binding = 0;
  *a1 = v30;
LABEL_39:
  v38 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v38);
  v31 = v36;
  v32 = v36 == 0;
  v36 = 0;
  if ( !v32 )
    LocalFree(v31);
  v33 = hMem;
  v32 = hMem == 0;
  hMem = 0;
  if ( !v32 )
    LocalFree(v33);
  return v24;
}

```

## disassembly

```asm
0x18001672c  mov     [rsp-8+arg_8], rbx
0x180016731  mov     [rsp-8+arg_10], rsi
0x180016736  push    rbp
0x180016737  push    rdi
0x180016738  push    r13
0x18001673a  push    r14
0x18001673c  push    r15
0x18001673e  lea     rbp, [rsp-40h]
0x180016743  sub     rsp, 140h
0x18001674a  mov     rax, cs:__security_cookie
0x180016751  xor     rax, rsp
0x180016754  mov     [rbp+60h+var_30], rax
0x180016758  mov     r14, rcx
0x18001675b  xor     r15d, r15d
0x18001675e  mov     [rsp+160h+var_F4], r15d
0x180016763  mov     [rsp+160h+var_F8], r15d
0x180016768  lea     rax, [rsp+160h+var_F8]
0x18001676d  mov     [rsp+160h+pcbData], rax; pcbData
0x180016772  mov     [rsp+160h+pvData], r15; pvData
0x180016777  lea     rax, [rsp+160h+var_F4]
0x18001677c  mov     [rsp+160h+pdwType], rax; int
0x180016781  lea     r9d, [r15+2]; dwFlags
0x180016785  lea     r8, aVschandlerpath; "VscHandlerPath"
0x18001678c  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ng"...
0x180016793  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001679a  call    cs:__imp_RegGetValueW
0x1800167a0  mov     rcx, [rbp+68h]; this
0x1800167a4  test    eax, eax
0x1800167a6  jz      short loc_1800167D3
0x1800167a8  mov     r9d, eax; char *
0x1800167ab  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800167b0  lea     edx, [r15+54h]; void *
0x1800167b4  mov     ebx, 80070032h
0x1800167b9  lea     r8, aDsSecurityNgcC; "ds\\security\\ngc\\ctnrsvc\\client\\gid"...
0x1800167c0  mov     r9d, ebx; char *
0x1800167c3  mov     rcx, [rbp+68h]; this
0x1800167c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167cc  mov     eax, ebx
0x1800167ce  jmp     loc_180016B03
0x1800167d3  cmp     [rsp+160h+var_F8], r15d
0x1800167d8  jnz     short loc_1800167E1
0x1800167da  mov     edx, 59h ; 'Y'
0x1800167df  jmp     short loc_1800167B4
0x1800167e1  mov     [rsp+160h+hMem], r15
0x1800167e6  lea     rax, [rsp+160h+hMem]
0x1800167eb  mov     [rsp+160h+var_F0], rax
0x1800167f0  mov     [rsp+160h+Sid], r15
0x1800167f5  mov     r13d, 1
0x1800167fb  mov     [rbp+60h+var_E0], r13b
0x1800167ff  lea     rdx, [rsp+160h+Sid]; Sid
0x180016804  lea     rcx, StringSid; "LS"
0x18001680b  call    cs:__imp_ConvertStringSidToSidW
0x180016811  mov     ebx, eax
0x180016813  lea     rcx, [rsp+160h+var_F0]
0x180016818  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001681d  test    ebx, ebx
0x18001681f  jnz     short loc_180016879
0x180016821  call    cs:__imp_GetLastError
0x180016827  mov     ebx, eax
0x180016829  mov     eax, cs:dword_18004B048
0x18001682f  cmp     eax, 2
0x180016832  jbe     short loc_18001684E
0x180016834  mov     dword ptr [rsp+160h+var_110], ebx
0x180016838  lea     rax, [rsp+160h+var_110]
0x18001683d  mov     [rsp+160h+pdwType], rax
0x180016842  lea     rdx, dword_180042CBC
0x180016849  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001684e  test    ebx, ebx
0x180016850  jle     short loc_18001685B
0x180016852  movzx   ebx, bx
0x180016855  or      ebx, 80070000h
0x18001685b  mov     rcx, [rsp+160h+hMem]; hMem
0x180016860  mov     [rsp+160h+hMem], r15
0x180016865  test    rcx, rcx
0x180016868  jz      loc_1800167CC
0x18001686e  call    cs:__imp_LocalFree
0x180016874  jmp     loc_1800167CC
0x180016879  mov     [rsp+160h+var_118], r15
0x18001687e  lea     rax, [rsp+160h+var_118]
0x180016883  mov     [rsp+160h+var_F0], rax
0x180016888  mov     [rsp+160h+Sid], r15
0x18001688d  mov     [rbp+60h+var_E0], r13b
0x180016891  xor     r9d, r9d; SecurityDescriptorSize
0x180016894  lea     r8, [rsp+160h+Sid]; SecurityDescriptor
0x180016899  mov     edx, r13d; StringSDRevision
0x18001689c  lea     rcx, aDAGrS158023812; "D:(A;;GR;;;S-1-5-80-2381253463-26940038"...
0x1800168a3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800168a9  mov     ebx, eax
0x1800168ab  lea     rcx, [rsp+160h+var_F0]
0x1800168b0  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800168b5  test    ebx, ebx
0x1800168b7  jnz     short loc_180016911
0x1800168b9  call    cs:__imp_GetLastError
0x1800168bf  mov     ebx, eax
0x1800168c1  mov     eax, cs:dword_18004B048
0x1800168c7  cmp     eax, 2
0x1800168ca  jbe     short loc_1800168E6
0x1800168cc  mov     dword ptr [rsp+160h+var_110], ebx
0x1800168d0  lea     rax, [rsp+160h+var_110]
0x1800168d5  mov     [rsp+160h+pdwType], rax
0x1800168da  lea     rdx, unk_180042C70
0x1800168e1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800168e6  test    ebx, ebx
0x1800168e8  jle     short loc_1800168F3
0x1800168ea  movzx   ebx, bx
0x1800168ed  or      ebx, 80070000h
0x1800168f3  mov     rcx, [rsp+160h+var_118]; hMem
0x1800168f8  mov     [rsp+160h+var_118], r15
0x1800168fd  test    rcx, rcx
0x180016900  jz      loc_18001685B
0x180016906  call    cs:__imp_LocalFree
0x18001690c  jmp     loc_18001685B
0x180016911  mov     qword ptr [rbp+60h+Template.Version], 1
0x180016919  mov     qword ptr [rbp+60h+Template.ProtocolSequence], 3
0x180016921  xorps   xmm0, xmm0
0x180016924  movdqu  xmmword ptr [rbp+60h+Template.NetworkAddress], xmm0
0x180016929  mov     qword ptr [rbp+60h+Template.u1], r15
0x18001692d  mov     [rbp+60h+Template.ObjectUuid.Data1], r15d
0x180016931  xor     eax, eax
0x180016933  mov     qword ptr [rbp+60h+Template.ObjectUuid.Data2], rax
0x180016937  mov     dword ptr [rbp+60h+Template.ObjectUuid.Data4+4], eax
0x18001693a  lea     ecx, [rax+5]
0x18001693d  mov     [rbp+60h+var_D8], ecx
0x180016940  mov     [rbp+60h+var_D4], 11h
0x180016947  mov     [rbp+60h+var_D0], r13d
0x18001694b  mov     [rbp+60h+var_CC], 2
0x180016953  mov     [rbp+60h+var_C4], eax
0x180016956  mov     [rbp+60h+var_C0], r15
0x18001695a  mov     rax, [rsp+160h+hMem]
0x18001695f  mov     [rbp+60h+var_B8], rax
0x180016963  mov     [rbp+60h+var_B0], 1
0x18001696b  mov     rax, [rsp+160h+var_118]
0x180016970  mov     [rbp+60h+var_A8], rax
0x180016974  mov     qword ptr [rbp+60h+Security.Version], 1
0x18001697c  mov     [rbp+60h+Security.ServerPrincName], r15
0x180016980  mov     [rbp+60h+Security.AuthnLevel], 6
0x180016987  mov     [rbp+60h+Security.AuthnSvc], 0Ah
0x18001698e  mov     [rbp+60h+Security.AuthIdentity], r15
0x180016992  lea     rax, [rbp+60h+var_D8]
0x180016996  mov     [rbp+60h+Security.SecurityQos], rax
0x18001699a  mov     qword ptr [rbp+60h+Options.Version], 1
0x1800169a2  mov     qword ptr [rbp+60h+Options.ComTimeout], rcx
0x1800169a6  lea     rdi, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x1800169ad  mov     [rsp+160h+var_108], rdi
0x1800169b2  mov     [rsp+160h+Binding], r15
0x1800169b7  lea     rcx, [rsp+160h+var_108]
0x1800169bc  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800169c1  lea     r9, [rsp+160h+Binding]; Binding
0x1800169c6  lea     r8, [rbp+60h+Options]; Options
0x1800169ca  lea     rdx, [rbp+60h+Security]; Security
0x1800169ce  lea     rcx, [rbp+60h+Template]; Template
0x1800169d2  call    cs:__imp_RpcBindingCreateW
0x1800169d8  mov     ebx, eax
0x1800169da  test    eax, eax
0x1800169dc  jz      short loc_180016A24
0x1800169de  mov     eax, cs:dword_18004B048
0x1800169e4  cmp     eax, 2
0x1800169e7  jbe     short loc_180016A03
0x1800169e9  mov     dword ptr [rsp+160h+var_110], ebx
0x1800169ed  lea     rax, [rsp+160h+var_110]
0x1800169f2  mov     [rsp+160h+pdwType], rax
0x1800169f7  lea     rdx, byte_180042C47
0x1800169fe  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180016a03  test    ebx, ebx
0x180016a05  jle     short loc_180016A10
0x180016a07  movzx   ebx, bx
0x180016a0a  or      ebx, 80070000h
0x180016a10  mov     [rsp+160h+var_108], rdi
0x180016a15  lea     rcx, [rsp+160h+var_108]
0x180016a1a  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x180016a1f  jmp     loc_1800168F3
0x180016a24  mov     esi, r15d
0x180016a27  lea     r8, qword_18003AA30; IfSpec
0x180016a2e  mov     rdx, [rsp+160h+Binding]; Binding
0x180016a33  xor     ecx, ecx; pAsync
0x180016a35  call    cs:__imp_RpcBindingBind
0x180016a3b  movsxd  rbx, eax
0x180016a3e  test    eax, eax
0x180016a40  jg      short loc_180016A48
0x180016a42  mov     edi, ebx
0x180016a44  jz      short loc_180016AB2
0x180016a46  jmp     short loc_180016A51
0x180016a48  movzx   edi, bx
0x180016a4b  or      edi, 80070000h
0x180016a51  mov     eax, cs:dword_18004B048
0x180016a57  cmp     eax, 2
0x180016a5a  jbe     short loc_180016A91
0x180016a5c  mov     rdx, 200000000000h
0x180016a66  lea     rcx, dword_18004B048
0x180016a6d  call    _tlgKeywordOn
0x180016a72  test    al, al
0x180016a74  jz      short loc_180016A91
0x180016a76  mov     [rsp+160h+var_110], rbx
0x180016a7b  lea     rax, [rsp+160h+var_110]
0x180016a80  mov     [rsp+160h+pdwType], rax
0x180016a85  lea     rdx, byte_180042C1D
0x180016a8c  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180016a91  add     ebx, 7FF8F94Bh
0x180016a97  cmp     ebx, 0Ah
0x180016a9a  ja      short loc_180016ABF
0x180016a9c  mov     eax, 641h
0x180016aa1  bt      eax, ebx
0x180016aa4  jnb     short loc_180016ABF
0x180016aa6  add     esi, r13d
0x180016aa9  cmp     esi, 14h
0x180016aac  jb      loc_180016A27
0x180016ab2  mov     rax, [rsp+160h+Binding]
0x180016ab7  mov     [rsp+160h+Binding], r15
0x180016abc  mov     [r14], rax
0x180016abf  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x180016ac6  mov     [rsp+160h+var_108], rax
0x180016acb  lea     rcx, [rsp+160h+var_108]
0x180016ad0  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x180016ad5  nop
0x180016ad6  mov     rcx, [rsp+160h+var_118]; hMem
0x180016adb  test    rcx, rcx
0x180016ade  mov     [rsp+160h+var_118], r15
0x180016ae3  jz      short loc_180016AEC
0x180016ae5  call    cs:__imp_LocalFree
0x180016aeb  nop
0x180016aec  mov     rcx, [rsp+160h+hMem]; hMem
0x180016af1  test    rcx, rcx
0x180016af4  mov     [rsp+160h+hMem], r15
0x180016af9  jz      short loc_180016B01
0x180016afb  call    cs:__imp_LocalFree
0x180016b01  mov     eax, edi
0x180016b03  mov     rcx, [rbp+60h+var_30]
0x180016b07  xor     rcx, rsp; StackCookie
0x180016b0a  call    __security_check_cookie
0x180016b0f  lea     r11, [rsp+160h+var_20]
0x180016b17  mov     rbx, [r11+38h]
0x180016b1b  mov     rsi, [r11+40h]
0x180016b1f  mov     rsp, r11
0x180016b22  pop     r15
0x180016b24  pop     r14
0x180016b26  pop     r13
0x180016b28  pop     rdi
0x180016b29  pop     rbp
0x180016b2a  retn
```
