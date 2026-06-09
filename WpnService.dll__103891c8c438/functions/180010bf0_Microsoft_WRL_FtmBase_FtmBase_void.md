# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180010bf0`
- end: `0x180010c92`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `162`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010b90`
- `0x1800222e4`

## callees

- `0x180003190`
- `0x180010bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180010c2b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180010c2b`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v4; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      (char *)this + 24);
  }
  v4 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v4->lpVtbl->Release)(v4);
  }
  return this;
}

```

## disassembly

```asm
0x180010bf0  mov     [rsp+arg_8], rbx
0x180010bf5  mov     [rsp+arg_10], rbp
0x180010bfa  push    rsi
0x180010bfb  push    rdi
0x180010bfc  push    r14
0x180010bfe  sub     rsp, 20h
0x180010c02  mov     rsi, rcx
0x180010c05  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180010c0c  mov     [rcx], rax
0x180010c0f  xor     ebp, ebp
0x180010c11  mov     [rcx+18h], rbp
0x180010c15  mov     [rsp+38h+ppunkMarshal], rbp
0x180010c1a  lea     rcx, [rsp+38h+ppunkMarshal]
0x180010c1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010c24  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x180010c29  xor     ecx, ecx; punkOuter
0x180010c2b  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180010c31  test    eax, eax
0x180010c33  js      short loc_180010C60
0x180010c35  mov     rbx, [rsp+38h+ppunkMarshal]
0x180010c3a  mov     rax, [rbx]
0x180010c3d  mov     rdi, [rax]
0x180010c40  lea     rcx, [rsi+18h]
0x180010c44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010c49  lea     r8, [rsi+18h]
0x180010c4d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180010c54  mov     rcx, rbx
0x180010c57  mov     rax, rdi
0x180010c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c5f  nop
0x180010c60  mov     rcx, [rsp+38h+ppunkMarshal]
0x180010c65  test    rcx, rcx
0x180010c68  jz      short loc_180010C7C
0x180010c6a  mov     [rsp+38h+ppunkMarshal], rbp
0x180010c6f  mov     rax, [rcx]
0x180010c72  mov     rax, [rax+10h]
0x180010c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c7b  nop
0x180010c7c  mov     rax, rsi
0x180010c7f  mov     rbx, [rsp+38h+arg_8]
0x180010c84  mov     rbp, [rsp+38h+arg_10]
0x180010c89  add     rsp, 20h
0x180010c8d  pop     r14
0x180010c8f  pop     rdi
0x180010c90  pop     rsi
0x180010c91  retn
```
