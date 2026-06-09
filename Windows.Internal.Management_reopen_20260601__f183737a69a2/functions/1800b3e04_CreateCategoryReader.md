# CreateCategoryReader

- ea: `0x1800b3e04`
- end: `0x1800b3f5f`
- name: `CreateCategoryReader`
- size: `347`
- prototype: `__int64 __fastcall(void **ppvObject, LPCWSTR pszFile)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b4544`

## callees

- `0x180003884`
- `0x180009be4`
- `0x18003e5d4`
- `0x1800b3e04`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800b3ec0`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800b3ec0`
- `XmlLite!CreateXmlReader` at `0x1800b3e41`
- `XmlLite!CreateXmlReader` at `0x1800b3e41`

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
  if ( (unsigned int)dword_1800FE488 > 5 )
  {
    v14 = pszFile;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)retaddr,
      (unsigned int)&byte_1800EE5A7,
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
0x1800b3e04  mov     rax, rsp
0x1800b3e07  mov     [rax+10h], rbx
0x1800b3e0b  mov     [rax+8], rcx
0x1800b3e0f  push    rdi
0x1800b3e10  sub     rsp, 40h
0x1800b3e14  mov     rdi, rdx
0x1800b3e17  mov     rbx, rcx
0x1800b3e1a  mov     dword ptr [rax-18h], 0
0x1800b3e21  mov     qword ptr [rcx], 0
0x1800b3e28  mov     dword ptr [rax-18h], 1
0x1800b3e2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3e34  xor     r8d, r8d; pMalloc
0x1800b3e37  mov     rdx, rbx; ppvObject
0x1800b3e3a  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800b3e41  call    cs:__imp_CreateXmlReader
0x1800b3e48  nop     dword ptr [rax+rax+00h]
0x1800b3e4d  mov     rcx, [rsp+48h]; this
0x1800b3e52  test    eax, eax
0x1800b3e54  js      loc_1800B3F20
0x1800b3e5a  mov     rcx, [rbx]
0x1800b3e5d  mov     rax, [rcx]
0x1800b3e60  xor     r8d, r8d
0x1800b3e63  lea     edx, [r8+4]
0x1800b3e67  mov     rax, [rax+28h]
0x1800b3e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e70  mov     rcx, [rsp+48h]; this
0x1800b3e75  test    eax, eax
0x1800b3e77  js      loc_1800B3F35
0x1800b3e7d  mov     eax, cs:dword_1800FE488
0x1800b3e83  cmp     eax, 5
0x1800b3e86  jbe     short loc_1800B3EA3
0x1800b3e88  mov     [rsp+48h+arg_18], rdi
0x1800b3e8d  lea     rax, [rsp+48h+arg_18]
0x1800b3e92  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800b3e97  lea     rdx, byte_1800EE5A7
0x1800b3e9e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800b3ea3  mov     [rsp+48h+ppstm], 0
0x1800b3eac  lea     rcx, [rsp+48h+ppstm]
0x1800b3eb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3eb6  lea     r8, [rsp+48h+ppstm]; ppstm
0x1800b3ebb  xor     edx, edx; grfMode
0x1800b3ebd  mov     rcx, rdi; pszFile
0x1800b3ec0  call    cs:__imp_SHCreateStreamOnFileW
0x1800b3ec7  nop     dword ptr [rax+rax+00h]
0x1800b3ecc  mov     rcx, [rsp+48h]; this
0x1800b3ed1  test    eax, eax
0x1800b3ed3  js      short loc_1800B3F4A
0x1800b3ed5  mov     rcx, [rbx]
0x1800b3ed8  mov     rax, [rcx]
0x1800b3edb  mov     rdx, [rsp+48h+ppstm]
0x1800b3ee0  mov     rax, [rax+18h]
0x1800b3ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ee9  mov     rcx, [rsp+48h]; this
0x1800b3eee  test    eax, eax
0x1800b3ef0  js      short loc_1800B3F0B
0x1800b3ef2  lea     rcx, [rsp+48h+ppstm]
0x1800b3ef7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3efc  mov     rax, rbx
0x1800b3eff  mov     rbx, [rsp+48h+arg_8]
0x1800b3f04  add     rsp, 40h
0x1800b3f08  pop     rdi
0x1800b3f09  retn
0x1800b3f0b  mov     r9d, eax; char *
0x1800b3f0e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b3f15  mov     edx, 2Fh ; '/'; void *
0x1800b3f1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3f20  mov     r9d, eax; char *
0x1800b3f23  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b3f2a  mov     edx, 23h ; '#'; void *
0x1800b3f2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3f35  mov     r9d, eax; char *
0x1800b3f38  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b3f3f  mov     edx, 24h ; '$'; void *
0x1800b3f44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3f4a  mov     r9d, eax; char *
0x1800b3f4d  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800b3f54  mov     edx, 2Eh ; '.'; void *
0x1800b3f59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
