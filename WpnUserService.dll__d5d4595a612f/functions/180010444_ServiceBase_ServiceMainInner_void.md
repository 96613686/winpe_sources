# ServiceBase::_ServiceMainInner(void)

- ea: `0x180010444`
- end: `0x18001087d`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `1081`
- prototype: `__int64 __fastcall(ServiceBase *this, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000e9e8`

## callees

- `0x180002bc0`
- `0x1800052d8`
- `0x180006244`
- `0x1800071a8`
- `0x180007e58`
- `0x18000ce34`
- `0x18000d564`
- `0x18000d600`
- `0x18000d7e0`
- `0x18000dc1c`
- `0x18000dcdc`
- `0x18000e2ec`
- `0x18000e51c`
- `0x18000f094`
- `0x18000f4b0`
- `0x180010444`
- `0x18001096c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800105f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800105f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001060e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001060e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001061a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001061a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001053c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001053c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010563`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010592`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800105a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010563`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010592`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800105a4`

## string_xrefs

- `0x1800106af`: `ServiceStartActivity`
- `0x1800104d4`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18001086b`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this, __int64 a2, __int64 a3, const char *a4)
{
  const unsigned __int16 *v5; // r14
  const WCHAR *v6; // rax
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  int started; // ebx
  __int64 v10; // rdx
  wil::details *v12; // rcx
  HANDLE Event; // r15
  void *v14; // rbx
  DWORD LastError; // r12d
  __int64 v16; // r8
  const char *v17; // r9
  unsigned int v18; // ebx
  int LastErrorFailHr; // eax
  unsigned int updated; // eax
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  __int64 v23; // rdx
  unsigned int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v33[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v5 = (const unsigned __int16 *)((char *)this + 8);
  if ( !*((_QWORD *)this + 22) )
  {
    v30 = 3;
    LODWORD(hKey) = -2147023537;
    v32[0] = (__int64)this + 8;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long,unsigned int>(v32, (int *)&hKey, &v30);
  }
  if ( !*((_QWORD *)this + 22) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x201,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      a4);
  v6 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 80LL))(this);
  if ( !v6 )
  {
    if ( ((*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 56LL))(this) & 0x100) != 0 )
    {
      v7 = -2147483635;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
        (const char *)0x8000000DLL,
        phkResult);
      goto LABEL_19;
    }
    goto LABEL_12;
  }
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_CURRENT_USER, v6, 0, 0x20019u, &hKey);
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
  if ( v7 == -2147024894 )
  {
    if ( hKey )
      RegCloseKey(hKey);
LABEL_12:
    v7 = 0;
    goto LABEL_19;
  }
  if ( (v7 & 0x80000000) == 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    v7 = -2147023781;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)v7,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
  }
LABEL_19:
  started = LogIfStartSrvFailedAndReturnHr(v7, v5, 4);
  if ( started < 0 )
  {
    v10 = 518;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)(unsigned int)started,
      phkResult);
    return (unsigned int)started;
  }
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v14 = (void *)*((_QWORD *)this + 10);
    if ( v14 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v14) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 10) = Event;
    goto LABEL_28;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
  v18 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
  {
LABEL_28:
    v18 = 0;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x50,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
    (const char *)(unsigned int)LastErrorFailHr,
    phkResult);
LABEL_29:
  started = LogIfStartSrvFailedAndReturnHr(v18, v5, 5);
  if ( started < 0 )
  {
    v10 = 520;
    goto LABEL_21;
  }
  updated = ServiceBase::_UpdateStatus(this, 2u);
  started = LogIfStartSrvFailedAndReturnHr(updated, v5, 6);
  if ( started < 0 )
  {
    v10 = 524;
    goto LABEL_21;
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v33,
    (__int64)"ServiceStartActivity");
  v33[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  ServiceHostTelemetry::ServiceStartActivity::StartActivity((ServiceHostTelemetry::ServiceStartActivity *)v33, v5);
  started = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 8LL))(this);
  v30 = started;
  if ( started < 0 )
  {
    ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[9],long &>(
      (__int64)v5,
      v21,
      &v30);
    LODWORD(hKey) = 7;
    v32[0] = (__int64)v5;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(v32, &v30, (int *)&hKey);
    v22 = (unsigned int)started;
    v23 = 537;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)v22,
      phkResult);
    v33[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v33);
    return (unsigned int)started;
  }
  *((_DWORD *)this + 31) = 1;
  v24 = ServiceBase::_UpdateStatus(this, 4u);
  v25 = LogIfStartSrvFailedAndReturnHr(v24, v5, 8);
  started = v25;
  if ( v25 < 0 )
  {
    v23 = 545;
LABEL_43:
    v22 = (unsigned int)v25;
    goto LABEL_44;
  }
  v26 = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 24LL))(this);
  started = v26;
  v30 = v26;
  if ( v26 < 0 )
  {
    ServiceHostTelemetry::ServiceBaseError<unsigned short (&)[32],unsigned short const (&)[8],long &>(
      (__int64)v5,
      v27,
      &v30);
    LODWORD(hKey) = 9;
    v32[0] = (__int64)v5;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(v32, &v30, (int *)&hKey);
    v22 = (unsigned int)started;
    v23 = 558;
    goto LABEL_44;
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v33,
    (unsigned int)v26);
  v28 = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 104LL))(this);
  v25 = LogIfStartSrvFailedAndReturnHr(v28, v5, 10);
  started = v25;
  if ( v25 < 0 )
  {
    v23 = 570;
    goto LABEL_43;
  }
  v33[0] = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v33);
  return 0;
}

```

## disassembly

```asm
0x180010444  mov     [rsp-8+arg_8], rbx
0x180010449  mov     [rsp-8+arg_10], rsi
0x18001044e  push    rbp
0x18001044f  push    rdi
0x180010450  push    r12
0x180010452  push    r14
0x180010454  push    r15
0x180010456  lea     rbp, [rsp-0B0h]
0x18001045e  sub     rsp, 1B0h
0x180010465  mov     rax, cs:__security_cookie
0x18001046c  xor     rax, rsp
0x18001046f  mov     [rbp+0D0h+var_30], rax
0x180010476  mov     rdi, rcx
0x180010479  lea     r14, [rcx+8]
0x18001047d  cmp     qword ptr [rcx+0B0h], 0
0x180010485  jnz     short loc_1800104B0
0x180010487  mov     [rsp+1D0h+var_1A0], 3
0x18001048f  mov     dword ptr [rsp+1D0h+hKey], 8007054Fh
0x180010497  mov     [rsp+1D0h+var_190], r14
0x18001049c  lea     r8, [rsp+1D0h+var_1A0]
0x1800104a1  lea     rdx, [rsp+1D0h+hKey]
0x1800104a6  lea     rcx, [rsp+1D0h+var_190]
0x1800104ab  call    ??$ServiceStartFailure@PEBGJI@ServiceHostTelemetry@@SAX$$QEAPEBG$$QEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long,uint>(ushort const * &&,long &&,uint &&)
0x1800104b0  mov     rcx, [rbp+0D8h]; this
0x1800104b7  cmp     qword ptr [rdi+0B0h], 0
0x1800104bf  jz      loc_18001086B
0x1800104c5  mov     rax, [rdi]
0x1800104c8  mov     rcx, rdi
0x1800104cb  mov     rax, [rax+50h]
0x1800104cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d4  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800104db  test    rax, rax
0x1800104de  jnz     short loc_180010516
0x1800104e0  mov     rax, [rdi]
0x1800104e3  mov     rcx, rdi
0x1800104e6  mov     rax, [rax+38h]
0x1800104ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ef  bt      eax, 8
0x1800104f3  jnb     short loc_180010569
0x1800104f5  mov     rcx, [rbp+0D8h]; this
0x1800104fc  mov     ebx, 8000000Dh
0x180010501  mov     r9d, ebx; char *
0x180010504  mov     r8, rsi; unsigned int
0x180010507  mov     edx, 253h; void *
0x18001050c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010511  jmp     loc_1800105AF
0x180010516  mov     [rsp+1D0h+hKey], 0
0x18001051f  lea     rcx, [rsp+1D0h+hKey]
0x180010524  mov     qword ptr [rsp+1D0h+phkResult], rcx; int
0x180010529  mov     r9d, 20019h; samDesired
0x18001052f  xor     r8d, r8d; ulOptions
0x180010532  mov     rdx, rax; lpSubKey
0x180010535  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001053c  call    cs:__imp_RegOpenKeyExW
0x180010542  mov     ebx, eax
0x180010544  test    eax, eax
0x180010546  jle     short loc_180010551
0x180010548  movzx   ebx, ax
0x18001054b  or      ebx, 80070000h
0x180010551  cmp     ebx, 80070002h
0x180010557  jnz     short loc_18001056D
0x180010559  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18001055e  test    rcx, rcx
0x180010561  jz      short loc_180010569
0x180010563  call    cs:__imp_RegCloseKey
0x180010569  xor     ebx, ebx
0x18001056b  jmp     short loc_1800105AF
0x18001056d  test    ebx, ebx
0x18001056f  jns     short loc_18001059A
0x180010571  mov     rcx, [rbp+0D8h]; this
0x180010578  mov     r9d, ebx; char *
0x18001057b  mov     r8, rsi; unsigned int
0x18001057e  mov     edx, 263h; void *
0x180010583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010588  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18001058d  test    rcx, rcx
0x180010590  jz      short loc_1800105AF
0x180010592  call    cs:__imp_RegCloseKey
0x180010598  jmp     short loc_1800105AF
0x18001059a  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18001059f  test    rcx, rcx
0x1800105a2  jz      short loc_1800105AA
0x1800105a4  call    cs:__imp_RegCloseKey
0x1800105aa  mov     ebx, 8007045Bh
0x1800105af  mov     r8d, 4
0x1800105b5  mov     rdx, r14
0x1800105b8  mov     ecx, ebx
0x1800105ba  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x1800105bf  mov     ebx, eax
0x1800105c1  test    eax, eax
0x1800105c3  jns     short loc_1800105E3
0x1800105c5  mov     edx, 206h; void *
0x1800105ca  mov     rcx, [rbp+0D8h]; this
0x1800105d1  mov     r9d, ebx; char *
0x1800105d4  mov     r8, rsi; unsigned int
0x1800105d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800105dc  mov     eax, ebx
0x1800105de  jmp     loc_180010835
0x1800105e3  xor     edx, edx; lpName
0x1800105e5  xor     ecx, ecx; lpEventAttributes
0x1800105e7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800105ed  lea     r8d, [rdx+1]; dwFlags
0x1800105f1  call    cs:__imp_CreateEventExW
0x1800105f7  mov     r15, rax
0x1800105fa  test    rax, rax
0x1800105fd  jz      short loc_18001065E
0x1800105ff  call    cs:__imp_GetLastError
0x180010605  mov     rbx, [rdi+50h]
0x180010609  test    rbx, rbx
0x18001060c  jz      short loc_180010638
0x18001060e  call    cs:__imp_GetLastError
0x180010614  mov     r12d, eax
0x180010617  mov     rcx, rbx; hObject
0x18001061a  call    cs:__imp_CloseHandle
0x180010620  mov     rcx, [rbp+0D8h]; this
0x180010627  test    eax, eax
0x180010629  jz      loc_180010860
0x18001062f  mov     ecx, r12d; dwErrCode
0x180010632  call    cs:__imp_SetLastError
0x180010638  mov     [rdi+50h], r15
0x18001063c  xor     ebx, ebx
0x18001063e  mov     r8d, 5
0x180010644  mov     rdx, r14
0x180010647  mov     ecx, ebx
0x180010649  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001064e  mov     ebx, eax
0x180010650  test    eax, eax
0x180010652  jns     short loc_180010682
0x180010654  mov     edx, 208h
0x180010659  jmp     loc_1800105CA
0x18001065e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010663  mov     ebx, eax
0x180010665  test    eax, eax
0x180010667  jns     short loc_18001063C
0x180010669  mov     rcx, [rbp+0D8h]; this
0x180010670  mov     r9d, eax; char *
0x180010673  mov     r8, rsi; unsigned int
0x180010676  mov     edx, 50h ; 'P'; void *
0x18001067b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010680  jmp     short loc_18001063E
0x180010682  mov     edx, 2; unsigned int
0x180010687  mov     rcx, rdi; this
0x18001068a  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18001068f  mov     r8d, 6
0x180010695  mov     rdx, r14
0x180010698  mov     ecx, eax
0x18001069a  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18001069f  mov     ebx, eax
0x1800106a1  test    eax, eax
0x1800106a3  jns     short loc_1800106AF
0x1800106a5  mov     edx, 20Ch
0x1800106aa  jmp     loc_1800105CA
0x1800106af  lea     rdx, aServicestartac; "ServiceStartActivity"
0x1800106b6  lea     rcx, [rsp+1D0h+var_180]
0x1800106bb  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800106c0  lea     r15, ??_7ServiceStartActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStartActivity::`vftable'
0x1800106c7  mov     [rsp+1D0h+var_180], r15
0x1800106cc  mov     rdx, r14; unsigned __int16 *
0x1800106cf  lea     rcx, [rsp+1D0h+var_180]; this
0x1800106d4  call    ?StartActivity@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBG@Z; ServiceHostTelemetry::ServiceStartActivity::StartActivity(ushort const *)
0x1800106d9  nop
0x1800106da  mov     rax, [rdi]
0x1800106dd  mov     rcx, rdi
0x1800106e0  mov     rax, [rax+8]
0x1800106e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e9  mov     ebx, eax
0x1800106eb  mov     [rsp+1D0h+var_1A0], eax
0x1800106ef  test    eax, eax
0x1800106f1  jns     short loc_18001072E
0x1800106f3  lea     r8, [rsp+1D0h+var_1A0]
0x1800106f8  mov     rcx, r14
0x1800106fb  call    ??$ServiceBaseError@AEAY0CA@GAEAY08$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY08$$CBGAEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[9],long &>(ushort (&)[32],ushort const (&)[9],long &)
0x180010700  mov     dword ptr [rsp+1D0h+hKey], 7
0x180010708  mov     [rsp+1D0h+var_190], r14
0x18001070d  lea     r8, [rsp+1D0h+hKey]
0x180010712  lea     rdx, [rsp+1D0h+var_1A0]
0x180010717  lea     rcx, [rsp+1D0h+var_190]
0x18001071c  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x180010721  mov     r9d, ebx
0x180010724  mov     edx, 219h
0x180010729  jmp     loc_1800107EC
0x18001072e  mov     dword ptr [rdi+7Ch], 1
0x180010735  mov     edx, 4; unsigned int
0x18001073a  mov     rcx, rdi; this
0x18001073d  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x180010742  mov     r8d, 8
0x180010748  mov     rdx, r14
0x18001074b  mov     ecx, eax
0x18001074d  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x180010752  mov     ebx, eax
0x180010754  test    eax, eax
0x180010756  jns     short loc_180010762
0x180010758  mov     edx, 221h
0x18001075d  jmp     loc_1800107E9
0x180010762  mov     rax, [rdi]
0x180010765  mov     rcx, rdi
0x180010768  mov     rax, [rax+18h]
0x18001076c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010771  mov     ebx, eax
0x180010773  mov     [rsp+1D0h+var_1A0], eax
0x180010777  test    eax, eax
0x180010779  jns     short loc_1800107B3
0x18001077b  lea     r8, [rsp+1D0h+var_1A0]
0x180010780  mov     rcx, r14
0x180010783  call    ??$ServiceBaseError@AEAY0CA@GAEAY07$$CBGAEAJ@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY07$$CBGAEAJ@Z; ServiceHostTelemetry::ServiceBaseError<ushort (&)[32],ushort const (&)[8],long &>(ushort (&)[32],ushort const (&)[8],long &)
0x180010788  mov     dword ptr [rsp+1D0h+hKey], 9
0x180010790  mov     [rsp+1D0h+var_190], r14
0x180010795  lea     r8, [rsp+1D0h+hKey]
0x18001079a  lea     rdx, [rsp+1D0h+var_1A0]
0x18001079f  lea     rcx, [rsp+1D0h+var_190]
0x1800107a4  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x1800107a9  mov     r9d, ebx
0x1800107ac  mov     edx, 22Eh
0x1800107b1  jmp     short loc_1800107EC
0x1800107b3  mov     edx, ebx
0x1800107b5  lea     rcx, [rsp+1D0h+var_180]
0x1800107ba  call    ?Stop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800107bf  mov     rax, [rdi]
0x1800107c2  mov     rcx, rdi
0x1800107c5  mov     rax, [rax+68h]
0x1800107c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ce  mov     r8d, 0Ah
0x1800107d4  mov     rdx, r14
0x1800107d7  mov     ecx, eax
0x1800107d9  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x1800107de  mov     ebx, eax
0x1800107e0  test    eax, eax
0x1800107e2  jns     short loc_18001081A
0x1800107e4  mov     edx, 23Ah; void *
0x1800107e9  mov     r9d, eax; char *
0x1800107ec  mov     r8, rsi; unsigned int
0x1800107ef  mov     rcx, [rbp+0D8h]; this
0x1800107f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107fb  nop
0x1800107fc  mov     [rsp+1D0h+var_180], r15
0x180010801  lea     rcx, [rsp+1D0h+var_180]
0x180010806  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001080b  lea     rcx, [rsp+1D0h+var_180]
0x180010810  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010815  jmp     loc_1800105DC
0x18001081a  mov     [rsp+1D0h+var_180], r15
0x18001081f  lea     rcx, [rsp+1D0h+var_180]
0x180010824  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010829  lea     rcx, [rsp+1D0h+var_180]
0x18001082e  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010833  xor     eax, eax
0x180010835  mov     rcx, [rbp+0D0h+var_30]
0x18001083c  xor     rcx, rsp; StackCookie
0x18001083f  call    __security_check_cookie
0x180010844  lea     r11, [rsp+1D0h+var_20]
0x18001084c  mov     rbx, [r11+38h]
0x180010850  mov     rsi, [r11+40h]
0x180010854  mov     rsp, r11
0x180010857  pop     r15
0x180010859  pop     r14
0x18001085b  pop     r12
0x18001085d  pop     rdi
0x18001085e  pop     rbp
0x18001085f  retn
0x180010860  mov     edx, 0A0Bh; void *
0x180010865  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001086b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010872  mov     edx, 201h; void *
0x180010877  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
