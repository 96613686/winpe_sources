# Rdp::Avenc::Hevc::CColorConversionRGB2YUVXVP::CreateXVPConverter(void)

- ea: `0x180031d9c`
- end: `0x180032185`
- name: `?CreateXVPConverter@CColorConversionRGB2YUVXVP@Hevc@Avenc@Rdp@@QEAAXXZ`
- size: `1001`
- prototype: `void __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e2f4`
- `0x18002f05c`

## callees

- `0x180001008`
- `0x18000e848`
- `0x1800275fc`
- `0x180031d9c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031de1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031de1`

## string_xrefs

- `0x180031deb`: `CoCreateInstance ColorConverter failed`
- `0x180031ebe`: `Rdp::Avenc::Hevc::CColorConversionRGB2YUVXVP::CreateXVPConverter`

## pseudocode

```c
void __fastcall Rdp::Avenc::Hevc::CColorConversionRGB2YUVXVP::CreateXVPConverter(LPVOID *ppv)
{
  LPVOID v2; // rcx
  unsigned int Instance; // eax
  const char *v4; // r9
  __int64 *v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // r8d
  int v10; // r9d
  int v11; // r8d
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // eax
  const char *v16; // r9
  LPVOID v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  char *v21; // [rsp+28h] [rbp-30h]
  char *v22; // [rsp+28h] [rbp-30h]
  char *v23; // [rsp+28h] [rbp-30h]
  char *v24; // [rsp+28h] [rbp-30h]
  char *v25; // [rsp+28h] [rbp-30h]
  char *v26; // [rsp+28h] [rbp-30h]
  char *v27; // [rsp+28h] [rbp-30h]
  _QWORD v28[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  int v30; // [rsp+80h] [rbp+28h] BYREF
  __int64 v31; // [rsp+88h] [rbp+30h] BYREF
  const char *v32; // [rsp+90h] [rbp+38h] BYREF
  const char *v33; // [rsp+98h] [rbp+40h] BYREF

  v2 = *ppv;
  *ppv = 0;
  if ( v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  Instance = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)Instance,
    (int)"CoCreateInstance ColorConverter failed",
    v21);
  v5 = (__int64 *)*ppv;
  if ( !*ppv )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
      v4);
  v31 = 0;
  v6 = *v5;
  v31 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 64))(v5, &v31);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x49,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)v7,
    (int)"GetAttributes failed",
    v22);
  v8 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v31 + 168LL))(v31, &MF_XVP_DISABLE_FRC, 1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x4C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)v8,
    (int)"Set MF_XVP_DISABLE_FRC failed",
    v23);
  if ( (*(int (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v31 + 168LL))(v31, MF_LOW_LATENCY, 1) >= 0
    && (unsigned int)dword_1800C1058 > 5 )
  {
    v32 = "XVP low latency mode enabled";
    v33 = "Rdp::Avenc::Hevc::CColorConversionRGB2YUVXVP::CreateXVPConverter";
    v30 = 82;
    v28[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800AECF5,
      v9,
      v10,
      (__int64)v28,
      (__int64)&v30,
      (__int64)&v33,
      (__int64)&v32);
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v31 + 168LL))(v31, MF_SA_D3D11_AWARE, 1) >= 0
    && (unsigned int)dword_1800C1058 > 5 )
  {
    v32 = "XVP D3D11 aware mode enabled";
    v33 = "Rdp::Avenc::Hevc::CColorConversionRGB2YUVXVP::CreateXVPConverter";
    v30 = 88;
    v28[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800AECBF,
      v11,
      v12,
      (__int64)v28,
      (__int64)&v30,
      (__int64)&v33,
      (__int64)&v32);
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v31 + 168LL))(v31, MF_XVP_SAMPLE_LOCK_TIMEOUT, 0) >= 0
    && (unsigned int)dword_1800C1058 > 5 )
  {
    v32 = "XVP non-blocking mode enabled";
    v33 = "Rdp::Avenc::Hevc::CColorConversionRGB2YUVXVP::CreateXVPConverter";
    v30 = 94;
    v28[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800AEC89,
      v13,
      v14,
      (__int64)v28,
      (__int64)&v30,
      (__int64)&v33,
      (__int64)&v32);
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID))(*(_QWORD *)*ppv + 184LL))(*ppv, 2, ppv[3]);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)v15,
    (int)"MFT_MESSAGE_SET_D3D_MANAGER failed",
    v24);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( !ppv[1] )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
      v16);
  v17 = ppv[2];
  if ( !v17 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
      v16);
  v18 = (*(__int64 (__fastcall **)(LPVOID, const GUID *, unsigned __int64))(*(_QWORD *)v17 + 176LL))(
          v17,
          &MF_MT_FRAME_SIZE,
          *((unsigned int *)ppv + 9) | ((unsigned __int64)*((unsigned int *)ppv + 8) << 32));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x83,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)v18,
    (int)"MF_MT_FRAME_SIZE failed",
    v25);
  v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, _QWORD))(*(_QWORD *)*ppv + 120LL))(*ppv, 0, ppv[1], 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x86,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)v19,
    (int)"m_XVPConverter->SetInputType() failed",
    v26);
  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, _QWORD))(*(_QWORD *)*ppv + 128LL))(*ppv, 0, ppv[2], 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x89,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\colorconversionrgb2yuvxvp.cpp",
    (const char *)v20,
    (int)"m_XVPConverter->SetOutputType() failed",
    v27);
}

```

## disassembly

```asm
0x180031d9c  push    rbp
0x180031d9e  push    rbx
0x180031d9f  push    rsi
0x180031da0  push    r15
0x180031da2  mov     rbp, rsp
0x180031da5  sub     rsp, 58h
0x180031da9  mov     rbx, rcx
0x180031dac  mov     rcx, [rcx]
0x180031daf  mov     qword ptr [rbx], 0
0x180031db6  test    rcx, rcx
0x180031db9  jz      short loc_180031DC8
0x180031dbb  mov     rax, [rcx]
0x180031dbe  mov     rax, [rax+10h]
0x180031dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031dc7  nop
0x180031dc8  mov     [rsp+58h+ppv], rbx; ppv
0x180031dcd  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x180031dd4  xor     edx, edx; pUnkOuter
0x180031dd6  lea     r8d, [rdx+1]; dwClsContext
0x180031dda  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x180031de1  call    cs:__imp_CoCreateInstance
0x180031de7  mov     rcx, [rbp+20h]; this
0x180031deb  lea     rdx, aCocreateinstan; "CoCreateInstance ColorConverter failed"
0x180031df2  mov     [rsp+58h+ppv], rdx; int
0x180031df7  mov     r9d, eax; char *
0x180031dfa  lea     rsi, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180031e01  mov     r8, rsi; unsigned int
0x180031e04  mov     edx, 3Fh ; '?'; void *
0x180031e09  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180031e0e  mov     rax, [rbp+20h]
0x180031e12  mov     rcx, [rbx]
0x180031e15  test    rcx, rcx
0x180031e18  jz      loc_180032166
0x180031e1e  mov     [rbp+arg_8], 0
0x180031e26  mov     rax, [rcx]
0x180031e29  mov     [rbp+arg_8], 0
0x180031e31  lea     rdx, [rbp+arg_8]
0x180031e35  mov     rax, [rax+40h]
0x180031e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e3e  mov     rcx, [rbp+20h]; this
0x180031e42  lea     rdx, aGetattributesF; "GetAttributes failed"
0x180031e49  mov     [rsp+58h+ppv], rdx; int
0x180031e4e  mov     r9d, eax; char *
0x180031e51  mov     r8, rsi; unsigned int
0x180031e54  mov     edx, 49h ; 'I'; void *
0x180031e59  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180031e5e  mov     rcx, [rbp+arg_8]
0x180031e62  mov     rax, [rcx]
0x180031e65  mov     r8d, 1
0x180031e6b  lea     rdx, MF_XVP_DISABLE_FRC
0x180031e72  mov     rax, [rax+0A8h]
0x180031e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e7e  mov     rcx, [rbp+20h]; this
0x180031e82  lea     rdx, aSetMfXvpDisabl; "Set MF_XVP_DISABLE_FRC failed"
0x180031e89  mov     [rsp+58h+ppv], rdx; int
0x180031e8e  mov     r9d, eax; char *
0x180031e91  mov     r8, rsi; unsigned int
0x180031e94  mov     edx, 4Ch ; 'L'; void *
0x180031e99  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180031e9e  mov     rcx, [rbp+arg_8]
0x180031ea2  mov     rax, [rcx]
0x180031ea5  mov     r8d, 1
0x180031eab  lea     rdx, MF_LOW_LATENCY
0x180031eb2  mov     rax, [rax+0A8h]
0x180031eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ebe  lea     r15, aRdpAvencHevcCc; "Rdp::Avenc::Hevc::CColorConversionRGB2Y"...
0x180031ec5  test    eax, eax
0x180031ec7  js      short loc_180031F25
0x180031ec9  mov     eax, cs:dword_1800C1058
0x180031ecf  cmp     eax, 5
0x180031ed2  jbe     short loc_180031F25
0x180031ed4  lea     rax, aXvpLowLatencyM; "XVP low latency mode enabled"
0x180031edb  mov     [rbp+arg_10], rax
0x180031edf  mov     [rbp+arg_18], r15
0x180031ee3  mov     [rbp+arg_0], 52h ; 'R'
0x180031eea  mov     [rbp+var_18], rsi
0x180031eee  lea     rax, [rbp+arg_10]
0x180031ef2  mov     [rsp+58h+var_20], rax
0x180031ef7  lea     rax, [rbp+arg_18]
0x180031efb  mov     [rsp+58h+var_28], rax
0x180031f00  lea     rax, [rbp+arg_0]
0x180031f04  mov     [rsp+58h+var_30], rax
0x180031f09  lea     rax, [rbp+var_18]
0x180031f0d  mov     [rsp+58h+ppv], rax
0x180031f12  lea     rdx, byte_1800AECF5
0x180031f19  lea     rcx, dword_1800C1058
0x180031f20  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180031f25  mov     rcx, [rbp+arg_8]
0x180031f29  mov     rax, [rcx]
0x180031f2c  mov     r8d, 1
0x180031f32  lea     rdx, MF_SA_D3D11_AWARE
0x180031f39  mov     rax, [rax+0A8h]
0x180031f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f45  test    eax, eax
0x180031f47  js      short loc_180031FA5
0x180031f49  mov     eax, cs:dword_1800C1058
0x180031f4f  cmp     eax, 5
0x180031f52  jbe     short loc_180031FA5
0x180031f54  lea     rax, aXvpD3d11AwareM; "XVP D3D11 aware mode enabled"
0x180031f5b  mov     [rbp+arg_10], rax
0x180031f5f  mov     [rbp+arg_18], r15
0x180031f63  mov     [rbp+arg_0], 58h ; 'X'
0x180031f6a  mov     [rbp+var_18], rsi
0x180031f6e  lea     rax, [rbp+arg_10]
0x180031f72  mov     [rsp+58h+var_20], rax
0x180031f77  lea     rax, [rbp+arg_18]
0x180031f7b  mov     [rsp+58h+var_28], rax
0x180031f80  lea     rax, [rbp+arg_0]
0x180031f84  mov     [rsp+58h+var_30], rax
0x180031f89  lea     rax, [rbp+var_18]
0x180031f8d  mov     [rsp+58h+ppv], rax
0x180031f92  lea     rdx, byte_1800AECBF
0x180031f99  lea     rcx, dword_1800C1058
0x180031fa0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180031fa5  mov     rcx, [rbp+arg_8]
0x180031fa9  mov     rax, [rcx]
0x180031fac  xor     r8d, r8d
0x180031faf  lea     rdx, MF_XVP_SAMPLE_LOCK_TIMEOUT
0x180031fb6  mov     rax, [rax+0A8h]
0x180031fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fc2  test    eax, eax
0x180031fc4  js      short loc_180032022
0x180031fc6  mov     eax, cs:dword_1800C1058
0x180031fcc  cmp     eax, 5
0x180031fcf  jbe     short loc_180032022
0x180031fd1  lea     rax, aXvpNonBlocking; "XVP non-blocking mode enabled"
0x180031fd8  mov     [rbp+arg_10], rax
0x180031fdc  mov     [rbp+arg_18], r15
0x180031fe0  mov     [rbp+arg_0], 5Eh ; '^'
0x180031fe7  mov     [rbp+var_18], rsi
0x180031feb  lea     rax, [rbp+arg_10]
0x180031fef  mov     [rsp+58h+var_20], rax
0x180031ff4  lea     rax, [rbp+arg_18]
0x180031ff8  mov     [rsp+58h+var_28], rax
0x180031ffd  lea     rax, [rbp+arg_0]
0x180032001  mov     [rsp+58h+var_30], rax; char *
0x180032006  lea     rax, [rbp+var_18]
0x18003200a  mov     [rsp+58h+ppv], rax
0x18003200f  lea     rdx, byte_1800AEC89
0x180032016  lea     rcx, dword_1800C1058
0x18003201d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180032022  mov     rcx, [rbx]
0x180032025  mov     rax, [rcx]
0x180032028  mov     r8, [rbx+18h]
0x18003202c  mov     edx, 2
0x180032031  mov     rax, [rax+0B8h]
0x180032038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003203d  mov     rcx, [rbp+20h]; this
0x180032041  lea     rdx, aMftMessageSetD; "MFT_MESSAGE_SET_D3D_MANAGER failed"
0x180032048  mov     [rsp+58h+ppv], rdx; int
0x18003204d  mov     r9d, eax; char *
0x180032050  mov     r8, rsi; unsigned int
0x180032053  mov     edx, 63h ; 'c'; void *
0x180032058  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003205d  nop
0x18003205e  mov     rcx, [rbp+arg_8]
0x180032062  test    rcx, rcx
0x180032065  jz      short loc_180032074
0x180032067  mov     rax, [rcx]
0x18003206a  mov     rax, [rax+10h]
0x18003206e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032073  nop
0x180032074  mov     rcx, [rbp+20h]; this
0x180032078  cmp     qword ptr [rbx+8], 0
0x18003207d  jz      loc_180032177
0x180032083  mov     rax, [rbp+20h]
0x180032087  mov     rcx, [rbx+10h]
0x18003208b  test    rcx, rcx
0x18003208e  jz      loc_180032155
0x180032094  mov     r9, [rcx]
0x180032097  mov     r8d, [rbx+20h]
0x18003209b  shl     r8, 20h
0x18003209f  mov     eax, [rbx+24h]
0x1800320a2  or      r8, rax
0x1800320a5  lea     rdx, MF_MT_FRAME_SIZE
0x1800320ac  mov     rax, [r9+0B0h]
0x1800320b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320b8  mov     rcx, [rbp+20h]; this
0x1800320bc  lea     rdx, aMfMtFrameSizeF; "MF_MT_FRAME_SIZE failed"
0x1800320c3  mov     [rsp+58h+ppv], rdx; int
0x1800320c8  mov     r9d, eax; char *
0x1800320cb  mov     r8, rsi; unsigned int
0x1800320ce  mov     edx, 83h; void *
0x1800320d3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800320d8  mov     rcx, [rbx]
0x1800320db  mov     rax, [rcx]
0x1800320de  xor     r9d, r9d
0x1800320e1  mov     r8, [rbx+8]
0x1800320e5  xor     edx, edx
0x1800320e7  mov     rax, [rax+78h]
0x1800320eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320f0  mov     rcx, [rbp+20h]; this
0x1800320f4  lea     rdx, aMXvpconverterS; "m_XVPConverter->SetInputType() failed"
0x1800320fb  mov     [rsp+58h+ppv], rdx; int
0x180032100  mov     r9d, eax; char *
0x180032103  mov     r8, rsi; unsigned int
0x180032106  mov     edx, 86h; void *
0x18003210b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032110  mov     rcx, [rbx]
0x180032113  mov     rax, [rcx]
0x180032116  xor     r9d, r9d
0x180032119  mov     r8, [rbx+10h]
0x18003211d  xor     edx, edx
0x18003211f  mov     rax, [rax+80h]
0x180032126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003212b  mov     rcx, [rbp+20h]; this
0x18003212f  lea     rdx, aMXvpconverterS_0; "m_XVPConverter->SetOutputType() failed"
0x180032136  mov     [rsp+58h+ppv], rdx; int
0x18003213b  mov     r9d, eax; char *
0x18003213e  mov     r8, rsi; unsigned int
0x180032141  mov     edx, 89h; void *
0x180032146  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003214b  add     rsp, 58h
0x18003214f  pop     r15
0x180032151  pop     rsi
0x180032152  pop     rbx
0x180032153  pop     rbp
0x180032154  retn
0x180032155  mov     r8, rsi; unsigned int
0x180032158  mov     edx, 80h; void *
0x18003215d  mov     rcx, rax; this
0x180032160  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180032166  mov     r8, rsi; unsigned int
0x180032169  mov     edx, 41h ; 'A'; void *
0x18003216e  mov     rcx, rax; this
0x180032171  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180032177  mov     r8, rsi; unsigned int
0x18003217a  mov     edx, 7Fh; void *
0x18003217f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
