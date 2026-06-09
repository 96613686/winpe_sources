# CDPComAppControlHandler::SetResourceAsync(unsigned __int64,CDPComRemoteUserInfo,char const *,uchar const *,uint,unsigned __int64)

- ea: `0x18004df60`
- end: `0x18004e2e7`
- name: `?SetResourceAsync@CDPComAppControlHandler@@UEAAJ_KUCDPComRemoteUserInfo@@PEBDPEBEI0@Z`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800010a8`
- `0x180002a4c`
- `0x180003678`
- `0x180004a58`
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
- `0x18004ba48`
- `0x18004df60`
- `0x180064010`

## import_xrefs

- `cdp!CDPGetResourceHandler` at `0x18004e0ac`
- `cdp!CDPGetResourceHandler` at `0x18004e0ac`
- `cdp!CDPCreateRemoteUserInternal` at `0x18004e149`
- `cdp!CDPCreateRemoteUserInternal` at `0x18004e149`

## string_xrefs

- `0x18004dfb4`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004e296`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004e2ab`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004e2c0`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004e2d4`: `..\cdpcomappcontrolhandler.cpp`
- `0x18004e252`: `SetResource request complete. ResourceUrl = %s, Result = 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 CDPComAppControlHandler::SetResourceAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        ...)
{
  __int64 v9; // rdi
  __int64 v10; // r12
  __int64 v11; // rdx
  unsigned int v13; // r15d
  __int64 v14; // rcx
  __int64 v15; // r8
  _DWORD *v16; // r9
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  _QWORD *v21; // rsi
  int v22; // edi
  __int64 v23; // rbx
  __int64 v24; // r9
  int v25; // eax
  wil *v26; // rcx
  __int64 v27; // r8
  int v28; // [rsp+20h] [rbp-D8h]
  unsigned int v29; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C0h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-B8h] BYREF
  int v32[2]; // [rsp+48h] [rbp-B0h] BYREF
  int v33[2]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-98h] BYREF
  int v36; // [rsp+68h] [rbp-90h] BYREF
  char v37; // [rsp+6Ch] [rbp-8Ch]
  _BYTE v38[16]; // [rsp+70h] [rbp-88h] BYREF
  _DWORD v39[4]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v40[32]; // [rsp+90h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+10h] BYREF
  va_list va; // [rsp+130h] [rbp+38h] BYREF

  va_start(va, a6);
  v42 = a2;
  v34 = a4;
  v9 = a5;
  v10 = a6;
  if ( !a4 )
  {
    v11 = 187;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
      (const char *)0x80070057LL,
      v28);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    v11 = 188;
    goto LABEL_3;
  }
  v13 = 0;
  v29 = 0;
  v36 = 0;
  v37 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v36);
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v15) )
  {
    *(_QWORD *)v32 = a4;
    if ( v37 && (v39[0] || v39[1] || v39[2] || v39[3]) )
      v16 = v39;
    else
      v16 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)&dword_180094048,
      (__int64)byte_18008372D,
      (__int64)v38,
      (__int64)v16,
      v32);
  }
  Log<char const * &>(v14, "Starting request to SetResource. resourceUrl = %s", (const char *)&v34);
  v31 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v17 = CDPGetResourceHandler(&v31);
  try
  {
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v17,
        v28);
    v35 = *(_QWORD *)(a1 + 16);
    Microsoft::WRL::Details::Make<CDPComAppControlHandler::AppControlResourceHandlerCallback,ICDPComAppControlSystemHandlerCallback *,unsigned __int64 &,unsigned __int64 &>(
      v32,
      &v35,
      &v42,
      (__int64 *)va);
    *(_QWORD *)v33 = 0;
    v18 = Microsoft::WRL::ComPtr<CDPComAppControlHandler::AppControlResourceHandlerCallback>::As<ICDPResourceHandlerCallback>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v32,
            (__int64)v33);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v18,
        v28);
    std::string::string(v40, v9, v10);
    v30 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    LOBYTE(v19) = *(_DWORD *)a3 != 0;
    v20 = CDPCreateRemoteUserInternal(v19, *(_QWORD *)(a3 + 8), &v30);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCE,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v20,
        v28);
    v21 = v31;
    v22 = v33[0];
    v23 = *v31;
    v24 = std::_String_val<std::_Simple_types<char>>::_Myptr(v40);
    v25 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, __int64))(v23 + 40))(v21, v30, v34, v24);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"..\\cdpcomappcontrolhandler.cpp",
        (const char *)(unsigned int)v25,
        v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    std::string::_Tidy_deallocate(v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
    if ( *(_QWORD *)v32 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v32 + 16LL))(*(_QWORD *)v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  }
  catch ( ... )
  {
    v29 = wil::ResultFromCaughtException(v26);
    v13 = v29;
  }
  v36 = 2;
  if ( (unsigned int)dword_180094048 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v27) )
    {
      LODWORD(v30) = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180094048,
        (__int64)byte_180083709);
    }
  }
  Log<char const * &,long &>(
    3,
    "SetResource request complete. ResourceUrl = %s, Result = 0x%08x.",
    (const char *)&v34,
    (unsigned int)&v29);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v36);
  return v29;
}

```

## disassembly

```asm
0x18004df60  mov     [rsp+arg_8], rdx
0x18004df65  push    rbx
0x18004df66  push    rsi
0x18004df67  push    rdi
0x18004df68  push    r12
0x18004df6a  push    r13
0x18004df6c  push    r15
0x18004df6e  sub     rsp, 0C8h
0x18004df75  mov     rax, cs:__security_cookie
0x18004df7c  xor     rax, rsp
0x18004df7f  mov     [rsp+0F8h+var_48], rax
0x18004df87  mov     rbx, r9
0x18004df8a  mov     rsi, r8
0x18004df8d  mov     r13, rcx
0x18004df90  mov     [rsp+0F8h+var_A0], rbx
0x18004df95  mov     rdi, [rsp+0F8h+arg_20]
0x18004df9d  mov     r12d, [rsp+0F8h+arg_28]
0x18004dfa5  test    r9, r9
0x18004dfa8  jnz     short loc_18004DFD2
0x18004dfaa  mov     edx, 0BBh; void *
0x18004dfaf  mov     ebx, 80070057h
0x18004dfb4  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004dfbb  mov     r9d, ebx; char *
0x18004dfbe  mov     rcx, [rsp+0F8h]; this
0x18004dfc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dfcb  mov     eax, ebx
0x18004dfcd  jmp     loc_18004E272
0x18004dfd2  test    rdi, rdi
0x18004dfd5  jnz     short loc_18004DFDE
0x18004dfd7  mov     edx, 0BCh
0x18004dfdc  jmp     short loc_18004DFAF
0x18004dfde  xor     r15d, r15d
0x18004dfe1  mov     [rsp+0F8h+var_C8], r15d
0x18004dfe6  mov     [rsp+0F8h+var_90], r15d
0x18004dfeb  mov     [rsp+0F8h+var_8C], r15b
0x18004dff0  lea     rcx, [rsp+0F8h+var_90]
0x18004dff5  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18004dffa  mov     eax, cs:dword_180094048
0x18004e000  cmp     eax, 5
0x18004e003  jbe     short loc_18004E082
0x18004e005  mov     rdx, 400000000000h
0x18004e00f  lea     rcx, dword_180094048
0x18004e016  call    _tlgKeywordOn
0x18004e01b  test    al, al
0x18004e01d  jz      short loc_18004E082
0x18004e01f  mov     qword ptr [rsp+0F8h+var_B0], rbx
0x18004e024  cmp     [rsp+0F8h+var_8C], r15b
0x18004e029  jz      short loc_18004E05D
0x18004e02b  cmp     [rsp+0F8h+var_78], r15d
0x18004e033  jnz     short loc_18004E053
0x18004e035  cmp     [rsp+0F8h+var_74], r15d
0x18004e03d  jnz     short loc_18004E053
0x18004e03f  cmp     [rsp+0F8h+var_70], r15d
0x18004e047  jnz     short loc_18004E053
0x18004e049  cmp     [rsp+0F8h+var_6C], r15d
0x18004e051  jz      short loc_18004E05D
0x18004e053  lea     r9, [rsp+0F8h+var_78]
0x18004e05b  jmp     short loc_18004E060
0x18004e05d  xor     r9d, r9d
0x18004e060  lea     rax, [rsp+0F8h+var_B0]
0x18004e065  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x18004e06a  lea     r8, [rsp+0F8h+var_88]
0x18004e06f  lea     rdx, byte_18008372D
0x18004e076  lea     rcx, dword_180094048
0x18004e07d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004e082  lea     r8, [rsp+0F8h+var_A0]
0x18004e087  lea     rdx, aStartingReques_1; "Starting request to SetResource. resour"...
0x18004e08e  call    ??$Log@AEAPEBD@@YAXW4CDPLogLevel@@PEBDAEAPEBD@Z; Log<char const * &>(CDPLogLevel,char const *,char const * &)
0x18004e093  nop
0x18004e094  mov     [rsp+0F8h+var_B8], 0
0x18004e09d  lea     rcx, [rsp+0F8h+var_B8]
0x18004e0a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e0a7  lea     rcx, [rsp+0F8h+var_B8]
0x18004e0ac  call    cs:__imp_CDPGetResourceHandler
0x18004e0b2  mov     rcx, [rsp+0F8h]; this
0x18004e0ba  test    eax, eax
0x18004e0bc  js      loc_18004E293
0x18004e0c2  mov     rax, [r13+10h]
0x18004e0c6  mov     [rsp+0F8h+var_98], rax
0x18004e0cb  lea     r9, [rsp+0F8h+arg_30]
0x18004e0d3  lea     r8, [rsp+0F8h+arg_8]
0x18004e0db  lea     rdx, [rsp+0F8h+var_98]
0x18004e0e0  lea     rcx, [rsp+0F8h+var_B0]
0x18004e0e5  call    ??$Make@VAppControlResourceHandlerCallback@CDPComAppControlHandler@@PEAUICDPComAppControlSystemHandlerCallback@@AEA_KAEA_K@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppControlResourceHandlerCallback@CDPComAppControlHandler@@@12@$$QEAPEAUICDPComAppControlSystemHandlerCallback@@AEA_K1@Z; Microsoft::WRL::Details::Make<CDPComAppControlHandler::AppControlResourceHandlerCallback,ICDPComAppControlSystemHandlerCallback *,unsigned __int64 &,unsigned __int64 &>(ICDPComAppControlSystemHandlerCallback * &&,unsigned __int64 &,unsigned __int64 &)
0x18004e0ea  nop
0x18004e0eb  mov     qword ptr [rsp+0F8h+var_A8], 0
0x18004e0f4  lea     rdx, [rsp+0F8h+var_A8]
0x18004e0f9  lea     rcx, [rsp+0F8h+var_B0]
0x18004e0fe  call    ??$As@VICDPResourceHandlerCallback@@@?$ComPtr@VAppControlResourceHandlerCallback@CDPComAppControlHandler@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@VICDPResourceHandlerCallback@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<CDPComAppControlHandler::AppControlResourceHandlerCallback>::As<ICDPResourceHandlerCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICDPResourceHandlerCallback>>)
0x18004e103  mov     rcx, [rsp+0F8h]; this
0x18004e10b  test    eax, eax
0x18004e10d  js      loc_18004E2A8
0x18004e113  mov     r8, r12
0x18004e116  mov     rdx, rdi
0x18004e119  lea     rcx, [rsp+0F8h+var_68]
0x18004e121  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD_K@Z; std::string::string(char const * const,unsigned __int64)
0x18004e126  nop
0x18004e127  mov     [rsp+0F8h+var_C0], 0
0x18004e130  lea     rcx, [rsp+0F8h+var_C0]
0x18004e135  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e13a  cmp     dword ptr [rsi], 0
0x18004e13d  setnz   cl
0x18004e140  lea     r8, [rsp+0F8h+var_C0]
0x18004e145  mov     rdx, [rsi+8]
0x18004e149  call    cs:__imp_CDPCreateRemoteUserInternal
0x18004e14f  mov     rcx, [rsp+0F8h]; this
0x18004e157  test    eax, eax
0x18004e159  js      loc_18004E2BD
0x18004e15f  mov     rsi, [rsp+0F8h+var_B8]
0x18004e164  mov     rdi, qword ptr [rsp+0F8h+var_A8]
0x18004e169  mov     rbx, [rsi]
0x18004e16c  lea     rcx, [rsp+0F8h+var_68]
0x18004e174  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004e179  mov     r9, rax
0x18004e17c  mov     qword ptr [rsp+0F8h+var_D8], rdi; int
0x18004e181  mov     r8, [rsp+0F8h+var_A0]
0x18004e186  mov     rdx, [rsp+0F8h+var_C0]
0x18004e18b  mov     rcx, rsi
0x18004e18e  mov     rax, [rbx+28h]
0x18004e192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e197  mov     rcx, [rsp+0F8h]; this
0x18004e19f  test    eax, eax
0x18004e1a1  js      loc_18004E2D1
0x18004e1a7  lea     rcx, [rsp+0F8h+var_C0]
0x18004e1ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e1b1  nop
0x18004e1b2  lea     rcx, [rsp+0F8h+var_68]
0x18004e1ba  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004e1bf  nop
0x18004e1c0  lea     rcx, [rsp+0F8h+var_A8]
0x18004e1c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e1ca  nop
0x18004e1cb  mov     rcx, qword ptr [rsp+0F8h+var_B0]
0x18004e1d0  test    rcx, rcx
0x18004e1d3  jz      short loc_18004E1E2
0x18004e1d5  mov     rax, [rcx]
0x18004e1d8  mov     rax, [rax+10h]
0x18004e1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1e1  nop
0x18004e1e2  lea     rcx, [rsp+0F8h+var_B8]
0x18004e1e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e1ec  nop
0x18004e1ed  jmp     short loc_18004E1F4
0x18004e1ef  mov     r15d, [rsp+0F8h+var_C8]
0x18004e1f4  mov     [rsp+0F8h+var_90], 2
0x18004e1fc  mov     eax, cs:dword_180094048
0x18004e202  cmp     eax, 5
0x18004e205  jbe     short loc_18004E248
0x18004e207  mov     rdx, 400000000000h
0x18004e211  lea     rcx, dword_180094048
0x18004e218  call    _tlgKeywordOn
0x18004e21d  test    al, al
0x18004e21f  jz      short loc_18004E248
0x18004e221  mov     dword ptr [rsp+0F8h+var_C0], r15d
0x18004e226  lea     rax, [rsp+0F8h+var_C0]
0x18004e22b  mov     qword ptr [rsp+0F8h+var_D8], rax
0x18004e230  lea     r8, [rsp+0F8h+var_88]
0x18004e235  lea     rdx, byte_180083709
0x18004e23c  lea     rcx, dword_180094048
0x18004e243  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004e248  lea     r9, [rsp+0F8h+var_C8]
0x18004e24d  lea     r8, [rsp+0F8h+var_A0]
0x18004e252  lea     rdx, aSetresourceReq; "SetResource request complete. ResourceU"...
0x18004e259  mov     ecx, 3
0x18004e25e  call    ??$Log@AEAPEBDAEAJ@@YAXW4CDPLogLevel@@PEBDAEAPEBDAEAJ@Z; Log<char const * &,long &>(CDPLogLevel,char const *,char const * &,long &)
0x18004e263  nop
0x18004e264  lea     rcx, [rsp+0F8h+var_90]
0x18004e269  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004e26e  mov     eax, [rsp+0F8h+var_C8]
0x18004e272  mov     rcx, [rsp+0F8h+var_48]
0x18004e27a  xor     rcx, rsp; StackCookie
0x18004e27d  call    __security_check_cookie
0x18004e282  add     rsp, 0C8h
0x18004e289  pop     r15
0x18004e28b  pop     r13
0x18004e28d  pop     r12
0x18004e28f  pop     rdi
0x18004e290  pop     rsi
0x18004e291  pop     rbx
0x18004e292  retn
0x18004e293  mov     r9d, eax; char *
0x18004e296  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004e29d  mov     edx, 0C8h; void *
0x18004e2a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e2a8  mov     r9d, eax; char *
0x18004e2ab  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004e2b2  mov     edx, 0CBh; void *
0x18004e2b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e2bd  mov     r9d, eax; char *
0x18004e2c0  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004e2c7  mov     edx, 0CEh; void *
0x18004e2cc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e2d1  mov     r9d, eax; char *
0x18004e2d4  lea     r8, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004e2db  mov     edx, 0CFh; void *
0x18004e2e0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
