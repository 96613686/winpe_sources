# wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(ushort const *)

- ea: `0x180026f1c`
- end: `0x180026ff5`
- name: `??$ActivateInstance@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180031d00`
- `0x1800362a0`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x180020ae0`
- `0x180026f1c`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180026f65`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180026f65`

## string_xrefs

- `0x180026f3b`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x180026fce`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180026fe3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
_QWORD *__fastcall wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3)
{
  HSTRING_HEADER *v4; // rax
  int v5; // eax
  __int64 (__fastcall ***v6)(_QWORD, GUID *, _QWORD *); // rcx
  int v7; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v10; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v11; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager";
  v9 = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v11, &v10, a3);
  v5 = RoActivateInstance(v4[1].Reserved.Reserved1, &v9);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x74D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v5,
      (int)v9);
  v6 = v9;
  *a1 = 0;
  v7 = (**v6)(v6, &GUID_9353e170_8441_4b45_bd72_7c2fa925beee, a1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v7,
      (int)v9);
  if ( v9 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v9)[2])(v9);
  return a1;
}

```

## disassembly

```asm
0x180026f1c  mov     r11, rsp
0x180026f1f  push    rbx
0x180026f20  sub     rsp, 70h
0x180026f24  mov     rax, cs:__security_cookie
0x180026f2b  xor     rax, rsp
0x180026f2e  mov     [rsp+78h+var_10], rax
0x180026f33  mov     rbx, rcx
0x180026f36  mov     [rsp+78h+var_48], rcx
0x180026f3b  lea     rax, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180026f42  mov     [r11-48h], rax
0x180026f46  mov     qword ptr [r11-58h], 0
0x180026f4e  lea     rdx, [r11-48h]
0x180026f52  lea     rcx, [r11-30h]
0x180026f56  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026f5b  nop
0x180026f5c  lea     rdx, [rsp+78h+var_58]
0x180026f61  mov     rcx, [rax+18h]
0x180026f65  call    cs:__imp_RoActivateInstance
0x180026f6b  mov     rcx, [rsp+78h]; this
0x180026f70  test    eax, eax
0x180026f72  js      short loc_180026FE0
0x180026f74  mov     rcx, [rsp+78h+var_58]
0x180026f79  mov     qword ptr [rbx], 0
0x180026f80  mov     rax, [rcx]
0x180026f83  mov     r8, rbx
0x180026f86  lea     rdx, _GUID_9353e170_8441_4b45_bd72_7c2fa925beee
0x180026f8d  mov     rax, [rax]
0x180026f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f95  mov     rcx, [rsp+78h]; this
0x180026f9a  test    eax, eax
0x180026f9c  js      short loc_180026FCB
0x180026f9e  mov     rcx, [rsp+78h+var_58]
0x180026fa3  test    rcx, rcx
0x180026fa6  jz      short loc_180026FB5
0x180026fa8  mov     rdx, [rcx]
0x180026fab  mov     rax, [rdx+10h]
0x180026faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fb4  nop
0x180026fb5  mov     rax, rbx
0x180026fb8  mov     rcx, [rsp+78h+var_10]
0x180026fbd  xor     rcx, rsp; StackCookie
0x180026fc0  call    __security_check_cookie
0x180026fc5  add     rsp, 70h
0x180026fc9  pop     rbx
0x180026fca  retn
0x180026fcb  mov     r9d, eax; char *
0x180026fce  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026fd5  mov     edx, 1CBEh; void *
0x180026fda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026fe0  mov     r9d, eax; char *
0x180026fe3  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026fea  mov     edx, 74Dh; void *
0x180026fef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
