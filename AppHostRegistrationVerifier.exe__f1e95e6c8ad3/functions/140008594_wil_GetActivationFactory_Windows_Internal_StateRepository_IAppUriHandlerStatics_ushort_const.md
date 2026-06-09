# wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerStatics>(ushort const *)

- ea: `0x140008594`
- end: `0x14000862b`
- name: `??$GetActivationFactory@UIAppUriHandlerStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
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
- `0x140008594`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400085f0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400085f0`

## string_xrefs

- `0x140008602`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1400085ba`: `Windows.Internal.StateRepository.AppUriHandler`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerStatics>(
        const WCHAR *a1)
{
  HSTRING_HEADER *v2; // rax
  int ActivationFactory; // eax
  const WCHAR *v5[3]; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Internal.StateRepository.AppUriHandler";
  *(_QWORD *)a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(v2[1].Reserved.Reserved1, &GUID_1ba5bc58_ad5e_40de_9bf8_da4b9f7d0d90, a1);
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
0x140008594  mov     r11, rsp
0x140008597  push    rbx
0x140008598  sub     rsp, 70h
0x14000859c  mov     rax, cs:__security_cookie
0x1400085a3  xor     rax, rsp
0x1400085a6  mov     [rsp+78h+var_10], rax
0x1400085ab  mov     rbx, rcx
0x1400085ae  mov     [r11-38h], rcx
0x1400085b2  mov     [rsp+78h+var_58], 0
0x1400085ba  lea     rax, ?RuntimeClass_Windows_Internal_StateRepository_AppUriHandler@@3QBGB; "Windows.Internal.StateRepository.AppUri"...
0x1400085c1  mov     [r11-48h], rax
0x1400085c5  mov     [rsp+78h+var_58], 1; int
0x1400085cd  mov     qword ptr [rcx], 0
0x1400085d4  lea     rdx, [r11-48h]
0x1400085d8  lea     rcx, [r11-30h]
0x1400085dc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400085e1  nop
0x1400085e2  mov     r8, rbx
0x1400085e5  lea     rdx, _GUID_1ba5bc58_ad5e_40de_9bf8_da4b9f7d0d90
0x1400085ec  mov     rcx, [rax+18h]
0x1400085f0  call    cs:__imp_RoGetActivationFactory
0x1400085f6  mov     rcx, [rsp+78h]; this
0x1400085fb  test    eax, eax
0x1400085fd  jns     short loc_140008614
0x1400085ff  mov     r9d, eax; char *
0x140008602  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008609  mov     edx, 744h; void *
0x14000860e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008614  mov     rax, rbx
0x140008617  mov     rcx, [rsp+78h+var_10]
0x14000861c  xor     rcx, rsp; StackCookie
0x14000861f  call    __security_check_cookie
0x140008624  add     rsp, 70h
0x140008628  pop     rbx
0x140008629  retn
```
