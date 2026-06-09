# winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)

- ea: `0x18000964c`
- end: `0x180009725`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z`
- size: `217`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006068`
- `0x18000614c`
- `0x1800063c8`
- `0x180006434`
- `0x180006e30`
- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## callees

- `0x1800020b5`
- `0x1800020c1`
- `0x18000964c`
- `0x18000a014`
- `0x18000d010`

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
      result = (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)(a1 + 16));
    *v7 = v8;
  }
  if ( pperrinfo )
    return (__int64 *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pperrinfo);
  return result;
}

```

## disassembly

```asm
0x18000964c  push    rbp
0x18000964e  push    rbx
0x18000964f  push    rsi
0x180009650  push    rdi
0x180009651  mov     rbp, rsp
0x180009654  sub     rsp, 48h
0x180009658  mov     rdi, r9
0x18000965b  mov     rax, r8
0x18000965e  mov     ebx, edx
0x180009660  mov     rsi, rcx
0x180009663  xor     r8d, r8d
0x180009666  mov     rdx, rax
0x180009669  mov     ecx, ebx
0x18000966b  call    RoOriginateLanguageException_0
0x180009670  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180009677  test    rax, rax
0x18000967a  jz      short loc_180009693
0x18000967c  mov     r9, [rbp+20h]
0x180009680  mov     [rsp+48h+var_28], ebx
0x180009684  mov     r8, [rdi+10h]
0x180009688  mov     rdx, [rdi+8]
0x18000968c  mov     ecx, [rdi]
0x18000968e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009693  mov     [rbp+pperrinfo], 0
0x18000969b  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000969f  xor     ecx, ecx; dwReserved
0x1800096a1  call    GetErrorInfo_0
0x1800096a6  lea     rbx, [rsi+10h]
0x1800096aa  mov     rcx, [rbp+pperrinfo]
0x1800096ae  test    rcx, rcx
0x1800096b1  jnz     short loc_1800096BB
0x1800096b3  mov     [rbp+var_18], rcx
0x1800096b7  xor     edi, edi
0x1800096b9  jmp     short loc_1800096E1
0x1800096bb  mov     [rbp+var_10], 0
0x1800096c3  mov     rax, [rcx]
0x1800096c6  lea     r8, [rbp+var_10]
0x1800096ca  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800096d1  mov     rax, [rax]
0x1800096d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d9  mov     rdi, [rbp+var_10]
0x1800096dd  mov     [rbp+var_18], rdi
0x1800096e1  lea     rax, [rbp+var_18]
0x1800096e5  cmp     rbx, rax
0x1800096e8  jz      short loc_1800096FD
0x1800096ea  cmp     qword ptr [rbx], 0
0x1800096ee  jz      short loc_1800096F8
0x1800096f0  mov     rcx, rbx
0x1800096f3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800096f8  mov     [rbx], rdi
0x1800096fb  jmp     short loc_18000970B
0x1800096fd  test    rdi, rdi
0x180009700  jz      short loc_18000970B
0x180009702  lea     rcx, [rbp+var_18]
0x180009706  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000970b  cmp     [rbp+pperrinfo], 0
0x180009710  jz      short loc_18000971C
0x180009712  lea     rcx, [rbp+pperrinfo]
0x180009716  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000971b  nop
0x18000971c  add     rsp, 48h
0x180009720  pop     rdi
0x180009721  pop     rsi
0x180009722  pop     rbx
0x180009723  pop     rbp
0x180009724  retn
```
