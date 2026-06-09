# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180019c6c`
- end: `0x180019cf2`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015efc`
- `0x180015ff4`
- `0x180016b6c`
- `0x18001889c`
- `0x1800188c0`
- `0x180018b08`
- `0x180018bf4`
- `0x180019b20`

## callees

- `0x18000cfa4`
- `0x180019c6c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180019ca8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180019ca8`

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
0x180019c6c  push    rbx
0x180019c6e  push    rsi
0x180019c6f  push    rdi
0x180019c70  push    r14
0x180019c72  sub     rsp, 28h
0x180019c76  mov     rsi, rcx
0x180019c79  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180019c80  mov     [rcx], rax
0x180019c83  lea     r14, [rcx+18h]
0x180019c87  mov     qword ptr [r14], 0
0x180019c8e  mov     [rsp+48h+ppunkMarshal], 0
0x180019c97  lea     rcx, [rsp+48h+ppunkMarshal]
0x180019c9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019ca1  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180019ca6  xor     ecx, ecx; punkOuter
0x180019ca8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180019cae  test    eax, eax
0x180019cb0  js      short loc_180019CDB
0x180019cb2  mov     rbx, [rsp+48h+ppunkMarshal]
0x180019cb7  mov     rax, [rbx]
0x180019cba  mov     rdi, [rax]
0x180019cbd  mov     rcx, r14
0x180019cc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019cc5  mov     r8, r14
0x180019cc8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180019ccf  mov     rcx, rbx
0x180019cd2  mov     rax, rdi
0x180019cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cda  nop
0x180019cdb  lea     rcx, [rsp+48h+ppunkMarshal]
0x180019ce0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019ce5  mov     rax, rsi
0x180019ce8  add     rsp, 28h
0x180019cec  pop     r14
0x180019cee  pop     rdi
0x180019cef  pop     rsi
0x180019cf0  pop     rbx
0x180019cf1  retn
```
