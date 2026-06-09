# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18001ff04`
- end: `0x18001ffa0`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `156`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fb0c`
- `0x180041c08`
- `0x180041d48`

## callees

- `0x18001fa00`
- `0x18001ff04`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001ff40`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001ff40`

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
0x18001ff04  push    rbx
0x18001ff06  push    rsi
0x18001ff07  push    rdi
0x18001ff08  push    r14
0x18001ff0a  sub     rsp, 28h
0x18001ff0e  mov     rsi, rcx
0x18001ff11  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18001ff18  mov     [rcx], rax
0x18001ff1b  lea     r14, [rcx+18h]
0x18001ff1f  mov     qword ptr [r14], 0
0x18001ff26  mov     [rsp+48h+ppunkMarshal], 0
0x18001ff2f  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001ff34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff39  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001ff3e  xor     ecx, ecx; punkOuter
0x18001ff40  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001ff46  test    eax, eax
0x18001ff48  js      short loc_18001FF73
0x18001ff4a  mov     rbx, [rsp+48h+ppunkMarshal]
0x18001ff4f  mov     rax, [rbx]
0x18001ff52  mov     rdi, [rax]
0x18001ff55  mov     rcx, r14
0x18001ff58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff5d  mov     r8, r14
0x18001ff60  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001ff67  mov     rcx, rbx
0x18001ff6a  mov     rax, rdi
0x18001ff6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff72  nop
0x18001ff73  mov     rcx, [rsp+48h+ppunkMarshal]
0x18001ff78  test    rcx, rcx
0x18001ff7b  jz      short loc_18001FF93
0x18001ff7d  mov     [rsp+48h+ppunkMarshal], 0
0x18001ff86  mov     rax, [rcx]
0x18001ff89  mov     rax, [rax+10h]
0x18001ff8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff92  nop
0x18001ff93  mov     rax, rsi
0x18001ff96  add     rsp, 28h
0x18001ff9a  pop     r14
0x18001ff9c  pop     rdi
0x18001ff9d  pop     rsi
0x18001ff9e  pop     rbx
0x18001ff9f  retn
```
