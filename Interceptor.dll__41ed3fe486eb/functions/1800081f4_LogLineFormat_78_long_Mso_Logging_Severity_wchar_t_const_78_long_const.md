# LogLineFormat<78,long>(Mso::Logging::Severity,wchar_t const (&)[78],long const &)

- ea: `0x1800081f4`
- end: `0x18000824d`
- name: `??$LogLineFormat@$0EO@J@@YAXW4Severity@Logging@Mso@@AEAY0EO@$$CB_WAEBJ@Z`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800076b0`

## callees

- `0x1800045ec`
- `0x180009c90`
- `0x180021c30`
- `0x1800266e0`

## string_xrefs

- `0x180008210`: `(hr=0x%08x) CInterceptorFactory::CreateInstance() failed in StringFromCLSID()`

## pseudocode

```c
__int64 LogLineFormat<78,long>()
{
  __int64 result; // rax
  _BYTE v1[32]; // [rsp+28h] [rbp-30h] BYREF

  try
  {
    ArgumentWriter::Format<long>(
      (unsigned __int64)v1,
      L"(hr=0x%08x) CInterceptorFactory::CreateInstance() failed in StringFromCLSID()",
      77);
    LogLine(10, v1);
    result = std::wstring::_Tidy_deallocate(v1);
  }
  catch ( ... )
  {
    return MsoShipAssertTagProc(39068104);
  }
  return result;
}

```

## disassembly

```asm
0x1800081f4  sub     rsp, 58h
0x1800081f8  mov     rax, cs:__security_cookie
0x1800081ff  xor     rax, rsp
0x180008202  mov     [rsp+58h+var_10], rax
0x180008207  mov     r9, r8
0x18000820a  mov     r8d, 4Dh ; 'M'
0x180008210  lea     rdx, aHr0x08xCinterc_2; "(hr=0x%08x) CInterceptorFactory::Create"...
0x180008217  lea     rcx, [rsp+58h+var_30]
0x18000821c  call    ??$Format@J@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBJ@Z; ArgumentWriter::Format<long>(wchar_t const *,unsigned __int64,long const &)
0x180008221  lea     rdx, [rsp+58h+var_30]
0x180008226  mov     ecx, 0Ah
0x18000822b  call    ?LogLine@@YAXW4Severity@Logging@Mso@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogLine(Mso::Logging::Severity,std::wstring const &)
0x180008230  lea     rcx, [rsp+58h+var_30]
0x180008235  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000823a  nop
0x18000823b  mov     rcx, [rsp+58h+var_10]
0x180008240  xor     rcx, rsp; StackCookie
0x180008243  call    __security_check_cookie
0x180008248  add     rsp, 58h
0x18000824c  retn
```
