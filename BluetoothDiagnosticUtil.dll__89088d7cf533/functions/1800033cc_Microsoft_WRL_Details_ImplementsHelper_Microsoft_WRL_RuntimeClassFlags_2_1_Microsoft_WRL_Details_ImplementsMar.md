# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x1800033cc`
- end: `0x180003477`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `171`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b50`
- `0x180002df8`
- `0x1800030a0`

## callees

- `0x1800033cc`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800033fd`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800033fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800033cc  push    rbx
0x1800033ce  push    rbp
0x1800033cf  push    rsi
0x1800033d0  push    rdi
0x1800033d1  sub     rsp, 28h
0x1800033d5  mov     rsi, rcx
0x1800033d8  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800033df  mov     [rcx], rax
0x1800033e2  lea     rdi, [rcx+18h]
0x1800033e6  mov     qword ptr [rdi], 0
0x1800033ed  mov     [rsp+48h+ppunkMarshal], 0
0x1800033f6  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800033fb  xor     ecx, ecx; punkOuter
0x1800033fd  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003404  nop     dword ptr [rax+rax+00h]
0x180003409  test    eax, eax
0x18000340b  js      short loc_18000344A
0x18000340d  mov     rbx, [rsp+48h+ppunkMarshal]
0x180003412  mov     rax, [rbx]
0x180003415  mov     rbp, [rax]
0x180003418  mov     rcx, [rdi]
0x18000341b  test    rcx, rcx
0x18000341e  jz      short loc_180003434
0x180003420  mov     qword ptr [rdi], 0
0x180003427  mov     rdx, [rcx]
0x18000342a  mov     rax, [rdx+10h]
0x18000342e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003433  nop
0x180003434  mov     r8, rdi
0x180003437  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000343e  mov     rcx, rbx
0x180003441  mov     rax, rbp
0x180003444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003449  nop
0x18000344a  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000344f  test    rcx, rcx
0x180003452  jz      short loc_18000346A
0x180003454  mov     [rsp+48h+ppunkMarshal], 0
0x18000345d  mov     rax, [rcx]
0x180003460  mov     rax, [rax+10h]
0x180003464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003469  nop
0x18000346a  mov     rax, rsi
0x18000346d  add     rsp, 28h
0x180003471  pop     rdi
0x180003472  pop     rsi
0x180003473  pop     rbp
0x180003474  pop     rbx
0x180003475  retn
```
