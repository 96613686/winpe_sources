# s_DeviceCredentialRpcInitializeAuthentication

- ea: `0x18009f6a0`
- end: `0x18009fbcc`
- name: `s_DeviceCredentialRpcInitializeAuthentication`
- size: `1324`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x180022e30`
- `0x180029940`
- `0x180053144`
- `0x18005cee0`
- `0x180081438`
- `0x180097a9c`
- `0x18009b548`
- `0x18009b7d4`
- `0x18009b858`
- `0x18009b8b0`
- `0x18009bf64`
- `0x18009c998`
- `0x18009f6a0`
- `0x1800a28e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f855`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fa6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f855`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fa6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f864`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fa79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f864`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fa79`

## string_xrefs

- `0x18009f71f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f82d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f8ed`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009f96e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009fa2f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`
- `0x18009fa90`: `onecore\ds\security\devicecredential\service\lib\devicecredentialrpcimpl.cpp`

## pseudocode

```c
__int64 __fastcall s_DeviceCredentialRpcInitializeAuthentication(
        __int64 a1,
        const unsigned __int16 *a2,
        struct _DeviceCredentialcBufferDesc *a3,
        __int64 a4,
        __int64 a5,
        const WCHAR *a6)
{
  int v9; // ebx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  void *v13; // rdx
  DcaMgr::DeviceCredentialAuthentication *v14; // rcx
  unsigned int v15; // r14d
  void *v16; // rcx
  __int64 v17; // rdx
  wil::details *v18; // rcx
  HANDLE ProcessHeap; // rax
  wil::details *v20; // rax
  wil::details *v21; // rdi
  DcaMgr::DeviceCredentialAuthentication *v22; // rcx
  unsigned int v23; // eax
  void *v24; // rcx
  void *v25; // rdx
  wil::details *v26; // rcx
  unsigned int v27; // r13d
  void *v28; // rcx
  void *v29; // rdx
  wil::details *v30; // rcx
  wil::details *v31; // rcx
  wil::details *v32; // rcx
  unsigned int v33; // esi
  unsigned int v34; // r14d
  void *v35; // rcx
  wil::details *v36; // rcx
  HANDLE v37; // rax
  _DWORD *v38; // rax
  _DWORD *v39; // rdx
  DcaMgr::DeviceCredentialAuthentication *v40; // rcx
  WCHAR *v41; // rax
  wil::details *v42; // rcx
  wil::details *v43; // rcx
  wil::details *v44; // rcx
  wil::details *v45; // rcx
  int v47; // [rsp+20h] [rbp-E0h]
  DcaMgr::DeviceCredentialAuthentication *v48; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v49; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v50; // [rsp+40h] [rbp-C0h] BYREF
  wil::details *v51; // [rsp+48h] [rbp-B8h] BYREF
  wil::details *v52; // [rsp+50h] [rbp-B0h] BYREF
  DcaMgr::DeviceCredentialAuthentication **v53; // [rsp+58h] [rbp-A8h] BYREF
  struct DcaMgr::DeviceCredentialAuthentication *v54; // [rsp+60h] [rbp-A0h] BYREF
  char v55; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *v57; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v58[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v57 = (WCHAR *)a6;
  wil::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v58,
    "InitializeAuthentication");
  v58[0] = &DevCredSvcTraceLoggingProvider::InitializeAuthentication::`vftable';
  DevCredSvcTraceLoggingProvider::InitializeAuthentication::StartActivity((DevCredSvcTraceLoggingProvider::InitializeAuthentication *)v58);
  if ( !a6 )
  {
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)0x80004003LL,
      v47);
    goto LABEL_49;
  }
  *(_QWORD *)a6 = 0;
  v48 = 0;
  v53 = &v48;
  *(_OWORD *)a4 = 0;
  v54 = 0;
  v55 = 1;
  *(_OWORD *)a5 = 0;
  v9 = DcaMgr::DeviceCredentialAuthentication::CreateInstance(a2, a3, &v54);
  wil::details::out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialAuthentication,wistd::default_delete<DcaMgr::DeviceCredentialAuthentication>>>::~out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialAuthentication,wistd::default_delete<DcaMgr::DeviceCredentialAuthentication>>>(&v53);
  if ( v9 >= 0 )
  {
    v54 = 0;
    v55 = 1;
    v15 = *((_DWORD *)v48 + 20);
    v16 = (void *)*((_QWORD *)v48 + 9);
    v49 = 0;
    v53 = &v49;
    v9 = CopyToHeapMemory(v16, v15);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v53);
    if ( v9 < 0 )
    {
      v17 = 213;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
        (const char *)(unsigned int)v9,
        v47);
LABEL_11:
      v18 = v49;
      v49 = 0;
      if ( v18 )
        wil::details::FreeProcessHeap(v18, v13);
      goto LABEL_7;
    }
    ProcessHeap = GetProcessHeap();
    v20 = (wil::details *)HeapAlloc(ProcessHeap, 0, 0x10u);
    v21 = v20;
    if ( !v20 )
    {
      v9 = -2147024882;
      v17 = 217;
      goto LABEL_10;
    }
    *(_DWORD *)v20 = 6;
    *((_DWORD *)v20 + 1) = v15;
    *((_QWORD *)v20 + 1) = v49;
    v22 = v48;
    v53 = &v50;
    v54 = 0;
    v55 = 1;
    *(_DWORD *)a4 = *((_DWORD *)v48 + 4);
    *(_DWORD *)(a4 + 4) = 1;
    *(_QWORD *)(a4 + 8) = v20;
    v23 = *((_DWORD *)v22 + 8);
    v24 = (void *)*((_QWORD *)v22 + 3);
    v56 = v23;
    v50 = 0;
    v9 = CopyToHeapMemory(v24, v23);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v53);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
        (const char *)(unsigned int)v9,
        v47);
      v26 = v50;
      v50 = 0;
      if ( v26 )
        wil::details::FreeProcessHeap(v26, v25);
      wil::details::FreeProcessHeap(v21, v25);
      goto LABEL_11;
    }
    v55 = 1;
    v54 = 0;
    v27 = *((_DWORD *)v48 + 12);
    v28 = (void *)*((_QWORD *)v48 + 5);
    v51 = 0;
    v53 = &v51;
    v9 = CopyToHeapMemory(v28, v27);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v53);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
        (const char *)(unsigned int)v9,
        v47);
LABEL_21:
      v30 = v51;
      v51 = 0;
      if ( v30 )
        wil::details::FreeProcessHeap(v30, v29);
      v31 = v50;
      v50 = 0;
      if ( v31 )
        wil::details::FreeProcessHeap(v31, v29);
      wil::details::FreeProcessHeap(v21, v29);
      v32 = v49;
      v49 = 0;
      if ( v32 )
        wil::details::FreeProcessHeap(v32, v13);
      v14 = v48;
      v48 = 0;
      goto LABEL_47;
    }
    v33 = 2;
    v34 = *((_DWORD *)v48 + 16);
    v35 = (void *)*((_QWORD *)v48 + 7);
    v52 = 0;
    if ( v34 )
    {
      v55 = 1;
      v53 = &v52;
      v54 = 0;
      v9 = CopyToHeapMemory(v35, v34);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v53);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
          (const char *)(unsigned int)v9,
          v47);
LABEL_31:
        v36 = v52;
        v52 = 0;
        if ( v36 )
          wil::details::FreeProcessHeap(v36, v29);
        goto LABEL_21;
      }
      v33 = 3;
    }
    v37 = GetProcessHeap();
    v38 = HeapAlloc(v37, 0, 16LL * v33);
    v9 = 0;
    v39 = v38;
    if ( v38 )
    {
      *v38 = 5;
      v38[1] = v56;
      *((_QWORD *)v38 + 1) = v50;
      v38[4] = 4;
      v38[5] = v27;
      *((_QWORD *)v38 + 3) = v51;
      if ( v34 )
      {
        v38[8] = 9;
        v38[9] = v34;
        *((_QWORD *)v38 + 5) = v52;
      }
      v40 = v48;
      *(_DWORD *)a5 = *((_DWORD *)v48 + 4);
      v41 = v57;
      *(_QWORD *)(a5 + 8) = v39;
      *(_DWORD *)(a5 + 4) = v33;
      v49 = 0;
      *(_QWORD *)v41 = v40;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v48 = 0;
      DevCredSvcTraceLoggingProvider::InitializeAuthentication::Stop(
        (DevCredSvcTraceLoggingProvider::InitializeAuthentication *)v58,
        a2);
      v42 = v52;
      v52 = 0;
      if ( v42 )
        wil::details::FreeProcessHeap(v42, v13);
      v43 = v51;
      v51 = 0;
      if ( v43 )
        wil::details::FreeProcessHeap(v43, v13);
      v44 = v50;
      v50 = 0;
      if ( v44 )
        wil::details::FreeProcessHeap(v44, v13);
      v45 = v49;
      v49 = 0;
      if ( v45 )
        wil::details::FreeProcessHeap(v45, v13);
      v14 = v48;
      v48 = 0;
      goto LABEL_47;
    }
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialrpcimpl.cpp",
      (const char *)0x8007000ELL,
      v47);
    goto LABEL_31;
  }
  v10 = DevCredSvcTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v10 > 2u )
  {
    v56 = v9;
    v57 = (WCHAR *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v10,
      (unsigned __int8 *)byte_18010A40F,
      v11,
      v12,
      (const WCHAR **)&v57,
      (__int64)&v56);
  }
  DevCredSvcTraceLoggingProvider::InitializeAuthentication::Stop(
    (DevCredSvcTraceLoggingProvider::InitializeAuthentication *)v58,
    a2);
LABEL_7:
  v14 = v48;
  v48 = 0;
LABEL_47:
  if ( v14 )
    DcaMgr::DeviceCredentialAuthentication::`scalar deleting destructor'(v14, (unsigned int)v13);
LABEL_49:
  DevCredSvcTraceLoggingProvider::InitializeAuthentication::~InitializeAuthentication((DevCredSvcTraceLoggingProvider::InitializeAuthentication *)v58);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009f6a0  mov     [rsp-8+arg_0], rbx
0x18009f6a5  push    rbp
0x18009f6a6  push    rsi
0x18009f6a7  push    rdi
0x18009f6a8  push    r12
0x18009f6aa  push    r13
0x18009f6ac  push    r14
0x18009f6ae  push    r15
0x18009f6b0  lea     rbp, [rsp-0E0h]
0x18009f6b8  sub     rsp, 1E0h
0x18009f6bf  mov     rax, cs:__security_cookie
0x18009f6c6  xor     rax, rsp
0x18009f6c9  mov     [rbp+110h+var_40], rax
0x18009f6d0  mov     rbx, [rbp+110h+arg_28]
0x18009f6d7  lea     rcx, [rbp+110h+var_190]
0x18009f6db  mov     r12, [rbp+110h+arg_20]
0x18009f6e2  mov     r15, rdx
0x18009f6e5  lea     rdx, aInitializeauth; "InitializeAuthentication"
0x18009f6ec  mov     [rsp+210h+var_198], rbx
0x18009f6f1  mov     rsi, r9
0x18009f6f4  mov     rdi, r8
0x18009f6f7  call    ??0?$ActivityBase@VDevCredSvcTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009f6fc  lea     rax, ??_7InitializeAuthentication@DevCredSvcTraceLoggingProvider@@6B@; const DevCredSvcTraceLoggingProvider::InitializeAuthentication::`vftable'
0x18009f703  lea     rcx, [rbp+110h+var_190]; this
0x18009f707  mov     [rbp+110h+var_190], rax
0x18009f70b  call    ?StartActivity@InitializeAuthentication@DevCredSvcTraceLoggingProvider@@QEAAXXZ; DevCredSvcTraceLoggingProvider::InitializeAuthentication::StartActivity(void)
0x18009f710  xor     r13d, r13d
0x18009f713  test    rbx, rbx
0x18009f716  jnz     short loc_18009F73D
0x18009f718  mov     rcx, [rbp+118h]; this
0x18009f71f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f726  mov     ebx, 80004003h
0x18009f72b  mov     edx, 0B8h; void *
0x18009f730  mov     r9d, ebx; char *
0x18009f733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f738  jmp     loc_18009FB97
0x18009f73d  mov     [rbx], r13
0x18009f740  lea     rax, [rsp+210h+var_1E0]
0x18009f745  xorps   xmm0, xmm0
0x18009f748  mov     [rsp+210h+var_1E0], r13
0x18009f74d  xorps   xmm1, xmm1
0x18009f750  mov     [rsp+210h+var_1B8], rax
0x18009f755  movups  xmmword ptr [rsi], xmm0
0x18009f758  lea     r8, [rsp+210h+var_1B0]; struct DcaMgr::DeviceCredentialAuthentication **
0x18009f75d  mov     [rsp+210h+var_1B0], r13
0x18009f762  mov     rdx, rdi; struct _DeviceCredentialcBufferDesc *
0x18009f765  mov     [rsp+210h+var_1A8], 1
0x18009f76a  mov     rcx, r15; unsigned __int16 *
0x18009f76d  movups  xmmword ptr [r12], xmm1
0x18009f772  call    ?CreateInstance@DeviceCredentialAuthentication@DcaMgr@@SAJPEBGPEAU_DeviceCredentialcBufferDesc@@PEAPEAV12@@Z; DcaMgr::DeviceCredentialAuthentication::CreateInstance(ushort const *,_DeviceCredentialcBufferDesc *,DcaMgr::DeviceCredentialAuthentication * *)
0x18009f777  lea     rcx, [rsp+210h+var_1B8]
0x18009f77c  mov     ebx, eax
0x18009f77e  call    ??1?$out_param_t@V?$unique_ptr@VDeviceCredentialAuthentication@DcaMgr@@U?$default_delete@VDeviceCredentialAuthentication@DcaMgr@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialAuthentication,wistd::default_delete<DcaMgr::DeviceCredentialAuthentication>>>::~out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialAuthentication,wistd::default_delete<DcaMgr::DeviceCredentialAuthentication>>>(void)
0x18009f783  test    ebx, ebx
0x18009f785  jns     short loc_18009F7DE
0x18009f787  call    ?Provider@DevCredSvcTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DevCredSvcTraceLoggingProvider::Provider(void)
0x18009f78c  mov     esi, 2
0x18009f791  mov     ecx, [rax]
0x18009f793  cmp     ecx, esi
0x18009f795  jbe     short loc_18009F7C3
0x18009f797  lea     rcx, [rsp+210h+var_1A0]
0x18009f79c  mov     [rsp+210h+var_1A0], ebx
0x18009f7a0  mov     [rsp+210h+var_1E8], rcx
0x18009f7a5  lea     rdx, byte_18010A40F
0x18009f7ac  lea     rcx, [rsp+210h+var_198]
0x18009f7b1  mov     [rsp+210h+var_198], r15
0x18009f7b6  mov     [rsp+210h+var_1F0], rcx
0x18009f7bb  mov     rcx, rax
0x18009f7be  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18009f7c3  mov     rdx, r15; unsigned __int16 *
0x18009f7c6  lea     rcx, [rbp+110h+var_190]; this
0x18009f7ca  call    ?Stop@InitializeAuthentication@DevCredSvcTraceLoggingProvider@@QEAAXPEBG@Z; DevCredSvcTraceLoggingProvider::InitializeAuthentication::Stop(ushort const *)
0x18009f7cf  mov     rcx, [rsp+210h+var_1E0]
0x18009f7d4  mov     [rsp+210h+var_1E0], r13
0x18009f7d9  jmp     loc_18009FB8D
0x18009f7de  mov     rax, [rsp+210h+var_1E0]
0x18009f7e3  lea     r8, [rsp+210h+var_1B0]
0x18009f7e8  mov     [rsp+210h+var_1B0], r13
0x18009f7ed  mov     [rsp+210h+var_1A8], 1
0x18009f7f2  mov     r14d, [rax+50h]
0x18009f7f6  mov     rcx, [rax+48h]; Source
0x18009f7fa  mov     edx, r14d; SourceSize
0x18009f7fd  lea     rax, [rsp+210h+var_1D8]
0x18009f802  mov     [rsp+210h+var_1D8], r13
0x18009f807  mov     [rsp+210h+var_1B8], rax
0x18009f80c  call    CopyToHeapMemory
0x18009f811  lea     rcx, [rsp+210h+var_1B8]
0x18009f816  mov     ebx, eax
0x18009f818  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f81d  test    ebx, ebx
0x18009f81f  jns     short loc_18009F855
0x18009f821  mov     edx, 0D5h; void *
0x18009f826  mov     rcx, [rbp+118h]; this
0x18009f82d  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f834  mov     r9d, ebx; char *
0x18009f837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f83c  mov     rcx, [rsp+210h+var_1D8]; this
0x18009f841  mov     [rsp+210h+var_1D8], r13
0x18009f846  test    rcx, rcx
0x18009f849  jz      short loc_18009F7CF
0x18009f84b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f850  jmp     loc_18009F7CF
0x18009f855  call    cs:__imp_GetProcessHeap
0x18009f85b  xor     edx, edx; dwFlags
0x18009f85d  mov     rcx, rax; hHeap
0x18009f860  lea     r8d, [rdx+10h]; dwBytes
0x18009f864  call    cs:__imp_HeapAlloc
0x18009f86a  mov     rdi, rax
0x18009f86d  test    rax, rax
0x18009f870  jnz     short loc_18009F87E
0x18009f872  mov     ebx, 8007000Eh
0x18009f877  mov     edx, 0D9h
0x18009f87c  jmp     short loc_18009F826
0x18009f87e  mov     dword ptr [rax], 6
0x18009f884  lea     rdx, [rsp+210h+var_1D0]
0x18009f889  mov     [rax+4], r14d
0x18009f88d  lea     r8, [rsp+210h+var_1B0]
0x18009f892  mov     rax, [rsp+210h+var_1D8]
0x18009f897  mov     [rdi+8], rax
0x18009f89b  mov     rcx, [rsp+210h+var_1E0]
0x18009f8a0  mov     [rsp+210h+var_1B8], rdx
0x18009f8a5  mov     [rsp+210h+var_1B0], r13
0x18009f8aa  mov     [rsp+210h+var_1A8], 1
0x18009f8af  mov     eax, [rcx+10h]
0x18009f8b2  mov     [rsi], eax
0x18009f8b4  mov     dword ptr [rsi+4], 1
0x18009f8bb  mov     [rsi+8], rdi
0x18009f8bf  mov     eax, [rcx+20h]
0x18009f8c2  mov     rcx, [rcx+18h]; Source
0x18009f8c6  mov     edx, eax; SourceSize
0x18009f8c8  mov     [rsp+210h+var_1A0], eax
0x18009f8cc  mov     [rsp+210h+var_1D0], r13
0x18009f8d1  call    CopyToHeapMemory
0x18009f8d6  lea     rcx, [rsp+210h+var_1B8]
0x18009f8db  mov     ebx, eax
0x18009f8dd  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f8e2  test    ebx, ebx
0x18009f8e4  jns     short loc_18009F922
0x18009f8e6  mov     rcx, [rbp+118h]; this
0x18009f8ed  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f8f4  mov     r9d, ebx; char *
0x18009f8f7  mov     edx, 0EAh; void *
0x18009f8fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f901  mov     rcx, [rsp+210h+var_1D0]; this
0x18009f906  mov     [rsp+210h+var_1D0], r13
0x18009f90b  test    rcx, rcx
0x18009f90e  jz      short loc_18009F915
0x18009f910  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f915  mov     rcx, rdi; this
0x18009f918  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f91d  jmp     loc_18009F83C
0x18009f922  mov     rax, [rsp+210h+var_1E0]
0x18009f927  lea     r8, [rsp+210h+var_1B0]
0x18009f92c  xor     esi, esi
0x18009f92e  mov     [rsp+210h+var_1A8], 1
0x18009f933  mov     [rsp+210h+var_1B0], rsi
0x18009f938  mov     r13d, [rax+30h]
0x18009f93c  mov     rcx, [rax+28h]; Source
0x18009f940  mov     edx, r13d; SourceSize
0x18009f943  lea     rax, [rsp+210h+var_1C8]
0x18009f948  mov     [rsp+210h+var_1C8], rsi
0x18009f94d  mov     [rsp+210h+var_1B8], rax
0x18009f952  call    CopyToHeapMemory
0x18009f957  lea     rcx, [rsp+210h+var_1B8]
0x18009f95c  mov     ebx, eax
0x18009f95e  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009f963  test    ebx, ebx
0x18009f965  jns     short loc_18009F9D5
0x18009f967  mov     rcx, [rbp+118h]; this
0x18009f96e  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009f975  mov     r9d, ebx; char *
0x18009f978  mov     edx, 0F3h; void *
0x18009f97d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f982  mov     rcx, [rsp+210h+var_1C8]; this
0x18009f987  mov     [rsp+210h+var_1C8], rsi
0x18009f98c  test    rcx, rcx
0x18009f98f  jz      short loc_18009F996
0x18009f991  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f996  mov     rcx, [rsp+210h+var_1D0]; this
0x18009f99b  mov     [rsp+210h+var_1D0], rsi
0x18009f9a0  test    rcx, rcx
0x18009f9a3  jz      short loc_18009F9AA
0x18009f9a5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f9aa  mov     rcx, rdi; this
0x18009f9ad  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f9b2  mov     rcx, [rsp+210h+var_1D8]; this
0x18009f9b7  mov     [rsp+210h+var_1D8], rsi
0x18009f9bc  test    rcx, rcx
0x18009f9bf  jz      short loc_18009F9C6
0x18009f9c1  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009f9c6  mov     rcx, [rsp+210h+var_1E0]
0x18009f9cb  mov     [rsp+210h+var_1E0], rsi
0x18009f9d0  jmp     loc_18009FB8D
0x18009f9d5  mov     rax, [rsp+210h+var_1E0]
0x18009f9da  mov     esi, 2
0x18009f9df  mov     r14d, [rax+40h]
0x18009f9e3  mov     rcx, [rax+38h]; Source
0x18009f9e7  mov     [rsp+210h+var_1C0], 0
0x18009f9f0  test    r14d, r14d
0x18009f9f3  jz      short loc_18009FA65
0x18009f9f5  lea     rax, [rsp+210h+var_1C0]
0x18009f9fa  mov     [rsp+210h+var_1A8], 1
0x18009f9ff  xor     esi, esi
0x18009fa01  mov     [rsp+210h+var_1B8], rax
0x18009fa06  mov     edx, r14d; SourceSize
0x18009fa09  mov     [rsp+210h+var_1B0], rsi
0x18009fa0e  lea     r8, [rsp+210h+var_1B0]
0x18009fa13  call    CopyToHeapMemory
0x18009fa18  lea     rcx, [rsp+210h+var_1B8]
0x18009fa1d  mov     ebx, eax
0x18009fa1f  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18009fa24  test    ebx, ebx
0x18009fa26  jns     short loc_18009FA60
0x18009fa28  mov     rcx, [rbp+118h]; this
0x18009fa2f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009fa36  mov     r9d, ebx; char *
0x18009fa39  mov     edx, 0FEh; void *
0x18009fa3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fa43  mov     rcx, [rsp+210h+var_1C0]; this
0x18009fa48  mov     [rsp+210h+var_1C0], rsi
0x18009fa4d  test    rcx, rcx
0x18009fa50  jz      loc_18009F982
0x18009fa56  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009fa5b  jmp     loc_18009F982
0x18009fa60  mov     esi, 3
0x18009fa65  mov     ebx, esi
0x18009fa67  shl     rbx, 4
0x18009fa6b  call    cs:__imp_GetProcessHeap
0x18009fa71  mov     r8, rbx; dwBytes
0x18009fa74  xor     edx, edx; dwFlags
0x18009fa76  mov     rcx, rax; hHeap
0x18009fa79  call    cs:__imp_HeapAlloc
0x18009fa7f  xor     ebx, ebx
0x18009fa81  mov     rdx, rax
0x18009fa84  test    rax, rax
0x18009fa87  jnz     short loc_18009FAAD
0x18009fa89  mov     rcx, [rbp+118h]; this
0x18009fa90  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\devicecredential"...
0x18009fa97  mov     ebx, 8007000Eh
0x18009fa9c  mov     edx, 104h; void *
0x18009faa1  mov     r9d, ebx; char *
0x18009faa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009faa9  xor     esi, esi
0x18009faab  jmp     short loc_18009FA43
0x18009faad  mov     dword ptr [rax], 5
0x18009fab3  mov     eax, [rsp+210h+var_1A0]
0x18009fab7  mov     [rdx+4], eax
0x18009faba  mov     rax, [rsp+210h+var_1D0]
0x18009fabf  mov     [rdx+8], rax
0x18009fac3  mov     dword ptr [rdx+10h], 4
0x18009faca  mov     [rdx+14h], r13d
0x18009face  mov     rax, [rsp+210h+var_1C8]
0x18009fad3  mov     [rdx+18h], rax
0x18009fad7  test    r14d, r14d
0x18009fada  jz      short loc_18009FAF0
0x18009fadc  mov     dword ptr [rdx+20h], 9
0x18009fae3  mov     [rdx+24h], r14d
0x18009fae7  mov     rax, [rsp+210h+var_1C0]
0x18009faec  mov     [rdx+28h], rax
0x18009faf0  mov     rcx, [rsp+210h+var_1E0]
0x18009faf5  mov     eax, [rcx+10h]
0x18009faf8  mov     [r12], eax
0x18009fafc  mov     rax, [rsp+210h+var_198]
0x18009fb01  mov     [r12+8], rdx
0x18009fb06  mov     rdx, r15; unsigned __int16 *
0x18009fb09  mov     [r12+4], esi
0x18009fb0e  mov     [rsp+210h+var_1D8], rbx
0x18009fb13  mov     [rax], rcx
0x18009fb16  lea     rcx, [rbp+110h+var_190]; this
0x18009fb1a  mov     [rsp+210h+var_1D0], rbx
0x18009fb1f  mov     [rsp+210h+var_1C8], rbx
0x18009fb24  mov     [rsp+210h+var_1C0], rbx
0x18009fb29  mov     [rsp+210h+var_1E0], rbx
0x18009fb2e  call    ?Stop@InitializeAuthentication@DevCredSvcTraceLoggingProvider@@QEAAXPEBG@Z; DevCredSvcTraceLoggingProvider::InitializeAuthentication::Stop(ushort const *)
0x18009fb33  mov     rcx, [rsp+210h+var_1C0]; this
0x18009fb38  mov     [rsp+210h+var_1C0], rbx
0x18009fb3d  test    rcx, rcx
0x18009fb40  jz      short loc_18009FB47
0x18009fb42  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009fb47  mov     rcx, [rsp+210h+var_1C8]; this
0x18009fb4c  mov     [rsp+210h+var_1C8], rbx
0x18009fb51  test    rcx, rcx
0x18009fb54  jz      short loc_18009FB5B
0x18009fb56  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009fb5b  mov     rcx, [rsp+210h+var_1D0]; this
0x18009fb60  mov     [rsp+210h+var_1D0], rbx
0x18009fb65  test    rcx, rcx
0x18009fb68  jz      short loc_18009FB6F
0x18009fb6a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009fb6f  mov     rcx, [rsp+210h+var_1D8]; this
0x18009fb74  mov     [rsp+210h+var_1D8], rbx
0x18009fb79  test    rcx, rcx
0x18009fb7c  jz      short loc_18009FB83
0x18009fb7e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009fb83  mov     rcx, [rsp+210h+var_1E0]; this
0x18009fb88  mov     [rsp+210h+var_1E0], rbx
0x18009fb8d  test    rcx, rcx
0x18009fb90  jz      short loc_18009FB97
0x18009fb92  call    ??_GDeviceCredentialAuthentication@DcaMgr@@QEAAPEAXI@Z; DcaMgr::DeviceCredentialAuthentication::`scalar deleting destructor'(uint)
0x18009fb97  lea     rcx, [rbp+110h+var_190]; this
  ... truncated ...
```
