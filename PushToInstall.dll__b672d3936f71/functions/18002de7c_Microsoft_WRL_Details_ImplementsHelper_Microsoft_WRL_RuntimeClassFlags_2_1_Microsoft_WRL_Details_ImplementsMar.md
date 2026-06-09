# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x18002de7c`
- end: `0x18002df20`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d114`
- `0x18003182c`
- `0x180033e38`
- `0x1800357d8`
- `0x180038690`
- `0x18003893c`
- `0x180038be8`
- `0x180038e94`
- `0x180039140`
- `0x1800393f8`

## callees

- `0x18002de7c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002dead`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002dead`

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
0x18002de7c  push    rbx
0x18002de7e  push    rbp
0x18002de7f  push    rsi
0x18002de80  push    rdi
0x18002de81  sub     rsp, 28h
0x18002de85  mov     rsi, rcx
0x18002de88  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18002de8f  mov     [rcx], rax
0x18002de92  lea     rdi, [rcx+18h]
0x18002de96  mov     qword ptr [rdi], 0
0x18002de9d  mov     [rsp+48h+ppunkMarshal], 0
0x18002dea6  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18002deab  xor     ecx, ecx; punkOuter
0x18002dead  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18002deb3  test    eax, eax
0x18002deb5  js      short loc_18002DEF4
0x18002deb7  mov     rbx, [rsp+48h+ppunkMarshal]
0x18002debc  mov     rax, [rbx]
0x18002debf  mov     rbp, [rax]
0x18002dec2  mov     rcx, [rdi]
0x18002dec5  test    rcx, rcx
0x18002dec8  jz      short loc_18002DEDE
0x18002deca  mov     qword ptr [rdi], 0
0x18002ded1  mov     rdx, [rcx]
0x18002ded4  mov     rax, [rdx+10h]
0x18002ded8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dedd  nop
0x18002dede  mov     r8, rdi
0x18002dee1  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18002dee8  mov     rcx, rbx
0x18002deeb  mov     rax, rbp
0x18002deee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002def3  nop
0x18002def4  mov     rcx, [rsp+48h+ppunkMarshal]
0x18002def9  test    rcx, rcx
0x18002defc  jz      short loc_18002DF14
0x18002defe  mov     [rsp+48h+ppunkMarshal], 0
0x18002df07  mov     rax, [rcx]
0x18002df0a  mov     rax, [rax+10h]
0x18002df0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df13  nop
0x18002df14  mov     rax, rsi
0x18002df17  add     rsp, 28h
0x18002df1b  pop     rdi
0x18002df1c  pop     rsi
0x18002df1d  pop     rbp
0x18002df1e  pop     rbx
0x18002df1f  retn
```
