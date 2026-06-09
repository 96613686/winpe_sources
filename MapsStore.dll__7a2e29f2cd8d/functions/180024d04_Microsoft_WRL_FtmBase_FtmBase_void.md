# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180024d04`
- end: `0x180024d8a`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022078`
- `0x180022140`
- `0x18002220c`
- `0x1800248c0`
- `0x180025090`

## callees

- `0x180019f3c`
- `0x180024d04`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180024d40`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180024d40`

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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180024d04  push    rbx
0x180024d06  push    rsi
0x180024d07  push    rdi
0x180024d08  push    r14
0x180024d0a  sub     rsp, 28h
0x180024d0e  mov     rsi, rcx
0x180024d11  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180024d18  mov     [rcx], rax
0x180024d1b  lea     r14, [rcx+18h]
0x180024d1f  mov     qword ptr [r14], 0
0x180024d26  mov     [rsp+48h+ppunkMarshal], 0
0x180024d2f  lea     rcx, [rsp+48h+ppunkMarshal]
0x180024d34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024d39  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180024d3e  xor     ecx, ecx; punkOuter
0x180024d40  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180024d46  test    eax, eax
0x180024d48  js      short loc_180024D73
0x180024d4a  mov     rbx, [rsp+48h+ppunkMarshal]
0x180024d4f  mov     rax, [rbx]
0x180024d52  mov     rdi, [rax]
0x180024d55  mov     rcx, r14
0x180024d58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024d5d  mov     r8, r14
0x180024d60  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180024d67  mov     rcx, rbx
0x180024d6a  mov     rax, rdi
0x180024d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d72  nop
0x180024d73  lea     rcx, [rsp+48h+ppunkMarshal]
0x180024d78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024d7d  mov     rax, rsi
0x180024d80  add     rsp, 28h
0x180024d84  pop     r14
0x180024d86  pop     rdi
0x180024d87  pop     rsi
0x180024d88  pop     rbx
0x180024d89  retn
```
