# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000b47c`
- end: `0x18000b502`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `38`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009638`
- `0x180009bec`
- `0x180009e10`
- `0x18000adf4`
- `0x18000aea0`
- `0x18000af3c`
- `0x18000afd8`
- `0x18000b074`
- `0x18000b110`
- `0x18000b1ac`
- `0x18000b25c`
- `0x18000b2f8`
- `0x18000b394`
- `0x18000b508`
- `0x18000b5a4`
- `0x18000b640`
- `0x18000b6dc`
- `0x18000b778`
- `0x18001c1b0`
- `0x180021010`
- `0x1800210e0`
- `0x1800211b0`
- `0x180021280`
- `0x180021348`
- `0x180022f64`
- `0x180023228`
- `0x180040ed4`
- `0x18005723c`
- `0x180087318`
- `0x18008a2c0`
- `0x1800947d8`
- `0x180094884`
- `0x180094928`
- `0x180097bf4`
- `0x18009a37c`
- `0x1800b1510`
- `0x1800b2404`
- `0x1800dabb4`

## callees

- `0x18000b47c`
- `0x1800101bc`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000b4b8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000b4b8`

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
0x18000b47c  push    rbx
0x18000b47e  push    rsi
0x18000b47f  push    rdi
0x18000b480  push    r14
0x18000b482  sub     rsp, 28h
0x18000b486  mov     rsi, rcx
0x18000b489  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000b490  mov     [rcx], rax
0x18000b493  lea     r14, [rcx+18h]
0x18000b497  mov     qword ptr [r14], 0
0x18000b49e  mov     [rsp+48h+ppunkMarshal], 0
0x18000b4a7  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000b4ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000b4b1  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000b4b6  xor     ecx, ecx; punkOuter
0x18000b4b8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000b4be  test    eax, eax
0x18000b4c0  js      short loc_18000B4EB
0x18000b4c2  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000b4c7  mov     rax, [rbx]
0x18000b4ca  mov     rdi, [rax]
0x18000b4cd  mov     rcx, r14
0x18000b4d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000b4d5  mov     r8, r14
0x18000b4d8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000b4df  mov     rcx, rbx
0x18000b4e2  mov     rax, rdi
0x18000b4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ea  nop
0x18000b4eb  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000b4f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000b4f5  mov     rax, rsi
0x18000b4f8  add     rsp, 28h
0x18000b4fc  pop     r14
0x18000b4fe  pop     rdi
0x18000b4ff  pop     rsi
0x18000b500  pop     rbx
0x18000b501  retn
```
