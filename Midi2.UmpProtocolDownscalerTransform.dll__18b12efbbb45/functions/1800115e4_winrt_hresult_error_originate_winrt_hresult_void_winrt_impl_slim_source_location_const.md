# winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)

- ea: `0x1800115e4`
- end: `0x1800116bd`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z`
- size: `217`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c890`
- `0x18000c974`
- `0x18000cbe4`
- `0x18000cca0`
- `0x18000cd34`
- `0x180012791`
- `0x180012895`
- `0x180012999`

## callees

- `0x180003b55`
- `0x180003b61`
- `0x1800115e4`
- `0x180011e0c`
- `0x180013010`

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
0x1800115e4  push    rbp
0x1800115e6  push    rbx
0x1800115e7  push    rsi
0x1800115e8  push    rdi
0x1800115e9  mov     rbp, rsp
0x1800115ec  sub     rsp, 48h
0x1800115f0  mov     rdi, r9
0x1800115f3  mov     rax, r8
0x1800115f6  mov     ebx, edx
0x1800115f8  mov     rsi, rcx
0x1800115fb  xor     r8d, r8d
0x1800115fe  mov     rdx, rax
0x180011601  mov     ecx, ebx
0x180011603  call    RoOriginateLanguageException_0
0x180011608  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18001160f  test    rax, rax
0x180011612  jz      short loc_18001162B
0x180011614  mov     r9, [rbp+20h]
0x180011618  mov     [rsp+48h+var_28], ebx
0x18001161c  mov     r8, [rdi+10h]
0x180011620  mov     rdx, [rdi+8]
0x180011624  mov     ecx, [rdi]
0x180011626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001162b  mov     [rbp+pperrinfo], 0
0x180011633  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180011637  xor     ecx, ecx; dwReserved
0x180011639  call    GetErrorInfo_0
0x18001163e  lea     rbx, [rsi+10h]
0x180011642  mov     rcx, [rbp+pperrinfo]
0x180011646  test    rcx, rcx
0x180011649  jnz     short loc_180011653
0x18001164b  mov     [rbp+var_18], rcx
0x18001164f  xor     edi, edi
0x180011651  jmp     short loc_180011679
0x180011653  mov     [rbp+var_10], 0
0x18001165b  mov     rax, [rcx]
0x18001165e  lea     r8, [rbp+var_10]
0x180011662  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180011669  mov     rax, [rax]
0x18001166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011671  mov     rdi, [rbp+var_10]
0x180011675  mov     [rbp+var_18], rdi
0x180011679  lea     rax, [rbp+var_18]
0x18001167d  cmp     rbx, rax
0x180011680  jz      short loc_180011695
0x180011682  cmp     qword ptr [rbx], 0
0x180011686  jz      short loc_180011690
0x180011688  mov     rcx, rbx
0x18001168b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011690  mov     [rbx], rdi
0x180011693  jmp     short loc_1800116A3
0x180011695  test    rdi, rdi
0x180011698  jz      short loc_1800116A3
0x18001169a  lea     rcx, [rbp+var_18]
0x18001169e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800116a3  cmp     [rbp+pperrinfo], 0
0x1800116a8  jz      short loc_1800116B4
0x1800116aa  lea     rcx, [rbp+pperrinfo]
0x1800116ae  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800116b3  nop
0x1800116b4  add     rsp, 48h
0x1800116b8  pop     rdi
0x1800116b9  pop     rsi
0x1800116ba  pop     rbx
0x1800116bb  pop     rbp
0x1800116bc  retn
```
