# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000578c`
- end: `0x180005812`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004cac`
- `0x18000dce4`
- `0x18000febc`
- `0x18000fee0`
- `0x180010040`
- `0x18001058c`
- `0x18001ef98`
- `0x18001f020`
- `0x18001f20c`
- `0x180048650`

## callees

- `0x18000578c`
- `0x180008128`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800057c8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800057c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000578c  push    rbx
0x18000578e  push    rsi
0x18000578f  push    rdi
0x180005790  push    r14
0x180005792  sub     rsp, 28h
0x180005796  mov     rsi, rcx
0x180005799  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800057a0  mov     [rcx], rax
0x1800057a3  lea     r14, [rcx+18h]
0x1800057a7  mov     qword ptr [r14], 0
0x1800057ae  mov     [rsp+48h+ppunkMarshal], 0
0x1800057b7  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800057bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800057c1  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800057c6  xor     ecx, ecx; punkOuter
0x1800057c8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800057ce  test    eax, eax
0x1800057d0  js      short loc_1800057FB
0x1800057d2  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800057d7  mov     rax, [rbx]
0x1800057da  mov     rdi, [rax]
0x1800057dd  mov     rcx, r14
0x1800057e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800057e5  mov     r8, r14
0x1800057e8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800057ef  mov     rcx, rbx
0x1800057f2  mov     rax, rdi
0x1800057f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fa  nop
0x1800057fb  lea     rcx, [rsp+48h+ppunkMarshal]
0x180005800  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180005805  mov     rax, rsi
0x180005808  add     rsp, 28h
0x18000580c  pop     r14
0x18000580e  pop     rdi
0x18000580f  pop     rsi
0x180005810  pop     rbx
0x180005811  retn
```
