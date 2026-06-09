# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180001920`
- end: `0x1800019c7`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `167`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001270`
- `0x180001870`

## callees

- `0x180001840`
- `0x180001920`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001955`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001955`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v4; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      (char *)this + 24);
  }
  v4 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v4->lpVtbl->Release)(v4);
  }
  return this;
}

```

## disassembly

```asm
0x180001920  push    rbp
0x180001922  push    rsi
0x180001923  sub     rsp, 28h
0x180001927  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000192e  mov     [rsp+38h+var_18], r14
0x180001933  mov     [rcx], rax
0x180001936  xor     ebp, ebp
0x180001938  mov     [rcx+18h], rbp
0x18000193c  mov     rsi, rcx
0x18000193f  lea     rcx, [rsp+38h+ppunkMarshal]
0x180001944  mov     [rsp+38h+ppunkMarshal], rbp
0x180001949  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000194e  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x180001953  xor     ecx, ecx; punkOuter
0x180001955  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000195b  test    eax, eax
0x18000195d  js      short loc_18000199D
0x18000195f  mov     [rsp+38h+arg_8], rbx
0x180001964  lea     rcx, [rsi+18h]
0x180001968  mov     rbx, [rsp+38h+ppunkMarshal]
0x18000196d  mov     [rsp+38h+arg_10], rdi
0x180001972  mov     rax, [rbx]
0x180001975  mov     rdi, [rax]
0x180001978  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000197d  lea     r8, [rsi+18h]
0x180001981  mov     rcx, rbx
0x180001984  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000198b  mov     rax, rdi
0x18000198e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001993  mov     rdi, [rsp+38h+arg_10]
0x180001998  mov     rbx, [rsp+38h+arg_8]
0x18000199d  mov     rcx, [rsp+38h+ppunkMarshal]
0x1800019a2  mov     r14, [rsp+38h+var_18]
0x1800019a7  test    rcx, rcx
0x1800019aa  jz      short loc_1800019BD
0x1800019ac  mov     [rsp+38h+ppunkMarshal], rbp
0x1800019b1  mov     rax, [rcx]
0x1800019b4  mov     rax, [rax+10h]
0x1800019b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019bd  mov     rax, rsi
0x1800019c0  add     rsp, 28h
0x1800019c4  pop     rsi
0x1800019c5  pop     rbp
0x1800019c6  retn
```
