# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000a8cc`
- end: `0x18000a970`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a614`
- `0x180021af0`

## callees

- `0x18000a8cc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a8fd`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a8fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  return this;
}

```

## disassembly

```asm
0x18000a8cc  push    rbx
0x18000a8ce  push    rbp
0x18000a8cf  push    rsi
0x18000a8d0  push    rdi
0x18000a8d1  sub     rsp, 28h
0x18000a8d5  mov     rsi, rcx
0x18000a8d8  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000a8df  mov     [rcx], rax
0x18000a8e2  lea     rdi, [rcx+18h]
0x18000a8e6  mov     qword ptr [rdi], 0
0x18000a8ed  mov     [rsp+48h+ppunkMarshal], 0
0x18000a8f6  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000a8fb  xor     ecx, ecx; punkOuter
0x18000a8fd  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000a903  test    eax, eax
0x18000a905  js      short loc_18000A944
0x18000a907  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000a90c  mov     rax, [rbx]
0x18000a90f  mov     rbp, [rax]
0x18000a912  mov     rcx, [rdi]
0x18000a915  test    rcx, rcx
0x18000a918  jz      short loc_18000A92E
0x18000a91a  mov     qword ptr [rdi], 0
0x18000a921  mov     rdx, [rcx]
0x18000a924  mov     rax, [rdx+10h]
0x18000a928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a92d  nop
0x18000a92e  mov     r8, rdi
0x18000a931  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000a938  mov     rcx, rbx
0x18000a93b  mov     rax, rbp
0x18000a93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a943  nop
0x18000a944  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000a949  test    rcx, rcx
0x18000a94c  jz      short loc_18000A964
0x18000a94e  mov     [rsp+48h+ppunkMarshal], 0
0x18000a957  mov     rax, [rcx]
0x18000a95a  mov     rax, [rax+10h]
0x18000a95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a963  nop
0x18000a964  mov     rax, rsi
0x18000a967  add     rsp, 28h
0x18000a96b  pop     rdi
0x18000a96c  pop     rsi
0x18000a96d  pop     rbp
0x18000a96e  pop     rbx
0x18000a96f  retn
```
