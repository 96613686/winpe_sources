# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000ae70`
- end: `0x18000af17`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `167`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ab38`
- `0x18000add8`
- `0x1800136c4`
- `0x18001376c`

## callees

- `0x1800018c4`
- `0x18000ae70`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000aea5`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000aea5`

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
0x18000ae70  push    rbp
0x18000ae72  push    rsi
0x18000ae73  sub     rsp, 28h
0x18000ae77  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000ae7e  mov     [rsp+38h+var_18], r14
0x18000ae83  mov     [rcx], rax
0x18000ae86  xor     ebp, ebp
0x18000ae88  mov     [rcx+18h], rbp
0x18000ae8c  mov     rsi, rcx
0x18000ae8f  lea     rcx, [rsp+38h+ppunkMarshal]
0x18000ae94  mov     [rsp+38h+ppunkMarshal], rbp
0x18000ae99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ae9e  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x18000aea3  xor     ecx, ecx; punkOuter
0x18000aea5  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000aeab  test    eax, eax
0x18000aead  js      short loc_18000AEED
0x18000aeaf  mov     [rsp+38h+arg_8], rbx
0x18000aeb4  lea     rcx, [rsi+18h]
0x18000aeb8  mov     rbx, [rsp+38h+ppunkMarshal]
0x18000aebd  mov     [rsp+38h+arg_10], rdi
0x18000aec2  mov     rax, [rbx]
0x18000aec5  mov     rdi, [rax]
0x18000aec8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000aecd  lea     r8, [rsi+18h]
0x18000aed1  mov     rcx, rbx
0x18000aed4  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000aedb  mov     rax, rdi
0x18000aede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee3  mov     rdi, [rsp+38h+arg_10]
0x18000aee8  mov     rbx, [rsp+38h+arg_8]
0x18000aeed  mov     rcx, [rsp+38h+ppunkMarshal]
0x18000aef2  mov     r14, [rsp+38h+var_18]
0x18000aef7  test    rcx, rcx
0x18000aefa  jz      short loc_18000AF0D
0x18000aefc  mov     [rsp+38h+ppunkMarshal], rbp
0x18000af01  mov     rax, [rcx]
0x18000af04  mov     rax, [rax+10h]
0x18000af08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af0d  mov     rax, rsi
0x18000af10  add     rsp, 28h
0x18000af14  pop     rsi
0x18000af15  pop     rbp
0x18000af16  retn
```
