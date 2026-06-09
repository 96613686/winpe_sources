# CDPComAppControlHandler::LaunchAppService(unsigned __int64,uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,CDPComAppLocation,std::vector<uchar,std::allocator<uchar>> const &,unsigned __int64,char const *,char const *)

- ea: `0x18004c76c`
- end: `0x18004cddf`
- name: `?LaunchAppService@CDPComAppControlHandler@@AEAAJ_KIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CDPComAppLocation@@AEBV?$vector@EV?$allocator@E@std@@@3@0PEBD4@Z`
- size: `1651`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004bc54`

## callees

- `0x180001008`
- `0x180003678`
- `0x180015288`
- `0x1800198bc`
- `0x18001aeb8`
- `0x18001b1f0`
- `0x18001b92c`
- `0x18001c284`
- `0x180028670`
- `0x18002c570`
- `0x180041054`
- `0x18004abac`
- `0x18004b288`
- `0x18004c76c`
- `0x18005c1d0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c9e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c9e9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004c92f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004c92f`

## string_xrefs

- `0x18004ccfd`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd12`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd27`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd3b`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd50`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd65`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd7a`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cd8f`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cda3`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cdb7`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004cdcc`: `..\cdpcomappcontrolhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CDPComAppControlHandler::LaunchAppService(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // r13
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  const size_t *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rbx
  int ActivationFactory; // eax
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, __int64, _QWORD, __int64); // r12
  int v21; // ebx
  __int64 v22; // rdi
  _QWORD *v23; // rax
  __int64 v24; // r15
  int v25; // eax
  int (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rbx
  HRESULT v27; // edx
  __int64 v28; // r8
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rbx
  int v33; // eax
  int v34; // eax
  HSTRING v35; // rdi
  __int64 (__fastcall *v36)(HSTRING, __int64, _QWORD); // rbx
  int v37; // eax
  wil *v38; // rcx
  __int64 v39; // r8
  const char *v40; // r9
  __int64 v41; // r9
  int v42; // edx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  unsigned int v47; // ebx
  int v49; // [rsp+20h] [rbp-118h]
  int v50; // [rsp+20h] [rbp-118h]
  int v51; // [rsp+20h] [rbp-118h]
  unsigned int v52; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v53; // [rsp+48h] [rbp-F0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v55; // [rsp+58h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp-D8h] BYREF
  __int64 v57; // [rsp+68h] [rbp-D0h] BYREF
  int (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-C8h] BYREF
  __int64 v59; // [rsp+78h] [rbp-C0h]
  __int64 v60; // [rsp+80h] [rbp-B8h]
  __int64 v61; // [rsp+88h] [rbp-B0h]
  HSTRING v62; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+98h] [rbp-A0h]
  __int64 v64; // [rsp+A0h] [rbp-98h]
  int v65; // [rsp+A8h] [rbp-90h] BYREF
  char v66; // [rsp+ACh] [rbp-8Ch]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v68; // [rsp+E8h] [rbp-50h]
  const size_t *v69; // [rsp+F0h] [rbp-48h]
  int v70; // [rsp+F8h] [rbp-40h]
  int v71; // [rsp+FCh] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v61 = a2;
  v10 = a1;
  v63 = a1;
  v64 = a2;
  v60 = a8;
  v59 = a9;
  v65 = 0;
  v66 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v65);
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v11) )
  {
    v14 = (const size_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4, v12, v13);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)v14 + v15) );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v14 = &cchOriginalDestLength;
      v16 = 2;
    }
    v69 = v14;
    v70 = v16;
    v71 = 0;
    v49 = 3;
    tlgWriteTransfer_EventWriteTransfer(&dword_180094048, byte_180083889);
  }
  v52 = 0;
  v56 = 0;
  v55 = 0;
  v68 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Contracts.Internal.BackgroundContractOperationFactoryInterop",
    0x56u,
    0x55u);
  v17 = v68;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_faf4b6c0_5261_4cf0_a61c_132bd3ea105e, &v55);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v49);
    v58 = 0;
    v19 = v55;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v55 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    v21 = *(_DWORD *)(a6 + 8) - *(_QWORD *)a6;
    v22 = *(_QWORD *)cdp::UTF8CStrToHSTRING(&v62, v59);
    v23 = (_QWORD *)cdp::UTF8CStrToHSTRING(&string, v60);
    v50 = v21;
    v24 = v61;
    v25 = v20(v19, v61, *v23, v22);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v25,
        v21);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v62);
    v57 = 0;
    v26 = v58;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    v29 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(
            v26,
            v27,
            v28);
    if ( v29 >= 0 )
      v29 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v26)[8])(v26, &v57);
    if ( v29 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v29,
        v50);
    v30 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v57 + 48LL))(v57, &v52);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v30,
        v50);
    v53 = 0;
    v31 = v57;
    v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    v33 = v32(v31, &v53);
    if ( v33 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v33,
        v50);
    if ( v53 )
    {
      string = 0;
      v68 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Internal.RemoteSystems.RemoteSystemInterop",
        0x3Au,
        0x39u);
      v34 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(
              v68,
              (__int64)&string);
      if ( v34 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v34,
          v50);
      v35 = string;
      v36 = *(__int64 (__fastcall **)(HSTRING, __int64, _QWORD))(*(_QWORD *)string + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
      v37 = v36(v35, v53, &v56);
      if ( v37 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v37,
          v50);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  }
  catch ( ... )
  {
    v52 = wil::ResultFromCaughtException(v38);
    v10 = v63;
    v24 = v64;
  }
  try
  {
    if ( *(_QWORD *)(v10 + 16) )
    {
      v41 = 0;
      v55 = 0;
      v42 = 0;
      LODWORD(v53) = 0;
      if ( v56 )
      {
        string = 0;
        v43 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
                &v56,
                (__int64)&string);
        if ( v43 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x114,
            (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
            (const char *)(unsigned int)v43,
            v50);
        v44 = (*(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)string + 24LL))(string, &v55);
        if ( v44 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x115,
            (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
            (const char *)(unsigned int)v44,
            v50);
        v45 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*v56)[7])(
                v56,
                &v53);
        if ( v45 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x116,
            (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
            (const char *)(unsigned int)v45,
            v50);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
        v41 = v55;
        v42 = v53;
      }
      v51 = v42;
      v46 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(v10 + 16) + 24LL))(
              *(_QWORD *)(v10 + 16),
              v24,
              v52,
              v41);
      if ( v46 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v46,
          v51);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x11B, v39, v40);
  }
  v65 = 2;
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v39) )
  {
    LODWORD(v53) = v52;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180094048,
      (__int64)&byte_18008380F);
  }
  v47 = v52;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v65);
  return v47;
}

```

## disassembly

```asm
0x18004c76c  mov     [rsp+arg_10], rbx
0x18004c771  mov     [rsp+arg_18], rsi
0x18004c776  push    rdi
0x18004c777  push    r12
0x18004c779  push    r13
0x18004c77b  push    r14
0x18004c77d  push    r15
0x18004c77f  sub     rsp, 110h
0x18004c786  mov     rax, cs:__security_cookie
0x18004c78d  xor     rax, rsp
0x18004c790  mov     [rsp+138h+var_38], rax
0x18004c798  mov     rbx, r9
0x18004c79b  mov     [rsp+138h+var_B0], rdx
0x18004c7a3  mov     r13, rcx
0x18004c7a6  mov     [rsp+138h+var_A0], rcx
0x18004c7ae  mov     [rsp+138h+var_98], rdx
0x18004c7b6  mov     rdi, [rsp+138h+arg_28]
0x18004c7be  mov     rax, [rsp+138h+arg_38]
0x18004c7c6  mov     [rsp+138h+var_B8], rax
0x18004c7ce  mov     rax, [rsp+138h+arg_40]
0x18004c7d6  mov     [rsp+138h+var_C0], rax
0x18004c7db  xor     esi, esi
0x18004c7dd  mov     [rsp+138h+var_90], esi
0x18004c7e4  mov     [rsp+138h+var_8C], sil
0x18004c7ec  lea     rcx, [rsp+138h+var_90]
0x18004c7f4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18004c7f9  mov     eax, cs:dword_180094048
0x18004c7ff  cmp     eax, 5
0x18004c802  jbe     loc_18004C8D9
0x18004c808  mov     rdx, 400000000000h
0x18004c812  lea     rcx, dword_180094048
0x18004c819  call    _tlgKeywordOn
0x18004c81e  test    al, al
0x18004c820  jz      loc_18004C8D9
0x18004c826  mov     rcx, rbx
0x18004c829  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004c82e  mov     rdx, rax
0x18004c831  cmp     [rsp+138h+var_8C], sil
0x18004c839  jz      short loc_18004C869
0x18004c83b  cmp     [rsp+138h+var_78], esi
0x18004c842  jnz     short loc_18004C85F
0x18004c844  cmp     [rsp+138h+var_74], esi
0x18004c84b  jnz     short loc_18004C85F
0x18004c84d  cmp     [rsp+138h+var_70], esi
0x18004c854  jnz     short loc_18004C85F
0x18004c856  cmp     [rsp+138h+var_6C], esi
0x18004c85d  jz      short loc_18004C869
0x18004c85f  lea     r9, [rsp+138h+var_78]
0x18004c867  jmp     short loc_18004C86C
0x18004c869  mov     r9, rsi
0x18004c86c  test    rdx, rdx
0x18004c86f  jz      short loc_18004C887
0x18004c871  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c875  inc     rax
0x18004c878  cmp     [rdx+rax*2], si
0x18004c87c  jnz     short loc_18004C875
0x18004c87e  lea     eax, ds:2[rax*2]
0x18004c885  jmp     short loc_18004C893
0x18004c887  lea     rdx, cchOriginalDestLength
0x18004c88e  mov     eax, 2
0x18004c893  mov     [rsp+138h+var_48], rdx
0x18004c89b  mov     [rsp+138h+var_40], eax
0x18004c8a2  mov     [rsp+138h+var_3C], esi
0x18004c8a9  lea     rax, [rsp+138h+hstringHeader]
0x18004c8b1  mov     [rsp+138h+var_110], rax
0x18004c8b6  mov     [rsp+138h+var_118], 3; int
0x18004c8be  lea     r8, [rsp+138h+var_88]
0x18004c8c6  lea     rdx, byte_180083889
0x18004c8cd  lea     rcx, dword_180094048
0x18004c8d4  call    _tlgWriteTransfer_EventWriteTransfer
0x18004c8d9  mov     [rsp+138h+var_F8], esi
0x18004c8dd  mov     [rsp+138h+var_D8], rsi
0x18004c8e2  mov     [rsp+138h+var_E0], rsi
0x18004c8e7  mov     [rsp+138h+var_50], rsi
0x18004c8ef  mov     r9d, 55h ; 'U'; unsigned int
0x18004c8f5  lea     r8d, [r9+1]; unsigned int
0x18004c8f9  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Contracts_Internal_BackgroundContractOperationFactoryInterop@@3QBGB; "Windows.ApplicationModel.Contracts.Inte"...
0x18004c900  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x18004c908  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004c90d  nop
0x18004c90e  mov     rbx, [rsp+138h+var_50]
0x18004c916  lea     rcx, [rsp+138h+var_E0]
0x18004c91b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c920  lea     r8, [rsp+138h+var_E0]
0x18004c925  lea     rdx, _GUID_faf4b6c0_5261_4cf0_a61c_132bd3ea105e
0x18004c92c  mov     rcx, rbx
0x18004c92f  call    cs:__imp_RoGetActivationFactory
0x18004c935  mov     rcx, [rsp+138h]; this
0x18004c93d  test    eax, eax
0x18004c93f  js      loc_18004CCFA
0x18004c945  mov     [rsp+138h+var_C8], rsi
0x18004c94a  mov     r14, [rsp+138h+var_E0]
0x18004c94f  mov     rax, [r14]
0x18004c952  mov     r12, [rax+38h]
0x18004c956  lea     rcx, [rsp+138h+var_C8]
0x18004c95b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c960  mov     r15, [rdi]
0x18004c963  mov     ebx, [rdi+8]
0x18004c966  sub     ebx, r15d
0x18004c969  mov     rdx, [rsp+138h+var_C0]
0x18004c96e  lea     rcx, [rsp+138h+var_A8]
0x18004c976  call    ?UTF8CStrToHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBD@Z; cdp::UTF8CStrToHSTRING(char const *)
0x18004c97b  nop
0x18004c97c  mov     rdi, [rax]
0x18004c97f  mov     rdx, [rsp+138h+var_B8]
0x18004c987  lea     rcx, [rsp+138h+string]
0x18004c98c  call    ?UTF8CStrToHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBD@Z; cdp::UTF8CStrToHSTRING(char const *)
0x18004c991  nop
0x18004c992  lea     rcx, [rsp+138h+var_C8]
0x18004c997  mov     [rsp+138h+var_108], rcx
0x18004c99c  mov     [rsp+138h+var_110], r15
0x18004c9a1  mov     [rsp+138h+var_118], ebx; int
0x18004c9a5  mov     r9, rdi
0x18004c9a8  mov     r8, [rax]
0x18004c9ab  mov     r15, [rsp+138h+var_B0]
0x18004c9b3  mov     rdx, r15
0x18004c9b6  mov     rcx, r14
0x18004c9b9  mov     rax, r12
0x18004c9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9c1  mov     rcx, [rsp+138h]; this
0x18004c9c9  test    eax, eax
0x18004c9cb  js      loc_18004CD0F
0x18004c9d1  mov     rcx, [rsp+138h+string]; string
0x18004c9d6  call    cs:__imp_WindowsDeleteString
0x18004c9dc  mov     [rsp+138h+string], rsi
0x18004c9e1  mov     rcx, [rsp+138h+var_A8]; string
0x18004c9e9  call    cs:__imp_WindowsDeleteString
0x18004c9ef  mov     [rsp+138h+var_D0], rsi
0x18004c9f4  mov     rbx, [rsp+138h+var_C8]
0x18004c9f9  lea     rcx, [rsp+138h+var_D0]
0x18004c9fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ca03  mov     rcx, rbx
0x18004ca06  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *> *,tagCOWAIT_FLAGS,void *)
0x18004ca0b  test    eax, eax
0x18004ca0d  js      short loc_18004CA23
0x18004ca0f  mov     rax, [rbx]
0x18004ca12  lea     rdx, [rsp+138h+var_D0]
0x18004ca17  mov     rcx, rbx
0x18004ca1a  mov     rax, [rax+40h]
0x18004ca1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca23  mov     rcx, [rsp+138h]; this
0x18004ca2b  test    eax, eax
0x18004ca2d  js      loc_18004CD24
0x18004ca33  mov     rcx, [rsp+138h+var_D0]
0x18004ca38  mov     rax, [rcx]
0x18004ca3b  lea     rdx, [rsp+138h+var_F8]
0x18004ca40  mov     rax, [rax+30h]
0x18004ca44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca49  mov     rcx, [rsp+138h]; this
0x18004ca51  test    eax, eax
0x18004ca53  js      loc_18004CD38
0x18004ca59  mov     [rsp+138h+var_F0], rsi
0x18004ca5e  mov     rdi, [rsp+138h+var_D0]
0x18004ca63  mov     rax, [rdi]
0x18004ca66  mov     rbx, [rax+38h]
0x18004ca6a  lea     rcx, [rsp+138h+var_F0]
0x18004ca6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ca74  lea     rdx, [rsp+138h+var_F0]
0x18004ca79  mov     rcx, rdi
0x18004ca7c  mov     rax, rbx
0x18004ca7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca84  mov     rcx, [rsp+138h]; this
0x18004ca8c  test    eax, eax
0x18004ca8e  js      loc_18004CD4D
0x18004ca94  cmp     [rsp+138h+var_F0], rsi
0x18004ca99  jz      loc_18004CB33
0x18004ca9f  mov     [rsp+138h+string], rsi
0x18004caa4  mov     [rsp+138h+var_50], rsi
0x18004caac  mov     r9d, 39h ; '9'; unsigned int
0x18004cab2  lea     r8d, [r9+1]; unsigned int
0x18004cab6  lea     rdx, ?RuntimeClass_Windows_System_Internal_RemoteSystems_RemoteSystemInterop@@3QBGB; "Windows.System.Internal.RemoteSystems.R"...
0x18004cabd  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x18004cac5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004caca  nop
0x18004cacb  lea     rdx, [rsp+138h+string]
0x18004cad0  mov     rcx, [rsp+138h+var_50]
0x18004cad8  call    ??$GetActivationFactory@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>)
0x18004cadd  mov     rcx, [rsp+138h]; this
0x18004cae5  test    eax, eax
0x18004cae7  js      loc_18004CD62
0x18004caed  mov     rdi, [rsp+138h+string]
0x18004caf2  mov     rax, [rdi]
0x18004caf5  mov     rbx, [rax+30h]
0x18004caf9  lea     rcx, [rsp+138h+var_D8]
0x18004cafe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb03  lea     r8, [rsp+138h+var_D8]
0x18004cb08  mov     rdx, [rsp+138h+var_F0]
0x18004cb0d  mov     rcx, rdi
0x18004cb10  mov     rax, rbx
0x18004cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb18  mov     rcx, [rsp+138h]; this
0x18004cb20  test    eax, eax
0x18004cb22  js      loc_18004CD77
0x18004cb28  lea     rcx, [rsp+138h+string]
0x18004cb2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb32  nop
0x18004cb33  lea     rcx, [rsp+138h+var_F0]
0x18004cb38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb3d  nop
0x18004cb3e  lea     rcx, [rsp+138h+var_D0]
0x18004cb43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb48  nop
0x18004cb49  lea     rcx, [rsp+138h+var_C8]
0x18004cb4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb53  nop
0x18004cb54  lea     rcx, [rsp+138h+var_E0]
0x18004cb59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb5e  nop
0x18004cb5f  jmp     short loc_18004CB73
0x18004cb61  xor     esi, esi
0x18004cb63  mov     r13, [rsp+138h+var_A0]
0x18004cb6b  mov     r15, [rsp+138h+var_98]
0x18004cb73  cmp     [r13+10h], rsi
0x18004cb77  jz      loc_18004CC52
0x18004cb7d  mov     r9, rsi
0x18004cb80  mov     [rsp+138h+var_E0], rsi
0x18004cb85  mov     edx, esi
0x18004cb87  mov     dword ptr [rsp+138h+var_F0], edx
0x18004cb8b  cmp     [rsp+138h+var_D8], rsi
0x18004cb90  jz      loc_18004CC19
0x18004cb96  mov     [rsp+138h+string], rsi
0x18004cb9b  lea     rdx, [rsp+138h+string]
0x18004cba0  lea     rcx, [rsp+138h+var_D8]
0x18004cba5  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x18004cbaa  mov     rcx, [rsp+138h]; this
0x18004cbb2  test    eax, eax
0x18004cbb4  js      loc_18004CD8C
0x18004cbba  mov     rcx, [rsp+138h+string]
0x18004cbbf  mov     rax, [rcx]
0x18004cbc2  lea     rdx, [rsp+138h+var_E0]
0x18004cbc7  mov     rax, [rax+18h]
0x18004cbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbd0  mov     rcx, [rsp+138h]; this
0x18004cbd8  test    eax, eax
0x18004cbda  js      loc_18004CDA0
0x18004cbe0  mov     rcx, [rsp+138h+var_D8]
0x18004cbe5  mov     rax, [rcx]
0x18004cbe8  lea     rdx, [rsp+138h+var_F0]
0x18004cbed  mov     rax, [rax+38h]
0x18004cbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbf6  mov     rcx, [rsp+138h]; this
0x18004cbfe  test    eax, eax
0x18004cc00  js      loc_18004CDB4
0x18004cc06  lea     rcx, [rsp+138h+string]
0x18004cc0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cc10  mov     r9, [rsp+138h+var_E0]
0x18004cc15  mov     edx, dword ptr [rsp+138h+var_F0]
0x18004cc19  mov     rcx, [r13+10h]
0x18004cc1d  mov     rax, [rcx]
0x18004cc20  mov     r10, [rsp+138h+arg_30]
0x18004cc28  mov     [rsp+138h+var_110], r10
0x18004cc2d  mov     [rsp+138h+var_118], edx; int
0x18004cc31  mov     r8d, [rsp+138h+var_F8]
0x18004cc36  mov     rdx, r15
0x18004cc39  mov     rax, [rax+18h]
0x18004cc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc42  mov     rcx, [rsp+138h]; this
0x18004cc4a  test    eax, eax
0x18004cc4c  js      loc_18004CDC9
0x18004cc52  mov     [rsp+138h+var_90], 2
0x18004cc5d  mov     eax, cs:dword_180094048
0x18004cc63  cmp     eax, 5
0x18004cc66  jbe     short loc_18004CCAF
0x18004cc68  mov     rdx, 400000000000h
0x18004cc72  lea     rcx, dword_180094048
0x18004cc79  call    _tlgKeywordOn
0x18004cc7e  test    al, al
0x18004cc80  jz      short loc_18004CCAF
0x18004cc82  mov     eax, [rsp+138h+var_F8]
0x18004cc86  mov     dword ptr [rsp+138h+var_F0], eax
0x18004cc8a  lea     rax, [rsp+138h+var_F0]
0x18004cc8f  mov     qword ptr [rsp+138h+var_118], rax
0x18004cc94  lea     r8, [rsp+138h+var_88]
0x18004cc9c  lea     rdx, byte_18008380F
0x18004cca3  lea     rcx, dword_180094048
0x18004ccaa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004ccaf  mov     ebx, [rsp+138h+var_F8]
0x18004ccb3  lea     rcx, [rsp+138h+var_D8]
0x18004ccb8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ccbd  nop
0x18004ccbe  lea     rcx, [rsp+138h+var_90]
0x18004ccc6  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004cccb  mov     eax, ebx
0x18004cccd  mov     rcx, [rsp+138h+var_38]
0x18004ccd5  xor     rcx, rsp; StackCookie
0x18004ccd8  call    __security_check_cookie
0x18004ccdd  lea     r11, [rsp+138h+var_28]
0x18004cce5  mov     rbx, [r11+40h]
0x18004cce9  mov     rsi, [r11+48h]
0x18004cced  mov     rsp, r11
0x18004ccf0  pop     r15
0x18004ccf2  pop     r14
0x18004ccf4  pop     r13
0x18004ccf6  pop     r12
0x18004ccf8  pop     rdi
0x18004ccf9  retn
0x18004ccfa  mov     r9d, eax; char *
0x18004ccfd  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004cd04  mov     edx, 0EDh; void *
0x18004cd09  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
