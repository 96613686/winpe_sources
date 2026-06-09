# wil::GetActivationFactory<Windows::Internal::StateRepository::IUserStatics>(ushort const *)

- ea: `0x140008774`
- end: `0x14000880b`
- name: `??$GetActivationFactory@UIUserStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: `const WCHAR *__fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c33c`

## callees

- `0x140002210`
- `0x14000834c`
- `0x140008774`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400087d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400087d0`

## string_xrefs

- `0x1400087e2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Windows::Internal::StateRepository::IUserStatics>(const WCHAR *a1)
{
  HSTRING_HEADER *v2; // rax
  int ActivationFactory; // eax
  const WCHAR *v5[3]; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Internal.StateRepository.User";
  *(_QWORD *)a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(v2[1].Reserved.Reserved1, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, a1);
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
0x140008774  mov     r11, rsp
0x140008777  push    rbx
0x140008778  sub     rsp, 70h
0x14000877c  mov     rax, cs:__security_cookie
0x140008783  xor     rax, rsp
0x140008786  mov     [rsp+78h+var_10], rax
0x14000878b  mov     rbx, rcx
0x14000878e  mov     [r11-38h], rcx
0x140008792  mov     [rsp+78h+var_58], 0
0x14000879a  lea     rax, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x1400087a1  mov     [r11-48h], rax
0x1400087a5  mov     [rsp+78h+var_58], 1; int
0x1400087ad  mov     qword ptr [rcx], 0
0x1400087b4  lea     rdx, [r11-48h]
0x1400087b8  lea     rcx, [r11-30h]
0x1400087bc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400087c1  nop
0x1400087c2  mov     r8, rbx
0x1400087c5  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x1400087cc  mov     rcx, [rax+18h]
0x1400087d0  call    cs:__imp_RoGetActivationFactory
0x1400087d6  mov     rcx, [rsp+78h]; this
0x1400087db  test    eax, eax
0x1400087dd  jns     short loc_1400087F4
0x1400087df  mov     r9d, eax; char *
0x1400087e2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400087e9  mov     edx, 744h; void *
0x1400087ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400087f4  mov     rax, rbx
0x1400087f7  mov     rcx, [rsp+78h+var_10]
0x1400087fc  xor     rcx, rsp; StackCookie
0x1400087ff  call    __security_check_cookie
0x140008804  add     rsp, 70h
0x140008808  pop     rbx
0x140008809  retn
```
