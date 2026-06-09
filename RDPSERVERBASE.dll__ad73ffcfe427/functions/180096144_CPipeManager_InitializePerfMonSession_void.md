# CPipeManager::InitializePerfMonSession(void)

- ea: `0x180096144`
- end: `0x180096747`
- name: `?InitializePerfMonSession@CPipeManager@@IEAAJXZ`
- size: `1539`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180094a60`

## callees

- `0x180001574`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180051870`
- `0x18007e9e0`
- `0x180096144`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGlobalObject` at `0x1800961b4`
- `RDPBASE!RDPAPI_GetGlobalObject` at `0x1800961b4`
- `OLEAUT32!__imp_VariantInit` at `0x180096185`
- `OLEAUT32!__imp_VariantInit` at `0x18009619c`
- `OLEAUT32!__imp_VariantInit` at `0x180096185`
- `OLEAUT32!__imp_VariantInit` at `0x18009619c`
- `OLEAUT32!__imp_VariantClear` at `0x1800966fd`
- `OLEAUT32!__imp_VariantClear` at `0x180096707`
- `OLEAUT32!__imp_VariantClear` at `0x1800966fd`
- `OLEAUT32!__imp_VariantClear` at `0x180096707`

## string_xrefs

- `0x180096305`: `Failed to create PerfMon log session. Non-critical error.`
- `0x180096637`: `Failed to create PerfMon log session. Non-critical error.`
- `0x1800963a7`: `Created Perfmon log session`
- `0x1800966cb`: `Created Perfmon log session`
- `0x180096414`: `Failed to get property RDP_PROPERTY_PROTOCOL_NAME`
- `0x180096584`: `failed to create an session instance name for perf counter`

## pseudocode

```c
__int64 __fastcall CPipeManager::InitializePerfMonSession(CPipeManager *this)
{
  int GlobalObject; // eax
  int v3; // r8d
  int v4; // r9d
  int v5; // ebx
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rcx
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v27; // [rsp+54h] [rbp-ACh] BYREF
  const char *v28; // [rsp+58h] [rbp-A8h] BYREF
  const char *pcVal; // [rsp+60h] [rbp-A0h] BYREF
  const char *v30; // [rsp+68h] [rbp-98h] BYREF
  const char *v31; // [rsp+70h] [rbp-90h] BYREF
  const char *v32; // [rsp+78h] [rbp-88h] BYREF
  const char *v33; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v35; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v37[264]; // [rsp+C0h] [rbp-40h] BYREF

  v34 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  memset(&v35, 0, sizeof(v35));
  VariantInit(&v35);
  GlobalObject = RDPAPI_GetGlobalObject(&CLSID_RDPPlatformPerfMonLogger, &IID_IRdpPerfMonLogger, &v34);
  v5 = GlobalObject;
  if ( GlobalObject >= 0 )
  {
    if ( !v34 )
      goto LABEL_33;
    v33 = (char *)this + 48896;
    CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
    if ( *((_QWORD *)this + 1637) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 13096);
      *((_QWORD *)this + 1637) = 0;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 13096);
    }
    v6 = *((_QWORD *)this + 1627);
    if ( !v6 )
      goto LABEL_32;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v6 + 24LL))(
           v6,
           L"GfxPipeline::RdpPerfMonInstanceName",
           &v35) >= 0
      && v35.vt == 8 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, LONGLONG, char *))(*(_QWORD *)v34 + 24LL))(
             v34,
             0,
             v35.llVal,
             (char *)this + 13096);
      if ( v5 >= 0 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          pcVal = v35.pcVal;
          v28 = "Created Perfmon log session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v7,
            (unsigned int)&dword_180275B54,
            v8,
            v9,
            (__int64)&v28,
            (__int64)&pcVal);
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v26 = 9039;
        v28 = "Failed to create PerfMon log session. Non-critical error.";
        v27 = v5;
        v31 = "InitializePerfMonSession";
        v30 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        pcVal = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v7,
          (unsigned int)&dword_180275B84,
          v8,
          v9,
          (__int64)&pcVal,
          (__int64)&v27,
          (__int64)&v30,
          (__int64)&v26,
          (__int64)&v31,
          (__int64)&v28);
      }
    }
    else
    {
      v10 = *((_QWORD *)this + 1627);
      v27 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v10 + 24LL))(
              v10,
              L"RDP::TerminalName",
              &pvarg);
      v5 = v11;
      if ( pvarg.vt == 8 )
      {
        if ( v11 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *))(**((_QWORD **)this + 1627) + 40LL))(
                 *((_QWORD *)this + 1627),
                 L"ConnectionID",
                 &v27);
          if ( v5 >= 0 )
          {
            v5 = StringCchPrintfW(v37, 0x104u, L"%s %d", pvarg.llVal, v27);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, char *))(*(_QWORD *)v34 + 24LL))(
                     v34,
                     v27,
                     v37,
                     (char *)this + 13096);
              if ( v5 >= 0 )
              {
                if ( (unsigned int)CallbackContext > 4 )
                {
                  v32 = (const char *)v37;
                  pcVal = "Created Perfmon log session";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                    v21,
                    (unsigned int)&dword_1802759EC,
                    v22,
                    v23,
                    (__int64)&pcVal,
                    (__int64)&v32);
                }
              }
              else if ( (unsigned int)CallbackContext > 2 )
              {
                LODWORD(v30) = 9062;
                v32 = "Failed to create PerfMon log session. Non-critical error.";
                v26 = v5;
                pcVal = "InitializePerfMonSession";
                v28 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
                v31 = "Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v21,
                  (unsigned int)&dword_180275A1C,
                  v22,
                  v23,
                  (__int64)&v31,
                  (__int64)&v26,
                  (__int64)&v28,
                  (__int64)&v30,
                  (__int64)&pcVal,
                  (__int64)&v32);
              }
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v30) = 9059;
              v32 = "failed to create an session instance name for perf counter";
              v26 = v5;
              pcVal = "InitializePerfMonSession";
              v28 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
              v31 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v18,
                (unsigned int)word_180275A6A,
                v19,
                v20,
                (__int64)&v31,
                (__int64)&v26,
                (__int64)&v28,
                (__int64)&v30,
                (__int64)&pcVal,
                (__int64)&v32);
            }
          }
          else if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v30) = 9056;
            v32 = "Failed to get property CONN_PROPERTY_CONNECTION_ID";
            v26 = v5;
            pcVal = "InitializePerfMonSession";
            v28 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            v31 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v15,
              (unsigned int)qword_180275AB8,
              v16,
              v17,
              (__int64)&v31,
              (__int64)&v26,
              (__int64)&v28,
              (__int64)&v30,
              (__int64)&pcVal,
              (__int64)&v32);
          }
          goto LABEL_32;
        }
      }
      else
      {
        v5 = -2147467259;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        v26 = 9053;
        pcVal = "Failed to get property RDP_PROPERTY_PROTOCOL_NAME";
        LODWORD(v30) = v5;
        v28 = "InitializePerfMonSession";
        v31 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v32 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v12,
          (unsigned int)&word_180275B06,
          v13,
          v14,
          (__int64)&v32,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v26,
          (__int64)&v28,
          (__int64)&pcVal);
      }
    }
LABEL_32:
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v33);
    goto LABEL_33;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v27 = 9021;
    v33 = "Failed to get PerfMon logger";
    v26 = GlobalObject;
    v30 = "InitializePerfMonSession";
    v31 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v28 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)word_180275BD2,
      v3,
      v4,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v31,
      (__int64)&v27,
      (__int64)&v30,
      (__int64)&v33);
  }
LABEL_33:
  VariantClear(&pvarg);
  VariantClear(&v35);
  v24 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180096144  push    rbp
0x180096146  push    rbx
0x180096147  push    rsi
0x180096148  push    rdi
0x180096149  lea     rbp, [rsp-1E8h]
0x180096151  sub     rsp, 2E8h
0x180096158  mov     rax, cs:__security_cookie
0x18009615f  xor     rax, rsp
0x180096162  mov     [rbp+200h+var_30], rax
0x180096169  mov     rsi, rcx
0x18009616c  mov     [rbp+200h+var_278], 0
0x180096174  xorps   xmm0, xmm0
0x180096177  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18009617b  xor     eax, eax
0x18009617d  movups  xmmword ptr [rbp+200h+pvarg], xmm0
0x180096181  mov     qword ptr [rbp+200h+pvarg+10h], rax
0x180096185  call    cs:__imp_VariantInit
0x18009618b  xorps   xmm0, xmm0
0x18009618e  lea     rcx, [rbp+200h+var_270]; pvarg
0x180096192  xor     eax, eax
0x180096194  movups  xmmword ptr [rbp+200h+var_270], xmm0
0x180096198  mov     qword ptr [rbp+200h+var_270+10h], rax
0x18009619c  call    cs:__imp_VariantInit
0x1800961a2  lea     r8, [rbp+200h+var_278]
0x1800961a6  lea     rdx, IID_IRdpPerfMonLogger
0x1800961ad  lea     rcx, CLSID_RDPPlatformPerfMonLogger
0x1800961b4  call    cs:__imp_RDPAPI_GetGlobalObject
0x1800961ba  mov     ebx, eax
0x1800961bc  test    eax, eax
0x1800961be  jns     loc_18009625A
0x1800961c4  mov     ecx, cs:CallbackContext
0x1800961ca  cmp     ecx, 2
0x1800961cd  jbe     loc_1800966F9
0x1800961d3  lea     rax, aFailedToGetPer_0; "Failed to get PerfMon logger"
0x1800961da  mov     [rsp+300h+var_2AC], 233Dh
0x1800961e2  mov     [rbp+200h+var_280], rax
0x1800961e6  lea     rdx, word_180275BD2
0x1800961ed  lea     rax, aInitializeperf; "InitializePerfMonSession"
0x1800961f4  mov     [rsp+300h+var_2B0], ebx
0x1800961f8  mov     [rsp+300h+var_298], rax
0x1800961fd  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180096204  mov     [rsp+300h+var_290], rax
0x180096209  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180096210  mov     [rsp+300h+var_2A8], rax
0x180096215  lea     rax, [rbp+200h+var_280]
0x180096219  mov     [rsp+300h+var_2B8], rax
0x18009621e  lea     rax, [rsp+300h+var_298]
0x180096223  mov     [rsp+300h+var_2C0], rax
0x180096228  lea     rax, [rsp+300h+var_2AC]
0x18009622d  mov     [rsp+300h+var_2C8], rax
0x180096232  lea     rax, [rsp+300h+var_290]
0x180096237  mov     [rsp+300h+var_2D0], rax
0x18009623c  lea     rax, [rsp+300h+var_2B0]
0x180096241  mov     [rsp+300h+var_2D8], rax
0x180096246  lea     rax, [rsp+300h+var_2A8]
0x18009624b  mov     [rsp+300h+var_2E0], rax
0x180096250  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180096255  jmp     loc_1800966F9
0x18009625a  cmp     [rbp+200h+var_278], 0
0x18009625f  jz      loc_1800966F9
0x180096265  lea     rcx, [rsi+0BF00h]; this
0x18009626c  mov     [rbp+200h+var_280], rcx
0x180096270  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180096275  lea     rdi, [rsi+3328h]
0x18009627c  cmp     qword ptr [rdi], 0
0x180096280  jz      short loc_180096299
0x180096282  mov     rcx, rdi
0x180096285  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009628a  mov     rcx, rdi
0x18009628d  mov     qword ptr [rdi], 0
0x180096294  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180096299  mov     rcx, [rsi+32D8h]
0x1800962a0  test    rcx, rcx
0x1800962a3  jz      loc_1800966F0
0x1800962a9  mov     rax, [rcx]
0x1800962ac  lea     r8, [rbp+200h+var_270]
0x1800962b0  lea     rdx, aGfxpipelineRdp; "GfxPipeline::RdpPerfMonInstanceName"
0x1800962b7  mov     rax, [rax+18h]
0x1800962bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962c0  test    eax, eax
0x1800962c2  js      loc_1800963C7
0x1800962c8  cmp     word ptr [rbp+200h+var_270], 8
0x1800962cd  jnz     loc_1800963C7
0x1800962d3  mov     rcx, [rbp+200h+var_278]
0x1800962d7  mov     r9, rdi
0x1800962da  mov     r8, qword ptr [rbp+200h+var_270+8]
0x1800962de  xor     edx, edx
0x1800962e0  mov     rax, [rcx]
0x1800962e3  mov     rax, [rax+18h]
0x1800962e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962ec  mov     ebx, eax
0x1800962ee  test    eax, eax
0x1800962f0  mov     eax, cs:CallbackContext
0x1800962f6  jns     loc_18009638E
0x1800962fc  cmp     eax, 2
0x1800962ff  jbe     loc_1800966F0
0x180096305  lea     rax, aFailedToCreate_129; "Failed to create PerfMon log session. N"...
0x18009630c  mov     [rsp+300h+var_2B0], 234Fh
0x180096314  mov     [rsp+300h+var_2A8], rax
0x180096319  lea     rdx, dword_180275B84
0x180096320  lea     rax, aInitializeperf; "InitializePerfMonSession"
0x180096327  mov     [rsp+300h+var_2AC], ebx
0x18009632b  mov     [rsp+300h+var_290], rax
0x180096330  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180096337  mov     [rsp+300h+var_298], rax
0x18009633c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180096343  mov     [rsp+300h+var_2A0], rax
0x180096348  lea     rax, [rsp+300h+var_2A8]
0x18009634d  mov     [rsp+300h+var_2B8], rax
0x180096352  lea     rax, [rsp+300h+var_290]
0x180096357  mov     [rsp+300h+var_2C0], rax
0x18009635c  lea     rax, [rsp+300h+var_2B0]
0x180096361  mov     [rsp+300h+var_2C8], rax
0x180096366  lea     rax, [rsp+300h+var_298]
0x18009636b  mov     [rsp+300h+var_2D0], rax
0x180096370  lea     rax, [rsp+300h+var_2AC]
0x180096375  mov     [rsp+300h+var_2D8], rax
0x18009637a  lea     rax, [rsp+300h+var_2A0]
0x18009637f  mov     [rsp+300h+var_2E0], rax
0x180096384  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180096389  jmp     loc_1800966F0
0x18009638e  cmp     eax, 4
0x180096391  jbe     loc_1800966F0
0x180096397  mov     rax, qword ptr [rbp+200h+var_270+8]
0x18009639b  lea     rdx, dword_180275B54
0x1800963a2  mov     [rsp+300h+var_2A0], rax
0x1800963a7  lea     rax, aCreatedPerfmon; "Created Perfmon log session"
0x1800963ae  mov     [rsp+300h+var_2A8], rax
0x1800963b3  lea     rax, [rsp+300h+var_2A0]
0x1800963b8  mov     [rsp+300h+var_2D8], rax
0x1800963bd  lea     rax, [rsp+300h+var_2A8]
0x1800963c2  jmp     loc_1800966E6
0x1800963c7  mov     rcx, [rsi+32D8h]
0x1800963ce  lea     r8, [rbp+200h+pvarg]
0x1800963d2  mov     [rsp+300h+var_2AC], 0
0x1800963da  lea     rdx, aRdpTerminalnam; "RDP::TerminalName"
0x1800963e1  mov     rax, [rcx]
0x1800963e4  mov     rax, [rax+18h]
0x1800963e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800963ed  cmp     word ptr [rbp+200h+pvarg], 8
0x1800963f2  mov     ebx, eax
0x1800963f4  jz      short loc_1800963FD
0x1800963f6  mov     ebx, 80004005h
0x1800963fb  jmp     short loc_180096405
0x1800963fd  test    eax, eax
0x1800963ff  jns     loc_180096493
0x180096405  mov     eax, cs:CallbackContext
0x18009640b  cmp     eax, 2
0x18009640e  jbe     loc_1800966F0
0x180096414  lea     rax, aFailedToGetPro_4; "Failed to get property RDP_PROPERTY_PRO"...
0x18009641b  mov     [rsp+300h+var_2B0], 235Dh
0x180096423  mov     [rsp+300h+var_2A0], rax
0x180096428  lea     rdx, word_180275B06
0x18009642f  lea     rax, aInitializeperf; "InitializePerfMonSession"
0x180096436  mov     dword ptr [rsp+300h+var_298], ebx
0x18009643a  mov     [rsp+300h+var_2A8], rax
0x18009643f  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180096446  mov     [rsp+300h+var_290], rax
0x18009644b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180096452  mov     [rsp+300h+var_288], rax
0x180096457  lea     rax, [rsp+300h+var_2A0]
0x18009645c  mov     [rsp+300h+var_2B8], rax
0x180096461  lea     rax, [rsp+300h+var_2A8]
0x180096466  mov     [rsp+300h+var_2C0], rax
0x18009646b  lea     rax, [rsp+300h+var_2B0]
0x180096470  mov     [rsp+300h+var_2C8], rax
0x180096475  lea     rax, [rsp+300h+var_290]
0x18009647a  mov     [rsp+300h+var_2D0], rax
0x18009647f  lea     rax, [rsp+300h+var_298]
0x180096484  mov     [rsp+300h+var_2D8], rax
0x180096489  lea     rax, [rsp+300h+var_288]
0x18009648e  jmp     loc_18009637F
0x180096493  mov     rcx, [rsi+32D8h]
0x18009649a  lea     r8, [rsp+300h+var_2AC]
0x18009649f  lea     rdx, aConnectionid; "ConnectionID"
0x1800964a6  mov     rax, [rcx]
0x1800964a9  mov     rax, [rax+28h]
0x1800964ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800964b2  mov     ebx, eax
0x1800964b4  test    eax, eax
0x1800964b6  jns     loc_18009654A
0x1800964bc  mov     eax, cs:CallbackContext
0x1800964c2  cmp     eax, 2
0x1800964c5  jbe     loc_1800966F0
0x1800964cb  lea     rax, aFailedToGetPro_3; "Failed to get property CONN_PROPERTY_CO"...
0x1800964d2  mov     dword ptr [rsp+300h+var_298], 2360h
0x1800964da  mov     [rsp+300h+var_288], rax
0x1800964df  lea     rdx, qword_180275AB8
0x1800964e6  lea     rax, aInitializeperf; "InitializePerfMonSession"
0x1800964ed  mov     [rsp+300h+var_2B0], ebx
0x1800964f1  mov     [rsp+300h+var_2A0], rax
0x1800964f6  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800964fd  mov     [rsp+300h+var_2A8], rax
0x180096502  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180096509  mov     [rsp+300h+var_290], rax
0x18009650e  lea     rax, [rsp+300h+var_288]
0x180096513  mov     [rsp+300h+var_2B8], rax
0x180096518  lea     rax, [rsp+300h+var_2A0]
0x18009651d  mov     [rsp+300h+var_2C0], rax
0x180096522  lea     rax, [rsp+300h+var_298]
0x180096527  mov     [rsp+300h+var_2C8], rax
0x18009652c  lea     rax, [rsp+300h+var_2A8]
0x180096531  mov     [rsp+300h+var_2D0], rax
0x180096536  lea     rax, [rsp+300h+var_2B0]
0x18009653b  mov     [rsp+300h+var_2D8], rax
0x180096540  lea     rax, [rsp+300h+var_290]
0x180096545  jmp     loc_18009637F
0x18009654a  mov     eax, [rsp+300h+var_2AC]
0x18009654e  lea     r8, aSD; "%s %d"
0x180096555  mov     r9, qword ptr [rbp+200h+pvarg+8]
0x180096559  lea     rcx, [rbp+200h+var_240]; unsigned __int16 *
0x18009655d  mov     edx, 104h; unsigned __int64
0x180096562  mov     dword ptr [rsp+300h+var_2E0], eax
0x180096566  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009656b  mov     ebx, eax
0x18009656d  test    eax, eax
0x18009656f  jns     loc_180096603
0x180096575  mov     eax, cs:CallbackContext
0x18009657b  cmp     eax, 2
0x18009657e  jbe     loc_1800966F0
0x180096584  lea     rax, aFailedToCreate_135; "failed to create an session instance na"...
0x18009658b  mov     dword ptr [rsp+300h+var_298], 2363h
0x180096593  mov     [rsp+300h+var_288], rax
0x180096598  lea     rdx, word_180275A6A
0x18009659f  lea     rax, aInitializeperf; "InitializePerfMonSession"
0x1800965a6  mov     [rsp+300h+var_2B0], ebx
0x1800965aa  mov     [rsp+300h+var_2A0], rax
0x1800965af  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800965b6  mov     [rsp+300h+var_2A8], rax
0x1800965bb  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800965c2  mov     [rsp+300h+var_290], rax
0x1800965c7  lea     rax, [rsp+300h+var_288]
0x1800965cc  mov     [rsp+300h+var_2B8], rax
0x1800965d1  lea     rax, [rsp+300h+var_2A0]
0x1800965d6  mov     [rsp+300h+var_2C0], rax
0x1800965db  lea     rax, [rsp+300h+var_298]
0x1800965e0  mov     [rsp+300h+var_2C8], rax
0x1800965e5  lea     rax, [rsp+300h+var_2A8]
0x1800965ea  mov     [rsp+300h+var_2D0], rax
0x1800965ef  lea     rax, [rsp+300h+var_2B0]
0x1800965f4  mov     [rsp+300h+var_2D8], rax
0x1800965f9  lea     rax, [rsp+300h+var_290]
0x1800965fe  jmp     loc_18009637F
0x180096603  mov     rcx, [rbp+200h+var_278]
0x180096607  lea     r8, [rbp+200h+var_240]
0x18009660b  mov     edx, [rsp+300h+var_2AC]
0x18009660f  mov     r9, rdi
0x180096612  mov     rax, [rcx]
0x180096615  mov     rax, [rax+18h]
0x180096619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009661e  mov     ebx, eax
0x180096620  test    eax, eax
0x180096622  mov     eax, cs:CallbackContext
0x180096628  jns     loc_1800966B6
0x18009662e  cmp     eax, 2
0x180096631  jbe     loc_1800966F0
0x180096637  lea     rax, aFailedToCreate_129; "Failed to create PerfMon log session. N"...
0x18009663e  mov     dword ptr [rsp+300h+var_298], 2366h
0x180096646  mov     [rsp+300h+var_288], rax
0x18009664b  lea     rdx, dword_180275A1C
0x180096652  lea     rax, aInitializeperf; "InitializePerfMonSession"
0x180096659  mov     [rsp+300h+var_2B0], ebx
0x18009665d  mov     [rsp+300h+var_2A0], rax
0x180096662  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180096669  mov     [rsp+300h+var_2A8], rax
0x18009666e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180096675  mov     [rsp+300h+var_290], rax
0x18009667a  lea     rax, [rsp+300h+var_288]
0x18009667f  mov     [rsp+300h+var_2B8], rax
0x180096684  lea     rax, [rsp+300h+var_2A0]
0x180096689  mov     [rsp+300h+var_2C0], rax
0x18009668e  lea     rax, [rsp+300h+var_298]
0x180096693  mov     [rsp+300h+var_2C8], rax
0x180096698  lea     rax, [rsp+300h+var_2A8]
0x18009669d  mov     [rsp+300h+var_2D0], rax
0x1800966a2  lea     rax, [rsp+300h+var_2B0]
0x1800966a7  mov     [rsp+300h+var_2D8], rax
0x1800966ac  lea     rax, [rsp+300h+var_290]
0x1800966b1  jmp     loc_18009637F
0x1800966b6  cmp     eax, 4
0x1800966b9  jbe     short loc_1800966F0
0x1800966bb  lea     rax, [rbp+200h+var_240]
0x1800966bf  mov     [rsp+300h+var_288], rax
0x1800966c4  lea     rdx, dword_1802759EC
0x1800966cb  lea     rax, aCreatedPerfmon; "Created Perfmon log session"
0x1800966d2  mov     [rsp+300h+var_2A0], rax
0x1800966d7  lea     rax, [rsp+300h+var_288]
0x1800966dc  mov     [rsp+300h+var_2D8], rax
0x1800966e1  lea     rax, [rsp+300h+var_2A0]
0x1800966e6  mov     [rsp+300h+var_2E0], rax
0x1800966eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800966f0  lea     rcx, [rbp+200h+var_280]; this
0x1800966f4  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800966f9  lea     rcx, [rbp+200h+pvarg]; pvarg
0x1800966fd  call    cs:__imp_VariantClear
0x180096703  lea     rcx, [rbp+200h+var_270]; pvarg
0x180096707  call    cs:__imp_VariantClear
0x18009670d  mov     rcx, [rbp+200h+var_278]
0x180096711  test    rcx, rcx
0x180096714  jz      short loc_18009672A
  ... truncated ...
```
