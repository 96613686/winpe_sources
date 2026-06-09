# CloudBackupTask::StartWorker(IUnknown *,ushort *)

- ea: `0x18001b310`
- end: `0x18001b6ec`
- name: `?StartWorker@CloudBackupTask@@EEAAJPEAUIUnknown@@PEAG@Z`
- size: `988`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18000cbbc`
- `0x18001024c`
- `0x180011434`
- `0x1800124b4`
- `0x180012b84`
- `0x180012c0c`
- `0x180012f30`
- `0x1800139b8`
- `0x1800139ec`
- `0x18001510c`
- `0x1800154e4`
- `0x1800161ec`
- `0x1800162a4`
- `0x18001662c`
- `0x180016648`
- `0x1800166e8`
- `0x18001676c`
- `0x180017cc4`
- `0x180018424`
- `0x1800194a0`
- `0x18001ac54`
- `0x18001b088`
- `0x18001b2b0`
- `0x18001b310`
- `0x18001b7b0`
- `0x18001c180`
- `0x18001cfa4`
- `0x18001da24`
- `0x18011d214`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x18001b4f9`
- `KERNEL32!OpenEventW` at `0x18001b4f9`
- `KERNEL32!Sleep` at `0x18001b3ab`
- `KERNEL32!Sleep` at `0x18001b3ab`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b5c3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b5c3`

## string_xrefs

- `0x18001b33a`: `CloudBackupScheduledTaskStartWorker`
- `0x18001b378`: `CloudBackupTaskWaitForDebugger`
- `0x18001b40d`: `CompletedEventGuid`
- `0x18001b695`: `pcshell\shell\cloudrestorelauncher\dll\cloudbackuptask.cpp`
- `0x18001b6c4`: `pcshell\shell\cloudrestorelauncher\dll\cloudbackuptask.cpp`
- `0x18001b6d9`: `pcshell\shell\cloudrestorelauncher\dll\cloudbackuptask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CloudBackupTask::StartWorker(RTL_SRWLOCK *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  int DWORD; // eax
  wil::details *v7; // rcx
  __int64 v9; // rbx
  int v10; // eax
  HANDLE v11; // rax
  const char *v12; // r9
  const unsigned __int16 *v13; // rax
  bool v14; // dl
  struct TraceLoggingCorrelationVector *v15; // rax
  _QWORD *v16; // rax
  int started; // eax
  const char *v18; // r9
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-308h]
  unsigned int v21; // [rsp+30h] [rbp-2F8h] BYREF
  _QWORD *v22; // [rsp+38h] [rbp-2F0h] BYREF
  RTL_SRWLOCK *v23; // [rsp+40h] [rbp-2E8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-2E0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-2D8h] BYREF
  __int64 v26; // [rsp+58h] [rbp-2D0h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-2C8h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-2A8h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-288h] BYREF
  _QWORD v30[42]; // [rsp+C0h] [rbp-268h] BYREF
  _DWORD v31[8]; // [rsp+210h] [rbp-118h] BYREF
  __int16 v32; // [rsp+230h] [rbp-F8h]
  WCHAR Name[88]; // [rsp+240h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v30);
  v30[0] = &CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker::`vftable';
  CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker::StartActivity((CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker *)v30);
  v21 = 0;
  DWORD = SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Cloudstore\\SystemMetaData",
            L"CloudBackupTaskWaitForDebugger",
            &v21);
  if ( DWORD >= 0 && v21 )
  {
    while ( !wil::details::IsDebuggerPresent(v7) )
      Sleep(0x1F4u);
  }
  v9 = 0;
  v25 = 0;
  try
  {
    std::make_unique<TraceLoggingCorrelationVector,TraceLoggingCorrelationVectorV2_t const &,0>();
    if ( wcscmp_0(a3, L"$(Arg0)") )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v27, a3);
      winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)&v22);
      winrt::param::hstring::hstring((winrt::param::hstring *)v28, &word_1801382A0);
      winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"CompletedEventGuid");
      winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
        &v22,
        &v23,
        v29,
        v28);
      if ( v23 )
      {
        v31[0] = 7077955;
        v31[1] = 7667823;
        v31[2] = 4325476;
        v31[3] = 6488161;
        v31[4] = 7667819;
        v31[5] = 5505136;
        v31[6] = 7536737;
        v31[7] = 3014763;
        v32 = 0;
        v20 = (unsigned int)winrt::hstring::c_str((winrt::hstring *)&v23);
        v10 = StringCchPrintfW(Name, 0x51u, L"%s%s", v31);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\dll\\cloudbackuptask.cpp",
            (const char *)(unsigned int)v10,
            v20);
        v11 = OpenEventW(2u, 0, Name);
        if ( !v11 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x1CC8,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            v12);
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          &v25,
          v11);
        v9 = v25;
      }
      winrt::param::hstring::hstring((winrt::param::hstring *)v27, &word_1801382A0);
      winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"CorrelationVector");
      winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
        &v22,
        &v26,
        v31,
        v27);
      if ( v26 )
      {
        v13 = winrt::hstring::c_str((winrt::hstring *)&v26);
        v15 = TraceLoggingCorrelationVector::ExtendW(v13, v14);
        std::unique_ptr<TraceLoggingCorrelationVector>::reset(&v24, v15);
        if ( !v24 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x52,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\dll\\cloudbackuptask.cpp",
            (const char *)0x83750007LL,
            v20);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v26);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v23);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v22);
    }
    AcquireSRWLockExclusive(this + 7);
    v23 = this + 7;
    v16 = operator new(0x10u);
    *v16 = 0;
    v16[1] = v9;
    v25 = 0;
    v22 = v16;
    std::unique_ptr<CloudBackupTask::CompletionEventSignaler>::operator=<std::default_delete<CloudBackupTask::CompletionEventSignaler>,0>(
      &this[8],
      &v22);
    std::unique_ptr<CloudBackupTask::CompletionEventSignaler>::~unique_ptr<CloudBackupTask::CompletionEventSignaler>(&v22);
    std::unique_ptr<TraceLoggingCorrelationVector>::operator=<std::default_delete<TraceLoggingCorrelationVector>,0>(
      &this[9],
      &v24);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
    started = CWinTaskHandler::StartWorker((CWinTaskHandler *)this, a2, a3);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\dll\\cloudbackuptask.cpp",
        (const char *)(unsigned int)started,
        v20);
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v30);
    std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker::~CloudBackupScheduledTaskStartWorker((CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker *)v30);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x63,
                           (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\dll\\cloudbackuptask.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18001b310  push    rbx
0x18001b312  push    rsi
0x18001b313  push    rdi
0x18001b314  push    r14
0x18001b316  push    r15
0x18001b318  sub     rsp, 300h
0x18001b31f  mov     rax, cs:__security_cookie
0x18001b326  xor     rax, rsp
0x18001b329  mov     [rsp+328h+var_38], rax
0x18001b331  mov     r14, r8
0x18001b334  mov     r15, rdx
0x18001b337  mov     rsi, rcx
0x18001b33a  lea     rdx, aCloudbackupsch_0; "CloudBackupScheduledTaskStartWorker"
0x18001b341  lea     rcx, [rsp+328h+var_268]; struct wil::details::IFailureCallback *
0x18001b349  call    ??0?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001b34e  lea     rax, ??_7CloudBackupScheduledTaskStartWorker@CloudRestoreLauncherTelemetry@@6B@; const CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker::`vftable'
0x18001b355  mov     [rsp+328h+var_268], rax
0x18001b35d  lea     rcx, [rsp+328h+var_268]; this
0x18001b365  call    ?StartActivity@CloudBackupScheduledTaskStartWorker@CloudRestoreLauncherTelemetry@@QEAAXXZ; CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker::StartActivity(void)
0x18001b36a  nop
0x18001b36b  mov     [rsp+328h+var_2F8], 0
0x18001b373  lea     r9, [rsp+328h+var_2F8]; unsigned int *
0x18001b378  lea     r8, aCloudbackuptas; "CloudBackupTaskWaitForDebugger"
0x18001b37f  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001b386  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001b38d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001b392  test    eax, eax
0x18001b394  js      short loc_18001B3B3
0x18001b396  cmp     [rsp+328h+var_2F8], 0
0x18001b39b  jz      short loc_18001B3B3
0x18001b39d  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x18001b3a2  test    al, al
0x18001b3a4  jnz     short loc_18001B3B3
0x18001b3a6  mov     ecx, 1F4h; dwMilliseconds
0x18001b3ab  call    cs:__imp_Sleep
0x18001b3b1  jmp     short loc_18001B39D
0x18001b3b3  xor     ebx, ebx
0x18001b3b5  mov     [rsp+328h+var_2D8], rbx
0x18001b3ba  lea     rcx, [rsp+328h+var_2E0]
0x18001b3bf  call    ??$make_unique@VTraceLoggingCorrelationVector@@AEBUTraceLoggingCorrelationVectorV2_t@@$0A@@std@@YA?AV?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@0@AEBUTraceLoggingCorrelationVectorV2_t@@@Z; std::make_unique<TraceLoggingCorrelationVector,TraceLoggingCorrelationVectorV2_t const &,0>(TraceLoggingCorrelationVectorV2_t const &)
0x18001b3c4  nop
0x18001b3c5  lea     rdx, aArg0; "$(Arg0)"
0x18001b3cc  mov     rcx, r14; String1
0x18001b3cf  call    wcscmp_0
0x18001b3d4  test    eax, eax
0x18001b3d6  jz      loc_18001B5BC
0x18001b3dc  mov     rdx, r14; unsigned __int16 *
0x18001b3df  lea     rcx, [rsp+328h+var_2C8]; this
0x18001b3e4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001b3e9  lea     rdx, [rsp+328h+var_2C8]
0x18001b3ee  lea     rcx, [rsp+328h+var_2F0]; struct winrt::param::hstring *
0x18001b3f3  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x18001b3f8  nop
0x18001b3f9  lea     rdx, word_1801382A0; unsigned __int16 *
0x18001b400  lea     rcx, [rsp+328h+var_2A8]; this
0x18001b408  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001b40d  lea     rdx, aCompletedevent; "CompletedEventGuid"
0x18001b414  lea     rcx, [rsp+328h+var_288]; this
0x18001b41c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001b421  lea     r9, [rsp+328h+var_2A8]
0x18001b429  lea     r8, [rsp+328h+var_288]
0x18001b431  lea     rdx, [rsp+328h+var_2E8]
0x18001b436  lea     rcx, [rsp+328h+var_2F0]
0x18001b43b  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18001b440  nop
0x18001b441  cmp     [rsp+328h+var_2E8], rbx
0x18001b446  jz      loc_18001B51A
0x18001b44c  mov     [rsp+328h+var_118], 6C0043h
0x18001b457  mov     [rsp+328h+var_114], 75006Fh
0x18001b462  mov     [rsp+328h+var_110], 420064h
0x18001b46d  mov     [rsp+328h+var_10C], 630061h
0x18001b478  mov     [rsp+328h+var_108], 75006Bh
0x18001b483  mov     [rsp+328h+var_104], 540070h
0x18001b48e  mov     [rsp+328h+var_100], 730061h
0x18001b499  mov     [rsp+328h+var_FC], 2E006Bh
0x18001b4a4  xor     eax, eax
0x18001b4a6  mov     [rsp+328h+var_F8], ax
0x18001b4ae  lea     rcx, [rsp+328h+var_2E8]; this
0x18001b4b3  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001b4b8  mov     qword ptr [rsp+328h+var_308], rax; int
0x18001b4bd  lea     r9, [rsp+328h+var_118]
0x18001b4c5  lea     r8, aSS_0; "%s%s"
0x18001b4cc  lea     edx, [rbx+51h]; unsigned __int64
0x18001b4cf  lea     rcx, [rsp+328h+Name]; unsigned __int16 *
0x18001b4d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b4dc  mov     rcx, [rsp+328h]; this
0x18001b4e4  test    eax, eax
0x18001b4e6  js      loc_18001B692
0x18001b4ec  lea     r8, [rsp+328h+Name]; lpName
0x18001b4f4  xor     edx, edx; bInheritHandle
0x18001b4f6  lea     ecx, [rdx+2]; dwDesiredAccess
0x18001b4f9  call    cs:__imp_OpenEventW
0x18001b4ff  test    rax, rax
0x18001b502  jz      loc_18001B6A4
0x18001b508  mov     rdx, rax
0x18001b50b  lea     rcx, [rsp+328h+var_2D8]
0x18001b510  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001b515  mov     rbx, [rsp+328h+var_2D8]
0x18001b51a  lea     rdx, word_1801382A0; unsigned __int16 *
0x18001b521  lea     rcx, [rsp+328h+var_2C8]; this
0x18001b526  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001b52b  lea     rdx, aCorrelationvec; "CorrelationVector"
0x18001b532  lea     rcx, [rsp+328h+var_118]; this
0x18001b53a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001b53f  lea     r9, [rsp+328h+var_2C8]
0x18001b544  lea     r8, [rsp+328h+var_118]
0x18001b54c  lea     rdx, [rsp+328h+var_2D0]
0x18001b551  lea     rcx, [rsp+328h+var_2F0]
0x18001b556  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18001b55b  nop
0x18001b55c  cmp     [rsp+328h+var_2D0], 0
0x18001b562  jz      short loc_18001B59C
0x18001b564  lea     rcx, [rsp+328h+var_2D0]; this
0x18001b569  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001b56e  mov     rcx, rax; unsigned __int16 *
0x18001b571  call    ?ExtendW@TraceLoggingCorrelationVector@@SAPEAV1@PEBG_N@Z; TraceLoggingCorrelationVector::ExtendW(ushort const *,bool)
0x18001b576  mov     rdx, rax
0x18001b579  lea     rcx, [rsp+328h+var_2E0]
0x18001b57e  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; std::unique_ptr<TraceLoggingCorrelationVector>::reset(TraceLoggingCorrelationVector *)
0x18001b583  cmp     [rsp+328h+var_2E0], 0
0x18001b589  setz    al
0x18001b58c  mov     rcx, [rsp+328h]; this
0x18001b594  test    al, al
0x18001b596  jnz     loc_18001B6BE
0x18001b59c  lea     rcx, [rsp+328h+var_2D0]
0x18001b5a1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001b5a6  nop
0x18001b5a7  lea     rcx, [rsp+328h+var_2E8]
0x18001b5ac  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001b5b1  nop
0x18001b5b2  lea     rcx, [rsp+328h+var_2F0]; this
0x18001b5b7  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18001b5bc  lea     rdi, [rsi+38h]
0x18001b5c0  mov     rcx, rdi; SRWLock
0x18001b5c3  call    cs:__imp_AcquireSRWLockExclusive
0x18001b5c9  mov     [rsp+328h+var_2E8], rdi
0x18001b5ce  mov     ecx, 10h; Size
0x18001b5d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b5d8  xor     ecx, ecx
0x18001b5da  mov     [rax], rcx
0x18001b5dd  mov     [rax+8], rbx
0x18001b5e1  mov     [rsp+328h+var_2D8], rcx
0x18001b5e6  mov     [rsp+328h+var_2F0], rax
0x18001b5eb  lea     rcx, [rsi+40h]
0x18001b5ef  lea     rdx, [rsp+328h+var_2F0]
0x18001b5f4  call    ??$?4U?$default_delete@VCompletionEventSignaler@CloudBackupTask@@@std@@$0A@@?$unique_ptr@VCompletionEventSignaler@CloudBackupTask@@U?$default_delete@VCompletionEventSignaler@CloudBackupTask@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CloudBackupTask::CompletionEventSignaler>::operator=<std::default_delete<CloudBackupTask::CompletionEventSignaler>,0>(std::unique_ptr<CloudBackupTask::CompletionEventSignaler> &&)
0x18001b5f9  lea     rcx, [rsp+328h+var_2F0]
0x18001b5fe  call    ??1?$unique_ptr@VCompletionEventSignaler@CloudBackupTask@@U?$default_delete@VCompletionEventSignaler@CloudBackupTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CloudBackupTask::CompletionEventSignaler>::~unique_ptr<CloudBackupTask::CompletionEventSignaler>(void)
0x18001b603  lea     rcx, [rsi+48h]
0x18001b607  lea     rdx, [rsp+328h+var_2E0]
0x18001b60c  call    ??$?4U?$default_delete@VTraceLoggingCorrelationVector@@@std@@$0A@@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TraceLoggingCorrelationVector>::operator=<std::default_delete<TraceLoggingCorrelationVector>,0>(std::unique_ptr<TraceLoggingCorrelationVector> &&)
0x18001b611  nop
0x18001b612  lea     rcx, [rsp+328h+var_2E8]
0x18001b617  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b61c  mov     r8, r14; unsigned __int16 *
0x18001b61f  mov     rdx, r15; struct IUnknown *
0x18001b622  mov     rcx, rsi; this
0x18001b625  call    ?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z; CWinTaskHandler::StartWorker(IUnknown *,ushort *)
0x18001b62a  mov     rcx, [rsp+328h]; this
0x18001b632  test    eax, eax
0x18001b634  js      loc_18001B6D6
0x18001b63a  lea     rcx, [rsp+328h+var_268]
0x18001b642  call    ?Stop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001b647  nop
0x18001b648  lea     rcx, [rsp+328h+var_2E0]
0x18001b64d  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x18001b652  nop
0x18001b653  lea     rcx, [rsp+328h+var_2D8]
0x18001b658  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b65d  nop
0x18001b65e  lea     rcx, [rsp+328h+var_268]; this
0x18001b666  call    ??1CloudBackupScheduledTaskStartWorker@CloudRestoreLauncherTelemetry@@QEAA@XZ; CloudRestoreLauncherTelemetry::CloudBackupScheduledTaskStartWorker::~CloudBackupScheduledTaskStartWorker(void)
0x18001b66b  xor     eax, eax
0x18001b66d  jmp     short loc_18001B673
0x18001b66f  mov     eax, [rsp+328h+var_2F8]
0x18001b673  mov     rcx, [rsp+328h+var_38]
0x18001b67b  xor     rcx, rsp; StackCookie
0x18001b67e  call    __security_check_cookie
0x18001b683  add     rsp, 300h
0x18001b68a  pop     r15
0x18001b68c  pop     r14
0x18001b68e  pop     rdi
0x18001b68f  pop     rsi
0x18001b690  pop     rbx
0x18001b691  retn
0x18001b692  mov     r9d, eax; char *
0x18001b695  lea     r8, aPcshellShellCl_16; "pcshell\\shell\\cloudrestorelauncher\\d"...
0x18001b69c  lea     edx, [rbx+48h]; void *
0x18001b69f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b6a4  mov     rcx, [rsp+328h]; this
0x18001b6ac  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18001b6b3  mov     edx, 1CC8h; void *
0x18001b6b8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001b6be  mov     r9d, 83750007h; char *
0x18001b6c4  lea     r8, aPcshellShellCl_16; "pcshell\\shell\\cloudrestorelauncher\\d"...
0x18001b6cb  mov     edx, 52h ; 'R'; void *
0x18001b6d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b6d6  mov     r9d, eax; char *
0x18001b6d9  lea     r8, aPcshellShellCl_16; "pcshell\\shell\\cloudrestorelauncher\\d"...
0x18001b6e0  mov     edx, 5Fh ; '_'; void *
0x18001b6e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
