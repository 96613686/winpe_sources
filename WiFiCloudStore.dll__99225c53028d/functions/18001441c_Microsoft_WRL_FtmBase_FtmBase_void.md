# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18001441c`
- end: `0x1800144b8`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `156`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014380`
- `0x18001b5d4`
- `0x180023d80`

## callees

- `0x180006b88`
- `0x18001441c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180014458`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180014458`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v5; // rcx
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
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x18001441c  push    rbx
0x18001441e  push    rsi
0x18001441f  push    rdi
0x180014420  push    r14
0x180014422  sub     rsp, 28h
0x180014426  mov     rsi, rcx
0x180014429  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180014430  mov     [rcx], rax
0x180014433  lea     r14, [rcx+18h]
0x180014437  mov     qword ptr [r14], 0
0x18001443e  mov     [rsp+48h+ppunkMarshal], 0
0x180014447  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001444c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014451  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180014456  xor     ecx, ecx; punkOuter
0x180014458  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001445e  test    eax, eax
0x180014460  js      short loc_18001448B
0x180014462  mov     rbx, [rsp+48h+ppunkMarshal]
0x180014467  mov     rax, [rbx]
0x18001446a  mov     rdi, [rax]
0x18001446d  mov     rcx, r14
0x180014470  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014475  mov     r8, r14
0x180014478  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001447f  mov     rcx, rbx
0x180014482  mov     rax, rdi
0x180014485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001448a  nop
0x18001448b  mov     rcx, [rsp+48h+ppunkMarshal]
0x180014490  test    rcx, rcx
0x180014493  jz      short loc_1800144AB
0x180014495  mov     [rsp+48h+ppunkMarshal], 0
0x18001449e  mov     rax, [rcx]
0x1800144a1  mov     rax, [rax+10h]
0x1800144a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144aa  nop
0x1800144ab  mov     rax, rsi
0x1800144ae  add     rsp, 28h
0x1800144b2  pop     r14
0x1800144b4  pop     rdi
0x1800144b5  pop     rsi
0x1800144b6  pop     rbx
0x1800144b7  retn
```
