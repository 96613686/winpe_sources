# CDPComAppControlHandler::GetResourceAsync(unsigned __int64,CDPComRemoteUserInfo,char const *,unsigned __int64)

- ea: `0x18004c440`
- end: `0x18004c764`
- name: `?GetResourceAsync@CDPComAppControlHandler@@UEAAJ_KUCDPComRemoteUserInfo@@PEBD0@Z`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800010a8`
- `0x180003678`
- `0x18001b1f0`
- `0x18001b92c`
- `0x18001bc80`
- `0x18001c284`
- `0x18001e798`
- `0x18002c570`
- `0x180041054`
- `0x18004abfc`
- `0x18004ad34`
- `0x18004ad88`
- `0x18004c440`
- `0x180064010`

## import_xrefs

- `cdp!CDPGetResourceHandler` at `0x18004c567`
- `cdp!CDPGetResourceHandler` at `0x18004c567`
- `cdp!CDPCreateRemoteUserInternal` at `0x18004c5f1`
- `cdp!CDPCreateRemoteUserInternal` at `0x18004c5f1`

## string_xrefs

- `0x18004c485`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c713`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c728`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c73d`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c751`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004c6d2`: `GetResource request complete. ResourceUrl = %s, Result = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 CDPComAppControlHandler::GetResourceAsync(__int64 a1, __int64 a2, __int64 a3, __int64 a4, ...)
{
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // r8
  _DWORD *v11; // r9
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  wil *v17; // rcx
  __int64 v18; // r8
  int v19; // [rsp+20h] [rbp-A8h]
  unsigned int v20; // [rsp+30h] [rbp-98h] BYREF
  __int64 v21; // [rsp+38h] [rbp-90h] BYREF
  __int64 v22; // [rsp+40h] [rbp-88h] BYREF
  int v23[2]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v24; // [rsp+50h] [rbp-78h] BYREF
  __int64 v25; // [rsp+58h] [rbp-70h] BYREF
  __int64 v26; // [rsp+60h] [rbp-68h] BYREF
  int v27; // [rsp+68h] [rbp-60h] BYREF
  char v28; // [rsp+6Ch] [rbp-5Ch]
  _BYTE v29[16]; // [rsp+70h] [rbp-58h] BYREF
  _DWORD v30[4]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  __int64 v32; // [rsp+D8h] [rbp+10h] BYREF
  va_list va; // [rsp+F0h] [rbp+28h] BYREF

  va_start(va, a4);
  v32 = a2;
  v25 = a4;
  if ( a4 )
  {
    v8 = 0;
    v20 = 0;
    v27 = 0;
    v28 = 0;
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v27);
    if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v10) )
    {
      *(_QWORD *)v23 = a4;
      if ( v28 && (v30[0] || v30[1] || v30[2] || v30[3]) )
        v11 = v30;
      else
        v11 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)&dword_180094048,
        (__int64)byte_180083861,
        (__int64)v29,
        (__int64)v11,
        v23);
    }
    Log<char const * &>(v9, "Starting request to GetResource. resourceUrl = %s", (const char *)&v25);
    v22 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v12 = CDPGetResourceHandler(&v22);
    try
    {
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v12,
          v19);
      v26 = *(_QWORD *)(a1 + 16);
      Microsoft::WRL::Details::Make<CDPComAppControlHandler::AppControlResourceHandlerCallback,ICDPComAppControlSystemHandlerCallback *,unsigned __int64 &,unsigned __int64 &>(
        v23,
        &v26,
        &v32,
        (__int64 *)va);
      v24 = 0;
      v13 = Microsoft::WRL::ComPtr<CDPComAppControlHandler::AppControlResourceHandlerCallback>::As<ICDPResourceHandlerCallback>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v23,
              (__int64)&v24);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v13,
          v19);
      v21 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      LOBYTE(v14) = *(_DWORD *)a3 != 0;
      v15 = CDPCreateRemoteUserInternal(v14, *(_QWORD *)(a3 + 8), &v21);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v15,
          v19);
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v22 + 32LL))(v22, v21, v25, v24);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xAC,
          (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
          (const char *)(unsigned int)v16,
          v19);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      if ( *(_QWORD *)v23 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    }
    catch ( ... )
    {
      v20 = wil::ResultFromCaughtException(v17);
      v8 = v20;
    }
    v27 = 2;
    if ( (unsigned int)dword_180094048 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v18) )
      {
        LODWORD(v21) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180094048,
          (__int64)byte_1800837EB);
      }
    }
    Log<char const * &,long &>(
      3,
      "GetResource request complete. ResourceUrl = %s, Result = 0x%08x.",
      (const char *)&v25,
      (unsigned int)&v20);
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v27);
    return v20;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
      (const char *)0x80070057LL,
      v19);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18004c440  mov     [rsp+arg_8], rdx
0x18004c445  push    rsi
0x18004c446  push    rdi
0x18004c447  push    r14
0x18004c449  push    r15
0x18004c44b  sub     rsp, 0A8h
0x18004c452  mov     rax, cs:__security_cookie
0x18004c459  xor     rax, rsp
0x18004c45c  mov     [rsp+0C8h+var_38], rax
0x18004c464  mov     rdi, r9
0x18004c467  mov     r14, r8
0x18004c46a  mov     r15, rcx
0x18004c46d  mov     [rsp+0C8h+var_70], r9
0x18004c472  test    r9, r9
0x18004c475  jnz     short loc_18004C4A0
0x18004c477  mov     rcx, [rsp+0C8h]; this
0x18004c47f  mov     r9d, 80070057h; char *
0x18004c485  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004c48c  mov     edx, 9Ah; void *
0x18004c491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c496  mov     eax, 80070057h
0x18004c49b  jmp     loc_18004C6F2
0x18004c4a0  xor     esi, esi
0x18004c4a2  mov     [rsp+0C8h+var_98], esi
0x18004c4a6  mov     [rsp+0C8h+var_60], esi
0x18004c4aa  mov     [rsp+0C8h+var_5C], sil
0x18004c4af  lea     rcx, [rsp+0C8h+var_60]
0x18004c4b4  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18004c4b9  mov     eax, cs:dword_180094048
0x18004c4bf  cmp     eax, 5
0x18004c4c2  jbe     short loc_18004C53D
0x18004c4c4  mov     rdx, 400000000000h
0x18004c4ce  lea     rcx, dword_180094048
0x18004c4d5  call    _tlgKeywordOn
0x18004c4da  test    al, al
0x18004c4dc  jz      short loc_18004C53D
0x18004c4de  mov     qword ptr [rsp+0C8h+var_80], rdi
0x18004c4e3  cmp     [rsp+0C8h+var_5C], sil
0x18004c4e8  jz      short loc_18004C518
0x18004c4ea  cmp     [rsp+0C8h+var_48], esi
0x18004c4f1  jnz     short loc_18004C50E
0x18004c4f3  cmp     [rsp+0C8h+var_44], esi
0x18004c4fa  jnz     short loc_18004C50E
0x18004c4fc  cmp     [rsp+0C8h+var_40], esi
0x18004c503  jnz     short loc_18004C50E
0x18004c505  cmp     [rsp+0C8h+var_3C], esi
0x18004c50c  jz      short loc_18004C518
0x18004c50e  lea     r9, [rsp+0C8h+var_48]
0x18004c516  jmp     short loc_18004C51B
0x18004c518  xor     r9d, r9d
0x18004c51b  lea     rax, [rsp+0C8h+var_80]
0x18004c520  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x18004c525  lea     r8, [rsp+0C8h+var_58]
0x18004c52a  lea     rdx, byte_180083861
0x18004c531  lea     rcx, dword_180094048
0x18004c538  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004c53d  lea     r8, [rsp+0C8h+var_70]
0x18004c542  lea     rdx, aStartingReques_0; "Starting request to GetResource. resour"...
0x18004c549  call    ??$Log@AEAPEBD@@YAXW4CDPLogLevel@@PEBDAEAPEBD@Z; Log<char const * &>(CDPLogLevel,char const *,char const * &)
0x18004c54e  nop
0x18004c54f  mov     [rsp+0C8h+var_88], 0
0x18004c558  lea     rcx, [rsp+0C8h+var_88]
0x18004c55d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c562  lea     rcx, [rsp+0C8h+var_88]
0x18004c567  call    cs:__imp_CDPGetResourceHandler
0x18004c56d  mov     rcx, [rsp+0C8h]; this
0x18004c575  test    eax, eax
0x18004c577  js      loc_18004C710
0x18004c57d  mov     rax, [r15+10h]
0x18004c581  mov     [rsp+0C8h+var_68], rax
0x18004c586  lea     r9, [rsp+0C8h+arg_20]
0x18004c58e  lea     r8, [rsp+0C8h+arg_8]
0x18004c596  lea     rdx, [rsp+0C8h+var_68]
0x18004c59b  lea     rcx, [rsp+0C8h+var_80]
0x18004c5a0  call    ??$Make@VAppControlResourceHandlerCallback@CDPComAppControlHandler@@PEAUICDPComAppControlSystemHandlerCallback@@AEA_KAEA_K@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppControlResourceHandlerCallback@CDPComAppControlHandler@@@12@$$QEAPEAUICDPComAppControlSystemHandlerCallback@@AEA_K1@Z; Microsoft::WRL::Details::Make<CDPComAppControlHandler::AppControlResourceHandlerCallback,ICDPComAppControlSystemHandlerCallback *,unsigned __int64 &,unsigned __int64 &>(ICDPComAppControlSystemHandlerCallback * &&,unsigned __int64 &,unsigned __int64 &)
0x18004c5a5  nop
0x18004c5a6  mov     [rsp+0C8h+var_78], 0
0x18004c5af  lea     rdx, [rsp+0C8h+var_78]
0x18004c5b4  lea     rcx, [rsp+0C8h+var_80]
0x18004c5b9  call    ??$As@VICDPResourceHandlerCallback@@@?$ComPtr@VAppControlResourceHandlerCallback@CDPComAppControlHandler@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@VICDPResourceHandlerCallback@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<CDPComAppControlHandler::AppControlResourceHandlerCallback>::As<ICDPResourceHandlerCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>>)
0x18004c5be  mov     rcx, [rsp+0C8h]; this
0x18004c5c6  test    eax, eax
0x18004c5c8  js      loc_18004C725
0x18004c5ce  mov     [rsp+0C8h+var_90], 0
0x18004c5d7  lea     rcx, [rsp+0C8h+var_90]
0x18004c5dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c5e1  cmp     dword ptr [r14], 0
0x18004c5e5  setnz   cl
0x18004c5e8  lea     r8, [rsp+0C8h+var_90]
0x18004c5ed  mov     rdx, [r14+8]
0x18004c5f1  call    cs:__imp_CDPCreateRemoteUserInternal
0x18004c5f7  mov     rcx, [rsp+0C8h]; this
0x18004c5ff  test    eax, eax
0x18004c601  js      loc_18004C73A
0x18004c607  mov     rcx, [rsp+0C8h+var_88]
0x18004c60c  mov     rax, [rcx]
0x18004c60f  mov     r9, [rsp+0C8h+var_78]
0x18004c614  mov     r8, [rsp+0C8h+var_70]
0x18004c619  mov     rdx, [rsp+0C8h+var_90]
0x18004c61e  mov     rax, [rax+20h]
0x18004c622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c627  mov     rcx, [rsp+0C8h]; this
0x18004c62f  test    eax, eax
0x18004c631  js      loc_18004C74E
0x18004c637  lea     rcx, [rsp+0C8h+var_90]
0x18004c63c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c641  nop
0x18004c642  lea     rcx, [rsp+0C8h+var_78]
0x18004c647  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c64c  nop
0x18004c64d  mov     rcx, qword ptr [rsp+0C8h+var_80]
0x18004c652  test    rcx, rcx
0x18004c655  jz      short loc_18004C664
0x18004c657  mov     rax, [rcx]
0x18004c65a  mov     rax, [rax+10h]
0x18004c65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c663  nop
0x18004c664  lea     rcx, [rsp+0C8h+var_88]
0x18004c669  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c66e  nop
0x18004c66f  jmp     short loc_18004C675
0x18004c671  mov     esi, [rsp+0C8h+var_98]
0x18004c675  mov     [rsp+0C8h+var_60], 2
0x18004c67d  mov     eax, cs:dword_180094048
0x18004c683  cmp     eax, 5
0x18004c686  jbe     short loc_18004C6C8
0x18004c688  mov     rdx, 400000000000h
0x18004c692  lea     rcx, dword_180094048
0x18004c699  call    _tlgKeywordOn
0x18004c69e  test    al, al
0x18004c6a0  jz      short loc_18004C6C8
0x18004c6a2  mov     dword ptr [rsp+0C8h+var_90], esi
0x18004c6a6  lea     rax, [rsp+0C8h+var_90]
0x18004c6ab  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18004c6b0  lea     r8, [rsp+0C8h+var_58]
0x18004c6b5  lea     rdx, byte_1800837EB
0x18004c6bc  lea     rcx, dword_180094048
0x18004c6c3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004c6c8  lea     r9, [rsp+0C8h+var_98]
0x18004c6cd  lea     r8, [rsp+0C8h+var_70]
0x18004c6d2  lea     rdx, aGetresourceReq; "GetResource request complete. ResourceU"...
0x18004c6d9  mov     ecx, 3
0x18004c6de  call    ??$Log@AEAPEBDAEAJ@@YAXW4CDPLogLevel@@PEBDAEAPEBDAEAJ@Z; Log<char const * &,long &>(CDPLogLevel,char const *,char const * &,long &)
0x18004c6e3  nop
0x18004c6e4  lea     rcx, [rsp+0C8h+var_60]
0x18004c6e9  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004c6ee  mov     eax, [rsp+0C8h+var_98]
0x18004c6f2  mov     rcx, [rsp+0C8h+var_38]
0x18004c6fa  xor     rcx, rsp; StackCookie
0x18004c6fd  call    __security_check_cookie
0x18004c702  add     rsp, 0A8h
0x18004c709  pop     r15
0x18004c70b  pop     r14
0x18004c70d  pop     rdi
0x18004c70e  pop     rsi
0x18004c70f  retn
0x18004c710  mov     r9d, eax; char *
0x18004c713  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004c71a  mov     edx, 0A6h; void *
0x18004c71f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c725  mov     r9d, eax; char *
0x18004c728  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004c72f  mov     edx, 0A9h; void *
0x18004c734  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c73a  mov     r9d, eax; char *
0x18004c73d  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004c744  mov     edx, 0ABh; void *
0x18004c749  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c74e  mov     r9d, eax; char *
0x18004c751  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004c758  mov     edx, 0ACh; void *
0x18004c75d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
