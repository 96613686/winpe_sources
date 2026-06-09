# CloudExperienceHostLaunchTask::ShowToastNotificationFromXml(ushort const *,ushort const *)

- ea: `0x180015d00`
- end: `0x180016013`
- name: `?ShowToastNotificationFromXml@CloudExperienceHostLaunchTask@@AEAAXPEBG0@Z`
- size: `787`
- prototype: `void __fastcall(CloudExperienceHostLaunchTask *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015a90`

## callees

- `0x1800032b0`
- `0x1800041dc`
- `0x18000e2bc`
- `0x18000ee5c`
- `0x18001136c`
- `0x180012328`
- `0x180015d00`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015d61`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015d61`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015e89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015f1b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015e89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015f1b`

## string_xrefs

- `0x180015e00`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`
- `0x180015d40`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x180015dc5`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015e45`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015e9a`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015ed7`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015f2c`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015f7d`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180015fae`: `shell\oobe\user\dll\oobelauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall CloudExperienceHostLaunchTask::ShowToastNotificationFromXml(
        CloudExperienceHostLaunchTask *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // ebx
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD); // rbx
  __int64 v7; // rax
  int v8; // eax
  int ActivationFactory; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-49h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-41h] BYREF
  __int64 v20; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v23; // [rsp+48h] [rbp-21h] BYREF
  __int64 v24; // [rsp+50h] [rbp-19h] BYREF
  const unsigned __int16 *v25; // [rsp+58h] [rbp-11h] BYREF
  const WCHAR *v26; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v28; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v25 = a3;
  v26 = L"Windows.SystemToast.CloudExperienceHostLauncherCustom";
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Xml.Dom.XmlDocument",
    0x21u,
    0x20u);
  v18 = 0;
  v19 = 0;
  v3 = RoActivateInstance(v28, &v19);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v18 = v19;
    }
    else
    {
      v3 = (**v19)(v19, &GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, (__int64 *)&v18);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v19)[2])(v19);
    }
  }
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
  v24 = 0;
  v4 = (**v18)(v18, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v24);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x551,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/com.h",
      (const char *)(unsigned int)v4,
      (int)v18);
  v5 = v24;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 48LL);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v25);
  v8 = v6(v5, *(_QWORD *)(v7 + 24));
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v8,
      (int)v18);
  v23 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Notifications.ToastNotification",
    0x2Bu,
    0x2Au);
  ActivationFactory = RoGetActivationFactory(v28, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v23);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v18);
  v21 = 0;
  v10 = *v23;
  v21 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v10 + 48))(v23, v18, &v21);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v11,
      (int)v18);
  v22 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Notifications.ToastNotificationManager",
    0x32u,
    0x31u);
  v12 = RoGetActivationFactory(v28, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v22);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v12,
      (int)v18);
  v20 = 0;
  v13 = v22;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 56LL);
  v20 = 0;
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v26);
  v16 = v14(v13, *(_QWORD *)(v15 + 24), &v20);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v16,
      (int)v18);
  v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 48LL))(v20, v21);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v17,
      (int)v18);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v22);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v23);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v24);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v18);
}

```

## disassembly

```asm
0x180015d00  push    rbp
0x180015d02  push    rbx
0x180015d03  push    rsi
0x180015d04  push    rdi
0x180015d05  lea     rbp, [rsp-3Fh]
0x180015d0a  sub     rsp, 0A8h
0x180015d11  mov     rax, cs:__security_cookie
0x180015d18  xor     rax, rsp
0x180015d1b  mov     [rbp+57h+var_30], rax
0x180015d1f  mov     [rbp+57h+var_68], r8
0x180015d23  lea     rax, aWindowsSystemt; "Windows.SystemToast.CloudExperienceHost"...
0x180015d2a  mov     [rbp+57h+var_60], rax
0x180015d2e  xor     esi, esi
0x180015d30  mov     [rbp+57h+var_A0], rsi
0x180015d34  mov     [rbp+57h+var_38], rsi
0x180015d38  lea     r9d, [rsi+20h]; unsigned int
0x180015d3c  lea     r8d, [rsi+21h]; unsigned int
0x180015d40  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180015d47  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180015d4b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015d50  nop
0x180015d51  mov     [rbp+57h+var_A0], rsi
0x180015d55  mov     [rbp+57h+var_98], rsi
0x180015d59  lea     rdx, [rbp+57h+var_98]
0x180015d5d  mov     rcx, [rbp+57h+var_38]
0x180015d61  call    cs:__imp_RoActivateInstance
0x180015d67  mov     ebx, eax
0x180015d69  test    eax, eax
0x180015d6b  js      short loc_180015DBA
0x180015d6d  lea     r8d, [rsi+10h]; Size
0x180015d71  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180015d78  lea     rcx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494; Buf1
0x180015d7f  call    memcmp_0
0x180015d84  mov     rcx, [rbp+57h+var_98]
0x180015d88  test    eax, eax
0x180015d8a  jnz     short loc_180015D92
0x180015d8c  mov     [rbp+57h+var_A0], rcx
0x180015d90  jmp     short loc_180015DBA
0x180015d92  mov     rax, [rcx]
0x180015d95  lea     r8, [rbp+57h+var_A0]
0x180015d99  lea     rdx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494
0x180015da0  mov     rax, [rax]
0x180015da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015da8  mov     ebx, eax
0x180015daa  mov     rcx, [rbp+57h+var_98]
0x180015dae  mov     rax, [rcx]
0x180015db1  mov     rax, [rax+10h]
0x180015db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dba  mov     rcx, [rbp+5Fh]; this
0x180015dbe  test    ebx, ebx
0x180015dc0  jns     short loc_180015DD7
0x180015dc2  mov     r9d, ebx; char *
0x180015dc5  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015dcc  mov     edx, 104h; void *
0x180015dd1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015dd7  mov     [rbp+57h+var_70], rsi
0x180015ddb  mov     rcx, [rbp+57h+var_A0]
0x180015ddf  mov     rax, [rcx]
0x180015de2  lea     r8, [rbp+57h+var_70]
0x180015de6  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x180015ded  mov     rax, [rax]
0x180015df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df5  mov     rcx, [rbp+5Fh]; this
0x180015df9  test    eax, eax
0x180015dfb  jns     short loc_180015E12
0x180015dfd  mov     r9d, eax; char *
0x180015e00  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015e07  mov     edx, 551h; void *
0x180015e0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015e12  mov     rdi, [rbp+57h+var_70]
0x180015e16  mov     rax, [rdi]
0x180015e19  mov     rbx, [rax+30h]
0x180015e1d  lea     rdx, [rbp+57h+var_68]
0x180015e21  lea     rcx, [rbp+57h+hstringHeader]
0x180015e25  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015e2a  nop
0x180015e2b  mov     rdx, [rax+18h]
0x180015e2f  mov     rcx, rdi
0x180015e32  mov     rax, rbx
0x180015e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e3a  mov     rcx, [rbp+5Fh]; this
0x180015e3e  test    eax, eax
0x180015e40  jns     short loc_180015E57
0x180015e42  mov     r9d, eax; char *
0x180015e45  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015e4c  mov     edx, 107h; void *
0x180015e51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015e57  mov     [rbp+57h+var_78], rsi
0x180015e5b  mov     [rbp+57h+var_38], rsi
0x180015e5f  mov     r9d, 2Ah ; '*'; unsigned int
0x180015e65  lea     r8d, [r9+1]; unsigned int
0x180015e69  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotification@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x180015e70  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180015e74  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015e79  nop
0x180015e7a  lea     r8, [rbp+57h+var_78]
0x180015e7e  lea     rdx, _GUID_04124b20_82c6_4229_b109_fd9ed4662b53
0x180015e85  mov     rcx, [rbp+57h+var_38]
0x180015e89  call    cs:__imp_RoGetActivationFactory
0x180015e8f  mov     rcx, [rbp+5Fh]; this
0x180015e93  test    eax, eax
0x180015e95  jns     short loc_180015EAC
0x180015e97  mov     r9d, eax; char *
0x180015e9a  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015ea1  mov     edx, 109h; void *
0x180015ea6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015eac  mov     [rbp+57h+var_88], rsi
0x180015eb0  mov     rcx, [rbp+57h+var_78]
0x180015eb4  mov     rax, [rcx]
0x180015eb7  mov     [rbp+57h+var_88], rsi
0x180015ebb  lea     r8, [rbp+57h+var_88]
0x180015ebf  mov     rdx, [rbp+57h+var_A0]
0x180015ec3  mov     rax, [rax+30h]
0x180015ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ecc  mov     rcx, [rbp+5Fh]; this
0x180015ed0  test    eax, eax
0x180015ed2  jns     short loc_180015EE9
0x180015ed4  mov     r9d, eax; char *
0x180015ed7  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015ede  mov     edx, 10Bh; void *
0x180015ee3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015ee9  mov     [rbp+57h+var_80], rsi
0x180015eed  mov     [rbp+57h+var_38], rsi
0x180015ef1  mov     r9d, 31h ; '1'; unsigned int
0x180015ef7  lea     r8d, [r9+1]; unsigned int
0x180015efb  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x180015f02  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180015f06  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015f0b  nop
0x180015f0c  lea     r8, [rbp+57h+var_80]
0x180015f10  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x180015f17  mov     rcx, [rbp+57h+var_38]
0x180015f1b  call    cs:__imp_RoGetActivationFactory
0x180015f21  mov     rcx, [rbp+5Fh]; this
0x180015f25  test    eax, eax
0x180015f27  jns     short loc_180015F3E
0x180015f29  mov     r9d, eax; char *
0x180015f2c  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015f33  mov     edx, 10Dh; void *
0x180015f38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015f3e  mov     [rbp+57h+var_90], rsi
0x180015f42  mov     rdi, [rbp+57h+var_80]
0x180015f46  mov     rax, [rdi]
0x180015f49  mov     rbx, [rax+38h]
0x180015f4d  mov     [rbp+57h+var_90], rsi
0x180015f51  lea     rdx, [rbp+57h+var_60]
0x180015f55  lea     rcx, [rbp+57h+hstringHeader]
0x180015f59  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015f5e  nop
0x180015f5f  lea     r8, [rbp+57h+var_90]
0x180015f63  mov     rdx, [rax+18h]
0x180015f67  mov     rcx, rdi
0x180015f6a  mov     rax, rbx
0x180015f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f72  mov     rcx, [rbp+5Fh]; this
0x180015f76  test    eax, eax
0x180015f78  jns     short loc_180015F8F
0x180015f7a  mov     r9d, eax; char *
0x180015f7d  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015f84  mov     edx, 10Fh; void *
0x180015f89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015f8f  mov     rcx, [rbp+57h+var_90]
0x180015f93  mov     rax, [rcx]
0x180015f96  mov     rdx, [rbp+57h+var_88]
0x180015f9a  mov     rax, [rax+30h]
0x180015f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fa3  mov     rcx, [rbp+5Fh]; this
0x180015fa7  test    eax, eax
0x180015fa9  jns     short loc_180015FC0
0x180015fab  mov     r9d, eax; char *
0x180015fae  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180015fb5  mov     edx, 110h; void *
0x180015fba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015fc0  lea     rcx, [rbp+57h+var_90]
0x180015fc4  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180015fc9  nop
0x180015fca  lea     rcx, [rbp+57h+var_80]
0x180015fce  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180015fd3  nop
0x180015fd4  lea     rcx, [rbp+57h+var_88]
0x180015fd8  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180015fdd  nop
0x180015fde  lea     rcx, [rbp+57h+var_78]
0x180015fe2  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180015fe7  nop
0x180015fe8  lea     rcx, [rbp+57h+var_70]
0x180015fec  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180015ff1  nop
0x180015ff2  lea     rcx, [rbp+57h+var_A0]
0x180015ff6  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180015ffb  mov     rcx, [rbp+57h+var_30]
0x180015fff  xor     rcx, rsp; StackCookie
0x180016002  call    __security_check_cookie
0x180016007  add     rsp, 0A8h
0x18001600e  pop     rdi
0x18001600f  pop     rsi
0x180016010  pop     rbx
0x180016011  pop     rbp
0x180016012  retn
```
