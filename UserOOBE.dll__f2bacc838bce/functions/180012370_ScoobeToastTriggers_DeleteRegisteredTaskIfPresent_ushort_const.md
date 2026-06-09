# ScoobeToastTriggers::DeleteRegisteredTaskIfPresent(ushort const *)

- ea: `0x180012370`
- end: `0x1800124ab`
- name: `?DeleteRegisteredTaskIfPresent@ScoobeToastTriggers@@YAJPEBG@Z`
- size: `315`
- prototype: `__int64 __fastcall(ScoobeToastTriggers *__hidden this, const unsigned __int16 *)`
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
- `0x180012370`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800123d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800123d4`

## string_xrefs

- `0x1800123b5`: `CloudExperienceHostAPI.ScheduledTasksRegistrationManagerCore`
- `0x1800123e7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeTriggers.h`
- `0x180012444`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\scoobe\ScoobeTriggers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ScoobeToastTriggers::DeleteRegisteredTaskIfPresent(
        ScoobeToastTriggers *this,
        const unsigned __int16 *a2)
{
  int ActivationFactory; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 *); // rbx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  const WCHAR *v12; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v12 = L"PostponeDeviceSetupToast";
  v11 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"CloudExperienceHostAPI.ScheduledTasksRegistrationManagerCore",
    0x3Du,
    0x3Cu);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_b1b3efc4_a1b8_465c_87cd_31e389c2546b, &v11);
  v3 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v10 = 0;
    v4 = v11;
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 56LL);
    v10 = 0;
    v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v12);
    v7 = v5(v4, *(_QWORD *)(v6 + 24), &v10);
    v3 = v7;
    if ( v7 >= 0 )
    {
      v7 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v10);
      v3 = v7;
      if ( v7 >= 0 )
      {
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v10);
        v3 = 0;
        goto LABEL_9;
      }
      v8 = 30;
    }
    else
    {
      v8 = 29;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeTriggers.h",
      (const char *)(unsigned int)v7,
      v10);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v10);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\scoobe\\ScoobeTriggers.h",
      (const char *)(unsigned int)ActivationFactory,
      v10);
  }
LABEL_9:
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v11);
  return v3;
}

```

## disassembly

```asm
0x180012370  mov     [rsp-8+arg_0], rbx
0x180012375  mov     [rsp-8+arg_8], rdi
0x18001237a  push    rbp
0x18001237b  mov     rbp, rsp
0x18001237e  sub     rsp, 60h
0x180012382  mov     rax, cs:__security_cookie
0x180012389  xor     rax, rsp
0x18001238c  mov     [rbp+var_8], rax
0x180012390  lea     rax, String2; "PostponeDeviceSetupToast"
0x180012397  mov     [rbp+var_30], rax
0x18001239b  mov     [rbp+var_38], 0
0x1800123a3  mov     [rbp+var_10], 0
0x1800123ab  mov     r9d, 3Ch ; '<'; unsigned int
0x1800123b1  lea     r8d, [r9+1]; unsigned int
0x1800123b5  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_ScheduledTasksRegistrationManagerCore@@3QBGB; "CloudExperienceHostAPI.ScheduledTasksRe"...
0x1800123bc  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800123c0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800123c5  lea     r8, [rbp+var_38]
0x1800123c9  lea     rdx, _GUID_b1b3efc4_a1b8_465c_87cd_31e389c2546b
0x1800123d0  mov     rcx, [rbp+var_10]
0x1800123d4  call    cs:__imp_RoGetActivationFactory
0x1800123da  mov     ebx, eax
0x1800123dc  test    eax, eax
0x1800123de  jns     short loc_1800123FD
0x1800123e0  mov     rcx, [rbp+8]; this
0x1800123e4  mov     r9d, eax; char *
0x1800123e7  lea     r8, aShellcommondes_1; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800123ee  mov     edx, 1Bh; void *
0x1800123f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123f8  jmp     loc_180012484
0x1800123fd  mov     [rbp+var_40], 0
0x180012405  mov     rdi, [rbp+var_38]
0x180012409  mov     rax, [rdi]
0x18001240c  mov     rbx, [rax+38h]
0x180012410  mov     [rbp+var_40], 0
0x180012418  lea     rdx, [rbp+var_30]
0x18001241c  lea     rcx, [rbp+hstringHeader]
0x180012420  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180012425  nop
0x180012426  lea     r8, [rbp+var_40]
0x18001242a  mov     rdx, [rax+18h]
0x18001242e  mov     rcx, rdi
0x180012431  mov     rax, rbx
0x180012434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012439  mov     ebx, eax
0x18001243b  test    eax, eax
0x18001243d  jns     short loc_180012463
0x18001243f  mov     edx, 1Dh; void *
0x180012444  lea     r8, aShellcommondes_1; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18001244b  mov     r9d, eax; char *
0x18001244e  mov     rcx, [rbp+8]; this
0x180012452  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012457  nop
0x180012458  lea     rcx, [rbp+var_40]
0x18001245c  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180012461  jmp     short loc_180012484
0x180012463  mov     rcx, [rbp+var_40]
0x180012467  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x18001246c  mov     ebx, eax
0x18001246e  test    eax, eax
0x180012470  jns     short loc_180012479
0x180012472  mov     edx, 1Eh
0x180012477  jmp     short loc_180012444
0x180012479  lea     rcx, [rbp+var_40]
0x18001247d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180012482  xor     ebx, ebx
0x180012484  lea     rcx, [rbp+var_38]
0x180012488  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001248d  mov     eax, ebx
0x18001248f  mov     rcx, [rbp+var_8]
0x180012493  xor     rcx, rsp; StackCookie
0x180012496  call    __security_check_cookie
0x18001249b  mov     rbx, [rsp+60h+arg_0]
0x1800124a0  mov     rdi, [rsp+60h+arg_8]
0x1800124a5  add     rsp, 60h
0x1800124a9  pop     rbp
0x1800124aa  retn
```
