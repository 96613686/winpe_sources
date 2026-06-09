# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1400139a4`
- end: `0x140013a2a`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013308`
- `0x140013448`
- `0x140019c30`
- `0x14001ead8`
- `0x14001fadc`

## callees

- `0x14000c32c`
- `0x1400139a4`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400139e0`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400139e0`

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
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x1400139a4  push    rbx
0x1400139a6  push    rsi
0x1400139a7  push    rdi
0x1400139a8  push    r14
0x1400139aa  sub     rsp, 28h
0x1400139ae  mov     rsi, rcx
0x1400139b1  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1400139b8  mov     [rcx], rax
0x1400139bb  lea     r14, [rcx+18h]
0x1400139bf  mov     qword ptr [r14], 0
0x1400139c6  mov     [rsp+48h+ppunkMarshal], 0
0x1400139cf  lea     rcx, [rsp+48h+ppunkMarshal]
0x1400139d4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400139d9  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400139de  xor     ecx, ecx; punkOuter
0x1400139e0  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1400139e6  test    eax, eax
0x1400139e8  js      short loc_140013A13
0x1400139ea  mov     rbx, [rsp+48h+ppunkMarshal]
0x1400139ef  mov     rax, [rbx]
0x1400139f2  mov     rdi, [rax]
0x1400139f5  mov     rcx, r14
0x1400139f8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400139fd  mov     r8, r14
0x140013a00  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140013a07  mov     rcx, rbx
0x140013a0a  mov     rax, rdi
0x140013a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013a12  nop
0x140013a13  lea     rcx, [rsp+48h+ppunkMarshal]
0x140013a18  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140013a1d  mov     rax, rsi
0x140013a20  add     rsp, 28h
0x140013a24  pop     r14
0x140013a26  pop     rdi
0x140013a27  pop     rsi
0x140013a28  pop     rbx
0x140013a29  retn
```
