# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180007a0c`
- end: `0x180007a92`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `17`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007b44`
- `0x1800113e8`
- `0x18001159c`
- `0x180011794`
- `0x18001c39c`
- `0x18001d014`
- `0x18001d0cc`
- `0x18001d17c`
- `0x18001d234`
- `0x18001d2e0`
- `0x18001d394`
- `0x18001d44c`
- `0x18001d504`
- `0x18001d5c4`
- `0x18001d674`
- `0x18001d748`
- `0x1800276f4`

## callees

- `0x180007a0c`
- `0x18000955c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180007a48`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180007a48`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
0x180007a0c  push    rbx
0x180007a0e  push    rsi
0x180007a0f  push    rdi
0x180007a10  push    r14
0x180007a12  sub     rsp, 28h
0x180007a16  mov     rsi, rcx
0x180007a19  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180007a20  mov     [rcx], rax
0x180007a23  lea     r14, [rcx+18h]
0x180007a27  mov     qword ptr [r14], 0
0x180007a2e  mov     [rsp+48h+ppunkMarshal], 0
0x180007a37  lea     rcx, [rsp+48h+ppunkMarshal]
0x180007a3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007a41  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180007a46  xor     ecx, ecx; punkOuter
0x180007a48  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180007a4e  test    eax, eax
0x180007a50  js      short loc_180007A7B
0x180007a52  mov     rbx, [rsp+48h+ppunkMarshal]
0x180007a57  mov     rax, [rbx]
0x180007a5a  mov     rdi, [rax]
0x180007a5d  mov     rcx, r14
0x180007a60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007a65  mov     r8, r14
0x180007a68  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180007a6f  mov     rcx, rbx
0x180007a72  mov     rax, rdi
0x180007a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a7a  nop
0x180007a7b  lea     rcx, [rsp+48h+ppunkMarshal]
0x180007a80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007a85  mov     rax, rsi
0x180007a88  add     rsp, 28h
0x180007a8c  pop     r14
0x180007a8e  pop     rdi
0x180007a8f  pop     rsi
0x180007a90  pop     rbx
0x180007a91  retn
```
