# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180006f80`
- end: `0x18000703d`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `189`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005c80`
- `0x180006b38`
- `0x180006d9c`
- `0x180006ee8`
- `0x180007044`

## callees

- `0x180001dc0`
- `0x180006f80`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006fc0`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006fc0`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v1; // rdi
  LPUNKNOWN v3; // rbx
  __int64 v4; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-38h] BYREF

  v1 = (__int64 *)((char *)this + 24);
  ppunkMarshal = 0;
  *(_QWORD *)this = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    v4 = *v1;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    if ( *v1 )
    {
      *v1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v1);
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
0x180006f80  push    rbx
0x180006f82  push    rbp
0x180006f83  push    rsi
0x180006f84  push    rdi
0x180006f85  sub     rsp, 38h
0x180006f89  mov     rax, cs:__security_cookie
0x180006f90  xor     rax, rsp
0x180006f93  mov     [rsp+58h+var_30], rax
0x180006f98  lea     rdi, [rcx+18h]
0x180006f9c  mov     [rsp+58h+ppunkMarshal], 0
0x180006fa5  lea     rax, ??_7CActivatedEventArgsBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180006fac  mov     rsi, rcx
0x180006faf  mov     [rcx], rax
0x180006fb2  lea     rdx, [rsp+58h+ppunkMarshal]; ppunkMarshal
0x180006fb7  xor     ecx, ecx; punkOuter
0x180006fb9  mov     qword ptr [rdi], 0
0x180006fc0  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180006fc6  test    eax, eax
0x180006fc8  js      short loc_180007005
0x180006fca  mov     rbx, [rsp+58h+ppunkMarshal]
0x180006fcf  mov     rcx, [rdi]
0x180006fd2  mov     rax, [rbx]
0x180006fd5  mov     rbp, [rax]
0x180006fd8  test    rcx, rcx
0x180006fdb  jz      short loc_180006FF0
0x180006fdd  mov     qword ptr [rdi], 0
0x180006fe4  mov     rdx, [rcx]
0x180006fe7  mov     rax, [rdx+10h]
0x180006feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff0  mov     r8, rdi
0x180006ff3  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180006ffa  mov     rcx, rbx
0x180006ffd  mov     rax, rbp
0x180007000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007005  mov     rcx, [rsp+58h+ppunkMarshal]
0x18000700a  test    rcx, rcx
0x18000700d  jz      short loc_180007024
0x18000700f  mov     [rsp+58h+ppunkMarshal], 0
0x180007018  mov     rdx, [rcx]
0x18000701b  mov     rax, [rdx+10h]
0x18000701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007024  mov     rax, rsi
0x180007027  mov     rcx, [rsp+58h+var_30]
0x18000702c  xor     rcx, rsp; StackCookie
0x18000702f  call    __security_check_cookie
0x180007034  add     rsp, 38h
0x180007038  pop     rdi
0x180007039  pop     rsi
0x18000703a  pop     rbp
0x18000703b  pop     rbx
0x18000703c  retn
```
