# ServiceBase::_ServiceMainInner(void)

- ea: `0x18001fab0`
- end: `0x18001fd87`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `727`
- prototype: `__int64 __fastcall(ServiceBase *this, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002c188`

## callees

- `0x18001fab0`
- `0x18002012c`
- `0x1800201c8`
- `0x1800202bc`
- `0x180020344`
- `0x180020cfc`
- `0x1800212a0`
- `0x1800225c8`
- `0x180023efc`
- `0x180026200`
- `0x1800274c8`
- `0x18002b728`
- `0x18002b7b8`
- `0x18002b93c`
- `0x18002b9d4`
- `0x18002bdd8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001fb81`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001fb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb8f`

## string_xrefs

- `0x18001fb21`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18001fb60`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18001fbd5`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18001fd3c`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this, __int64 a2, __int64 a3, const char *a4)
{
  char *v5; // r14
  unsigned int v6; // eax
  int started; // esi
  __int64 v8; // rdx
  wil::details *v10; // rcx
  HANDLE Event; // rsi
  unsigned int v12; // esi
  int LastErrorFailHr; // eax
  unsigned int updated; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  unsigned int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+24h] [rbp-DCh] BYREF
  char *v25; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v26[336]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v5 = (char *)this + 8;
  if ( !*((_QWORD *)this + 22) )
  {
    v23 = 3;
    v24 = -2147023537;
    v25 = (char *)this + 8;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long,unsigned int>(&v25, &v24, &v23);
  }
  if ( !*((_QWORD *)this + 22) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x201,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      a4);
  v6 = ServiceBase::_CheckServiceShutdownAlready(this);
  started = LogIfStartSrvFailedAndReturnHr(v6, v5, 4);
  if ( started < 0 )
  {
    v8 = 518;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)(unsigned int)started,
      v23);
    return (unsigned int)started;
  }
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 80,
      Event);
LABEL_11:
    v12 = 0;
    goto LABEL_12;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
  v12 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_11;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x50,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
    (const char *)(unsigned int)LastErrorFailHr,
    v23);
LABEL_12:
  started = LogIfStartSrvFailedAndReturnHr(v12, v5, 5);
  if ( started < 0 )
  {
    v8 = 520;
    goto LABEL_7;
  }
  updated = ServiceBase::_UpdateStatus(this, 2u);
  started = LogIfStartSrvFailedAndReturnHr(updated, v5, 6);
  if ( started < 0 )
  {
    v8 = 524;
    goto LABEL_7;
  }
  v25 = v5;
  ServiceHostTelemetry::ServiceStartActivity::Start<unsigned short const *>((ServiceHostTelemetry::ServiceStartActivity *)v26);
  started = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 8LL))(this);
  v23 = started;
  if ( started < 0 )
  {
    ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[9],long &>(v5, v15, &v23);
    v24 = 7;
    v25 = v5;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(&v25, &v23, &v24);
    v16 = (unsigned int)started;
    v17 = 537;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)v16,
      v23);
    ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)v26);
    return (unsigned int)started;
  }
  *((_DWORD *)this + 31) = 1;
  v18 = ServiceBase::_UpdateStatus(this, 4u);
  v19 = LogIfStartSrvFailedAndReturnHr(v18, v5, 8);
  started = v19;
  if ( v19 < 0 )
  {
    v17 = 545;
LABEL_26:
    v16 = (unsigned int)v19;
    goto LABEL_27;
  }
  v20 = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 24LL))(this);
  started = v20;
  v23 = v20;
  if ( v20 < 0 )
  {
    ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[8],long &>(v5, v21, &v23);
    v24 = 9;
    v25 = v5;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(&v25, &v23, &v24);
    v16 = (unsigned int)started;
    v17 = 558;
    goto LABEL_27;
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v26,
    (unsigned int)v20);
  v22 = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 104LL))(this);
  v19 = LogIfStartSrvFailedAndReturnHr(v22, v5, 10);
  started = v19;
  if ( v19 < 0 )
  {
    v17 = 570;
    goto LABEL_26;
  }
  ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)v26);
  return 0;
}

```

## disassembly

```asm
0x18001fab0  push    rbp
0x18001fab2  push    rsi
0x18001fab3  push    rdi
0x18001fab4  push    r14
0x18001fab6  lea     rbp, [rsp-98h]
0x18001fabe  sub     rsp, 198h
0x18001fac5  mov     rax, cs:__security_cookie
0x18001facc  xor     rax, rsp
0x18001facf  mov     [rbp+0B0h+var_30], rax
0x18001fad6  mov     rdi, rcx
0x18001fad9  lea     r14, [rcx+8]
0x18001fadd  cmp     qword ptr [rcx+0B0h], 0
0x18001fae5  jnz     short loc_18001FB10
0x18001fae7  mov     [rsp+1B0h+var_190], 3; int
0x18001faef  mov     [rsp+1B0h+var_18C], 8007054Fh
0x18001faf7  mov     [rsp+1B0h+var_188], r14
0x18001fafc  lea     r8, [rsp+1B0h+var_190]
0x18001fb01  lea     rdx, [rsp+1B0h+var_18C]
0x18001fb06  lea     rcx, [rsp+1B0h+var_188]
0x18001fb0b  call    ??$ServiceStartFailure@PEBGJI@ServiceHostTelemetry@@SAX$$QEAPEBG$$QEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long,uint>(ushort const * &&,long &&,uint &&)
0x18001fb10  mov     rcx, [rbp+0B8h]; this
0x18001fb17  cmp     qword ptr [rdi+0B0h], 0
0x18001fb1f  jnz     short loc_18001FB33
0x18001fb21  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001fb28  mov     edx, 201h; void *
0x18001fb2d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001fb33  mov     rcx, rdi; this
0x18001fb36  call    ?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ; ServiceBase::_CheckServiceShutdownAlready(void)
0x18001fb3b  mov     r8d, 4
0x18001fb41  mov     rdx, r14
0x18001fb44  mov     ecx, eax
0x18001fb46  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001fb4b  mov     esi, eax
0x18001fb4d  test    eax, eax
0x18001fb4f  jns     short loc_18001FB73
0x18001fb51  mov     edx, 206h; void *
0x18001fb56  mov     rcx, [rbp+0B8h]; this
0x18001fb5d  mov     r9d, esi; char *
0x18001fb60  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001fb67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb6c  mov     eax, esi
0x18001fb6e  jmp     loc_18001FD6B
0x18001fb73  xor     edx, edx; lpName
0x18001fb75  xor     ecx, ecx; lpEventAttributes
0x18001fb77  mov     r9d, 1F0003h; dwDesiredAccess
0x18001fb7d  lea     r8d, [rdx+1]; dwFlags
0x18001fb81  call    cs:__imp_CreateEventExW
0x18001fb87  mov     rsi, rax
0x18001fb8a  test    rax, rax
0x18001fb8d  jz      short loc_18001FBC0
0x18001fb8f  call    cs:__imp_GetLastError
0x18001fb95  lea     rcx, [rdi+50h]
0x18001fb99  mov     rdx, rsi
0x18001fb9c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001fba1  xor     esi, esi
0x18001fba3  mov     r8d, 5
0x18001fba9  mov     rdx, r14
0x18001fbac  mov     ecx, esi
0x18001fbae  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001fbb3  mov     esi, eax
0x18001fbb5  test    eax, eax
0x18001fbb7  jns     short loc_18001FBE8
0x18001fbb9  mov     edx, 208h
0x18001fbbe  jmp     short loc_18001FB56
0x18001fbc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001fbc5  mov     esi, eax
0x18001fbc7  test    eax, eax
0x18001fbc9  jns     short loc_18001FBA1
0x18001fbcb  mov     rcx, [rbp+0B8h]; this
0x18001fbd2  mov     r9d, eax; char *
0x18001fbd5  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001fbdc  mov     edx, 50h ; 'P'; void *
0x18001fbe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fbe6  jmp     short loc_18001FBA3
0x18001fbe8  mov     edx, 2; unsigned int
0x18001fbed  mov     rcx, rdi; this
0x18001fbf0  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18001fbf5  mov     r8d, 6
0x18001fbfb  mov     rdx, r14
0x18001fbfe  mov     ecx, eax
0x18001fc00  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001fc05  mov     esi, eax
0x18001fc07  test    eax, eax
0x18001fc09  jns     short loc_18001FC15
0x18001fc0b  mov     edx, 20Ch
0x18001fc10  jmp     loc_18001FB56
0x18001fc15  mov     [rsp+1B0h+var_188], r14
0x18001fc1a  lea     rdx, [rsp+1B0h+var_188]
0x18001fc1f  lea     rcx, [rsp+1B0h+var_180]; this
0x18001fc24  call    ??$Start@PEBG@ServiceStartActivity@ServiceHostTelemetry@@SA?AV01@$$QEAPEBG@Z; ServiceHostTelemetry::ServiceStartActivity::Start<ushort const *>(ushort const * &&)
0x18001fc29  nop
0x18001fc2a  mov     rax, [rdi]
0x18001fc2d  mov     rcx, rdi
0x18001fc30  mov     rax, [rax+8]
0x18001fc34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc39  mov     esi, eax
0x18001fc3b  mov     [rsp+1B0h+var_190], eax
0x18001fc3f  test    eax, eax
0x18001fc41  jns     short loc_18001FC7E
0x18001fc43  lea     r8, [rsp+1B0h+var_190]
0x18001fc48  mov     rcx, r14
0x18001fc4b  call    ??$ServiceBaseError@AEAY0CA@GAEAY08$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY08$$CBGAEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[9],long &>(ushort (&)[32],ushort const (&)[9],long &)
0x18001fc50  mov     [rsp+1B0h+var_18C], 7
0x18001fc58  mov     [rsp+1B0h+var_188], r14
0x18001fc5d  lea     r8, [rsp+1B0h+var_18C]
0x18001fc62  lea     rdx, [rsp+1B0h+var_190]
0x18001fc67  lea     rcx, [rsp+1B0h+var_188]
0x18001fc6c  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x18001fc71  mov     r9d, esi
0x18001fc74  mov     edx, 219h
0x18001fc79  jmp     loc_18001FD3C
0x18001fc7e  mov     dword ptr [rdi+7Ch], 1
0x18001fc85  mov     edx, 4; unsigned int
0x18001fc8a  mov     rcx, rdi; this
0x18001fc8d  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18001fc92  mov     r8d, 8
0x18001fc98  mov     rdx, r14
0x18001fc9b  mov     ecx, eax
0x18001fc9d  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001fca2  mov     esi, eax
0x18001fca4  test    eax, eax
0x18001fca6  jns     short loc_18001FCB2
0x18001fca8  mov     edx, 221h
0x18001fcad  jmp     loc_18001FD39
0x18001fcb2  mov     rax, [rdi]
0x18001fcb5  mov     rcx, rdi
0x18001fcb8  mov     rax, [rax+18h]
0x18001fcbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcc1  mov     esi, eax
0x18001fcc3  mov     [rsp+1B0h+var_190], eax; int
0x18001fcc7  test    eax, eax
0x18001fcc9  jns     short loc_18001FD03
0x18001fccb  lea     r8, [rsp+1B0h+var_190]
0x18001fcd0  mov     rcx, r14
0x18001fcd3  call    ??$ServiceBaseError@AEAY0CA@GAEAY07$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY07$$CBGAEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[8],long &>(ushort (&)[32],ushort const (&)[8],long &)
0x18001fcd8  mov     [rsp+1B0h+var_18C], 9
0x18001fce0  mov     [rsp+1B0h+var_188], r14
0x18001fce5  lea     r8, [rsp+1B0h+var_18C]
0x18001fcea  lea     rdx, [rsp+1B0h+var_190]
0x18001fcef  lea     rcx, [rsp+1B0h+var_188]
0x18001fcf4  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x18001fcf9  mov     r9d, esi
0x18001fcfc  mov     edx, 22Eh
0x18001fd01  jmp     short loc_18001FD3C
0x18001fd03  mov     edx, esi
0x18001fd05  lea     rcx, [rsp+1B0h+var_180]
0x18001fd0a  call    ?Stop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001fd0f  mov     rax, [rdi]
0x18001fd12  mov     rcx, rdi
0x18001fd15  mov     rax, [rax+68h]
0x18001fd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd1e  mov     r8d, 0Ah
0x18001fd24  mov     rdx, r14
0x18001fd27  mov     ecx, eax
0x18001fd29  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001fd2e  mov     esi, eax
0x18001fd30  test    eax, eax
0x18001fd32  jns     short loc_18001FD5F
0x18001fd34  mov     edx, 23Ah; void *
0x18001fd39  mov     r9d, eax; char *
0x18001fd3c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001fd43  mov     rcx, [rbp+0B8h]; this
0x18001fd4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd4f  nop
0x18001fd50  lea     rcx, [rsp+1B0h+var_180]; this
0x18001fd55  call    ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x18001fd5a  jmp     loc_18001FB6C
0x18001fd5f  lea     rcx, [rsp+1B0h+var_180]; this
0x18001fd64  call    ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x18001fd69  xor     eax, eax
0x18001fd6b  mov     rcx, [rbp+0B0h+var_30]
0x18001fd72  xor     rcx, rsp; StackCookie
0x18001fd75  call    __security_check_cookie
0x18001fd7a  add     rsp, 198h
0x18001fd81  pop     r14
0x18001fd83  pop     rdi
0x18001fd84  pop     rsi
0x18001fd85  pop     rbp
0x18001fd86  retn
```
