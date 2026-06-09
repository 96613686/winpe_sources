# wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(ushort const *)

- ea: `0x18001415c`
- end: `0x1800141ff`
- name: `??$GetActivationFactory@UIUserManagerStatics@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserManagerStatics@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `163`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015ee0`

## callees

- `0x180003530`
- `0x18000ccd4`
- `0x18001415c`
- `0x180015cb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800141c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800141c4`

## string_xrefs

- `0x1800141d6`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(_QWORD *a1)
{
  int ActivationFactory; // eax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v5; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  v5 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x744,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x18001415c  push    rbx
0x18001415e  sub     rsp, 60h
0x180014162  mov     rax, cs:__security_cookie
0x180014169  xor     rax, rsp
0x18001416c  mov     [rsp+68h+var_18], rax
0x180014171  mov     rbx, rcx
0x180014174  mov     [rsp+68h+var_40], rcx
0x180014179  mov     [rsp+68h+var_48], 0
0x180014181  mov     [rsp+68h+var_48], 1; int
0x180014189  mov     qword ptr [rcx], 0
0x180014190  mov     [rsp+68h+var_20], 0
0x180014199  mov     r9d, 23h ; '#'; unsigned int
0x18001419f  lea     r8d, [r9+1]; unsigned int
0x1800141a3  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800141aa  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1800141af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800141b4  nop
0x1800141b5  mov     r8, rbx
0x1800141b8  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x1800141bf  mov     rcx, [rsp+68h+var_20]
0x1800141c4  call    cs:__imp_RoGetActivationFactory
0x1800141ca  mov     rcx, [rsp+68h]; this
0x1800141cf  test    eax, eax
0x1800141d1  jns     short loc_1800141E8
0x1800141d3  mov     r9d, eax; char *
0x1800141d6  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800141dd  mov     edx, 744h; void *
0x1800141e2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800141e8  mov     rax, rbx
0x1800141eb  mov     rcx, [rsp+68h+var_18]
0x1800141f0  xor     rcx, rsp; StackCookie
0x1800141f3  call    __security_check_cookie
0x1800141f8  add     rsp, 60h
0x1800141fc  pop     rbx
0x1800141fd  retn
```
