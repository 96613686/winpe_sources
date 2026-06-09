# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000acb8`
- end: `0x18000ad3e`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a3dc`
- `0x18000a960`
- `0x18000aa28`
- `0x18000aaf0`
- `0x18000ab40`
- `0x18000ac08`
- `0x18000ad44`
- `0x180010088`
- `0x18001404c`
- `0x180018a1c`
- `0x180018b2c`
- `0x180019008`
- `0x1800190cc`

## callees

- `0x180007248`
- `0x18000acb8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000acf4`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000acf4`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x18000acb8  push    rbx
0x18000acba  push    rsi
0x18000acbb  push    rdi
0x18000acbc  push    r14
0x18000acbe  sub     rsp, 28h
0x18000acc2  mov     rsi, rcx
0x18000acc5  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000accc  mov     [rcx], rax
0x18000accf  lea     r14, [rcx+18h]
0x18000acd3  mov     qword ptr [r14], 0
0x18000acda  mov     [rsp+48h+ppunkMarshal], 0
0x18000ace3  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000ace8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000aced  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000acf2  xor     ecx, ecx; punkOuter
0x18000acf4  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000acfa  test    eax, eax
0x18000acfc  js      short loc_18000AD27
0x18000acfe  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000ad03  mov     rax, [rbx]
0x18000ad06  mov     rdi, [rax]
0x18000ad09  mov     rcx, r14
0x18000ad0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ad11  mov     r8, r14
0x18000ad14  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000ad1b  mov     rcx, rbx
0x18000ad1e  mov     rax, rdi
0x18000ad21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad26  nop
0x18000ad27  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000ad2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ad31  mov     rax, rsi
0x18000ad34  add     rsp, 28h
0x18000ad38  pop     r14
0x18000ad3a  pop     rdi
0x18000ad3b  pop     rsi
0x18000ad3c  pop     rbx
0x18000ad3d  retn
```
