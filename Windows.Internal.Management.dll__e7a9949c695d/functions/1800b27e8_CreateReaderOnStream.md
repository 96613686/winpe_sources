# CreateReaderOnStream

- ea: `0x1800b27e8`
- end: `0x1800b2921`
- name: `CreateReaderOnStream`
- size: `313`
- prototype: `__int64 __fastcall(void **ppvObject, IUnknown *pInputStream)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b2a78`

## callees

- `0x18000992c`
- `0x18003ec00`
- `0x1800b27e8`
- `0x1800b7010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x1800b2825`
- `XmlLite!CreateXmlReader` at `0x1800b2825`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800b28b2`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800b28b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall CreateReaderOnStream(void **ppvObject, IUnknown *pInputStream)
{
  HRESULT XmlReader; // eax
  int v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  int pwszBaseUri; // [rsp+20h] [rbp-28h]
  int pwszBaseUria; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IXmlReaderInput *ppInput; // [rsp+60h] [rbp+18h] BYREF

  *ppvObject = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppvObject);
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlReader < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)XmlReader,
      pwszBaseUri);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v5,
      pwszBaseUri);
  ppInput = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppInput);
  v6 = CreateXmlReaderInputWithEncodingName(pInputStream, 0, L"UTF-16", 0, 0, &ppInput);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v6,
      pwszBaseUria);
  v7 = (*(__int64 (__fastcall **)(_QWORD, IXmlReaderInput *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppInput);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v7,
      pwszBaseUria);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppInput);
  return ppvObject;
}

```

## disassembly

```asm
0x1800b27e8  mov     rax, rsp
0x1800b27eb  mov     [rax+10h], rbx
0x1800b27ef  mov     [rax+8], rcx
0x1800b27f3  push    rdi
0x1800b27f4  sub     rsp, 40h
0x1800b27f8  mov     rdi, rdx
0x1800b27fb  mov     rbx, rcx
0x1800b27fe  mov     dword ptr [rax-18h], 0
0x1800b2805  mov     qword ptr [rcx], 0
0x1800b280c  mov     dword ptr [rax-18h], 1
0x1800b2813  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2818  xor     r8d, r8d; pMalloc
0x1800b281b  mov     rdx, rbx; ppvObject
0x1800b281e  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800b2825  call    cs:__imp_CreateXmlReader
0x1800b282b  mov     rcx, [rsp+48h]; this
0x1800b2830  test    eax, eax
0x1800b2832  jns     short loc_1800B2849
0x1800b2834  mov     r9d, eax; char *
0x1800b2837  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b283e  mov     edx, 14h; void *
0x1800b2843  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2849  mov     rcx, [rbx]
0x1800b284c  mov     rax, [rcx]
0x1800b284f  xor     r8d, r8d
0x1800b2852  lea     edx, [r8+4]
0x1800b2856  mov     rax, [rax+28h]
0x1800b285a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b285f  mov     rcx, [rsp+48h]; this
0x1800b2864  test    eax, eax
0x1800b2866  jns     short loc_1800B287D
0x1800b2868  mov     r9d, eax; char *
0x1800b286b  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b2872  mov     edx, 15h; void *
0x1800b2877  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b287d  mov     [rsp+48h+arg_10], 0
0x1800b2886  lea     rcx, [rsp+48h+arg_10]
0x1800b288b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2890  lea     rax, [rsp+48h+arg_10]
0x1800b2895  mov     [rsp+48h+ppInput], rax; ppInput
0x1800b289a  mov     [rsp+48h+pwszBaseUri], 0; int
0x1800b28a3  xor     r9d, r9d; fEncodingHint
0x1800b28a6  lea     r8, pwszEncodingName; "UTF-16"
0x1800b28ad  xor     edx, edx; pMalloc
0x1800b28af  mov     rcx, rdi; pInputStream
0x1800b28b2  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800b28b8  mov     rcx, [rsp+48h]; this
0x1800b28bd  test    eax, eax
0x1800b28bf  jns     short loc_1800B28D6
0x1800b28c1  mov     r9d, eax; char *
0x1800b28c4  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b28cb  mov     edx, 18h; void *
0x1800b28d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b28d6  mov     rcx, [rbx]
0x1800b28d9  mov     rax, [rcx]
0x1800b28dc  mov     rdx, [rsp+48h+arg_10]
0x1800b28e1  mov     rax, [rax+18h]
0x1800b28e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b28ea  mov     rcx, [rsp+48h]; this
0x1800b28ef  test    eax, eax
0x1800b28f1  jns     short loc_1800B2908
0x1800b28f3  mov     r9d, eax; char *
0x1800b28f6  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b28fd  mov     edx, 19h; void *
0x1800b2902  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2908  lea     rcx, [rsp+48h+arg_10]
0x1800b290d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2912  mov     rax, rbx
0x1800b2915  mov     rbx, [rsp+48h+arg_8]
0x1800b291a  add     rsp, 40h
0x1800b291e  pop     rdi
0x1800b291f  retn
```
