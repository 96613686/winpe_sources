# wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(ushort const *)

- ea: `0x1400084f4`
- end: `0x14000858b`
- name: `??$GetActivationFactory@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: `const WCHAR *__fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c3ec`

## callees

- `0x140002210`
- `0x14000834c`
- `0x1400084f4`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008550`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008550`

## string_xrefs

- `0x140008562`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x14000851a`: `Windows.Internal.StateRepository.AppUriHandlerGroup`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(
        const WCHAR *a1)
{
  HSTRING_HEADER *v2; // rax
  int ActivationFactory; // eax
  const WCHAR *v5[3]; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Internal.StateRepository.AppUriHandlerGroup";
  *(_QWORD *)a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(v2[1].Reserved.Reserved1, &GUID_663fe24b_04ad_4778_8c44_71a357b68188, a1);
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
0x1400084f4  mov     r11, rsp
0x1400084f7  push    rbx
0x1400084f8  sub     rsp, 70h
0x1400084fc  mov     rax, cs:__security_cookie
0x140008503  xor     rax, rsp
0x140008506  mov     [rsp+78h+var_10], rax
0x14000850b  mov     rbx, rcx
0x14000850e  mov     [r11-38h], rcx
0x140008512  mov     [rsp+78h+var_58], 0
0x14000851a  lea     rax, ?RuntimeClass_Windows_Internal_StateRepository_AppUriHandlerGroup@@3QBGB; "Windows.Internal.StateRepository.AppUri"...
0x140008521  mov     [r11-48h], rax
0x140008525  mov     [rsp+78h+var_58], 1; int
0x14000852d  mov     qword ptr [rcx], 0
0x140008534  lea     rdx, [r11-48h]
0x140008538  lea     rcx, [r11-30h]
0x14000853c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140008541  nop
0x140008542  mov     r8, rbx
0x140008545  lea     rdx, _GUID_663fe24b_04ad_4778_8c44_71a357b68188
0x14000854c  mov     rcx, [rax+18h]
0x140008550  call    cs:__imp_RoGetActivationFactory
0x140008556  mov     rcx, [rsp+78h]; this
0x14000855b  test    eax, eax
0x14000855d  jns     short loc_140008574
0x14000855f  mov     r9d, eax; char *
0x140008562  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008569  mov     edx, 744h; void *
0x14000856e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008574  mov     rax, rbx
0x140008577  mov     rcx, [rsp+78h+var_10]
0x14000857c  xor     rcx, rsp; StackCookie
0x14000857f  call    __security_check_cookie
0x140008584  add     rsp, 70h
0x140008588  pop     rbx
0x140008589  retn
```
