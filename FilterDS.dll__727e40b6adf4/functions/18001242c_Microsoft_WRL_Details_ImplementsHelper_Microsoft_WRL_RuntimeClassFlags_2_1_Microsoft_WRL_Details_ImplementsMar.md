# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x18001242c`
- end: `0x1800124d0`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800118d8`
- `0x180011c14`

## callees

- `0x18001242c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001245d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001245d`

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
0x18001242c  push    rbx
0x18001242e  push    rbp
0x18001242f  push    rsi
0x180012430  push    rdi
0x180012431  sub     rsp, 28h
0x180012435  mov     rsi, rcx
0x180012438  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18001243f  mov     [rcx], rax
0x180012442  lea     rdi, [rcx+18h]
0x180012446  mov     qword ptr [rdi], 0
0x18001244d  mov     [rsp+48h+ppunkMarshal], 0
0x180012456  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001245b  xor     ecx, ecx; punkOuter
0x18001245d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180012463  test    eax, eax
0x180012465  js      short loc_1800124A4
0x180012467  mov     rbx, [rsp+48h+ppunkMarshal]
0x18001246c  mov     rax, [rbx]
0x18001246f  mov     rbp, [rax]
0x180012472  mov     rcx, [rdi]
0x180012475  test    rcx, rcx
0x180012478  jz      short loc_18001248E
0x18001247a  mov     qword ptr [rdi], 0
0x180012481  mov     rdx, [rcx]
0x180012484  mov     rax, [rdx+10h]
0x180012488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001248d  nop
0x18001248e  mov     r8, rdi
0x180012491  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180012498  mov     rcx, rbx
0x18001249b  mov     rax, rbp
0x18001249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a3  nop
0x1800124a4  mov     rcx, [rsp+48h+ppunkMarshal]
0x1800124a9  test    rcx, rcx
0x1800124ac  jz      short loc_1800124C4
0x1800124ae  mov     [rsp+48h+ppunkMarshal], 0
0x1800124b7  mov     rax, [rcx]
0x1800124ba  mov     rax, [rax+10h]
0x1800124be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c3  nop
0x1800124c4  mov     rax, rsi
0x1800124c7  add     rsp, 28h
0x1800124cb  pop     rdi
0x1800124cc  pop     rsi
0x1800124cd  pop     rbp
0x1800124ce  pop     rbx
0x1800124cf  retn
```
