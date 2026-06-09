# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180019474`
- end: `0x1800194f9`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `133`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019500`
- `0x18001a120`
- `0x18001a7a0`
- `0x18001ad24`
- `0x18001e340`
- `0x18001e3e8`
- `0x18002073c`

## callees

- `0x180006a8c`
- `0x18000b348`
- `0x180019474`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800194b0`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800194b0`

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
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v1);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v1);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180019474  push    rbx
0x180019476  push    rsi
0x180019477  push    rdi
0x180019478  push    r14
0x18001947a  sub     rsp, 28h
0x18001947e  lea     r14, [rcx+18h]
0x180019482  mov     [rsp+48h+ppunkMarshal], 0
0x18001948b  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180019492  mov     rsi, rcx
0x180019495  mov     [rcx], rax
0x180019498  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001949d  mov     qword ptr [r14], 0
0x1800194a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800194a9  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800194ae  xor     ecx, ecx; punkOuter
0x1800194b0  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800194b6  test    eax, eax
0x1800194b8  js      short loc_1800194E2
0x1800194ba  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800194bf  mov     rcx, r14
0x1800194c2  mov     rax, [rbx]
0x1800194c5  mov     rdi, [rax]
0x1800194c8  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800194cd  mov     r8, r14
0x1800194d0  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800194d7  mov     rcx, rbx
0x1800194da  mov     rax, rdi
0x1800194dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194e2  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800194e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800194ec  mov     rax, rsi
0x1800194ef  add     rsp, 28h
0x1800194f3  pop     r14
0x1800194f5  pop     rdi
0x1800194f6  pop     rsi
0x1800194f7  pop     rbx
0x1800194f8  retn
```
