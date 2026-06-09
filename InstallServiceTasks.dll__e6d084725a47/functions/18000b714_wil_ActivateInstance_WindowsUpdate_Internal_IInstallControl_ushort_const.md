# wil::ActivateInstance<WindowsUpdate::Internal::IInstallControl>(ushort const *)

- ea: `0x18000b714`
- end: `0x18000b7af`
- name: `??$ActivateInstance@UIInstallControl@Internal@WindowsUpdate@@@wil@@YA?AV?$com_ptr_t@UIInstallControl@Internal@WindowsUpdate@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f0e0`
- `0x180010230`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x18000b714`
- `0x18000c608`
- `0x18000d544`
- `0x180010150`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000b75d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000b75d`

## string_xrefs

- `0x18000b733`: `WindowsUpdate.Internal.InstallControl`
- `0x18000b76f`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance<WindowsUpdate::Internal::IInstallControl>(__int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v5[4]; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = L"WindowsUpdate.Internal.InstallControl";
  *(_QWORD *)v5 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6);
  v3 = RoActivateInstance(*(_QWORD *)(v2 + 24), v5);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x74D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v3,
      v5[0]);
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<WindowsUpdate::Internal::IInstallControl>(v5, a1);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(v5);
  return a1;
}

```

## disassembly

```asm
0x18000b714  mov     r11, rsp
0x18000b717  push    rbx
0x18000b718  sub     rsp, 70h
0x18000b71c  mov     rax, cs:__security_cookie
0x18000b723  xor     rax, rsp
0x18000b726  mov     [rsp+78h+var_10], rax
0x18000b72b  mov     rbx, rcx
0x18000b72e  mov     [rsp+78h+var_48], rcx
0x18000b733  lea     rax, ?RuntimeClass_WindowsUpdate_Internal_InstallControl@@3QBGB; "WindowsUpdate.Internal.InstallControl"
0x18000b73a  mov     [r11-48h], rax
0x18000b73e  mov     qword ptr [r11-58h], 0
0x18000b746  lea     rdx, [r11-48h]
0x18000b74a  lea     rcx, [r11-30h]
0x18000b74e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000b753  nop
0x18000b754  lea     rdx, [rsp+78h+var_58]
0x18000b759  mov     rcx, [rax+18h]
0x18000b75d  call    cs:__imp_RoActivateInstance
0x18000b763  mov     rcx, [rsp+78h]; this
0x18000b768  test    eax, eax
0x18000b76a  jns     short loc_18000B781
0x18000b76c  mov     r9d, eax; char *
0x18000b76f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b776  mov     edx, 74Dh; void *
0x18000b77b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b781  mov     rdx, rbx
0x18000b784  lea     rcx, [rsp+78h+var_58]
0x18000b789  call    ??$query@UIInstallControl@Internal@WindowsUpdate@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIInstallControl@Internal@WindowsUpdate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<WindowsUpdate::Internal::IInstallControl>(void)
0x18000b78e  nop
0x18000b78f  lea     rcx, [rsp+78h+var_58]
0x18000b794  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18000b799  mov     rax, rbx
0x18000b79c  mov     rcx, [rsp+78h+var_10]
0x18000b7a1  xor     rcx, rsp; StackCookie
0x18000b7a4  call    __security_check_cookie
0x18000b7a9  add     rsp, 70h
0x18000b7ad  pop     rbx
0x18000b7ae  retn
```
