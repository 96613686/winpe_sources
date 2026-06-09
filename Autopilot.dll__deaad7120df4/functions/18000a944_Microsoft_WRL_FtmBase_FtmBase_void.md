# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000a944`
- end: `0x18000a9ef`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `171`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a608`
- `0x180022580`

## callees

- `0x18000a944`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a975`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a975`

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
0x18000a944  push    rbx
0x18000a946  push    rbp
0x18000a947  push    rsi
0x18000a948  push    rdi
0x18000a949  sub     rsp, 28h
0x18000a94d  mov     rsi, rcx
0x18000a950  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000a957  mov     [rcx], rax
0x18000a95a  lea     rdi, [rcx+18h]
0x18000a95e  mov     qword ptr [rdi], 0
0x18000a965  mov     [rsp+48h+ppunkMarshal], 0
0x18000a96e  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000a973  xor     ecx, ecx; punkOuter
0x18000a975  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000a97c  nop     dword ptr [rax+rax+00h]
0x18000a981  test    eax, eax
0x18000a983  js      short loc_18000A9C2
0x18000a985  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000a98a  mov     rax, [rbx]
0x18000a98d  mov     rbp, [rax]
0x18000a990  mov     rcx, [rdi]
0x18000a993  test    rcx, rcx
0x18000a996  jz      short loc_18000A9AC
0x18000a998  mov     qword ptr [rdi], 0
0x18000a99f  mov     rdx, [rcx]
0x18000a9a2  mov     rax, [rdx+10h]
0x18000a9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ab  nop
0x18000a9ac  mov     r8, rdi
0x18000a9af  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000a9b6  mov     rcx, rbx
0x18000a9b9  mov     rax, rbp
0x18000a9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9c1  nop
0x18000a9c2  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000a9c7  test    rcx, rcx
0x18000a9ca  jz      short loc_18000A9E2
0x18000a9cc  mov     [rsp+48h+ppunkMarshal], 0
0x18000a9d5  mov     rax, [rcx]
0x18000a9d8  mov     rax, [rax+10h]
0x18000a9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e1  nop
0x18000a9e2  mov     rax, rsi
0x18000a9e5  add     rsp, 28h
0x18000a9e9  pop     rdi
0x18000a9ea  pop     rsi
0x18000a9eb  pop     rbp
0x18000a9ec  pop     rbx
0x18000a9ed  retn
```
