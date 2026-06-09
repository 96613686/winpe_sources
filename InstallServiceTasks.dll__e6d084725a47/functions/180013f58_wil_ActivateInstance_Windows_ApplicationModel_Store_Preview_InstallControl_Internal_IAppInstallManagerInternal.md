# wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(ushort const *)

- ea: `0x180013f58`
- end: `0x180013ff3`
- name: `??$ActivateInstance@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`
- `0x180020a1c`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x18000d544`
- `0x180010150`
- `0x180013f58`
- `0x180014f7c`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013fa1`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013fa1`

## string_xrefs

- `0x180013f77`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x180013fb3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v5[4]; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager";
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
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(
    v5,
    a1);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(v5);
  return a1;
}

```

## disassembly

```asm
0x180013f58  mov     r11, rsp
0x180013f5b  push    rbx
0x180013f5c  sub     rsp, 70h
0x180013f60  mov     rax, cs:__security_cookie
0x180013f67  xor     rax, rsp
0x180013f6a  mov     [rsp+78h+var_10], rax
0x180013f6f  mov     rbx, rcx
0x180013f72  mov     [rsp+78h+var_48], rcx
0x180013f77  lea     rax, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180013f7e  mov     [r11-48h], rax
0x180013f82  mov     qword ptr [r11-58h], 0
0x180013f8a  lea     rdx, [r11-48h]
0x180013f8e  lea     rcx, [r11-30h]
0x180013f92  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013f97  nop
0x180013f98  lea     rdx, [rsp+78h+var_58]
0x180013f9d  mov     rcx, [rax+18h]
0x180013fa1  call    cs:__imp_RoActivateInstance
0x180013fa7  mov     rcx, [rsp+78h]; this
0x180013fac  test    eax, eax
0x180013fae  jns     short loc_180013FC5
0x180013fb0  mov     r9d, eax; char *
0x180013fb3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013fba  mov     edx, 74Dh; void *
0x180013fbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013fc5  mov     rdx, rbx
0x180013fc8  lea     rcx, [rsp+78h+var_58]
0x180013fcd  call    ??$query@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(void)
0x180013fd2  nop
0x180013fd3  lea     rcx, [rsp+78h+var_58]
0x180013fd8  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180013fdd  mov     rax, rbx
0x180013fe0  mov     rcx, [rsp+78h+var_10]
0x180013fe5  xor     rcx, rsp; StackCookie
0x180013fe8  call    __security_check_cookie
0x180013fed  add     rsp, 70h
0x180013ff1  pop     rbx
0x180013ff2  retn
```
