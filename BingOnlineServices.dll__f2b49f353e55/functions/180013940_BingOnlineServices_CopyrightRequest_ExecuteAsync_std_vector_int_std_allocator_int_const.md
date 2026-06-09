# BingOnlineServices::CopyrightRequest::ExecuteAsync(std::vector<int,std::allocator<int>> const &)

- ea: `0x180013940`
- end: `0x180013b7d`
- name: `?ExecuteAsync@CopyrightRequest@BingOnlineServices@@QEAA?AV?$task@VCopyrightData@BingOnlineServices@@@pplx@@AEBV?$vector@HV?$allocator@H@std@@@std@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(BingOnlineServices::CopyrightRequest *this)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002c2c`
- `0x180002c6c`
- `0x180004fa0`
- `0x180005e9c`
- `0x180009778`
- `0x18000a2f4`
- `0x18000fc54`
- `0x1800116d4`
- `0x180011970`
- `0x180011fc4`
- `0x1800130b0`
- `0x180013940`
- `0x180013c90`
- `0x1800148ac`
- `0x1800167f8`
- `0x18001bd40`
- `0x18001be70`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180013a17`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180013a17`
- `ZTrace_Maps!ZTraceHelper` at `0x180013ad5`
- `ZTrace_Maps!ZTraceHelper` at `0x180013b56`
- `ZTrace_Maps!ZTraceHelper` at `0x180013ad5`
- `ZTrace_Maps!ZTraceHelper` at `0x180013b56`

## string_xrefs

- `0x180013aca`: `BingOnlineServices::CopyrightRequest::ExecuteAsync`
- `0x180013b4d`: `BingOnlineServices::CopyrightRequest::ExecuteAsync`
- `0x180013ab5`: `Executing copyright request`
- `0x180013b5c`: `The list of providers for the copyright reuest must have at least 1 item.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BingOnlineServices::CopyrightRequest::ExecuteAsync(
        BingOnlineServices::CopyrightRequest *this,
        __int64 a2,
        unsigned int **a3)
{
  const WCHAR *ValueFromConfig; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  WCHAR *p_pExceptionObject; // rcx
  unsigned int *v10; // r14
  unsigned int *v11; // rbx
  __int64 v12; // rax
  const WCHAR *v13; // rax
  __int64 v14; // rax
  __int64 JsonRequestAsync; // rax
  _BYTE v17[16]; // [rsp+40h] [rbp-C0h] BYREF
  char v18[8]; // [rsp+50h] [rbp-B0h] BYREF
  char v19[232]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pExceptionObject; // [rsp+140h] [rbp+40h] BYREF
  std::_Ref_count_base *v21; // [rsp+148h] [rbp+48h]
  _BYTE v22[32]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v23[16]; // [rsp+180h] [rbp+80h] BYREF

  pExceptionObject = a2;
  std::wstring::wstring(v22);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v17);
  if ( *((_BYTE *)this + 64) )
  {
    ValueFromConfig = BingOnlineServices::CopyrightRequest::GetValueFromConfig(
                        this,
                        (const WCHAR *)&pExceptionObject,
                        0xE2u);
    std::wstring::operator=(v22, ValueFromConfig);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    v7 = std::wstring::wstring(v23);
    v8 = BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(
           (unsigned int)&pExceptionObject,
           (unsigned int)v22,
           (int)this + 32,
           (_DWORD)this,
           v7);
    std::wstring::operator=(v22, v8);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    p_pExceptionObject = v23;
  }
  else
  {
    v10 = a3[1];
    v11 = *a3;
    if ( v11 == v10 )
    {
      ZTraceHelper(
        0,
        "BingOnlineServices::CopyrightRequest::ExecuteAsync",
        81,
        this,
        "Failed to specify valid provider list");
      std::invalid_argument::invalid_argument(
        (std::invalid_argument *)&pExceptionObject,
        "The list of providers for the copyright reuest must have at least 1 item.");
      throw (std::invalid_argument *)&pExceptionObject;
    }
    do
    {
      v12 = std::basic_ostream<unsigned short>::operator<<(v18, *v11);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, ",");
      ++v11;
    }
    while ( v11 != v10 );
    v13 = BingOnlineServices::CopyrightRequest::GetValueFromConfig(this, v23, 0xE0u);
    std::wstring::operator=(v22, v13);
    std::wstring::_Tidy_deallocate(v23);
    std::basic_stringbuf<unsigned short>::str(v19, &pExceptionObject);
    v14 = BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(
            (unsigned int)v23,
            (unsigned int)v22,
            (int)this + 32,
            (_DWORD)this,
            (__int64)&pExceptionObject);
    std::wstring::operator=(v22, v14);
    std::wstring::_Tidy_deallocate(v23);
    p_pExceptionObject = (WCHAR *)&pExceptionObject;
  }
  std::wstring::_Tidy_deallocate(p_pExceptionObject);
  ZTraceHelper(5, "BingOnlineServices::CopyrightRequest::ExecuteAsync", 93, this, "Executing copyright request");
  JsonRequestAsync = BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync(&pExceptionObject, v22);
  pplx::task_BingOnlineServices::OnlineServiceResponse_::then__lambda_c41e8d95a32c1ff378910e4cd353399c___(
    JsonRequestAsync,
    a2);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v17);
  std::wstring::_Tidy_deallocate(v22);
  return a2;
}

```

## disassembly

```asm
0x180013940  push    rbp
0x180013942  push    rbx
0x180013943  push    rsi
0x180013944  push    rdi
0x180013945  push    r14
0x180013947  lea     rbp, [rsp-0B0h]
0x18001394f  sub     rsp, 1B0h
0x180013956  mov     rax, cs:__security_cookie
0x18001395d  xor     rax, rsp
0x180013960  mov     [rbp+0D0h+var_30], rax
0x180013967  mov     rbx, r8
0x18001396a  mov     rsi, rdx
0x18001396d  mov     rdi, rcx
0x180013970  mov     [rbp+0D0h+pExceptionObject], rdx
0x180013974  lea     rcx, [rbp+0D0h+var_70]
0x180013978  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001397d  nop
0x18001397e  lea     rcx, [rsp+1D0h+var_190]
0x180013983  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180013988  nop
0x180013989  cmp     byte ptr [rdi+40h], 0
0x18001398d  jz      short loc_180013A00
0x18001398f  mov     r8d, 0E2h
0x180013995  lea     rdx, [rbp+0D0h+pExceptionObject]
0x180013999  mov     rcx, rdi; this
0x18001399c  call    ?GetValueFromConfig@CopyrightRequest@BingOnlineServices@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationManagerKeys@@@Z; BingOnlineServices::CopyrightRequest::GetValueFromConfig(ConfigurationManagerKeys)
0x1800139a1  mov     rdx, rax
0x1800139a4  lea     rcx, [rbp+0D0h+var_70]
0x1800139a8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800139ad  lea     rcx, [rbp+0D0h+pExceptionObject]
0x1800139b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800139b6  lea     rcx, [rbp+0D0h+var_50]
0x1800139bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800139c2  nop
0x1800139c3  lea     r8, [rdi+20h]
0x1800139c7  mov     [rsp+1D0h+var_1B0], rax
0x1800139cc  mov     r9, rdi
0x1800139cf  lea     rdx, [rbp+0D0h+var_70]
0x1800139d3  lea     rcx, [rbp+0D0h+pExceptionObject]
0x1800139d7  call    ?ReplaceFragmentUri@ServiceRequestHelper@BingOnlineServices@@SA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@000@Z; BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800139dc  nop
0x1800139dd  mov     rdx, rax
0x1800139e0  lea     rcx, [rbp+0D0h+var_70]
0x1800139e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800139e9  nop
0x1800139ea  lea     rcx, [rbp+0D0h+pExceptionObject]
0x1800139ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800139f3  nop
0x1800139f4  lea     rcx, [rbp+0D0h+var_50]
0x1800139fb  jmp     loc_180013AB0
0x180013a00  mov     r14, [rbx+8]
0x180013a04  mov     rbx, [rbx]
0x180013a07  cmp     rbx, r14
0x180013a0a  jz      loc_180013B38
0x180013a10  mov     edx, [rbx]
0x180013a12  lea     rcx, [rsp+1D0h+var_180]
0x180013a17  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x180013a1d  mov     rcx, rax
0x180013a20  lea     rdx, asc_18006794C; ","
0x180013a27  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180013a2c  add     rbx, 4
0x180013a30  cmp     rbx, r14
0x180013a33  jnz     short loc_180013A10
0x180013a35  mov     r8d, 0E0h
0x180013a3b  lea     rdx, [rbp+0D0h+var_50]
0x180013a42  mov     rcx, rdi; this
0x180013a45  call    ?GetValueFromConfig@CopyrightRequest@BingOnlineServices@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationManagerKeys@@@Z; BingOnlineServices::CopyrightRequest::GetValueFromConfig(ConfigurationManagerKeys)
0x180013a4a  mov     rdx, rax
0x180013a4d  lea     rcx, [rbp+0D0h+var_70]
0x180013a51  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180013a56  lea     rcx, [rbp+0D0h+var_50]
0x180013a5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013a62  lea     rdx, [rbp+0D0h+pExceptionObject]
0x180013a66  lea     rcx, [rsp+1D0h+var_178]
0x180013a6b  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180013a70  nop
0x180013a71  lea     r8, [rdi+20h]
0x180013a75  lea     rax, [rbp+0D0h+pExceptionObject]
0x180013a79  mov     [rsp+1D0h+var_1B0], rax
0x180013a7e  mov     r9, rdi
0x180013a81  lea     rdx, [rbp+0D0h+var_70]
0x180013a85  lea     rcx, [rbp+0D0h+var_50]
0x180013a8c  call    ?ReplaceFragmentUri@ServiceRequestHelper@BingOnlineServices@@SA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@000@Z; BingOnlineServices::ServiceRequestHelper::ReplaceFragmentUri(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180013a91  nop
0x180013a92  mov     rdx, rax
0x180013a95  lea     rcx, [rbp+0D0h+var_70]
0x180013a99  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180013a9e  nop
0x180013a9f  lea     rcx, [rbp+0D0h+var_50]
0x180013aa6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013aab  nop
0x180013aac  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180013ab0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013ab5  lea     rax, aExecutingCopyr; "Executing copyright request"
0x180013abc  mov     [rsp+1D0h+var_1B0], rax
0x180013ac1  mov     r9, rdi
0x180013ac4  mov     r8d, 5Dh ; ']'
0x180013aca  lea     rdx, aBingonlineserv_0; "BingOnlineServices::CopyrightRequest::E"...
0x180013ad1  lea     ecx, [r8-58h]
0x180013ad5  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180013adb  lea     rdx, [rbp+0D0h+var_70]
0x180013adf  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180013ae3  call    ?MakeJsonRequestAsync@ServiceRequestHelper@BingOnlineServices@@SA?AV?$task@UOnlineServiceResponse@BingOnlineServices@@@pplx@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync(std::wstring const &)
0x180013ae8  nop
0x180013ae9  mov     rdx, rsi
0x180013aec  mov     rcx, rax
0x180013aef  call    pplx__task_BingOnlineServices__OnlineServiceResponse___then__lambda_c41e8d95a32c1ff378910e4cd353399c___
0x180013af4  nop
0x180013af5  mov     rcx, [rbp+0D0h+var_88]; this
0x180013af9  test    rcx, rcx
0x180013afc  jz      short loc_180013B04
0x180013afe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180013b03  nop
0x180013b04  lea     rcx, [rsp+1D0h+var_190]
0x180013b09  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x180013b0e  nop
0x180013b0f  lea     rcx, [rbp+0D0h+var_70]
0x180013b13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013b18  mov     rax, rsi
0x180013b1b  mov     rcx, [rbp+0D0h+var_30]
0x180013b22  xor     rcx, rsp; StackCookie
0x180013b25  call    __security_check_cookie
0x180013b2a  add     rsp, 1B0h
0x180013b31  pop     r14
0x180013b33  pop     rdi
0x180013b34  pop     rsi
0x180013b35  pop     rbx
0x180013b36  pop     rbp
0x180013b37  retn
0x180013b38  lea     rax, aFailedToSpecif; "Failed to specify valid provider list"
0x180013b3f  mov     [rsp+1D0h+var_1B0], rax
0x180013b44  mov     r9, rdi
0x180013b47  mov     r8d, 51h ; 'Q'
0x180013b4d  lea     rdx, aBingonlineserv_0; "BingOnlineServices::CopyrightRequest::E"...
0x180013b54  xor     ecx, ecx
0x180013b56  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180013b5c  lea     rdx, aTheListOfProvi; "The list of providers for the copyright"...
0x180013b63  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x180013b67  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180013b6c  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180013b73  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x180013b77  call    _CxxThrowException_0
```
