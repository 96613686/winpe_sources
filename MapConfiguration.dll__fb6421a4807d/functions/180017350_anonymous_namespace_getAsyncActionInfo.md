# _anonymous_namespace_::getAsyncActionInfo

- ea: `0x180017350`
- end: `0x18001742f`
- name: `_anonymous_namespace_::getAsyncActionInfo`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180015d54`
- `0x18001722c`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000cd80`
- `0x18001006c`
- `0x180010b18`
- `0x180017350`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800173bf`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800173bf`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800173ca`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800173ca`

## string_xrefs

- `0x180017395`: `TaskQueueImplWinRT::getAsyncActionInfo - QueryInterface failed for IAsyncInfo interface`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::getAsyncActionInfo(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-150h] BYREF
  _BYTE v9[16]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v10[8]; // [rsp+50h] [rbp-128h] BYREF
  _BYTE v11[232]; // [rsp+58h] [rbp-120h] BYREF
  _BYTE v12[32]; // [rsp+140h] [rbp-38h] BYREF

  result = (**a1)(a1, &GUID_00000036_0000_0000_c000_000000000046, a2);
  v3 = result;
  if ( (int)result < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v9);
    v4 = std::operator<<<std::char_traits<char>>(
           (__int64)v10,
           (__int64)"TaskQueueImplWinRT::getAsyncActionInfo - QueryInterface failed for IAsyncInfo interface");
    v5 = std::operator<<<std::char_traits<char>>(v4, (__int64)" (HRESULT: 0x");
    v6 = std::ostream::operator<<(v5, std::hex);
    v7 = std::ostream::operator<<(v6, v3);
    std::operator<<<std::char_traits<char>>(v7, (__int64)")");
    std::stringbuf::str(v11, v12);
    std::runtime_error::runtime_error((std::exception *)pExceptionObject);
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180017350  push    rbx
0x180017352  sub     rsp, 170h
0x180017359  mov     rax, cs:__security_cookie
0x180017360  xor     rax, rsp
0x180017363  mov     [rsp+178h+var_18], rax
0x18001736b  mov     rax, [rcx]
0x18001736e  mov     r8, rdx
0x180017371  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180017378  mov     rax, [rax]
0x18001737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017380  mov     ebx, eax
0x180017382  test    eax, eax
0x180017384  jns     loc_180017416
0x18001738a  lea     rcx, [rsp+178h+var_138]
0x18001738f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180017394  nop
0x180017395  lea     rdx, aTaskqueueimplw_1; "TaskQueueImplWinRT::getAsyncActionInfo "...
0x18001739c  lea     rcx, [rsp+178h+var_128]
0x1800173a1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800173a6  mov     rcx, rax
0x1800173a9  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x1800173b0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800173b5  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x1800173bc  mov     rcx, rax
0x1800173bf  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800173c5  mov     edx, ebx
0x1800173c7  mov     rcx, rax
0x1800173ca  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x1800173d0  mov     rcx, rax
0x1800173d3  lea     rdx, asc_180048470; ")"
0x1800173da  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800173df  lea     rdx, [rsp+178h+var_38]
0x1800173e7  lea     rcx, [rsp+178h+var_120]
0x1800173ec  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800173f1  nop
0x1800173f2  lea     rdx, [rsp+178h+var_38]
0x1800173fa  lea     rcx, [rsp+178h+pExceptionObject]; this
0x1800173ff  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180017404  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001740b  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180017410  call    _CxxThrowException_0
0x180017416  mov     rcx, [rsp+178h+var_18]
0x18001741e  xor     rcx, rsp; StackCookie
0x180017421  call    __security_check_cookie
0x180017426  add     rsp, 170h
0x18001742d  pop     rbx
0x18001742e  retn
```
