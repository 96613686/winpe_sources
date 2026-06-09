# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180003c7c`
- end: `0x180003d02`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003b84`
- `0x180003be0`
- `0x180003d08`
- `0x180009474`

## callees

- `0x180003c7c`
- `0x18000539c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003cb8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003cb8`

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
0x180003c7c  push    rbx
0x180003c7e  push    rsi
0x180003c7f  push    rdi
0x180003c80  push    r14
0x180003c82  sub     rsp, 28h
0x180003c86  mov     rsi, rcx
0x180003c89  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180003c90  mov     [rcx], rax
0x180003c93  lea     r14, [rcx+18h]
0x180003c97  mov     qword ptr [r14], 0
0x180003c9e  mov     [rsp+48h+ppunkMarshal], 0
0x180003ca7  lea     rcx, [rsp+48h+ppunkMarshal]
0x180003cac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003cb1  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180003cb6  xor     ecx, ecx; punkOuter
0x180003cb8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003cbe  test    eax, eax
0x180003cc0  js      short loc_180003CEB
0x180003cc2  mov     rbx, [rsp+48h+ppunkMarshal]
0x180003cc7  mov     rax, [rbx]
0x180003cca  mov     rdi, [rax]
0x180003ccd  mov     rcx, r14
0x180003cd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003cd5  mov     r8, r14
0x180003cd8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180003cdf  mov     rcx, rbx
0x180003ce2  mov     rax, rdi
0x180003ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cea  nop
0x180003ceb  lea     rcx, [rsp+48h+ppunkMarshal]
0x180003cf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003cf5  mov     rax, rsi
0x180003cf8  add     rsp, 28h
0x180003cfc  pop     r14
0x180003cfe  pop     rdi
0x180003cff  pop     rsi
0x180003d00  pop     rbx
0x180003d01  retn
```
