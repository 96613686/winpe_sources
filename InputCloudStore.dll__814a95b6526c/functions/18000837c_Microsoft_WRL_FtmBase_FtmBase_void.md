# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000837c`
- end: `0x180008402`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800082c0`
- `0x180019fd8`

## callees

- `0x180006158`
- `0x18000837c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800083b8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800083b8`

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
0x18000837c  push    rbx
0x18000837e  push    rsi
0x18000837f  push    rdi
0x180008380  push    r14
0x180008382  sub     rsp, 28h
0x180008386  mov     rsi, rcx
0x180008389  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180008390  mov     [rcx], rax
0x180008393  lea     r14, [rcx+18h]
0x180008397  mov     qword ptr [r14], 0
0x18000839e  mov     [rsp+48h+ppunkMarshal], 0
0x1800083a7  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800083ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800083b1  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800083b6  xor     ecx, ecx; punkOuter
0x1800083b8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800083be  test    eax, eax
0x1800083c0  js      short loc_1800083EB
0x1800083c2  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800083c7  mov     rax, [rbx]
0x1800083ca  mov     rdi, [rax]
0x1800083cd  mov     rcx, r14
0x1800083d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800083d5  mov     r8, r14
0x1800083d8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800083df  mov     rcx, rbx
0x1800083e2  mov     rax, rdi
0x1800083e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ea  nop
0x1800083eb  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800083f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800083f5  mov     rax, rsi
0x1800083f8  add     rsp, 28h
0x1800083fc  pop     r14
0x1800083fe  pop     rdi
0x1800083ff  pop     rsi
0x180008400  pop     rbx
0x180008401  retn
```
