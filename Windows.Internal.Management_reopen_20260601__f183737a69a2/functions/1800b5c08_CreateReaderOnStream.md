# CreateReaderOnStream

- ea: `0x1800b5c08`
- end: `0x1800b5d4d`
- name: `CreateReaderOnStream`
- size: `325`
- prototype: `__int64 __fastcall(void **ppvObject, IUnknown *pInputStream)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b5eb8`

## callees

- `0x180009be4`
- `0x18003e5d4`
- `0x1800b5c08`
- `0x1800bb010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x1800b5c45`
- `XmlLite!CreateXmlReader` at `0x1800b5c45`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800b5cd8`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800b5cd8`

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
0x1800b5c08  mov     rax, rsp
0x1800b5c0b  mov     [rax+10h], rbx
0x1800b5c0f  mov     [rax+8], rcx
0x1800b5c13  push    rdi
0x1800b5c14  sub     rsp, 40h
0x1800b5c18  mov     rdi, rdx
0x1800b5c1b  mov     rbx, rcx
0x1800b5c1e  mov     dword ptr [rax-18h], 0
0x1800b5c25  mov     qword ptr [rcx], 0
0x1800b5c2c  mov     dword ptr [rax-18h], 1
0x1800b5c33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5c38  xor     r8d, r8d; pMalloc
0x1800b5c3b  mov     rdx, rbx; ppvObject
0x1800b5c3e  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800b5c45  call    cs:__imp_CreateXmlReader
0x1800b5c4c  nop     dword ptr [rax+rax+00h]
0x1800b5c51  mov     rcx, [rsp+48h]; this
0x1800b5c56  test    eax, eax
0x1800b5c58  jns     short loc_1800B5C6F
0x1800b5c5a  mov     r9d, eax; char *
0x1800b5c5d  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b5c64  mov     edx, 14h; void *
0x1800b5c69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5c6f  mov     rcx, [rbx]
0x1800b5c72  mov     rax, [rcx]
0x1800b5c75  xor     r8d, r8d
0x1800b5c78  lea     edx, [r8+4]
0x1800b5c7c  mov     rax, [rax+28h]
0x1800b5c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5c85  mov     rcx, [rsp+48h]; this
0x1800b5c8a  test    eax, eax
0x1800b5c8c  jns     short loc_1800B5CA3
0x1800b5c8e  mov     r9d, eax; char *
0x1800b5c91  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b5c98  mov     edx, 15h; void *
0x1800b5c9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5ca3  mov     [rsp+48h+arg_10], 0
0x1800b5cac  lea     rcx, [rsp+48h+arg_10]
0x1800b5cb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5cb6  lea     rax, [rsp+48h+arg_10]
0x1800b5cbb  mov     [rsp+48h+ppInput], rax; ppInput
0x1800b5cc0  mov     [rsp+48h+pwszBaseUri], 0; int
0x1800b5cc9  xor     r9d, r9d; fEncodingHint
0x1800b5ccc  lea     r8, pwszEncodingName; "UTF-16"
0x1800b5cd3  xor     edx, edx; pMalloc
0x1800b5cd5  mov     rcx, rdi; pInputStream
0x1800b5cd8  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800b5cdf  nop     dword ptr [rax+rax+00h]
0x1800b5ce4  mov     rcx, [rsp+48h]; this
0x1800b5ce9  test    eax, eax
0x1800b5ceb  jns     short loc_1800B5D02
0x1800b5ced  mov     r9d, eax; char *
0x1800b5cf0  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b5cf7  mov     edx, 18h; void *
0x1800b5cfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5d02  mov     rcx, [rbx]
0x1800b5d05  mov     rax, [rcx]
0x1800b5d08  mov     rdx, [rsp+48h+arg_10]
0x1800b5d0d  mov     rax, [rax+18h]
0x1800b5d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5d16  mov     rcx, [rsp+48h]; this
0x1800b5d1b  test    eax, eax
0x1800b5d1d  jns     short loc_1800B5D34
0x1800b5d1f  mov     r9d, eax; char *
0x1800b5d22  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800b5d29  mov     edx, 19h; void *
0x1800b5d2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5d34  lea     rcx, [rsp+48h+arg_10]
0x1800b5d39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5d3e  mov     rax, rbx
0x1800b5d41  mov     rbx, [rsp+48h+arg_8]
0x1800b5d46  add     rsp, 40h
0x1800b5d4a  pop     rdi
0x1800b5d4b  retn
```
