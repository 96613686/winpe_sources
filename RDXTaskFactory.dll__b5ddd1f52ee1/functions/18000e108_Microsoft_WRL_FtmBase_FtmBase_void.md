# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000e108`
- end: `0x18000e18e`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this, __int64, __int64)`
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d5a4`
- `0x18000df5c`
- `0x18000e074`
- `0x1800115c4`
- `0x180013550`
- `0x180016b98`
- `0x18001b8d0`
- `0x18001ba10`
- `0x18001cb50`
- `0x18002139c`
- `0x180024420`
- `0x180024560`
- `0x18002ee78`
- `0x180032898`
- `0x180032d38`
- `0x180032dd4`
- `0x18003632c`
- `0x180043d24`
- `0x180043db4`
- `0x180043e44`
- `0x18004a9fc`

## callees

- `0x180008bbc`
- `0x18000e108`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000e144`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000e144`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(
        Microsoft::WRL::FtmBase *this,
        __int64 a2,
        __int64 a3)
{
  char *v4; // r14
  __int64 v5; // rdx
  __int64 v6; // r8
  LPUNKNOWN v7; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v4 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal, a2, a3);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v7 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4, v5, v6);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v7, &GUID_00000003_0000_0000_c000_000000000046, v4);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal, v5, v6);
  return this;
}

```

## disassembly

```asm
0x18000e108  push    rbx
0x18000e10a  push    rsi
0x18000e10b  push    rdi
0x18000e10c  push    r14
0x18000e10e  sub     rsp, 28h
0x18000e112  mov     rsi, rcx
0x18000e115  lea     rax, ??_7CActivatedEventArgsBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e11c  mov     [rcx], rax
0x18000e11f  lea     r14, [rcx+18h]
0x18000e123  mov     qword ptr [r14], 0
0x18000e12a  mov     [rsp+48h+ppunkMarshal], 0
0x18000e133  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000e138  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e13d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000e142  xor     ecx, ecx; punkOuter
0x18000e144  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000e14a  test    eax, eax
0x18000e14c  js      short loc_18000E177
0x18000e14e  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000e153  mov     rax, [rbx]
0x18000e156  mov     rdi, [rax]
0x18000e159  mov     rcx, r14
0x18000e15c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e161  mov     r8, r14
0x18000e164  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000e16b  mov     rcx, rbx
0x18000e16e  mov     rax, rdi
0x18000e171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e176  nop
0x18000e177  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000e17c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e181  mov     rax, rsi
0x18000e184  add     rsp, 28h
0x18000e188  pop     r14
0x18000e18a  pop     rdi
0x18000e18b  pop     rsi
0x18000e18c  pop     rbx
0x18000e18d  retn
```
