# wil::ActivateInstance<ContentManagement::IContentManagementBroker>(ushort const *)

- ea: `0x180026ffc`
- end: `0x1800270d5`
- name: `??$ActivateInstance@UIContentManagementBroker@ContentManagement@@@wil@@YA?AV?$com_ptr_t@UIContentManagementBroker@ContentManagement@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002dfc0`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x180020ae0`
- `0x180026ffc`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180027045`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180027045`

## string_xrefs

- `0x1800270ae`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800270c3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18002701b`: `ContentManagement.ContentManagementBroker`

## pseudocode

```c
_QWORD *__fastcall wil::ActivateInstance<ContentManagement::IContentManagementBroker>(
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

  v10 = L"ContentManagement.ContentManagementBroker";
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
  v7 = (**v6)(v6, &GUID_44431c59_c5ec_4253_94f7_27563a8a242f, a1);
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
0x180026ffc  mov     r11, rsp
0x180026fff  push    rbx
0x180027000  sub     rsp, 70h
0x180027004  mov     rax, cs:__security_cookie
0x18002700b  xor     rax, rsp
0x18002700e  mov     [rsp+78h+var_10], rax
0x180027013  mov     rbx, rcx
0x180027016  mov     [rsp+78h+var_48], rcx
0x18002701b  lea     rax, ?RuntimeClass_ContentManagement_ContentManagementBroker@@3QBGB; "ContentManagement.ContentManagementBrok"...
0x180027022  mov     [r11-48h], rax
0x180027026  mov     qword ptr [r11-58h], 0
0x18002702e  lea     rdx, [r11-48h]
0x180027032  lea     rcx, [r11-30h]
0x180027036  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002703b  nop
0x18002703c  lea     rdx, [rsp+78h+var_58]
0x180027041  mov     rcx, [rax+18h]
0x180027045  call    cs:__imp_RoActivateInstance
0x18002704b  mov     rcx, [rsp+78h]; this
0x180027050  test    eax, eax
0x180027052  js      short loc_1800270C0
0x180027054  mov     rcx, [rsp+78h+var_58]
0x180027059  mov     qword ptr [rbx], 0
0x180027060  mov     rax, [rcx]
0x180027063  mov     r8, rbx
0x180027066  lea     rdx, _GUID_44431c59_c5ec_4253_94f7_27563a8a242f
0x18002706d  mov     rax, [rax]
0x180027070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027075  mov     rcx, [rsp+78h]; this
0x18002707a  test    eax, eax
0x18002707c  js      short loc_1800270AB
0x18002707e  mov     rcx, [rsp+78h+var_58]
0x180027083  test    rcx, rcx
0x180027086  jz      short loc_180027095
0x180027088  mov     rdx, [rcx]
0x18002708b  mov     rax, [rdx+10h]
0x18002708f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027094  nop
0x180027095  mov     rax, rbx
0x180027098  mov     rcx, [rsp+78h+var_10]
0x18002709d  xor     rcx, rsp; StackCookie
0x1800270a0  call    __security_check_cookie
0x1800270a5  add     rsp, 70h
0x1800270a9  pop     rbx
0x1800270aa  retn
0x1800270ab  mov     r9d, eax; char *
0x1800270ae  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800270b5  mov     edx, 1CBEh; void *
0x1800270ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800270c0  mov     r9d, eax; char *
0x1800270c3  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800270ca  mov     edx, 74Dh; void *
0x1800270cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
