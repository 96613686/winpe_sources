# ScoobeToastTriggers::RegisterTimeTriggeredTask(ushort const *,ulong)

- ea: `0x180014cc4`
- end: `0x180014df7`
- name: `?RegisterTimeTriggeredTask@ScoobeToastTriggers@@YAJPEBGK@Z`
- size: `307`
- prototype: `__int64 __fastcall(ScoobeToastTriggers *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011820`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x18000ee5c`
- `0x180010240`
- `0x18001136c`
- `0x180012328`
- `0x180014cc4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014d24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014d24`

## string_xrefs

- `0x180014d05`: `CloudExperienceHostAPI.ScheduledTasksRegistrationManagerCore`
- `0x180014d37`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeTriggers.h`
- `0x180014d97`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeTriggers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ScoobeToastTriggers::RegisterTimeTriggeredTask(
        ScoobeToastTriggers *this,
        const unsigned __int16 *a2)
{
  unsigned int v2; // esi
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  const WCHAR *v14; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  __int64 v16; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v2 = (unsigned int)a2;
  v14 = L"PostponeDeviceSetupToast";
  v13 = 0;
  v16 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"CloudExperienceHostAPI.ScheduledTasksRegistrationManagerCore",
    0x3Du,
    0x3Cu);
  ActivationFactory = RoGetActivationFactory(v16, &GUID_b1b3efc4_a1b8_465c_87cd_31e389c2546b, &v13);
  v4 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v12 = 0;
    v5 = v13;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v13 + 48LL);
    v12 = 0;
    v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v14);
    v8 = v6(v5, *(_QWORD *)(v7 + 24), v2, &v12);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v8 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v12);
      v4 = v8;
      if ( v8 >= 0 )
      {
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v12);
        v4 = 0;
        goto LABEL_9;
      }
      v9 = 20;
    }
    else
    {
      v9 = 19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeTriggers.h",
      (const char *)(unsigned int)v8,
      v11);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeTriggers.h",
      (const char *)(unsigned int)ActivationFactory,
      v11);
  }
LABEL_9:
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v13);
  return v4;
}

```

## disassembly

```asm
0x180014cc4  push    rbp
0x180014cc6  push    rbx
0x180014cc7  push    rsi
0x180014cc8  push    rdi
0x180014cc9  mov     rbp, rsp
0x180014ccc  sub     rsp, 78h
0x180014cd0  mov     rax, cs:__security_cookie
0x180014cd7  xor     rax, rsp
0x180014cda  mov     [rbp+var_10], rax
0x180014cde  mov     esi, edx
0x180014ce0  lea     rax, String2; "PostponeDeviceSetupToast"
0x180014ce7  mov     [rbp+var_38], rax
0x180014ceb  mov     [rbp+var_40], 0
0x180014cf3  mov     [rbp+var_18], 0
0x180014cfb  mov     r9d, 3Ch ; '<'; unsigned int
0x180014d01  lea     r8d, [r9+1]; unsigned int
0x180014d05  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_ScheduledTasksRegistrationManagerCore@@3QBGB; "CloudExperienceHostAPI.ScheduledTasksRe"...
0x180014d0c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180014d10  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014d15  lea     r8, [rbp+var_40]
0x180014d19  lea     rdx, _GUID_b1b3efc4_a1b8_465c_87cd_31e389c2546b
0x180014d20  mov     rcx, [rbp+var_18]
0x180014d24  call    cs:__imp_RoGetActivationFactory
0x180014d2a  mov     ebx, eax
0x180014d2c  test    eax, eax
0x180014d2e  jns     short loc_180014D4D
0x180014d30  mov     rcx, [rbp+20h]; this
0x180014d34  mov     r9d, eax; char *
0x180014d37  lea     r8, aShellcommondes_1; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180014d3e  mov     edx, 11h; void *
0x180014d43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d48  jmp     loc_180014DD7
0x180014d4d  mov     [rbp+var_48], 0
0x180014d55  mov     rdi, [rbp+var_40]
0x180014d59  mov     rax, [rdi]
0x180014d5c  mov     rbx, [rax+30h]
0x180014d60  mov     [rbp+var_48], 0
0x180014d68  lea     rdx, [rbp+var_38]
0x180014d6c  lea     rcx, [rbp+hstringHeader]
0x180014d70  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014d75  nop
0x180014d76  lea     r9, [rbp+var_48]
0x180014d7a  mov     r8d, esi
0x180014d7d  mov     rdx, [rax+18h]
0x180014d81  mov     rcx, rdi
0x180014d84  mov     rax, rbx
0x180014d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d8c  mov     ebx, eax
0x180014d8e  test    eax, eax
0x180014d90  jns     short loc_180014DB6
0x180014d92  mov     edx, 13h; void *
0x180014d97  lea     r8, aShellcommondes_1; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180014d9e  mov     r9d, eax; char *
0x180014da1  mov     rcx, [rbp+20h]; this
0x180014da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014daa  nop
0x180014dab  lea     rcx, [rbp+var_48]
0x180014daf  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180014db4  jmp     short loc_180014DD7
0x180014db6  mov     rcx, [rbp+var_48]
0x180014dba  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x180014dbf  mov     ebx, eax
0x180014dc1  test    eax, eax
0x180014dc3  jns     short loc_180014DCC
0x180014dc5  mov     edx, 14h
0x180014dca  jmp     short loc_180014D97
0x180014dcc  lea     rcx, [rbp+var_48]
0x180014dd0  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180014dd5  xor     ebx, ebx
0x180014dd7  lea     rcx, [rbp+var_40]
0x180014ddb  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180014de0  mov     eax, ebx
0x180014de2  mov     rcx, [rbp+var_10]
0x180014de6  xor     rcx, rsp; StackCookie
0x180014de9  call    __security_check_cookie
0x180014dee  add     rsp, 78h
0x180014df2  pop     rdi
0x180014df3  pop     rsi
0x180014df4  pop     rbx
0x180014df5  pop     rbp
0x180014df6  retn
```
