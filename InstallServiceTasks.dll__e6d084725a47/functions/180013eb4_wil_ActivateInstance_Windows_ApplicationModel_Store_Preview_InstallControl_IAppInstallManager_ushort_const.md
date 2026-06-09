# wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(ushort const *)

- ea: `0x180013eb4`
- end: `0x180013f4f`
- name: `??$ActivateInstance@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`
- `0x18001c58c`
- `0x18001d008`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x18000d544`
- `0x180010150`
- `0x180013eb4`
- `0x180014f24`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013efd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013efd`

## string_xrefs

- `0x180013ed3`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x180013f0f`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(
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
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(
    v5,
    a1);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(v5);
  return a1;
}

```

## disassembly

```asm
0x180013eb4  mov     r11, rsp
0x180013eb7  push    rbx
0x180013eb8  sub     rsp, 70h
0x180013ebc  mov     rax, cs:__security_cookie
0x180013ec3  xor     rax, rsp
0x180013ec6  mov     [rsp+78h+var_10], rax
0x180013ecb  mov     rbx, rcx
0x180013ece  mov     [rsp+78h+var_48], rcx
0x180013ed3  lea     rax, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180013eda  mov     [r11-48h], rax
0x180013ede  mov     qword ptr [r11-58h], 0
0x180013ee6  lea     rdx, [r11-48h]
0x180013eea  lea     rcx, [r11-30h]
0x180013eee  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013ef3  nop
0x180013ef4  lea     rdx, [rsp+78h+var_58]
0x180013ef9  mov     rcx, [rax+18h]
0x180013efd  call    cs:__imp_RoActivateInstance
0x180013f03  mov     rcx, [rsp+78h]; this
0x180013f08  test    eax, eax
0x180013f0a  jns     short loc_180013F21
0x180013f0c  mov     r9d, eax; char *
0x180013f0f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013f16  mov     edx, 74Dh; void *
0x180013f1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013f21  mov     rdx, rbx
0x180013f24  lea     rcx, [rsp+78h+var_58]
0x180013f29  call    ??$query@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(void)
0x180013f2e  nop
0x180013f2f  lea     rcx, [rsp+78h+var_58]
0x180013f34  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180013f39  mov     rax, rbx
0x180013f3c  mov     rcx, [rsp+78h+var_10]
0x180013f41  xor     rcx, rsp; StackCookie
0x180013f44  call    __security_check_cookie
0x180013f49  add     rsp, 70h
0x180013f4d  pop     rbx
0x180013f4e  retn
```
