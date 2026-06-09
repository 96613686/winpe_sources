# CredUXParameters::_ValidateAndCreateLogoStream(CREDUI_ADDITIONAL_INFO const *,CREDUI_IMAGE_MIME_TYPE &,Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> &)

- ea: `0x140018c68`
- end: `0x140018cf2`
- name: `?_ValidateAndCreateLogoStream@CredUXParameters@@AEAAJPEBUCREDUI_ADDITIONAL_INFO@@AEAW4CREDUI_IMAGE_MIME_TYPE@@AEAV?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, int *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001877c`
- `0x140018ac0`

## callees

- `0x140005560`
- `0x14000b3a8`
- `0x14000e920`
- `0x1400136fc`
- `0x140018c68`
- `0x140018f1c`

## string_xrefs

- `0x140018cc8`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_ValidateAndCreateLogoStream(
        __int64 a1,
        __int64 a2,
        int *a3,
        struct Windows::Storage::Streams::IRandomAccessStream **a4)
{
  int v7; // eax
  CredUXParameters *v9; // rcx
  int RandomAccessStreamFromBytes; // eax
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetImpl'::`2'::impl) )
  {
    v7 = *(_DWORD *)(a2 + 24);
    if ( v7 >= 5 )
    {
      CredUXTelemetry::InvalidMimeTypeFailure<unsigned short const (&)[53]>();
      return 2147942487LL;
    }
    *a3 = v7;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
  RandomAccessStreamFromBytes = CredUXParameters::CreateRandomAccessStreamFromBytes(
                                  v9,
                                  *(_DWORD *)(a2 + 28),
                                  *(const unsigned __int8 **)(a2 + 16),
                                  a4);
  v11 = RandomAccessStreamFromBytes;
  if ( RandomAccessStreamFromBytes >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29C,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)RandomAccessStreamFromBytes,
    v12);
  return v11;
}

```

## disassembly

```asm
0x140018c68  mov     [rsp+arg_0], rbx
0x140018c6d  mov     [rsp+arg_8], rsi
0x140018c72  push    rdi; int
0x140018c73  sub     rsp, 20h
0x140018c77  mov     rdi, r9
0x140018c7a  mov     rsi, r8
0x140018c7d  mov     rbx, rdx
0x140018c80  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG> `wil::Feature<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetImpl(void)'::`2'::impl
0x140018c87  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::__private_IsEnabled(void)
0x140018c8c  test    al, al
0x140018c8e  jz      short loc_140018CA6
0x140018c90  mov     eax, [rbx+18h]
0x140018c93  cmp     eax, 5
0x140018c96  jl      short loc_140018CA4
0x140018c98  call    ??$InvalidMimeTypeFailure@AEAY0DF@$$CBG@CredUXTelemetry@@SAXAEAY0DF@$$CBG@Z; CredUXTelemetry::InvalidMimeTypeFailure<ushort const (&)[53]>(ushort const (&)[53])
0x140018c9d  mov     eax, 80070057h
0x140018ca2  jmp     short loc_140018CE2
0x140018ca4  mov     [rsi], eax
0x140018ca6  mov     rcx, rdi
0x140018ca9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140018cae  mov     r8, [rbx+10h]; unsigned __int8 *
0x140018cb2  mov     r9, rdi; struct Windows::Storage::Streams::IRandomAccessStream **
0x140018cb5  mov     edx, [rbx+1Ch]; unsigned int
0x140018cb8  call    ?CreateRandomAccessStreamFromBytes@CredUXParameters@@AEAAJIPEBEPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CredUXParameters::CreateRandomAccessStreamFromBytes(uint,uchar const *,Windows::Storage::Streams::IRandomAccessStream * *)
0x140018cbd  mov     ebx, eax
0x140018cbf  test    eax, eax
0x140018cc1  jns     short loc_140018CE0
0x140018cc3  mov     rcx, [rsp+28h]; this
0x140018cc8  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018ccf  mov     r9d, eax; char *
0x140018cd2  mov     edx, 29Ch; void *
0x140018cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018cdc  mov     eax, ebx
0x140018cde  jmp     short loc_140018CE2
0x140018ce0  xor     eax, eax
0x140018ce2  mov     rbx, [rsp+28h+arg_0]
0x140018ce7  mov     rsi, [rsp+28h+arg_8]
0x140018cec  add     rsp, 20h
0x140018cf0  pop     rdi
0x140018cf1  retn
```
