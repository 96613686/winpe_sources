# ServiceBase::ServiceMain(ulong,ushort const * *)

- ea: `0x18002c188`
- end: `0x18002c3d7`
- name: `?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z`
- size: `591`
- prototype: `__int64 __fastcall(ServiceBase *this, int, const unsigned __int16 **, const char *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x18002b040`

## callees

- `0x18001f588`
- `0x18001f76c`
- `0x18001fab0`
- `0x1800202bc`
- `0x180020cfc`
- `0x180020e24`
- `0x1800212a0`
- `0x1800234f0`
- `0x180026200`
- `0x1800274c8`
- `0x18002b538`
- `0x18002b7b8`
- `0x18002b848`
- `0x18002b93c`
- `0x18002bb44`
- `0x18002bb9c`
- `0x18002bdd8`
- `0x18002c188`
- `0x18002c4dc`
- `0x18002cc44`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002c2a9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002c2a9`

## string_xrefs

- `0x18002c1c5`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18002c286`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18002c2d1`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18002c35c`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18002c1d7`: `ServiceStartActivity`
- `0x18002c2ba`: `Registration of service controller failed`

## pseudocode

```c
__int64 __fastcall ServiceBase::ServiceMain(ServiceBase *this, int a2, const unsigned __int16 **a3, const char *a4)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  int started; // eax
  unsigned int v9; // ebx
  SERVICE_STATUS_HANDLE v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  char *v17; // [rsp+38h] [rbp-C8h] BYREF
  ServiceBase *v18; // [rsp+40h] [rbp-C0h] BYREF
  char v19; // [rsp+48h] [rbp-B8h]
  _QWORD v20[42]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v21[42]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v22[336]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      a4);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "ServiceStartActivity");
  v20[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  v17 = (char *)this + 8;
  v6 = ServiceHostTelemetry::ServiceStartActivity::Start<unsigned short const *>((ServiceHostTelemetry::ServiceStartActivity *)v22);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    v20);
  v21[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
    v20,
    v6);
  ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)v21);
  ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)v22);
  ServiceBase::_ServiceInit(this);
  v7 = StringCchCopyW((unsigned __int16 *)this + 4, 0x20u, *a3);
  started = LogIfStartSrvFailedAndReturnHr(v7, (char *)this + 8, 1);
  v9 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)(unsigned int)started,
      v14);
LABEL_10:
    ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)v20);
    return v9;
  }
  v10 = RegisterServiceCtrlHandlerExW((LPCWSTR)this + 4, ServiceBase::_ServiceCtrlHandler, this);
  *((_QWORD *)this + 9) = v10;
  v15 = (int)v10;
  wil::details::in1diag3::Log_HrIfNullMsg<SERVICE_STATUS_HANDLE__ *,0>(
    retaddr,
    100,
    "onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
    2147942406LL);
  ServiceHostTelemetry::ServiceBaseStatus<unsigned short (&)[32],unsigned short const (&)[9]>(
    (char *)this + 8,
    L"Starting");
  v18 = this;
  v19 = 1;
  v11 = ServiceBase::_ServiceMainInner(this);
  v9 = v11;
  v16 = v11;
  if ( v11 < 0 )
  {
    if ( (v11 & 0x1FFF0000) == 0x70000 )
    {
      *((_DWORD *)this + 27) = (unsigned __int16)v11;
    }
    else
    {
      ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[9],long &>(
        (char *)this + 8,
        v12,
        &v16);
      *((_DWORD *)this + 27) = v9;
    }
    LODWORD(v17) = 2;
    v18 = (ServiceBase *)((char *)this + 8);
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(&v18, &v16, &v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)v9,
      v15);
    ServiceBase::ServiceStop(this);
    goto LABEL_10;
  }
  ServiceHostTelemetry::ServiceBaseStatus<unsigned short (&)[32],unsigned short const (&)[8]>(
    (char *)this + 8,
    L"Started");
  ServiceHostTelemetry::ServiceStartActivity::Stop(
    (ServiceHostTelemetry::ServiceStartActivity *)v20,
    (const unsigned __int16 *)this + 4,
    v9);
  ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)v20);
  return 0;
}

```

## disassembly

```asm
0x18002c188  mov     [rsp-8+arg_8], rbx
0x18002c18d  push    rbp
0x18002c18e  push    rsi
0x18002c18f  push    rdi
0x18002c190  push    r14
0x18002c192  push    r15
0x18002c194  lea     rbp, [rsp-350h]
0x18002c19c  sub     rsp, 450h
0x18002c1a3  mov     rax, cs:__security_cookie
0x18002c1aa  xor     rax, rsp
0x18002c1ad  mov     [rbp+370h+var_30], rax
0x18002c1b4  mov     r14, r8
0x18002c1b7  mov     rdi, rcx
0x18002c1ba  mov     rcx, [rbp+378h]; this
0x18002c1c1  test    edx, edx
0x18002c1c3  jnz     short loc_18002C1D7
0x18002c1c5  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c1cc  mov     edx, 170h; void *
0x18002c1d1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002c1d7  lea     rdx, aServicestartac; "ServiceStartActivity"
0x18002c1de  lea     rcx, [rsp+470h+var_420]
0x18002c1e3  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002c1e8  lea     r15, ??_7ServiceStartActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStartActivity::`vftable'
0x18002c1ef  mov     [rsp+470h+var_420], r15
0x18002c1f4  lea     rsi, [rdi+8]
0x18002c1f8  mov     [rsp+470h+var_438], rsi
0x18002c1fd  lea     rdx, [rsp+470h+var_438]
0x18002c202  lea     rcx, [rbp+370h+var_180]; this
0x18002c209  call    ??$Start@PEBG@ServiceStartActivity@ServiceHostTelemetry@@SA?AV01@$$QEAPEBG@Z; ServiceHostTelemetry::ServiceStartActivity::Start<ushort const *>(ushort const * &&)
0x18002c20e  mov     rbx, rax
0x18002c211  lea     rdx, [rsp+470h+var_420]
0x18002c216  lea     rcx, [rbp+370h+var_2D0]
0x18002c21d  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x18002c222  mov     [rbp+370h+var_2D0], r15
0x18002c229  mov     rdx, rbx
0x18002c22c  lea     rcx, [rsp+470h+var_420]
0x18002c231  call    ??4?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x18002c236  lea     rcx, [rbp+370h+var_2D0]; this
0x18002c23d  call    ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x18002c242  lea     rcx, [rbp+370h+var_180]; this
0x18002c249  call    ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x18002c24e  mov     rcx, rdi; this
0x18002c251  call    ?_ServiceInit@ServiceBase@@AEAAXXZ; ServiceBase::_ServiceInit(void)
0x18002c256  mov     r8, [r14]; unsigned __int16 *
0x18002c259  mov     edx, 20h ; ' '; unsigned __int64
0x18002c25e  mov     rcx, rsi; unsigned __int16 *
0x18002c261  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c266  mov     r8d, 1
0x18002c26c  mov     rdx, rsi
0x18002c26f  mov     ecx, eax
0x18002c271  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18002c276  mov     ebx, eax
0x18002c278  test    eax, eax
0x18002c27a  jns     short loc_18002C29C
0x18002c27c  mov     rcx, [rbp+378h]; this
0x18002c283  mov     r9d, eax; char *
0x18002c286  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c28d  mov     edx, 17Ch; void *
0x18002c292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c297  jmp     loc_18002C377
0x18002c29c  mov     r8, rdi; lpContext
0x18002c29f  lea     rdx, ?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z; lpHandlerProc
0x18002c2a6  mov     rcx, rsi; lpServiceName
0x18002c2a9  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002c2af  mov     [rdi+48h], rax
0x18002c2b3  mov     rcx, [rbp+378h]
0x18002c2ba  lea     rdx, aRegistrationOf; "Registration of service controller fail"...
0x18002c2c1  mov     [rsp+470h+var_448], rdx
0x18002c2c6  mov     qword ptr [rsp+470h+var_450], rax; int
0x18002c2cb  mov     r9d, 80070006h
0x18002c2d1  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c2d8  mov     edx, 64h ; 'd'
0x18002c2dd  call    ??$Log_HrIfNullMsg@PEAUSERVICE_STATUS_HANDLE__@@$0A@@in1diag3@details@wil@@YAPEAUSERVICE_STATUS_HANDLE__@@PEAXIPEBDJPEAU3@1ZZ; wil::details::in1diag3::Log_HrIfNullMsg<SERVICE_STATUS_HANDLE__ *,0>(void *,uint,char const *,long,SERVICE_STATUS_HANDLE__ *,char const *,...)
0x18002c2e2  lea     rdx, aStarting; "Starting"
0x18002c2e9  mov     rcx, rsi
0x18002c2ec  call    ??$ServiceBaseStatus@AEAY0CA@GAEAY08$$CBG@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY08$$CBG@Z; ServiceHostTelemetry::ServiceBaseStatus<ushort (&)[32],ushort const (&)[9]>(ushort (&)[32],ushort const (&)[9])
0x18002c2f1  mov     [rsp+470h+var_430], rdi
0x18002c2f6  mov     [rsp+470h+var_428], 1
0x18002c2fb  mov     rcx, rdi; this
0x18002c2fe  call    ?_ServiceMainInner@ServiceBase@@AEAAJXZ; ServiceBase::_ServiceMainInner(void)
0x18002c303  mov     ebx, eax
0x18002c305  mov     [rsp+470h+var_440], eax
0x18002c309  test    eax, eax
0x18002c30b  jns     short loc_18002C385
0x18002c30d  and     eax, 1FFF0000h
0x18002c312  cmp     eax, 70000h
0x18002c317  jnz     short loc_18002C321
0x18002c319  movzx   eax, bx
0x18002c31c  mov     [rdi+6Ch], eax
0x18002c31f  jmp     short loc_18002C331
0x18002c321  lea     r8, [rsp+470h+var_440]
0x18002c326  mov     rcx, rsi
0x18002c329  call    ??$ServiceBaseError@AEAY0CA@GAEAY08$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY08$$CBGAEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[9],long &>(ushort (&)[32],ushort const (&)[9],long &)
0x18002c32e  mov     [rdi+6Ch], ebx
0x18002c331  mov     dword ptr [rsp+470h+var_438], 2
0x18002c339  mov     [rsp+470h+var_430], rsi
0x18002c33e  lea     r8, [rsp+470h+var_438]
0x18002c343  lea     rdx, [rsp+470h+var_440]
0x18002c348  lea     rcx, [rsp+470h+var_430]
0x18002c34d  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x18002c352  mov     rcx, [rbp+378h]; this
0x18002c359  mov     r9d, ebx; char *
0x18002c35c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002c363  mov     edx, 1A1h; void *
0x18002c368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c36d  nop
0x18002c36e  mov     rcx, rdi; this
0x18002c371  call    ?ServiceStop@ServiceBase@@QEAAXXZ; ServiceBase::ServiceStop(void)
0x18002c376  nop
0x18002c377  lea     rcx, [rsp+470h+var_420]; this
0x18002c37c  call    ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x18002c381  mov     eax, ebx
0x18002c383  jmp     short loc_18002C3B1
0x18002c385  lea     rdx, aStarted; "Started"
0x18002c38c  mov     rcx, rsi
0x18002c38f  call    ??$ServiceBaseStatus@AEAY0CA@GAEAY07$$CBG@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY07$$CBG@Z; ServiceHostTelemetry::ServiceBaseStatus<ushort (&)[32],ushort const (&)[8]>(ushort (&)[32],ushort const (&)[8])
0x18002c394  mov     r8d, ebx; int
0x18002c397  mov     rdx, rsi; unsigned __int16 *
0x18002c39a  lea     rcx, [rsp+470h+var_420]; this
0x18002c39f  call    ?Stop@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z; ServiceHostTelemetry::ServiceStartActivity::Stop(ushort const *,long)
0x18002c3a4  nop
0x18002c3a5  lea     rcx, [rsp+470h+var_420]; this
0x18002c3aa  call    ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x18002c3af  xor     eax, eax
0x18002c3b1  mov     rcx, [rbp+370h+var_30]
0x18002c3b8  xor     rcx, rsp; StackCookie
0x18002c3bb  call    __security_check_cookie
0x18002c3c0  mov     rbx, [rsp+470h+arg_8]
0x18002c3c8  add     rsp, 450h
0x18002c3cf  pop     r15
0x18002c3d1  pop     r14
0x18002c3d3  pop     rdi
0x18002c3d4  pop     rsi
0x18002c3d5  pop     rbp
0x18002c3d6  retn
```
