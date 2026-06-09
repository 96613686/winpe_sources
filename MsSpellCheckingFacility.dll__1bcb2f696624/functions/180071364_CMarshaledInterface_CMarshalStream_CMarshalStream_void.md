# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x180071364`
- end: `0x1800713ff`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180071650`

## callees

- `0x18004d0b4`
- `0x180071364`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071385`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1800713cc`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1800713cc`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180071393`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180071393`

## pseudocode

```c
void __fastcall CMarshaledInterface::CMarshalStream::~CMarshalStream(CMarshaledInterface::CMarshalStream *this)
{
  LPSTREAM *v1; // rbx
  bool v3; // zf
  IStream *v4; // rcx
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v1 = (LPSTREAM *)((char *)this + 16);
  v3 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &CMarshaledInterface::CMarshalStream::`vftable';
  if ( !v3 )
  {
    if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    {
      CoReleaseMarshalData(*v1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v1);
    }
    else
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v4 = *v1;
      *v1 = 0;
      CoGetInterfaceAndReleaseStream(v4, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v1);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180071364  mov     [rsp+arg_8], rbx
0x180071369  push    rdi
0x18007136a  sub     rsp, 20h
0x18007136e  lea     rbx, [rcx+10h]
0x180071372  mov     rdi, rcx
0x180071375  cmp     qword ptr [rbx], 0
0x180071379  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x180071380  mov     [rcx], rax
0x180071383  jz      short loc_1800713DC
0x180071385  call    cs:__imp_GetCurrentThreadId
0x18007138b  cmp     [rdi+28h], eax
0x18007138e  jnz     short loc_1800713A3
0x180071390  mov     rcx, [rbx]; pStm
0x180071393  call    cs:__imp_CoReleaseMarshalData
0x180071399  mov     rcx, rbx
0x18007139c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800713a1  jmp     short loc_1800713DC
0x1800713a3  lea     rcx, [rsp+28h+ppv]
0x1800713a8  mov     [rsp+28h+ppv], 0
0x1800713b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800713b6  mov     rcx, [rbx]; pStm
0x1800713b9  lea     r8, [rsp+28h+ppv]; ppv
0x1800713be  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x1800713c5  mov     qword ptr [rbx], 0
0x1800713cc  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1800713d2  lea     rcx, [rsp+28h+ppv]
0x1800713d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800713dc  lea     rcx, [rdi+20h]
0x1800713e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800713e5  mov     rcx, rbx
0x1800713e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800713ed  mov     rbx, [rsp+28h+arg_8]
0x1800713f2  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800713f9  add     rsp, 20h
0x1800713fd  pop     rdi
0x1800713fe  retn
```
