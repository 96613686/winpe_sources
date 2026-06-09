# EnvironmentDefaultImpl::get_IdentityClientBinaryVersion(HSTRING__ * *)

- ea: `0x18003d060`
- end: `0x18003d0b7`
- name: `?get_IdentityClientBinaryVersion@EnvironmentDefaultImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `87`
- prototype: `int(EnvironmentDefaultImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800153f8`
- `0x180029350`
- `0x18003d060`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d086`

## string_xrefs

- `0x18003d097`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::get_IdentityClientBinaryVersion(EnvironmentDefaultImpl *this, HSTRING *a2)
{
  HSTRING *v2; // rbx
  HRESULT String; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl'::`2'::impl,
    a2);
  String = WindowsCreateString(L"3", 1u, v2);
  v4 = String;
  if ( String >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\environment.cpp",
    (const char *)(unsigned int)String,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18003d060  push    rbx; int
0x18003d062  sub     rsp, 20h
0x18003d066  mov     rbx, rdx
0x18003d069  mov     dl, 1
0x18003d06b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADPinResetV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2> `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl(void)'::`2'::impl
0x18003d072  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003d077  mov     r8, rbx; string
0x18003d07a  lea     rcx, a3; "3"
0x18003d081  mov     edx, 1; length
0x18003d086  call    cs:__imp_WindowsCreateString
0x18003d08c  mov     ebx, eax
0x18003d08e  test    eax, eax
0x18003d090  jns     short loc_18003D0AF
0x18003d092  mov     rcx, [rsp+28h]; this
0x18003d097  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x18003d09e  mov     r9d, eax; char *
0x18003d0a1  mov     edx, 0CCh; void *
0x18003d0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d0ab  mov     eax, ebx
0x18003d0ad  jmp     short loc_18003D0B1
0x18003d0af  xor     eax, eax
0x18003d0b1  add     rsp, 20h
0x18003d0b5  pop     rbx
0x18003d0b6  retn
```
