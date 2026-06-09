# wil::GetActivationFactory<Windows::Internal::StateRepository::IHostRuntimeStatics>(ushort const *)

- ea: `0x1400086d4`
- end: `0x14000876b`
- name: `??$GetActivationFactory@UIHostRuntimeStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIHostRuntimeStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: `const WCHAR *__fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x140002210`
- `0x14000834c`
- `0x1400086d4`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008730`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008730`

## string_xrefs

- `0x140008742`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Windows::Internal::StateRepository::IHostRuntimeStatics>(
        const WCHAR *a1)
{
  HSTRING_HEADER *v2; // rax
  int ActivationFactory; // eax
  const WCHAR *v5[3]; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Internal.StateRepository.HostRuntime";
  *(_QWORD *)a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(v2[1].Reserved.Reserved1, &GUID_1493f40f_2e38_4bbc_a161_93f5bdf6d056, a1);
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
0x1400086d4  mov     r11, rsp
0x1400086d7  push    rbx
0x1400086d8  sub     rsp, 70h
0x1400086dc  mov     rax, cs:__security_cookie
0x1400086e3  xor     rax, rsp
0x1400086e6  mov     [rsp+78h+var_10], rax
0x1400086eb  mov     rbx, rcx
0x1400086ee  mov     [r11-38h], rcx
0x1400086f2  mov     [rsp+78h+var_58], 0
0x1400086fa  lea     rax, ?RuntimeClass_Windows_Internal_StateRepository_HostRuntime@@3QBGB; "Windows.Internal.StateRepository.HostRu"...
0x140008701  mov     [r11-48h], rax
0x140008705  mov     [rsp+78h+var_58], 1; int
0x14000870d  mov     qword ptr [rcx], 0
0x140008714  lea     rdx, [r11-48h]
0x140008718  lea     rcx, [r11-30h]
0x14000871c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140008721  nop
0x140008722  mov     r8, rbx
0x140008725  lea     rdx, _GUID_1493f40f_2e38_4bbc_a161_93f5bdf6d056
0x14000872c  mov     rcx, [rax+18h]
0x140008730  call    cs:__imp_RoGetActivationFactory
0x140008736  mov     rcx, [rsp+78h]; this
0x14000873b  test    eax, eax
0x14000873d  jns     short loc_140008754
0x14000873f  mov     r9d, eax; char *
0x140008742  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008749  mov     edx, 744h; void *
0x14000874e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008754  mov     rax, rbx
0x140008757  mov     rcx, [rsp+78h+var_10]
0x14000875c  xor     rcx, rsp; StackCookie
0x14000875f  call    __security_check_cookie
0x140008764  add     rsp, 70h
0x140008768  pop     rbx
0x140008769  retn
```
