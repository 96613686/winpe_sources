# CDPComAppControlHandler::LaunchUriInternal(unsigned __int64,uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,CDPComAppLocation,std::vector<uchar,std::allocator<uchar>> const &,unsigned __int64)

- ea: `0x18004cde8`
- end: `0x18004d35c`
- name: `?LaunchUriInternal@CDPComAppControlHandler@@AEAAJ_KIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CDPComAppLocation@@AEBV?$vector@EV?$allocator@E@std@@@3@0@Z`
- size: `1396`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
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
- `0x180028854`
- `0x18002b5b4`
- `0x18002c570`
- `0x18003fe90`
- `0x1800409b4`
- `0x180041054`
- `0x18004abac`
- `0x18004cde8`
- `0x18004e2f0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004cf6f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004cf6f`

## string_xrefs

- `0x18004d2b8`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d2cd`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d2e2`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d2f7`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d30c`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d320`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d334`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d349`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004d021`: `LaunchUriStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall CDPComAppControlHandler::LaunchUriInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _QWORD *a6)
{
  __int64 v6; // r13
  __int64 v7; // r8
  unsigned int v8; // r12d
  HSTRING v9; // rbx
  int ActivationFactory; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r14
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, _QWORD); // rsi
  __int64 v15; // rdi
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, _QWORD); // rbx
  _QWORD *UnderlyingProperties; // rax
  int v23; // eax
  wil *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rbx
  __int64 v27; // r9
  unsigned int v28; // edx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v34; // [rsp+20h] [rbp-128h]
  int v35; // [rsp+20h] [rbp-128h]
  int v36; // [rsp+20h] [rbp-128h]
  unsigned int v37; // [rsp+40h] [rbp-108h] BYREF
  __int64 v38; // [rsp+48h] [rbp-100h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-F8h]
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-F0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-D8h] BYREF
  _QWORD *v44; // [rsp+78h] [rbp-D0h]
  __int64 v45; // [rsp+80h] [rbp-C8h]
  __int64 v46; // [rsp+88h] [rbp-C0h]
  _BYTE v47[24]; // [rsp+90h] [rbp-B8h] BYREF
  int v48; // [rsp+A8h] [rbp-A0h] BYREF
  char v49; // [rsp+ACh] [rbp-9Ch]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-78h] BYREF
  HSTRING v51; // [rsp+E8h] [rbp-60h]
  __int64 *v52; // [rsp+F0h] [rbp-58h]
  __int64 v53; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v42 = a4;
  v41 = a2;
  v6 = a1;
  v45 = a1;
  v46 = a2;
  v44 = a6;
  v48 = 0;
  v49 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v48);
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v7) )
  {
    v38 = 0x1000000;
    v52 = &v38;
    v53 = 8;
    v34 = 3;
    tlgWriteTransfer_EventWriteTransfer(&dword_180094048, qword_180083838);
  }
  v8 = 0;
  v39 = 0;
  v40 = 0;
  v43 = 0;
  v51 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.Launch.RemoteLauncherInterop",
    0x35u,
    0x34u);
  v9 = v51;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_461643b1_59e4_4e00_8e75_d56769cae169, &v43);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v34);
    v37 = 0;
    v13 = v43;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 56LL);
    v15 = *a6;
    v16 = *((_DWORD *)v44 + 2) - *a6;
    v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42, v11, v12);
    v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v42);
    v35 = v15;
    v18 = v14(v13, v41, *(_QWORD *)(v17 + 24), v16);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v18,
        v15);
    PropertySetHelper::PropertySetHelper((PropertySetHelper *)v47, 0);
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"LaunchUriStatus", 0x10u, 0xFu);
    PropertySetHelper::SetUInt32((PropertySetHelper *)v47, v51, v37);
    v38 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.RemoteSystems.RemoteSystemInterop",
      0x3Au,
      0x39u);
    v19 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(
            (__int64)v51,
            (__int64)&v38);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v19,
        v15);
    v20 = v38;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v38 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    UnderlyingProperties = (_QWORD *)PropertySetHelper::GetUnderlyingProperties(v47, &v42);
    v23 = v21(v20, *UnderlyingProperties, &v40);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v23,
        v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    PropertySetHelper::~PropertySetHelper((PropertySetHelper *)v47);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    v26 = v41;
  }
  catch ( ... )
  {
    v39 = wil::ResultFromCaughtException(v24);
    v8 = v39;
    v6 = v45;
    v26 = v46;
  }
  if ( *(_QWORD *)(v6 + 16) )
  {
    v27 = 0;
    v41 = 0;
    v28 = 0;
    v37 = 0;
    if ( v40 )
    {
      v38 = 0;
      v29 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
              &v40,
              (__int64)&v38);
      if ( v29 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v29,
          v35);
      v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 24LL))(v38, &v41);
      if ( v30 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v30,
          v35);
      v31 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), unsigned int *))(*v40)[7])(
              v40,
              &v37);
      if ( v31 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14F,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v31,
          v35);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v27 = v41;
      v28 = v37;
    }
    v36 = v28;
    v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(v6 + 16) + 24LL))(
            *(_QWORD *)(v6 + 16),
            v26,
            v8,
            v27);
    if ( v32 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v32,
        v36);
  }
  v48 = 2;
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v25) )
  {
    v37 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180094048,
      (__int64)&dword_18008377C);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v48);
  return v8;
}

```

## disassembly

```asm
0x18004cde8  push    rbx
0x18004cdea  push    rsi
0x18004cdeb  push    rdi
0x18004cdec  push    r12
0x18004cdee  push    r13
0x18004cdf0  push    r14
0x18004cdf2  push    r15
0x18004cdf4  sub     rsp, 110h
0x18004cdfb  mov     rax, cs:__security_cookie
0x18004ce02  xor     rax, rsp
0x18004ce05  mov     [rsp+148h+var_48], rax
0x18004ce0d  mov     [rsp+148h+var_E0], r9
0x18004ce12  mov     [rsp+148h+var_E8], rdx
0x18004ce17  mov     r13, rcx
0x18004ce1a  mov     [rsp+148h+var_C8], rcx
0x18004ce22  mov     [rsp+148h+var_C0], rdx
0x18004ce2a  mov     rdi, [rsp+148h+arg_28]
0x18004ce32  mov     [rsp+148h+var_D0], rdi
0x18004ce37  xor     r15d, r15d
0x18004ce3a  mov     [rsp+148h+var_A0], r15d
0x18004ce42  mov     [rsp+148h+var_9C], r15b
0x18004ce4a  lea     rcx, [rsp+148h+var_A0]
0x18004ce52  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18004ce57  mov     eax, cs:dword_180094048
0x18004ce5d  cmp     eax, 5
0x18004ce60  jbe     loc_18004CF15
0x18004ce66  mov     rdx, 400000000000h
0x18004ce70  lea     rcx, dword_180094048
0x18004ce77  call    _tlgKeywordOn
0x18004ce7c  test    al, al
0x18004ce7e  jz      loc_18004CF15
0x18004ce84  mov     [rsp+148h+var_100], 1000000h
0x18004ce8d  cmp     [rsp+148h+var_9C], r15b
0x18004ce95  jz      short loc_18004CEC9
0x18004ce97  cmp     [rsp+148h+var_88], r15d
0x18004ce9f  jnz     short loc_18004CEBF
0x18004cea1  cmp     [rsp+148h+var_84], r15d
0x18004cea9  jnz     short loc_18004CEBF
0x18004ceab  cmp     [rsp+148h+var_80], r15d
0x18004ceb3  jnz     short loc_18004CEBF
0x18004ceb5  cmp     [rsp+148h+var_7C], r15d
0x18004cebd  jz      short loc_18004CEC9
0x18004cebf  lea     r9, [rsp+148h+var_88]
0x18004cec7  jmp     short loc_18004CECC
0x18004cec9  mov     r9, r15
0x18004cecc  lea     rax, [rsp+148h+var_100]
0x18004ced1  mov     [rsp+148h+var_58], rax
0x18004ced9  mov     [rsp+148h+var_50], 8
0x18004cee5  lea     rax, [rsp+148h+hstringHeader]
0x18004ceed  mov     [rsp+148h+var_120], rax
0x18004cef2  mov     [rsp+148h+var_128], 3; int
0x18004cefa  lea     r8, [rsp+148h+var_98]
0x18004cf02  lea     rdx, qword_180083838
0x18004cf09  lea     rcx, dword_180094048
0x18004cf10  call    _tlgWriteTransfer_EventWriteTransfer
0x18004cf15  mov     r12d, r15d
0x18004cf18  mov     [rsp+148h+var_F8], r15d
0x18004cf1d  mov     [rsp+148h+var_F0], r15
0x18004cf22  mov     [rsp+148h+var_D8], r15
0x18004cf27  mov     [rsp+148h+var_60], r15
0x18004cf2f  mov     r9d, 34h ; '4'; unsigned int
0x18004cf35  lea     r8d, [r9+1]; unsigned int
0x18004cf39  lea     rdx, ?RuntimeClass_Windows_System_Internal_Launch_RemoteLauncherInterop@@3QBGB; "Windows.System.Internal.Launch.RemoteLa"...
0x18004cf40  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x18004cf48  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004cf4d  nop
0x18004cf4e  mov     rbx, [rsp+148h+var_60]
0x18004cf56  lea     rcx, [rsp+148h+var_D8]
0x18004cf5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cf60  lea     r8, [rsp+148h+var_D8]
0x18004cf65  lea     rdx, _GUID_461643b1_59e4_4e00_8e75_d56769cae169
0x18004cf6c  mov     rcx, rbx
0x18004cf6f  call    cs:__imp_RoGetActivationFactory
0x18004cf75  mov     rcx, [rsp+148h]; this
0x18004cf7d  test    eax, eax
0x18004cf7f  js      loc_18004D2B5
0x18004cf85  mov     [rsp+148h+var_108], r15d
0x18004cf8a  mov     r14, [rsp+148h+var_D8]
0x18004cf8f  mov     rax, [r14]
0x18004cf92  mov     rsi, [rax+38h]
0x18004cf96  mov     rdi, [rdi]
0x18004cf99  mov     rbx, [rsp+148h+var_D0]
0x18004cf9e  mov     ebx, [rbx+8]
0x18004cfa1  sub     ebx, edi
0x18004cfa3  mov     rcx, [rsp+148h+var_E0]
0x18004cfa8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004cfad  mov     [rsp+148h+var_E0], rax
0x18004cfb2  lea     rdx, [rsp+148h+var_E0]
0x18004cfb7  lea     rcx, [rsp+148h+hstringHeader]
0x18004cfbf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004cfc4  nop
0x18004cfc5  lea     rcx, [rsp+148h+var_108]
0x18004cfca  mov     [rsp+148h+var_120], rcx
0x18004cfcf  mov     qword ptr [rsp+148h+var_128], rdi; int
0x18004cfd4  mov     r9d, ebx
0x18004cfd7  mov     r8, [rax+18h]
0x18004cfdb  mov     rdx, [rsp+148h+var_E8]
0x18004cfe0  mov     rcx, r14
0x18004cfe3  mov     rax, rsi
0x18004cfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfeb  mov     rcx, [rsp+148h]; this
0x18004cff3  test    eax, eax
0x18004cff5  js      loc_18004D2CA
0x18004cffb  xor     edx, edx; struct Windows::Foundation::Collections::IPropertySet *
0x18004cffd  lea     rcx, [rsp+148h+var_B8]; this
0x18004d005  call    ??0PropertySetHelper@@QEAA@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x18004d00a  nop
0x18004d00b  mov     ebx, [rsp+148h+var_108]
0x18004d00f  mov     [rsp+148h+var_60], r15
0x18004d017  mov     r9d, 0Fh; unsigned int
0x18004d01d  lea     r8d, [r9+1]; unsigned int
0x18004d021  lea     rdx, ?LaunchUriStatus@RemoteLauncherOptionsKeys@@3QBGB; "LaunchUriStatus"
0x18004d028  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x18004d030  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004d035  nop
0x18004d036  mov     r8d, ebx; unsigned int
0x18004d039  mov     rdx, [rsp+148h+var_60]; HSTRING
0x18004d041  lea     rcx, [rsp+148h+var_B8]; this
0x18004d049  call    ?SetUInt32@PropertySetHelper@@QEAAXPEAUHSTRING__@@I@Z; PropertySetHelper::SetUInt32(HSTRING__ *,uint)
0x18004d04e  nop
0x18004d04f  mov     [rsp+148h+var_100], r15
0x18004d054  mov     [rsp+148h+var_60], r15
0x18004d05c  mov     r9d, 39h ; '9'; unsigned int
0x18004d062  lea     r8d, [r9+1]; unsigned int
0x18004d066  lea     rdx, ?RuntimeClass_Windows_System_Internal_RemoteSystems_RemoteSystemInterop@@3QBGB; "Windows.System.Internal.RemoteSystems.R"...
0x18004d06d  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x18004d075  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004d07a  nop
0x18004d07b  lea     rdx, [rsp+148h+var_100]
0x18004d080  mov     rcx, [rsp+148h+var_60]
0x18004d088  call    ??$GetActivationFactory@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRemoteSystemInteropStatics@RemoteSystems@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::RemoteSystems::IRemoteSystemInteropStatics>>)
0x18004d08d  mov     rcx, [rsp+148h]; this
0x18004d095  test    eax, eax
0x18004d097  js      loc_18004D2DF
0x18004d09d  mov     rdi, [rsp+148h+var_100]
0x18004d0a2  mov     rax, [rdi]
0x18004d0a5  mov     rbx, [rax+30h]
0x18004d0a9  lea     rcx, [rsp+148h+var_F0]
0x18004d0ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d0b3  lea     rdx, [rsp+148h+var_E0]
0x18004d0b8  lea     rcx, [rsp+148h+var_B8]
0x18004d0c0  call    ?GetUnderlyingProperties@PropertySetHelper@@QEBA?AV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; PropertySetHelper::GetUnderlyingProperties(void)
0x18004d0c5  nop
0x18004d0c6  lea     r8, [rsp+148h+var_F0]
0x18004d0cb  mov     rdx, [rax]
0x18004d0ce  mov     rcx, rdi
0x18004d0d1  mov     rax, rbx
0x18004d0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0d9  mov     rcx, [rsp+148h]; this
0x18004d0e1  test    eax, eax
0x18004d0e3  js      loc_18004D2F4
0x18004d0e9  lea     rcx, [rsp+148h+var_E0]
0x18004d0ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d0f3  nop
0x18004d0f4  lea     rcx, [rsp+148h+var_100]
0x18004d0f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d0fe  nop
0x18004d0ff  lea     rcx, [rsp+148h+var_B8]; this
0x18004d107  call    ??1PropertySetHelper@@QEAA@XZ; PropertySetHelper::~PropertySetHelper(void)
0x18004d10c  nop
0x18004d10d  lea     rcx, [rsp+148h+var_D8]
0x18004d112  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d117  nop
0x18004d118  mov     rbx, [rsp+148h+var_E8]
0x18004d11d  jmp     short loc_18004D137
0x18004d11f  xor     r15d, r15d
0x18004d122  mov     r12d, [rsp+148h+var_F8]
0x18004d127  mov     r13, [rsp+148h+var_C8]
0x18004d12f  mov     rbx, [rsp+148h+var_C0]
0x18004d137  cmp     [r13+10h], r15
0x18004d13b  jz      loc_18004D21C
0x18004d141  mov     r9, r15
0x18004d144  mov     [rsp+148h+var_E8], r15
0x18004d149  mov     edx, r15d
0x18004d14c  mov     [rsp+148h+var_108], edx
0x18004d150  cmp     [rsp+148h+var_F0], r15
0x18004d155  jz      loc_18004D1DE
0x18004d15b  mov     [rsp+148h+var_100], r15
0x18004d160  lea     rdx, [rsp+148h+var_100]
0x18004d165  lea     rcx, [rsp+148h+var_F0]
0x18004d16a  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x18004d16f  mov     rcx, [rsp+148h]; this
0x18004d177  test    eax, eax
0x18004d179  js      loc_18004D309
0x18004d17f  mov     rcx, [rsp+148h+var_100]
0x18004d184  mov     rax, [rcx]
0x18004d187  lea     rdx, [rsp+148h+var_E8]
0x18004d18c  mov     rax, [rax+18h]
0x18004d190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d195  mov     rcx, [rsp+148h]; this
0x18004d19d  test    eax, eax
0x18004d19f  js      loc_18004D31D
0x18004d1a5  mov     rcx, [rsp+148h+var_F0]
0x18004d1aa  mov     rax, [rcx]
0x18004d1ad  lea     rdx, [rsp+148h+var_108]
0x18004d1b2  mov     rax, [rax+38h]
0x18004d1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1bb  mov     rcx, [rsp+148h]; this
0x18004d1c3  test    eax, eax
0x18004d1c5  js      loc_18004D331
0x18004d1cb  lea     rcx, [rsp+148h+var_100]
0x18004d1d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d1d5  mov     r9, [rsp+148h+var_E8]
0x18004d1da  mov     edx, [rsp+148h+var_108]
0x18004d1de  mov     rcx, [r13+10h]
0x18004d1e2  mov     rax, [rcx]
0x18004d1e5  mov     r8, [rsp+148h+arg_30]
0x18004d1ed  mov     [rsp+148h+var_120], r8
0x18004d1f2  mov     [rsp+148h+var_128], edx; int
0x18004d1f6  mov     r8d, r12d
0x18004d1f9  mov     rdx, rbx
0x18004d1fc  mov     rax, [rax+18h]
0x18004d200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d205  mov     rcx, [rsp+148h]; this
0x18004d20d  test    eax, eax
0x18004d20f  js      loc_18004D346
0x18004d215  jmp     short loc_18004D21C
0x18004d217  mov     r12d, [rsp+148h+var_F8]
0x18004d21c  mov     [rsp+148h+var_A0], 2
0x18004d227  mov     eax, cs:dword_180094048
0x18004d22d  cmp     eax, 5
0x18004d230  jbe     short loc_18004D277
0x18004d232  mov     rdx, 400000000000h
0x18004d23c  lea     rcx, dword_180094048
0x18004d243  call    _tlgKeywordOn
0x18004d248  test    al, al
0x18004d24a  jz      short loc_18004D277
0x18004d24c  mov     [rsp+148h+var_108], r12d
0x18004d251  lea     rax, [rsp+148h+var_108]
0x18004d256  mov     qword ptr [rsp+148h+var_128], rax
0x18004d25b  lea     r8, [rsp+148h+var_98]
0x18004d263  lea     rdx, dword_18008377C
0x18004d26a  lea     rcx, dword_180094048
0x18004d271  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004d276  nop
0x18004d277  lea     rcx, [rsp+148h+var_F0]
0x18004d27c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d281  nop
0x18004d282  lea     rcx, [rsp+148h+var_A0]
0x18004d28a  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004d28f  mov     eax, r12d
0x18004d292  mov     rcx, [rsp+148h+var_48]
0x18004d29a  xor     rcx, rsp; StackCookie
0x18004d29d  call    __security_check_cookie
0x18004d2a2  add     rsp, 110h
0x18004d2a9  pop     r15
0x18004d2ab  pop     r14
0x18004d2ad  pop     r13
0x18004d2af  pop     r12
0x18004d2b1  pop     rdi
0x18004d2b2  pop     rsi
0x18004d2b3  pop     rbx
0x18004d2b4  retn
0x18004d2b5  mov     r9d, eax; char *
0x18004d2b8  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d2bf  mov     edx, 12Fh; void *
0x18004d2c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d2ca  mov     r9d, eax; char *
0x18004d2cd  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d2d4  mov     edx, 133h; void *
0x18004d2d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d2df  mov     r9d, eax; char *
0x18004d2e2  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d2e9  mov     edx, 13Ah; void *
0x18004d2ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d2f4  mov     r9d, eax; char *
0x18004d2f7  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d2fe  mov     edx, 13Ch; void *
0x18004d303  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d309  mov     r9d, eax; char *
0x18004d30c  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d313  mov     edx, 14Dh; void *
0x18004d318  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d31d  mov     r9d, eax; char *
0x18004d320  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d327  mov     edx, 14Eh; void *
0x18004d32c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d331  mov     r9d, eax; char *
0x18004d334  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d33b  mov     edx, 14Fh; void *
0x18004d340  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004d346  mov     r9d, eax; char *
0x18004d349  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d350  mov     edx, 152h; void *
0x18004d355  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
