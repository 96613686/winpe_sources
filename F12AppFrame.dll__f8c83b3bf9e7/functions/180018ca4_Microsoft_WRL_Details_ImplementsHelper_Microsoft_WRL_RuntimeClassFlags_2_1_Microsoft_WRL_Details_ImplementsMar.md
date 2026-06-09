# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x180018ca4`
- end: `0x180018d48`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800186ec`
- `0x1800189c8`

## callees

- `0x180018ca4`
- `0x180035010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180018cd5`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180018cd5`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(
        _QWORD *a1)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 3;
  a1[3] = 0;
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
  return a1;
}

```

## disassembly

```asm
0x180018ca4  push    rbx
0x180018ca6  push    rbp
0x180018ca7  push    rsi
0x180018ca8  push    rdi
0x180018ca9  sub     rsp, 28h
0x180018cad  mov     rsi, rcx
0x180018cb0  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180018cb7  mov     [rcx], rax
0x180018cba  lea     rdi, [rcx+18h]
0x180018cbe  mov     qword ptr [rdi], 0
0x180018cc5  mov     [rsp+48h+ppunkMarshal], 0
0x180018cce  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180018cd3  xor     ecx, ecx; punkOuter
0x180018cd5  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180018cdb  test    eax, eax
0x180018cdd  js      short loc_180018D1C
0x180018cdf  mov     rbx, [rsp+48h+ppunkMarshal]
0x180018ce4  mov     rax, [rbx]
0x180018ce7  mov     rbp, [rax]
0x180018cea  mov     rcx, [rdi]
0x180018ced  test    rcx, rcx
0x180018cf0  jz      short loc_180018D06
0x180018cf2  mov     qword ptr [rdi], 0
0x180018cf9  mov     rdx, [rcx]
0x180018cfc  mov     rax, [rdx+10h]
0x180018d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d05  nop
0x180018d06  mov     r8, rdi
0x180018d09  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180018d10  mov     rcx, rbx
0x180018d13  mov     rax, rbp
0x180018d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d1b  nop
0x180018d1c  mov     rcx, [rsp+48h+ppunkMarshal]
0x180018d21  test    rcx, rcx
0x180018d24  jz      short loc_180018D3C
0x180018d26  mov     [rsp+48h+ppunkMarshal], 0
0x180018d2f  mov     rax, [rcx]
0x180018d32  mov     rax, [rax+10h]
0x180018d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d3b  nop
0x180018d3c  mov     rax, rsi
0x180018d3f  add     rsp, 28h
0x180018d43  pop     rdi
0x180018d44  pop     rsi
0x180018d45  pop     rbp
0x180018d46  pop     rbx
0x180018d47  retn
```
