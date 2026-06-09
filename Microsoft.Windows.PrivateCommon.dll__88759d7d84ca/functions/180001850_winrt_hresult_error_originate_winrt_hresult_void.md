# winrt::hresult_error::originate(winrt::hresult,void *)

- ea: `0x180001850`
- end: `0x180001951`
- name: `?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAX@Z`
- size: `257`
- prototype: `IErrorInfo *__fastcall(__int64, unsigned int, __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001500`
- `0x180001530`
- `0x180007070`
- `0x18000c514`
- `0x18000c63a`
- `0x18000c760`

## callees

- `0x180001850`
- `0x180005cb0`
- `0x180007280`
- `0x18000b80d`
- `0x18000b825`
- `0x18000b930`

## pseudocode

```c
IErrorInfo *__fastcall winrt::hresult_error::originate(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 *v6; // rdi
  IErrorInfo *result; // rax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+38h] [rbp-20h] BYREF
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp-18h] BYREF
  void *retaddr; // [rsp+58h] [rbp+0h]

  RoOriginateLanguageException_0(a2, a3, 0);
  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(0, 0, 0, retaddr, a2);
  v5 = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  v6 = (__int64 *)(a1 + 16);
  result = pperrinfo;
  if ( pperrinfo )
  {
    v9 = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, __int64 *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &v9);
    v5 = v9;
    result = pperrinfo;
  }
  v8 = v5;
  if ( v6 == &v8 )
  {
    if ( v5 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
      result = pperrinfo;
    }
  }
  else
  {
    if ( *v6 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
      result = pperrinfo;
    }
    *v6 = v5;
  }
  if ( result )
    return (IErrorInfo *)winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return result;
}

```

## disassembly

```asm
0x180001850  mov     [rsp+arg_8], rbx
0x180001855  push    rdi
0x180001856  sub     rsp, 50h
0x18000185a  mov     rax, cs:__security_cookie
0x180001861  xor     rax, rsp
0x180001864  mov     [rsp+58h+var_10], rax
0x180001869  mov     rax, r8
0x18000186c  mov     ebx, edx
0x18000186e  mov     rdi, rcx
0x180001871  xor     r8d, r8d
0x180001874  mov     rdx, rax
0x180001877  mov     ecx, ebx
0x180001879  call    RoOriginateLanguageException_0
0x18000187e  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180001885  test    rax, rax
0x180001888  jz      short loc_1800018A0
0x18000188a  mov     r9, [rsp+58h]
0x18000188f  mov     [rsp+58h+var_38], ebx
0x180001893  xor     r8d, r8d
0x180001896  xor     edx, edx
0x180001898  xor     ecx, ecx
0x18000189a  call    cs:__guard_dispatch_icall_fptr
0x1800018a0  xor     ebx, ebx
0x1800018a2  mov     [rsp+58h+pperrinfo], rbx
0x1800018a7  lea     rdx, [rsp+58h+pperrinfo]; pperrinfo
0x1800018ac  xor     ecx, ecx; dwReserved
0x1800018ae  call    GetErrorInfo_0
0x1800018b3  add     rdi, 10h
0x1800018b7  mov     rax, [rsp+58h+pperrinfo]
0x1800018bc  test    rax, rax
0x1800018bf  jz      short loc_1800018EE
0x1800018c1  mov     [rsp+58h+var_20], rbx
0x1800018c6  mov     rcx, [rax]
0x1800018c9  mov     r9, [rcx]
0x1800018cc  lea     r8, [rsp+58h+var_20]
0x1800018d1  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800018d8  mov     rcx, rax
0x1800018db  mov     rax, r9
0x1800018de  call    cs:__guard_dispatch_icall_fptr
0x1800018e4  mov     rbx, [rsp+58h+var_20]
0x1800018e9  mov     rax, [rsp+58h+pperrinfo]
0x1800018ee  mov     [rsp+58h+var_28], rbx
0x1800018f3  lea     rcx, [rsp+58h+var_28]
0x1800018f8  cmp     rdi, rcx
0x1800018fb  jz      short loc_180001915
0x1800018fd  cmp     qword ptr [rdi], 0
0x180001901  jz      short loc_180001910
0x180001903  mov     rcx, rdi
0x180001906  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000190b  mov     rax, [rsp+58h+pperrinfo]
0x180001910  mov     [rdi], rbx
0x180001913  jmp     short loc_180001929
0x180001915  test    rbx, rbx
0x180001918  jz      short loc_180001929
0x18000191a  lea     rcx, [rsp+58h+var_28]
0x18000191f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180001924  mov     rax, [rsp+58h+pperrinfo]
0x180001929  test    rax, rax
0x18000192c  jz      short loc_180001939
0x18000192e  lea     rcx, [rsp+58h+pperrinfo]
0x180001933  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180001938  nop
0x180001939  mov     rcx, [rsp+58h+var_10]
0x18000193e  xor     rcx, rsp; StackCookie
0x180001941  call    __security_check_cookie
0x180001946  mov     rbx, [rsp+58h+arg_8]
0x18000194b  add     rsp, 50h
0x18000194f  pop     rdi
0x180001950  retn
```
