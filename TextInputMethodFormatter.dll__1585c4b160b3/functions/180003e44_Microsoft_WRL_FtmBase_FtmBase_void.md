# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180003e44`
- end: `0x180003ee8`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003370`
- `0x180018b70`
- `0x180018f2c`
- `0x18001dea0`
- `0x18001e090`
- `0x18001e2c0`
- `0x18001e500`
- `0x18001e750`
- `0x18001e940`
- `0x18001eb30`
- `0x18001ed20`
- `0x18001ef30`
- `0x18001f120`
- `0x18001f370`
- `0x18001f570`
- `0x18001f780`
- `0x18001f9b0`
- `0x18001fba0`
- `0x18001fdb0`
- `0x18001ffe0`
- `0x180020220`
- `0x180020660`
- `0x180020850`
- `0x180020a80`
- `0x180020c80`
- `0x180020e90`
- `0x180021070`
- `0x180021250`
- `0x180021470`
- `0x1800216c0`
- `0x180021900`
- `0x180021ae0`

## callees

- `0x180003e44`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003e75`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003e75`

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
0x180003e44  push    rbx
0x180003e46  push    rbp
0x180003e47  push    rsi
0x180003e48  push    rdi
0x180003e49  sub     rsp, 28h
0x180003e4d  mov     rsi, rcx
0x180003e50  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180003e57  mov     [rcx], rax
0x180003e5a  lea     rdi, [rcx+18h]
0x180003e5e  mov     qword ptr [rdi], 0
0x180003e65  mov     [rsp+48h+ppunkMarshal], 0
0x180003e6e  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180003e73  xor     ecx, ecx; punkOuter
0x180003e75  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003e7b  test    eax, eax
0x180003e7d  js      short loc_180003EBC
0x180003e7f  mov     rbx, [rsp+48h+ppunkMarshal]
0x180003e84  mov     rax, [rbx]
0x180003e87  mov     rbp, [rax]
0x180003e8a  mov     rcx, [rdi]
0x180003e8d  test    rcx, rcx
0x180003e90  jz      short loc_180003EA6
0x180003e92  mov     qword ptr [rdi], 0
0x180003e99  mov     rdx, [rcx]
0x180003e9c  mov     rax, [rdx+10h]
0x180003ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea5  nop
0x180003ea6  mov     r8, rdi
0x180003ea9  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180003eb0  mov     rcx, rbx
0x180003eb3  mov     rax, rbp
0x180003eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ebb  nop
0x180003ebc  mov     rcx, [rsp+48h+ppunkMarshal]
0x180003ec1  test    rcx, rcx
0x180003ec4  jz      short loc_180003EDC
0x180003ec6  mov     [rsp+48h+ppunkMarshal], 0
0x180003ecf  mov     rax, [rcx]
0x180003ed2  mov     rax, [rax+10h]
0x180003ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003edb  nop
0x180003edc  mov     rax, rsi
0x180003edf  add     rsp, 28h
0x180003ee3  pop     rdi
0x180003ee4  pop     rsi
0x180003ee5  pop     rbp
0x180003ee6  pop     rbx
0x180003ee7  retn
```
