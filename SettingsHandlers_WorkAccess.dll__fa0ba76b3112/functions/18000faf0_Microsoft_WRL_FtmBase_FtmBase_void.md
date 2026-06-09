# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000faf0`
- end: `0x18000fb7d`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d960`
- `0x18000da34`
- `0x18000dda8`
- `0x18000dedc`
- `0x18000f1c4`
- `0x18000f460`
- `0x18000f538`
- `0x18000f60c`
- `0x18000f948`
- `0x18001916c`
- `0x180021bb4`
- `0x180021ce8`
- `0x18002ad40`
- `0x1800449d8`
- `0x180044b24`
- `0x180044c70`
- `0x180044dbc`

## callees

- `0x1800076ac`
- `0x18000faf0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000fb2c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000fb2c`

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
0x18000faf0  push    rbx
0x18000faf2  push    rsi
0x18000faf3  push    rdi
0x18000faf4  push    r14
0x18000faf6  sub     rsp, 28h
0x18000fafa  mov     rsi, rcx
0x18000fafd  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000fb04  mov     [rcx], rax
0x18000fb07  lea     r14, [rcx+18h]
0x18000fb0b  mov     qword ptr [r14], 0
0x18000fb12  mov     [rsp+48h+ppunkMarshal], 0
0x18000fb1b  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000fb20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fb25  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000fb2a  xor     ecx, ecx; punkOuter
0x18000fb2c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000fb33  nop     dword ptr [rax+rax+00h]
0x18000fb38  test    eax, eax
0x18000fb3a  js      short loc_18000FB65
0x18000fb3c  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000fb41  mov     rax, [rbx]
0x18000fb44  mov     rdi, [rax]
0x18000fb47  mov     rcx, r14
0x18000fb4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fb4f  mov     r8, r14
0x18000fb52  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000fb59  mov     rcx, rbx
0x18000fb5c  mov     rax, rdi
0x18000fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb64  nop
0x18000fb65  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000fb6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fb6f  mov     rax, rsi
0x18000fb72  add     rsp, 28h
0x18000fb76  pop     r14
0x18000fb78  pop     rdi
0x18000fb79  pop     rsi
0x18000fb7a  pop     rbx
0x18000fb7b  retn
```
