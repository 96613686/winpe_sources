# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180010444`
- end: `0x1800104ca`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d0c4`
- `0x18000d18c`
- `0x18000d258`
- `0x18000fcf0`
- `0x1800107d0`

## callees

- `0x18000b4b8`
- `0x180010444`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180010480`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180010480`

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
0x180010444  push    rbx
0x180010446  push    rsi
0x180010447  push    rdi
0x180010448  push    r14
0x18001044a  sub     rsp, 28h
0x18001044e  mov     rsi, rcx
0x180010451  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180010458  mov     [rcx], rax
0x18001045b  lea     r14, [rcx+18h]
0x18001045f  mov     qword ptr [r14], 0
0x180010466  mov     [rsp+48h+ppunkMarshal], 0
0x18001046f  lea     rcx, [rsp+48h+ppunkMarshal]
0x180010474  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010479  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001047e  xor     ecx, ecx; punkOuter
0x180010480  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180010486  test    eax, eax
0x180010488  js      short loc_1800104B3
0x18001048a  mov     rbx, [rsp+48h+ppunkMarshal]
0x18001048f  mov     rax, [rbx]
0x180010492  mov     rdi, [rax]
0x180010495  mov     rcx, r14
0x180010498  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001049d  mov     r8, r14
0x1800104a0  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800104a7  mov     rcx, rbx
0x1800104aa  mov     rax, rdi
0x1800104ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104b2  nop
0x1800104b3  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800104b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800104bd  mov     rax, rsi
0x1800104c0  add     rsp, 28h
0x1800104c4  pop     r14
0x1800104c6  pop     rdi
0x1800104c7  pop     rsi
0x1800104c8  pop     rbx
0x1800104c9  retn
```
