# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180005b38`
- end: `0x180005bdc`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004dcc`
- `0x180004eb4`
- `0x18000b808`
- `0x18000eb48`

## callees

- `0x180005b38`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180005b69`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180005b69`

## pseudocode

```c
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
0x180005b38  push    rbx
0x180005b3a  push    rbp
0x180005b3b  push    rsi
0x180005b3c  push    rdi
0x180005b3d  sub     rsp, 28h
0x180005b41  mov     rsi, rcx
0x180005b44  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180005b4b  mov     [rcx], rax
0x180005b4e  lea     rdi, [rcx+18h]
0x180005b52  mov     qword ptr [rdi], 0
0x180005b59  mov     [rsp+48h+ppunkMarshal], 0
0x180005b62  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180005b67  xor     ecx, ecx; punkOuter
0x180005b69  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180005b6f  test    eax, eax
0x180005b71  js      short loc_180005BB0
0x180005b73  mov     rbx, [rsp+48h+ppunkMarshal]
0x180005b78  mov     rax, [rbx]
0x180005b7b  mov     rbp, [rax]
0x180005b7e  mov     rcx, [rdi]
0x180005b81  test    rcx, rcx
0x180005b84  jz      short loc_180005B9A
0x180005b86  mov     qword ptr [rdi], 0
0x180005b8d  mov     rdx, [rcx]
0x180005b90  mov     rax, [rdx+10h]
0x180005b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b99  nop
0x180005b9a  mov     r8, rdi
0x180005b9d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180005ba4  mov     rcx, rbx
0x180005ba7  mov     rax, rbp
0x180005baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005baf  nop
0x180005bb0  mov     rcx, [rsp+48h+ppunkMarshal]
0x180005bb5  test    rcx, rcx
0x180005bb8  jz      short loc_180005BD0
0x180005bba  mov     [rsp+48h+ppunkMarshal], 0
0x180005bc3  mov     rax, [rcx]
0x180005bc6  mov     rax, [rax+10h]
0x180005bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bcf  nop
0x180005bd0  mov     rax, rsi
0x180005bd3  add     rsp, 28h
0x180005bd7  pop     rdi
0x180005bd8  pop     rsi
0x180005bd9  pop     rbp
0x180005bda  pop     rbx
0x180005bdb  retn
```
