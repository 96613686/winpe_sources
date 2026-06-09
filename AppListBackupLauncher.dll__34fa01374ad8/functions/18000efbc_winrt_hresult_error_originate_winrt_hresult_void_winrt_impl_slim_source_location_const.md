# winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)

- ea: `0x18000efbc`
- end: `0x18000f095`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z`
- size: `217`
- prototype: `__int64 *__fastcall(__int64, unsigned int, __int64, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005230`
- `0x180005314`
- `0x180010e6d`
- `0x180010f66`
- `0x18001105f`

## callees

- `0x180002ef1`
- `0x180002f39`
- `0x18000efbc`
- `0x18000f544`
- `0x180012010`

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
0x18000efbc  push    rbp
0x18000efbe  push    rbx
0x18000efbf  push    rsi
0x18000efc0  push    rdi
0x18000efc1  mov     rbp, rsp
0x18000efc4  sub     rsp, 48h
0x18000efc8  mov     rdi, r9
0x18000efcb  mov     rax, r8
0x18000efce  mov     ebx, edx
0x18000efd0  mov     rsi, rcx
0x18000efd3  xor     r8d, r8d
0x18000efd6  mov     rdx, rax
0x18000efd9  mov     ecx, ebx
0x18000efdb  call    RoOriginateLanguageException_0
0x18000efe0  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18000efe7  test    rax, rax
0x18000efea  jz      short loc_18000F003
0x18000efec  mov     r9, [rbp+20h]
0x18000eff0  mov     [rsp+48h+var_28], ebx
0x18000eff4  mov     r8, [rdi+10h]
0x18000eff8  mov     rdx, [rdi+8]
0x18000effc  mov     ecx, [rdi]
0x18000effe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f003  mov     [rbp+pperrinfo], 0
0x18000f00b  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000f00f  xor     ecx, ecx; dwReserved
0x18000f011  call    GetErrorInfo_0
0x18000f016  lea     rbx, [rsi+10h]
0x18000f01a  mov     rcx, [rbp+pperrinfo]
0x18000f01e  test    rcx, rcx
0x18000f021  jnz     short loc_18000F02B
0x18000f023  mov     [rbp+var_18], rcx
0x18000f027  xor     edi, edi
0x18000f029  jmp     short loc_18000F051
0x18000f02b  mov     [rbp+var_10], 0
0x18000f033  mov     rax, [rcx]
0x18000f036  lea     r8, [rbp+var_10]
0x18000f03a  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000f041  mov     rax, [rax]
0x18000f044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f049  mov     rdi, [rbp+var_10]
0x18000f04d  mov     [rbp+var_18], rdi
0x18000f051  lea     rax, [rbp+var_18]
0x18000f055  cmp     rbx, rax
0x18000f058  jz      short loc_18000F06D
0x18000f05a  cmp     qword ptr [rbx], 0
0x18000f05e  jz      short loc_18000F068
0x18000f060  mov     rcx, rbx
0x18000f063  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f068  mov     [rbx], rdi
0x18000f06b  jmp     short loc_18000F07B
0x18000f06d  test    rdi, rdi
0x18000f070  jz      short loc_18000F07B
0x18000f072  lea     rcx, [rbp+var_18]
0x18000f076  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f07b  cmp     [rbp+pperrinfo], 0
0x18000f080  jz      short loc_18000F08C
0x18000f082  lea     rcx, [rbp+pperrinfo]
0x18000f086  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f08b  nop
0x18000f08c  add     rsp, 48h
0x18000f090  pop     rdi
0x18000f091  pop     rsi
0x18000f092  pop     rbx
0x18000f093  pop     rbp
0x18000f094  retn
```
