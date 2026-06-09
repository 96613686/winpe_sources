# ServiceBase::ServiceMain(ulong,ushort const * *)

- ea: `0x18000e9e8`
- end: `0x18000edb5`
- name: `?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z`
- size: `973`
- prototype: `__int64 __fastcall(ServiceBase *this, int, const unsigned __int16 **, const char *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task`

## callers

- `0x18000d3b0`

## callees

- `0x180001c7c`
- `0x180002bc0`
- `0x18000354c`
- `0x180006244`
- `0x1800071a8`
- `0x180007e58`
- `0x18000a648`
- `0x18000ce34`
- `0x18000d490`
- `0x18000d600`
- `0x18000d9a0`
- `0x18000dc1c`
- `0x18000dcdc`
- `0x18000df78`
- `0x18000e2ec`
- `0x18000e51c`
- `0x18000e9e8`
- `0x18000edbc`
- `0x18000f094`
- `0x18000f628`
- `0x180010444`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000eb47`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000eb47`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000ebed`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000ebed`

## string_xrefs

- `0x18000ea29`: `ServiceStartActivity`
- `0x18000ea4a`: `ServiceStartActivity`
- `0x18000ebca`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18000ec15`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18000ecd5`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18000eda3`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18000ebfe`: `Registration of service controller failed`

## pseudocode

```c
__int64 __fastcall ServiceBase::ServiceMain(ServiceBase *this, int a2, const unsigned __int16 **a3, const char *a4)
{
  void *v6; // rcx
  __int64 v7; // r8
  const char *v8; // r9
  __int64 v9; // rcx
  __int16 *v10; // r8
  __int64 v11; // rdx
  _WORD *v12; // rax
  __int16 v13; // r9
  _WORD *v14; // rcx
  int started; // eax
  unsigned int v16; // ebx
  SERVICE_STATUS_HANDLE v17; // rax
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  const char *v21; // r9
  int v22; // eax
  __int64 v23; // rdx
  const struct _tlgProvider_t *v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  const wchar_t *v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29[2]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v30; // [rsp+40h] [rbp-C0h] BYREF
  char v31; // [rsp+48h] [rbp-B8h]
  _QWORD v32[39]; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+188h] [rbp+88h]
  _QWORD v34[42]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v35[42]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x170,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      a4);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v32,
    (__int64)"ServiceStartActivity");
  v32[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v34,
    (__int64)"ServiceStartActivity");
  v34[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  ServiceHostTelemetry::ServiceStartActivity::StartActivity(
    (ServiceHostTelemetry::ServiceStartActivity *)v34,
    (const unsigned __int16 *)this + 4);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v35,
    (__int64)v32,
    v33 != 0);
  v35[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
    (__int64)v32,
    (__int64)v34);
  v35[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v35);
  v34[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v34);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v34);
  *((_DWORD *)this + 25) = 0;
  *((_DWORD *)this + 24) = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 48LL))(this);
  *((_DWORD *)this + 30) = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 64LL))(this);
  *((_DWORD *)this + 27) = 0;
  *((_DWORD *)this + 29) = 0;
  *((_DWORD *)this + 28) = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 72LL))(this);
  *((_DWORD *)this + 26) = 0;
  memset_0((char *)this + 8, 0, 0x40u);
  *(_QWORD *)((char *)this + 124) = 0;
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 && !ResetEvent(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v7, v8);
  v9 = 2147483646;
  v10 = (__int16 *)*a3;
  v11 = 32;
  v12 = (_WORD *)((char *)this + 8);
  do
  {
    if ( !v9 )
      break;
    v13 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v12++ = v13;
    --v9;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  started = LogIfStartSrvFailedAndReturnHr(v11 == 0 ? 0x8007007A : 0, (__int64)this + 8, 1);
  v16 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17C,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)(unsigned int)started);
LABEL_19:
    v32[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v32);
    return v16;
  }
  v17 = RegisterServiceCtrlHandlerExW((LPCWSTR)this + 4, (LPHANDLER_FUNCTION_EX)ServiceBase::_ServiceCtrlHandler, this);
  *((_QWORD *)this + 9) = v17;
  wil::details::in1diag3::Log_HrIfNullMsg<SERVICE_STATUS_HANDLE__ *,0>(
    (int)retaddr,
    100,
    (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
    -2147024890,
    (__int64)v17,
    (__int64)"Registration of service controller failed");
  v18 = ServiceHostLogging::Provider();
  if ( *(_DWORD *)v18 > 5u )
  {
    v28 = L"Starting";
    *(_QWORD *)v29 = (char *)this + 8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v18,
      (__int64)&byte_1800154E7,
      v20,
      (__int64)v21,
      (__int64 **)v29,
      (__int64 **)&v28);
  }
  v30 = (const wchar_t *)this;
  v31 = 1;
  v22 = ServiceBase::_ServiceMainInner(this, v19, v20, v21);
  v16 = v22;
  v29[0] = v22;
  if ( v22 < 0 )
  {
    if ( (v22 & 0x1FFF0000) == 0x70000 )
    {
      *((_DWORD *)this + 27) = (unsigned __int16)v22;
    }
    else
    {
      ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[9],long &>(
        (__int64)this + 8,
        v23,
        v29);
      *((_DWORD *)this + 27) = v16;
    }
    LODWORD(v28) = 2;
    v30 = (const wchar_t *)((char *)this + 8);
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(
      (__int64 *)&v30,
      v29,
      (int *)&v28);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)v16);
    ServiceBase::ServiceStop(this);
    goto LABEL_19;
  }
  v25 = ServiceHostLogging::Provider();
  if ( *(_DWORD *)v25 > 5u )
  {
    v30 = L"Started";
    v28 = (const wchar_t *)((char *)this + 8);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v25,
      (__int64)&unk_180015478,
      v26,
      v27,
      (__int64 **)&v28,
      (__int64 **)&v30);
  }
  ServiceHostTelemetry::ServiceStartActivity::Stop(
    (ServiceHostTelemetry::ServiceStartActivity *)v32,
    (const unsigned __int16 *)this + 4,
    v16);
  v32[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v32);
  return 0;
}

```

## disassembly

```asm
0x18000e9e8  push    rbp
0x18000e9ea  push    rbx
0x18000e9eb  push    rsi
0x18000e9ec  push    rdi
0x18000e9ed  push    r14
0x18000e9ef  push    r15
0x18000e9f1  lea     rbp, [rsp-358h]
0x18000e9f9  sub     rsp, 458h
0x18000ea00  mov     rax, cs:__security_cookie
0x18000ea07  xor     rax, rsp
0x18000ea0a  mov     [rbp+380h+var_40], rax
0x18000ea11  mov     rbx, r8
0x18000ea14  mov     rdi, rcx
0x18000ea17  mov     rcx, [rbp+388h]; this
0x18000ea1e  xor     r14d, r14d
0x18000ea21  test    edx, edx
0x18000ea23  jz      loc_18000EDA3
0x18000ea29  lea     rdx, aServicestartac; "ServiceStartActivity"
0x18000ea30  lea     rcx, [rsp+480h+var_430]
0x18000ea35  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ea3a  lea     r15, ??_7ServiceStartActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStartActivity::`vftable'
0x18000ea41  mov     [rsp+480h+var_430], r15
0x18000ea46  lea     rsi, [rdi+8]
0x18000ea4a  lea     rdx, aServicestartac; "ServiceStartActivity"
0x18000ea51  lea     rcx, [rbp+380h+var_2E0]
0x18000ea58  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ea5d  mov     [rbp+380h+var_2E0], r15
0x18000ea64  mov     rdx, rsi; unsigned __int16 *
0x18000ea67  lea     rcx, [rbp+380h+var_2E0]; this
0x18000ea6e  call    ?StartActivity@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBG@Z; ServiceHostTelemetry::ServiceStartActivity::StartActivity(ushort const *)
0x18000ea73  nop
0x18000ea74  cmp     [rbp+380h+var_2F8], r14d
0x18000ea7b  setnz   r8b
0x18000ea7f  lea     rdx, [rsp+480h+var_430]
0x18000ea84  lea     rcx, [rbp+380h+var_190]
0x18000ea8b  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18000ea90  mov     [rbp+380h+var_190], r15
0x18000ea97  lea     rdx, [rbp+380h+var_2E0]
0x18000ea9e  lea     rcx, [rsp+480h+var_430]
0x18000eaa3  call    ??4?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x18000eaa8  mov     [rbp+380h+var_190], r15
0x18000eaaf  lea     rcx, [rbp+380h+var_190]
0x18000eab6  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000eabb  lea     rcx, [rbp+380h+var_190]
0x18000eac2  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000eac7  mov     [rbp+380h+var_2E0], r15
0x18000eace  lea     rcx, [rbp+380h+var_2E0]
0x18000ead5  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000eada  lea     rcx, [rbp+380h+var_2E0]
0x18000eae1  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000eae6  mov     [rdi+64h], r14d
0x18000eaea  mov     rax, [rdi]
0x18000eaed  mov     rcx, rdi
0x18000eaf0  mov     rax, [rax+30h]
0x18000eaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaf9  mov     [rdi+60h], eax
0x18000eafc  mov     rax, [rdi]
0x18000eaff  mov     rcx, rdi
0x18000eb02  mov     rax, [rax+40h]
0x18000eb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb0b  mov     [rdi+78h], eax
0x18000eb0e  mov     [rdi+6Ch], r14d
0x18000eb12  mov     [rdi+74h], r14d
0x18000eb16  mov     rax, [rdi]
0x18000eb19  mov     rcx, rdi
0x18000eb1c  mov     rax, [rax+48h]
0x18000eb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb25  mov     [rdi+70h], eax
0x18000eb28  mov     [rdi+68h], r14d
0x18000eb2c  xor     edx, edx; Val
0x18000eb2e  lea     r8d, [r14+40h]; Size
0x18000eb32  mov     rcx, rsi; void *
0x18000eb35  call    memset_0
0x18000eb3a  mov     [rdi+7Ch], r14
0x18000eb3e  mov     rcx, [rdi+50h]; hEvent
0x18000eb42  test    rcx, rcx
0x18000eb45  jz      short loc_18000EB5C
0x18000eb47  call    cs:__imp_ResetEvent
0x18000eb4d  mov     rcx, [rbp+388h]; this
0x18000eb54  test    eax, eax
0x18000eb56  jz      loc_18000ED98
0x18000eb5c  mov     ecx, 7FFFFFFEh
0x18000eb61  mov     r8, [rbx]
0x18000eb64  mov     edx, 20h ; ' '
0x18000eb69  mov     rax, rsi
0x18000eb6c  test    rcx, rcx
0x18000eb6f  jz      short loc_18000EB90
0x18000eb71  movzx   r9d, word ptr [r8]
0x18000eb75  test    r9w, r9w
0x18000eb79  jz      short loc_18000EB90
0x18000eb7b  add     r8, 2
0x18000eb7f  mov     [rax], r9w
0x18000eb83  add     rax, 2
0x18000eb87  dec     rcx
0x18000eb8a  sub     rdx, 1
0x18000eb8e  jnz     short loc_18000EB6C
0x18000eb90  lea     rcx, [rax-2]
0x18000eb94  test    rdx, rdx
0x18000eb97  cmovnz  rcx, rax
0x18000eb9b  mov     [rcx], r14w
0x18000eb9f  neg     rdx
0x18000eba2  sbb     ecx, ecx
0x18000eba4  not     ecx
0x18000eba6  and     ecx, 8007007Ah
0x18000ebac  mov     r8d, 1
0x18000ebb2  mov     rdx, rsi
0x18000ebb5  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18000ebba  mov     ebx, eax
0x18000ebbc  test    eax, eax
0x18000ebbe  jns     short loc_18000EBE0
0x18000ebc0  mov     rcx, [rbp+388h]; this
0x18000ebc7  mov     r9d, eax; char *
0x18000ebca  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ebd1  mov     edx, 17Ch; void *
0x18000ebd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebdb  jmp     loc_18000ECF0
0x18000ebe0  mov     r8, rdi; lpContext
0x18000ebe3  lea     rdx, ?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z; lpHandlerProc
0x18000ebea  mov     rcx, rsi; lpServiceName
0x18000ebed  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000ebf3  mov     [rdi+48h], rax
0x18000ebf7  mov     rcx, [rbp+388h]
0x18000ebfe  lea     rdx, aRegistrationOf; "Registration of service controller fail"...
0x18000ec05  mov     [rsp+480h+var_458], rdx
0x18000ec0a  mov     qword ptr [rsp+480h+var_460], rax
0x18000ec0f  mov     r9d, 80070006h
0x18000ec15  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ec1c  mov     edx, 64h ; 'd'
0x18000ec21  call    ??$Log_HrIfNullMsg@PEAUSERVICE_STATUS_HANDLE__@@$0A@@in1diag3@details@wil@@YAPEAUSERVICE_STATUS_HANDLE__@@PEAXIPEBDJPEAU3@1ZZ; wil::details::in1diag3::Log_HrIfNullMsg<SERVICE_STATUS_HANDLE__ *,0>(void *,uint,char const *,long,SERVICE_STATUS_HANDLE__ *,char const *,...)
0x18000ec26  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000ec2b  mov     ecx, [rax]
0x18000ec2d  cmp     ecx, 5
0x18000ec30  jbe     short loc_18000EC66
0x18000ec32  lea     rcx, aStarting; "Starting"
0x18000ec39  mov     [rsp+480h+var_450], rcx
0x18000ec3e  mov     qword ptr [rsp+480h+var_448], rsi
0x18000ec43  lea     rcx, [rsp+480h+var_450]
0x18000ec48  mov     [rsp+480h+var_458], rcx
0x18000ec4d  lea     rcx, [rsp+480h+var_448]
0x18000ec52  mov     qword ptr [rsp+480h+var_460], rcx; int
0x18000ec57  lea     rdx, byte_1800154E7
0x18000ec5e  mov     rcx, rax
0x18000ec61  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000ec66  mov     [rsp+480h+var_440], rdi
0x18000ec6b  mov     [rsp+480h+var_438], 1
0x18000ec70  mov     rcx, rdi; this
0x18000ec73  call    ?_ServiceMainInner@ServiceBase@@AEAAJXZ; ServiceBase::_ServiceMainInner(void)
0x18000ec78  mov     ebx, eax
0x18000ec7a  mov     [rsp+480h+var_448], eax
0x18000ec7e  test    eax, eax
0x18000ec80  jns     loc_18000ED0D
0x18000ec86  and     eax, 1FFF0000h
0x18000ec8b  cmp     eax, 70000h
0x18000ec90  jnz     short loc_18000EC9A
0x18000ec92  movzx   eax, bx
0x18000ec95  mov     [rdi+6Ch], eax
0x18000ec98  jmp     short loc_18000ECAA
0x18000ec9a  lea     r8, [rsp+480h+var_448]
0x18000ec9f  mov     rcx, rsi
0x18000eca2  call    ??$ServiceBaseError@AEAY0CA@GAEAY08$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY08$$CBGAEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[9],long &>(ushort (&)[32],ushort const (&)[9],long &)
0x18000eca7  mov     [rdi+6Ch], ebx
0x18000ecaa  mov     dword ptr [rsp+480h+var_450], 2
0x18000ecb2  mov     [rsp+480h+var_440], rsi
0x18000ecb7  lea     r8, [rsp+480h+var_450]
0x18000ecbc  lea     rdx, [rsp+480h+var_448]
0x18000ecc1  lea     rcx, [rsp+480h+var_440]
0x18000ecc6  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x18000eccb  mov     rcx, [rbp+388h]; this
0x18000ecd2  mov     r9d, ebx; char *
0x18000ecd5  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ecdc  mov     edx, 1A1h; void *
0x18000ece1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ece6  nop
0x18000ece7  mov     rcx, rdi; this
0x18000ecea  call    ?ServiceStop@ServiceBase@@QEAAXXZ; ServiceBase::ServiceStop(void)
0x18000ecef  nop
0x18000ecf0  mov     [rsp+480h+var_430], r15
0x18000ecf5  lea     rcx, [rsp+480h+var_430]
0x18000ecfa  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000ecff  lea     rcx, [rsp+480h+var_430]
0x18000ed04  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000ed09  mov     eax, ebx
0x18000ed0b  jmp     short loc_18000ED79
0x18000ed0d  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000ed12  mov     ecx, [rax]
0x18000ed14  cmp     ecx, 5
0x18000ed17  jbe     short loc_18000ED4D
0x18000ed19  lea     rcx, aStarted; "Started"
0x18000ed20  mov     [rsp+480h+var_440], rcx
0x18000ed25  mov     [rsp+480h+var_450], rsi
0x18000ed2a  lea     rcx, [rsp+480h+var_440]
0x18000ed2f  mov     [rsp+480h+var_458], rcx
0x18000ed34  lea     rcx, [rsp+480h+var_450]
0x18000ed39  mov     qword ptr [rsp+480h+var_460], rcx
0x18000ed3e  lea     rdx, unk_180015478
0x18000ed45  mov     rcx, rax
0x18000ed48  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000ed4d  mov     r8d, ebx; int
0x18000ed50  mov     rdx, rsi; unsigned __int16 *
0x18000ed53  lea     rcx, [rsp+480h+var_430]; this
0x18000ed58  call    ?Stop@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z; ServiceHostTelemetry::ServiceStartActivity::Stop(ushort const *,long)
0x18000ed5d  nop
0x18000ed5e  mov     [rsp+480h+var_430], r15
0x18000ed63  lea     rcx, [rsp+480h+var_430]
0x18000ed68  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000ed6d  lea     rcx, [rsp+480h+var_430]
0x18000ed72  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000ed77  xor     eax, eax
0x18000ed79  mov     rcx, [rbp+380h+var_40]
0x18000ed80  xor     rcx, rsp; StackCookie
0x18000ed83  call    __security_check_cookie
0x18000ed88  add     rsp, 458h
0x18000ed8f  pop     r15
0x18000ed91  pop     r14
0x18000ed93  pop     rdi
0x18000ed94  pop     rsi
0x18000ed95  pop     rbx
0x18000ed96  pop     rbp
0x18000ed97  retn
0x18000ed98  mov     edx, 0A06h; void *
0x18000ed9d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000eda3  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000edaa  mov     edx, 170h; void *
0x18000edaf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
