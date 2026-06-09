# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000f46c`
- end: `0x18000f4f2`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000edd4`
- `0x18000eee0`
- `0x18000f4f8`
- `0x180015228`
- `0x180019c34`
- `0x18001bc14`

## callees

- `0x180005120`
- `0x18000f46c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000f4a8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000f4a8`

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
0x18000f46c  push    rbx
0x18000f46e  push    rsi
0x18000f46f  push    rdi
0x18000f470  push    r14
0x18000f472  sub     rsp, 28h
0x18000f476  mov     rsi, rcx
0x18000f479  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000f480  mov     [rcx], rax
0x18000f483  lea     r14, [rcx+18h]
0x18000f487  mov     qword ptr [r14], 0
0x18000f48e  mov     [rsp+48h+ppunkMarshal], 0
0x18000f497  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000f49c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4a1  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000f4a6  xor     ecx, ecx; punkOuter
0x18000f4a8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000f4ae  test    eax, eax
0x18000f4b0  js      short loc_18000F4DB
0x18000f4b2  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000f4b7  mov     rax, [rbx]
0x18000f4ba  mov     rdi, [rax]
0x18000f4bd  mov     rcx, r14
0x18000f4c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4c5  mov     r8, r14
0x18000f4c8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000f4cf  mov     rcx, rbx
0x18000f4d2  mov     rax, rdi
0x18000f4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4da  nop
0x18000f4db  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000f4e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4e5  mov     rax, rsi
0x18000f4e8  add     rsp, 28h
0x18000f4ec  pop     r14
0x18000f4ee  pop     rdi
0x18000f4ef  pop     rsi
0x18000f4f0  pop     rbx
0x18000f4f1  retn
```
