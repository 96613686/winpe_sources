# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800060bc`
- end: `0x180006160`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800062f0`
- `0x1800079f0`
- `0x180007e30`
- `0x180007f30`
- `0x180008030`
- `0x180009570`
- `0x18000f600`
- `0x18000fb00`
- `0x180010f54`

## callees

- `0x1800060bc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800060ed`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800060ed`

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
0x1800060bc  push    rbx
0x1800060be  push    rbp
0x1800060bf  push    rsi
0x1800060c0  push    rdi
0x1800060c1  sub     rsp, 28h
0x1800060c5  mov     rsi, rcx
0x1800060c8  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800060cf  mov     [rcx], rax
0x1800060d2  lea     rdi, [rcx+18h]
0x1800060d6  mov     qword ptr [rdi], 0
0x1800060dd  mov     [rsp+48h+ppunkMarshal], 0
0x1800060e6  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800060eb  xor     ecx, ecx; punkOuter
0x1800060ed  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800060f3  test    eax, eax
0x1800060f5  js      short loc_180006134
0x1800060f7  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800060fc  mov     rax, [rbx]
0x1800060ff  mov     rbp, [rax]
0x180006102  mov     rcx, [rdi]
0x180006105  test    rcx, rcx
0x180006108  jz      short loc_18000611E
0x18000610a  mov     qword ptr [rdi], 0
0x180006111  mov     rdx, [rcx]
0x180006114  mov     rax, [rdx+10h]
0x180006118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611d  nop
0x18000611e  mov     r8, rdi
0x180006121  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180006128  mov     rcx, rbx
0x18000612b  mov     rax, rbp
0x18000612e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006133  nop
0x180006134  mov     rcx, [rsp+48h+ppunkMarshal]
0x180006139  test    rcx, rcx
0x18000613c  jz      short loc_180006154
0x18000613e  mov     [rsp+48h+ppunkMarshal], 0
0x180006147  mov     rax, [rcx]
0x18000614a  mov     rax, [rax+10h]
0x18000614e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006153  nop
0x180006154  mov     rax, rsi
0x180006157  add     rsp, 28h
0x18000615b  pop     rdi
0x18000615c  pop     rsi
0x18000615d  pop     rbp
0x18000615e  pop     rbx
0x18000615f  retn
```
