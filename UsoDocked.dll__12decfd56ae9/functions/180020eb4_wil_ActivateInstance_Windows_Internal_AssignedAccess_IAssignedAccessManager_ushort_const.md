# wil::ActivateInstance<Windows::Internal::AssignedAccess::IAssignedAccessManager>(ushort const *)

- ea: `0x180020eb4`
- end: `0x180020f8d`
- name: `??$ActivateInstance@UIAssignedAccessManager@AssignedAccess@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAssignedAccessManager@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021e80`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x180020ae0`
- `0x180020eb4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180020efd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180020efd`

## string_xrefs

- `0x180020f66`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180020f7b`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180020ed3`: `Windows.Internal.AssignedAccess.AssignedAccessManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall wil::ActivateInstance<Windows::Internal::AssignedAccess::IAssignedAccessManager>(
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

  v10 = L"Windows.Internal.AssignedAccess.AssignedAccessManager";
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
  v7 = (**v6)(v6, &GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a, a1);
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
0x180020eb4  mov     r11, rsp
0x180020eb7  push    rbx
0x180020eb8  sub     rsp, 70h
0x180020ebc  mov     rax, cs:__security_cookie
0x180020ec3  xor     rax, rsp
0x180020ec6  mov     [rsp+78h+var_10], rax
0x180020ecb  mov     rbx, rcx
0x180020ece  mov     [rsp+78h+var_48], rcx
0x180020ed3  lea     rax, ?RuntimeClass_Windows_Internal_AssignedAccess_AssignedAccessManager@@3QBGB; "Windows.Internal.AssignedAccess.Assigne"...
0x180020eda  mov     [r11-48h], rax
0x180020ede  mov     qword ptr [r11-58h], 0
0x180020ee6  lea     rdx, [r11-48h]
0x180020eea  lea     rcx, [r11-30h]
0x180020eee  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020ef3  nop
0x180020ef4  lea     rdx, [rsp+78h+var_58]
0x180020ef9  mov     rcx, [rax+18h]
0x180020efd  call    cs:__imp_RoActivateInstance
0x180020f03  mov     rcx, [rsp+78h]; this
0x180020f08  test    eax, eax
0x180020f0a  js      short loc_180020F78
0x180020f0c  mov     rcx, [rsp+78h+var_58]
0x180020f11  mov     qword ptr [rbx], 0
0x180020f18  mov     rax, [rcx]
0x180020f1b  mov     r8, rbx
0x180020f1e  lea     rdx, _GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a
0x180020f25  mov     rax, [rax]
0x180020f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f2d  mov     rcx, [rsp+78h]; this
0x180020f32  test    eax, eax
0x180020f34  js      short loc_180020F63
0x180020f36  mov     rcx, [rsp+78h+var_58]
0x180020f3b  test    rcx, rcx
0x180020f3e  jz      short loc_180020F4D
0x180020f40  mov     rdx, [rcx]
0x180020f43  mov     rax, [rdx+10h]
0x180020f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f4c  nop
0x180020f4d  mov     rax, rbx
0x180020f50  mov     rcx, [rsp+78h+var_10]
0x180020f55  xor     rcx, rsp; StackCookie
0x180020f58  call    __security_check_cookie
0x180020f5d  add     rsp, 70h
0x180020f61  pop     rbx
0x180020f62  retn
0x180020f63  mov     r9d, eax; char *
0x180020f66  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020f6d  mov     edx, 1CBEh; void *
0x180020f72  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020f78  mov     r9d, eax; char *
0x180020f7b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020f82  mov     edx, 74Dh; void *
0x180020f87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
