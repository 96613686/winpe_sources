# BingOnlineServices::CopyrightDataImpl::ParseCopyrightResponse(web::json::value const &)

- ea: `0x18000ac30`
- end: `0x18000ad71`
- name: `?ParseCopyrightResponse@CopyrightDataImpl@BingOnlineServices@@QEAAXAEBVvalue@json@web@@@Z`
- size: `321`
- prototype: `void __fastcall(BingOnlineServices::CopyrightDataImpl *__hidden this, const struct web::json::value *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180012ee8`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x18000756c`
- `0x180008a60`
- `0x180009730`
- `0x180009f14`
- `0x18000ac30`
- `0x180016ee0`
- `0x18003fdc0`
- `0x180040120`
- `0x180041100`
- `0x1800510e0`

## import_xrefs

- `ZTrace_Maps!ZTraceHelper` at `0x18000ad40`
- `ZTrace_Maps!ZTraceHelper` at `0x18000ad40`

## string_xrefs

- `0x18000ad20`: `Ignored copyright results because the list of providers was not an array.`
- `0x18000ad35`: `BingOnlineServices::CopyrightDataImpl::ParseCopyrightResponse`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall BingOnlineServices::CopyrightDataImpl::ParseCopyrightResponse(
        BingOnlineServices::CopyrightDataImpl *this,
        const struct web::json::value *a2)
{
  const struct web::json::array *v4; // rax
  const struct web::json::value *v5; // rbx
  const struct web::json::value *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdx
  _BYTE v9[8]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v10[8]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v11[16]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-20h]

  web::json::value::value((web::json::value *)v9);
  std::wstring::wstring(v11, L"resourceSets[0]/resources[0]/imageryProviders");
  LOBYTE(a2) = BingOnlineServices::ServiceDataHelper::TryGetJsonArrayForPath(a2, v11, v9);
  std::wstring::_Tidy_deallocate(v11);
  if ( (_BYTE)a2 )
  {
    v4 = web::json::value::as_array((web::json::value *)v9);
    v5 = *(const struct web::json::value **)v4;
    v6 = (const struct web::json::value *)*((_QWORD *)v4 + 1);
    while ( v5 != v6 )
    {
      web::json::value::value((web::json::value *)v10, v5);
      web::json::value::as_string(v10);
      std::wstring::wstring(v11);
      if ( v12 )
      {
        v8 = *((_QWORD *)this + 16);
        if ( v8 == *((_QWORD *)this + 17) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>((char *)this + 120, v8, v11);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring &>(
            v7,
            v8,
            v11);
          *((_QWORD *)this + 16) += 32LL;
        }
      }
      std::wstring::_Tidy_deallocate(v11);
      std::unique_ptr<web::json::details::_Number>::~unique_ptr<web::json::details::_Number>(v10);
      v5 = (const struct web::json::value *)((char *)v5 + 8);
    }
  }
  else
  {
    ZTraceHelper(
      2,
      "BingOnlineServices::CopyrightDataImpl::ParseCopyrightResponse",
      33,
      this,
      "Ignored copyright results because the list of providers was not an array.");
  }
  std::unique_ptr<web::json::details::_Number>::~unique_ptr<web::json::details::_Number>(v9);
}

```

## disassembly

```asm
0x18000ac30  mov     [rsp-18h+arg_10], rbx
0x18000ac35  mov     [rsp-18h+arg_18], rsi
0x18000ac3a  push    rbp
0x18000ac3b  push    rdi
0x18000ac3c  push    r14
0x18000ac3e  mov     rbp, rsp
0x18000ac41  sub     rsp, 70h
0x18000ac45  mov     rax, cs:__security_cookie
0x18000ac4c  xor     rax, rsp
0x18000ac4f  mov     [rbp+var_10], rax
0x18000ac53  mov     rbx, rdx
0x18000ac56  mov     r14, rcx
0x18000ac59  lea     rcx, [rbp+var_40]; this
0x18000ac5d  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x18000ac62  nop
0x18000ac63  lea     rdx, aResourcesets0R; "resourceSets[0]/resources[0]/imageryPro"...
0x18000ac6a  lea     rcx, [rbp+var_30]
0x18000ac6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ac73  nop
0x18000ac74  lea     r8, [rbp+var_40]
0x18000ac78  lea     rdx, [rbp+var_30]
0x18000ac7c  mov     rcx, rbx
0x18000ac7f  call    ?TryGetJsonArrayForPath@ServiceDataHelper@BingOnlineServices@@SA_NAEBVvalue@json@web@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV345@@Z; BingOnlineServices::ServiceDataHelper::TryGetJsonArrayForPath(web::json::value const &,std::wstring const &,web::json::value &)
0x18000ac84  mov     bl, al
0x18000ac86  lea     rcx, [rbp+var_30]
0x18000ac8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ac8f  test    bl, bl
0x18000ac91  jz      loc_18000AD20
0x18000ac97  lea     rcx, [rbp+var_40]; this
0x18000ac9b  call    ?as_array@value@json@web@@QEBAAEBVarray@23@XZ; web::json::value::as_array(void)
0x18000aca0  mov     rbx, [rax]
0x18000aca3  mov     rdi, [rax+8]
0x18000aca7  cmp     rbx, rdi
0x18000acaa  jz      loc_18000AD47
0x18000acb0  mov     rdx, rbx; struct web::json::value *
0x18000acb3  lea     rcx, [rbp+var_38]; this
0x18000acb7  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x18000acbc  nop
0x18000acbd  lea     rcx, [rbp+var_38]
0x18000acc1  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x18000acc6  mov     rdx, rax
0x18000acc9  lea     rcx, [rbp+var_30]
0x18000accd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000acd2  nop
0x18000acd3  cmp     [rbp+var_20], 0
0x18000acd8  jz      short loc_18000AD07
0x18000acda  mov     rdx, [r14+80h]
0x18000ace1  lea     r8, [rbp+var_30]
0x18000ace5  cmp     rdx, [r14+88h]
0x18000acec  jz      short loc_18000ACFD
0x18000acee  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring &)
0x18000acf3  add     qword ptr [r14+80h], 20h ; ' '
0x18000acfb  jmp     short loc_18000AD07
0x18000acfd  lea     rcx, [r14+78h]
0x18000ad01  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000ad06  nop
0x18000ad07  lea     rcx, [rbp+var_30]
0x18000ad0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ad10  nop
0x18000ad11  lea     rcx, [rbp+var_38]
0x18000ad15  call    ??1?$unique_ptr@V_Number@details@json@web@@U?$default_delete@V_Number@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Number>::~unique_ptr<web::json::details::_Number>(void)
0x18000ad1a  add     rbx, 8
0x18000ad1e  jmp     short loc_18000ACA7
0x18000ad20  lea     rax, aIgnoredCopyrig; "Ignored copyright results because the l"...
0x18000ad27  mov     [rsp+70h+var_50], rax
0x18000ad2c  mov     r9, r14
0x18000ad2f  mov     r8d, 21h ; '!'
0x18000ad35  lea     rdx, aBingonlineserv_1; "BingOnlineServices::CopyrightDataImpl::"...
0x18000ad3c  lea     ecx, [r8-1Fh]
0x18000ad40  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000ad46  nop
0x18000ad47  lea     rcx, [rbp+var_40]
0x18000ad4b  call    ??1?$unique_ptr@V_Number@details@json@web@@U?$default_delete@V_Number@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Number>::~unique_ptr<web::json::details::_Number>(void)
0x18000ad50  mov     rcx, [rbp+var_10]
0x18000ad54  xor     rcx, rsp; StackCookie
0x18000ad57  call    __security_check_cookie
0x18000ad5c  lea     r11, [rsp+70h+var_s0]
0x18000ad61  mov     rbx, [r11+30h]
0x18000ad65  mov     rsi, [r11+38h]
0x18000ad69  mov     rsp, r11
0x18000ad6c  pop     r14
0x18000ad6e  pop     rdi
0x18000ad6f  pop     rbp
0x18000ad70  retn
```
