# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x140008380`
- end: `0x140008405`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `133`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005dd4`
- `0x140007e34`
- `0x1400081e4`

## callees

- `0x140008380`
- `0x14000e920`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400083bc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400083bc`

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
0x140008380  push    rbx
0x140008382  push    rsi
0x140008383  push    rdi
0x140008384  push    r14
0x140008386  sub     rsp, 28h
0x14000838a  lea     r14, [rcx+18h]
0x14000838e  mov     [rsp+48h+ppunkMarshal], 0
0x140008397  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x14000839e  mov     rsi, rcx
0x1400083a1  mov     [rcx], rax
0x1400083a4  lea     rcx, [rsp+48h+ppunkMarshal]
0x1400083a9  mov     qword ptr [r14], 0
0x1400083b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400083b5  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400083ba  xor     ecx, ecx; punkOuter
0x1400083bc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1400083c2  test    eax, eax
0x1400083c4  js      short loc_1400083EE
0x1400083c6  mov     rbx, [rsp+48h+ppunkMarshal]
0x1400083cb  mov     rcx, r14
0x1400083ce  mov     rax, [rbx]
0x1400083d1  mov     rdi, [rax]
0x1400083d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400083d9  mov     r8, r14
0x1400083dc  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1400083e3  mov     rcx, rbx
0x1400083e6  mov     rax, rdi
0x1400083e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083ee  lea     rcx, [rsp+48h+ppunkMarshal]
0x1400083f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400083f8  mov     rax, rsi
0x1400083fb  add     rsp, 28h
0x1400083ff  pop     r14
0x140008401  pop     rdi
0x140008402  pop     rsi
0x140008403  pop     rbx
0x140008404  retn
```
