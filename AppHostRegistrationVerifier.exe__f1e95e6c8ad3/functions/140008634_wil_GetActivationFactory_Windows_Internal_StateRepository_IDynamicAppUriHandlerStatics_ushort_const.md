# wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics>(ushort const *)

- ea: `0x140008634`
- end: `0x1400086cb`
- name: `??$GetActivationFactory@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: `const WCHAR *__fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x140002210`
- `0x14000834c`
- `0x140008634`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008690`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008690`

## string_xrefs

- `0x1400086a2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x14000865a`: `Windows.Internal.StateRepository.DynamicAppUriHandler`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics>(
        const WCHAR *a1)
{
  HSTRING_HEADER *v2; // rax
  int ActivationFactory; // eax
  const WCHAR *v5[3]; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Internal.StateRepository.DynamicAppUriHandler";
  *(_QWORD *)a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(v2[1].Reserved.Reserved1, &GUID_f2167c88_5b7a_4958_8195_7fa7a62f3815, a1);
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
0x140008634  mov     r11, rsp
0x140008637  push    rbx
0x140008638  sub     rsp, 70h
0x14000863c  mov     rax, cs:__security_cookie
0x140008643  xor     rax, rsp
0x140008646  mov     [rsp+78h+var_10], rax
0x14000864b  mov     rbx, rcx
0x14000864e  mov     [r11-38h], rcx
0x140008652  mov     [rsp+78h+var_58], 0
0x14000865a  lea     rax, ?RuntimeClass_Windows_Internal_StateRepository_DynamicAppUriHandler@@3QBGB; "Windows.Internal.StateRepository.Dynami"...
0x140008661  mov     [r11-48h], rax
0x140008665  mov     [rsp+78h+var_58], 1; int
0x14000866d  mov     qword ptr [rcx], 0
0x140008674  lea     rdx, [r11-48h]
0x140008678  lea     rcx, [r11-30h]
0x14000867c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140008681  nop
0x140008682  mov     r8, rbx
0x140008685  lea     rdx, _GUID_f2167c88_5b7a_4958_8195_7fa7a62f3815
0x14000868c  mov     rcx, [rax+18h]
0x140008690  call    cs:__imp_RoGetActivationFactory
0x140008696  mov     rcx, [rsp+78h]; this
0x14000869b  test    eax, eax
0x14000869d  jns     short loc_1400086B4
0x14000869f  mov     r9d, eax; char *
0x1400086a2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400086a9  mov     edx, 744h; void *
0x1400086ae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400086b4  mov     rax, rbx
0x1400086b7  mov     rcx, [rsp+78h+var_10]
0x1400086bc  xor     rcx, rsp; StackCookie
0x1400086bf  call    __security_check_cookie
0x1400086c4  add     rsp, 70h
0x1400086c8  pop     rbx
0x1400086c9  retn
```
