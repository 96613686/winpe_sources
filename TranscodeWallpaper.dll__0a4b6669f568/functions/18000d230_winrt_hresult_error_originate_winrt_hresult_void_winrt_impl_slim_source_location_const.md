# winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)

- ea: `0x18000d230`
- end: `0x18000d309`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z`
- size: `217`
- prototype: `__int64 *__fastcall(__int64, unsigned int, __int64, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d5f0`
- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## callees

- `0x180002e1d`
- `0x180002e29`
- `0x180006dec`
- `0x18000d230`
- `0x18000f010`

## pseudocode

```c
__int64 *__fastcall winrt::hresult_error::originate(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  __int64 *v7; // rbx
  __int64 v8; // rdi
  __int64 *result; // rax
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  __int64 v11; // [rsp+38h] [rbp-10h] BYREF
  void *retaddr; // [rsp+68h] [rbp+20h]
  IErrorInfo *pperrinfo; // [rsp+70h] [rbp+28h] BYREF

  RoOriginateLanguageException_0(a2, a3, 0);
  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(*a4, *((_QWORD *)a4 + 1), *((_QWORD *)a4 + 2), retaddr, a2);
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  v7 = (__int64 *)(a1 + 16);
  if ( pperrinfo )
  {
    v11 = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, __int64 *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &v11);
    v8 = v11;
    v10 = v11;
  }
  else
  {
    v10 = 0;
    v8 = 0;
  }
  result = &v10;
  if ( v7 == &v10 )
  {
    if ( v8 )
      result = (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  }
  else
  {
    if ( *v7 )
      result = (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 16);
    *v7 = v8;
  }
  if ( pperrinfo )
    return (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return result;
}

```

## disassembly

```asm
0x18000d230  push    rbp
0x18000d232  push    rbx
0x18000d233  push    rsi
0x18000d234  push    rdi
0x18000d235  mov     rbp, rsp
0x18000d238  sub     rsp, 48h
0x18000d23c  mov     rdi, r9
0x18000d23f  mov     rax, r8
0x18000d242  mov     ebx, edx
0x18000d244  mov     rsi, rcx
0x18000d247  xor     r8d, r8d
0x18000d24a  mov     rdx, rax
0x18000d24d  mov     ecx, ebx
0x18000d24f  call    RoOriginateLanguageException_0
0x18000d254  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18000d25b  test    rax, rax
0x18000d25e  jz      short loc_18000D277
0x18000d260  mov     r9, [rbp+20h]
0x18000d264  mov     [rsp+48h+var_28], ebx
0x18000d268  mov     r8, [rdi+10h]
0x18000d26c  mov     rdx, [rdi+8]
0x18000d270  mov     ecx, [rdi]
0x18000d272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d277  mov     [rbp+pperrinfo], 0
0x18000d27f  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000d283  xor     ecx, ecx; dwReserved
0x18000d285  call    GetErrorInfo_0
0x18000d28a  lea     rbx, [rsi+10h]
0x18000d28e  mov     rcx, [rbp+pperrinfo]
0x18000d292  test    rcx, rcx
0x18000d295  jnz     short loc_18000D29F
0x18000d297  mov     [rbp+var_18], rcx
0x18000d29b  xor     edi, edi
0x18000d29d  jmp     short loc_18000D2C5
0x18000d29f  mov     [rbp+var_10], 0
0x18000d2a7  mov     rax, [rcx]
0x18000d2aa  lea     r8, [rbp+var_10]
0x18000d2ae  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000d2b5  mov     rax, [rax]
0x18000d2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2bd  mov     rdi, [rbp+var_10]
0x18000d2c1  mov     [rbp+var_18], rdi
0x18000d2c5  lea     rax, [rbp+var_18]
0x18000d2c9  cmp     rbx, rax
0x18000d2cc  jz      short loc_18000D2E1
0x18000d2ce  cmp     qword ptr [rbx], 0
0x18000d2d2  jz      short loc_18000D2DC
0x18000d2d4  mov     rcx, rbx
0x18000d2d7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d2dc  mov     [rbx], rdi
0x18000d2df  jmp     short loc_18000D2EF
0x18000d2e1  test    rdi, rdi
0x18000d2e4  jz      short loc_18000D2EF
0x18000d2e6  lea     rcx, [rbp+var_18]
0x18000d2ea  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d2ef  cmp     [rbp+pperrinfo], 0
0x18000d2f4  jz      short loc_18000D300
0x18000d2f6  lea     rcx, [rbp+pperrinfo]
0x18000d2fa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d2ff  nop
0x18000d300  add     rsp, 48h
0x18000d304  pop     rdi
0x18000d305  pop     rsi
0x18000d306  pop     rbx
0x18000d307  pop     rbp
0x18000d308  retn
```
