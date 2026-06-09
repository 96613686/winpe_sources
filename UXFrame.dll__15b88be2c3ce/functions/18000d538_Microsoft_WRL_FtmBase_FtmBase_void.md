# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000d538`
- end: `0x18000d5da`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `162`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d1e0`

## callees

- `0x180002b20`
- `0x18000d538`
- `0x18001374c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000d583`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000d583`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-38h] BYREF

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
0x18000d538  push    rbx
0x18000d53a  push    rsi
0x18000d53b  push    rdi
0x18000d53c  push    r14
0x18000d53e  sub     rsp, 38h
0x18000d542  mov     rax, cs:__security_cookie
0x18000d549  xor     rax, rsp
0x18000d54c  mov     [rsp+58h+var_30], rax
0x18000d551  mov     rsi, rcx
0x18000d554  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000d55b  mov     [rcx], rax
0x18000d55e  lea     r14, [rcx+18h]
0x18000d562  mov     qword ptr [r14], 0
0x18000d569  mov     [rsp+58h+ppunkMarshal], 0
0x18000d572  lea     rcx, [rsp+58h+ppunkMarshal]
0x18000d577  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d57c  lea     rdx, [rsp+58h+ppunkMarshal]; ppunkMarshal
0x18000d581  xor     ecx, ecx; punkOuter
0x18000d583  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000d589  test    eax, eax
0x18000d58b  js      short loc_18000D5B6
0x18000d58d  mov     rbx, [rsp+58h+ppunkMarshal]
0x18000d592  mov     rax, [rbx]
0x18000d595  mov     rdi, [rax]
0x18000d598  mov     rcx, r14
0x18000d59b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d5a0  mov     r8, r14
0x18000d5a3  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000d5aa  mov     rcx, rbx
0x18000d5ad  mov     rax, rdi
0x18000d5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b5  nop
0x18000d5b6  lea     rcx, [rsp+58h+ppunkMarshal]
0x18000d5bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d5c0  mov     rax, rsi
0x18000d5c3  mov     rcx, [rsp+58h+var_30]
0x18000d5c8  xor     rcx, rsp; StackCookie
0x18000d5cb  call    __security_check_cookie
0x18000d5d0  add     rsp, 38h
0x18000d5d4  pop     r14
0x18000d5d6  pop     rdi
0x18000d5d7  pop     rsi
0x18000d5d8  pop     rbx
0x18000d5d9  retn
```
