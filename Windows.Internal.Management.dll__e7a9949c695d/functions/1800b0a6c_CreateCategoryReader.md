# CreateCategoryReader

- ea: `0x1800b0a6c`
- end: `0x1800b0bba`
- name: `CreateCategoryReader`
- size: `334`
- prototype: `void **__fastcall(void **ppvObject, LPCWSTR pszFile)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1184`

## callees

- `0x18000377c`
- `0x18000992c`
- `0x18003ec00`
- `0x1800b0a6c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800b0b22`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800b0b22`
- `XmlLite!CreateXmlReader` at `0x1800b0aa9`
- `XmlLite!CreateXmlReader` at `0x1800b0aa9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall CreateCategoryReader(void **ppvObject, LPCWSTR pszFile)
{
  HRESULT XmlReader; // eax
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  HRESULT v8; // eax
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IStream *ppstm; // [rsp+60h] [rbp+18h] BYREF
  LPCWSTR v14; // [rsp+68h] [rbp+20h] BYREF

  *ppvObject = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppvObject);
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlReader < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)XmlReader,
      v11);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v5,
      v11);
  if ( (unsigned int)dword_1800FA480 > 5 )
  {
    v14 = pszFile;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)retaddr,
      (unsigned int)&byte_1800EA7C7,
      v6,
      v7,
      (__int64)&v14);
  }
  ppstm = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  v8 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = (*(__int64 (__fastcall **)(_QWORD, IStream *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppstm);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
      (const char *)(unsigned int)v9,
      v11);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  return ppvObject;
}

```

## disassembly

```asm
0x1800b0a6c  mov     rax, rsp
0x1800b0a6f  mov     [rax+10h], rbx
0x1800b0a73  mov     [rax+8], rcx
0x1800b0a77  push    rdi
0x1800b0a78  sub     rsp, 40h
0x1800b0a7c  mov     rdi, rdx
0x1800b0a7f  mov     rbx, rcx
0x1800b0a82  mov     dword ptr [rax-18h], 0
0x1800b0a89  mov     qword ptr [rcx], 0
0x1800b0a90  mov     dword ptr [rax-18h], 1
0x1800b0a97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b0a9c  xor     r8d, r8d; pMalloc
0x1800b0a9f  mov     rdx, rbx; ppvObject
0x1800b0aa2  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800b0aa9  call    cs:__imp_CreateXmlReader
0x1800b0aaf  mov     rcx, [rsp+48h]; this
0x1800b0ab4  test    eax, eax
0x1800b0ab6  js      loc_1800B0B7B
0x1800b0abc  mov     rcx, [rbx]
0x1800b0abf  mov     rax, [rcx]
0x1800b0ac2  xor     r8d, r8d
0x1800b0ac5  lea     edx, [r8+4]
0x1800b0ac9  mov     rax, [rax+28h]
0x1800b0acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ad2  mov     rcx, [rsp+48h]; this
0x1800b0ad7  test    eax, eax
0x1800b0ad9  js      loc_1800B0B90
0x1800b0adf  mov     eax, cs:dword_1800FA480
0x1800b0ae5  cmp     eax, 5
0x1800b0ae8  jbe     short loc_1800B0B05
0x1800b0aea  mov     [rsp+48h+arg_18], rdi
0x1800b0aef  lea     rax, [rsp+48h+arg_18]
0x1800b0af4  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800b0af9  lea     rdx, byte_1800EA7C7
0x1800b0b00  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800b0b05  mov     [rsp+48h+ppstm], 0
0x1800b0b0e  lea     rcx, [rsp+48h+ppstm]
0x1800b0b13  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b0b18  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800b0b1d  xor     edx, edx; grfMode
0x1800b0b1f  mov     rcx, rdi; pszFile
0x1800b0b22  call    cs:__imp_SHCreateStreamOnFileW
0x1800b0b28  mov     rcx, [rsp+48h]; this
0x1800b0b2d  test    eax, eax
0x1800b0b2f  js      short loc_1800B0BA5
0x1800b0b31  mov     rcx, [rbx]
0x1800b0b34  mov     rax, [rcx]
0x1800b0b37  mov     rdx, [rsp+48h+ppstm]
0x1800b0b3c  mov     rax, [rax+18h]
0x1800b0b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b45  mov     rcx, [rsp+48h]; this
0x1800b0b4a  test    eax, eax
0x1800b0b4c  js      short loc_1800B0B66
0x1800b0b4e  lea     rcx, [rsp+48h+ppstm]
0x1800b0b53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b0b58  mov     rax, rbx
0x1800b0b5b  mov     rbx, [rsp+48h+arg_8]
0x1800b0b60  add     rsp, 40h
0x1800b0b64  pop     rdi
0x1800b0b65  retn
0x1800b0b66  mov     r9d, eax; char *
0x1800b0b69  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b0b70  mov     edx, 2Fh ; '/'; void *
0x1800b0b75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b0b7b  mov     r9d, eax; char *
0x1800b0b7e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b0b85  mov     edx, 23h ; '#'; void *
0x1800b0b8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b0b90  mov     r9d, eax; char *
0x1800b0b93  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b0b9a  mov     edx, 24h ; '$'; void *
0x1800b0b9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b0ba5  mov     r9d, eax; char *
0x1800b0ba8  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b0baf  mov     edx, 2Eh ; '.'; void *
0x1800b0bb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
