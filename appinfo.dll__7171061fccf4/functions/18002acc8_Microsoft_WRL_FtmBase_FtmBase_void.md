# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18002acc8`
- end: `0x18002ad4d`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `133`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a550`
- `0x18002ac34`

## callees

- `0x18002acc8`
- `0x1800371ec`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002ad04`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002ad04`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  v1 = (char *)this + 24;
  ppunkMarshal = 0;
  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v1);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x18002acc8  push    rbx
0x18002acca  push    rsi
0x18002accb  push    rdi
0x18002accc  push    r14
0x18002acce  sub     rsp, 28h
0x18002acd2  lea     r14, [rcx+18h]
0x18002acd6  mov     [rsp+48h+ppunkMarshal], 0
0x18002acdf  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18002ace6  mov     rsi, rcx
0x18002ace9  mov     [rcx], rax
0x18002acec  lea     rcx, [rsp+48h+ppunkMarshal]
0x18002acf1  mov     qword ptr [r14], 0
0x18002acf8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002acfd  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18002ad02  xor     ecx, ecx; punkOuter
0x18002ad04  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18002ad0a  test    eax, eax
0x18002ad0c  js      short loc_18002AD36
0x18002ad0e  mov     rbx, [rsp+48h+ppunkMarshal]
0x18002ad13  mov     rcx, r14
0x18002ad16  mov     rax, [rbx]
0x18002ad19  mov     rdi, [rax]
0x18002ad1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ad21  mov     r8, r14
0x18002ad24  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18002ad2b  mov     rcx, rbx
0x18002ad2e  mov     rax, rdi
0x18002ad31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad36  lea     rcx, [rsp+48h+ppunkMarshal]
0x18002ad3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ad40  mov     rax, rsi
0x18002ad43  add     rsp, 28h
0x18002ad47  pop     r14
0x18002ad49  pop     rdi
0x18002ad4a  pop     rsi
0x18002ad4b  pop     rbx
0x18002ad4c  retn
```
