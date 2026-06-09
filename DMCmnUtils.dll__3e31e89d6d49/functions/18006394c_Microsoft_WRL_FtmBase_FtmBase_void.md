# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18006394c`
- end: `0x1800639d9`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180063668`
- `0x180073048`
- `0x180073194`
- `0x1800732e0`
- `0x18007342c`

## callees

- `0x18006394c`
- `0x180064a44`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180063988`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180063988`

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
0x18006394c  push    rbx
0x18006394e  push    rsi
0x18006394f  push    rdi
0x180063950  push    r14
0x180063952  sub     rsp, 28h
0x180063956  mov     rsi, rcx
0x180063959  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180063960  mov     [rcx], rax
0x180063963  lea     r14, [rcx+18h]
0x180063967  mov     qword ptr [r14], 0
0x18006396e  mov     [rsp+48h+ppunkMarshal], 0
0x180063977  lea     rcx, [rsp+48h+ppunkMarshal]
0x18006397c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063981  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180063986  xor     ecx, ecx; punkOuter
0x180063988  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18006398f  nop     dword ptr [rax+rax+00h]
0x180063994  test    eax, eax
0x180063996  js      short loc_1800639C1
0x180063998  mov     rbx, [rsp+48h+ppunkMarshal]
0x18006399d  mov     rax, [rbx]
0x1800639a0  mov     rdi, [rax]
0x1800639a3  mov     rcx, r14
0x1800639a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800639ab  mov     r8, r14
0x1800639ae  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800639b5  mov     rcx, rbx
0x1800639b8  mov     rax, rdi
0x1800639bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639c0  nop
0x1800639c1  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800639c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800639cb  mov     rax, rsi
0x1800639ce  add     rsp, 28h
0x1800639d2  pop     r14
0x1800639d4  pop     rdi
0x1800639d5  pop     rsi
0x1800639d6  pop     rbx
0x1800639d7  retn
```
