# wil::ActivateInstance<Windows::Internal::InstallService::Control::IInstallServiceControl>(ushort const *)

- ea: `0x18000b7b8`
- end: `0x18000b853`
- name: `??$ActivateInstance@UIInstallServiceControl@Control@InstallService@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIInstallServiceControl@Control@InstallService@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
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
- `0x18000b7b8`
- `0x18000c660`
- `0x18000d544`
- `0x180010150`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000b801`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000b801`

## string_xrefs

- `0x18000b813`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18000b7d7`: `Windows.Internal.InstallService.Control.InstallServiceControl`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance<Windows::Internal::InstallService::Control::IInstallServiceControl>(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v5[4]; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = L"Windows.Internal.InstallService.Control.InstallServiceControl";
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
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Internal::InstallService::Control::IInstallServiceControl>(
    v5,
    a1);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(v5);
  return a1;
}

```

## disassembly

```asm
0x18000b7b8  mov     r11, rsp
0x18000b7bb  push    rbx
0x18000b7bc  sub     rsp, 70h
0x18000b7c0  mov     rax, cs:__security_cookie
0x18000b7c7  xor     rax, rsp
0x18000b7ca  mov     [rsp+78h+var_10], rax
0x18000b7cf  mov     rbx, rcx
0x18000b7d2  mov     [rsp+78h+var_48], rcx
0x18000b7d7  lea     rax, ?RuntimeClass_Windows_Internal_InstallService_Control_InstallServiceControl@@3QBGB; "Windows.Internal.InstallService.Control"...
0x18000b7de  mov     [r11-48h], rax
0x18000b7e2  mov     qword ptr [r11-58h], 0
0x18000b7ea  lea     rdx, [r11-48h]
0x18000b7ee  lea     rcx, [r11-30h]
0x18000b7f2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000b7f7  nop
0x18000b7f8  lea     rdx, [rsp+78h+var_58]
0x18000b7fd  mov     rcx, [rax+18h]
0x18000b801  call    cs:__imp_RoActivateInstance
0x18000b807  mov     rcx, [rsp+78h]; this
0x18000b80c  test    eax, eax
0x18000b80e  jns     short loc_18000B825
0x18000b810  mov     r9d, eax; char *
0x18000b813  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b81a  mov     edx, 74Dh; void *
0x18000b81f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b825  mov     rdx, rbx
0x18000b828  lea     rcx, [rsp+78h+var_58]
0x18000b82d  call    ??$query@UIInstallServiceControl@Control@InstallService@Internal@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIInstallServiceControl@Control@InstallService@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Internal::InstallService::Control::IInstallServiceControl>(void)
0x18000b832  nop
0x18000b833  lea     rcx, [rsp+78h+var_58]
0x18000b838  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18000b83d  mov     rax, rbx
0x18000b840  mov     rcx, [rsp+78h+var_10]
0x18000b845  xor     rcx, rsp; StackCookie
0x18000b848  call    __security_check_cookie
0x18000b84d  add     rsp, 70h
0x18000b851  pop     rbx
0x18000b852  retn
```
