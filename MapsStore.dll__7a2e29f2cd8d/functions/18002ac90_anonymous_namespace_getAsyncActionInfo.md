# _anonymous_namespace_::getAsyncActionInfo

- ea: `0x18002ac90`
- end: `0x18002ad6f`
- name: `_anonymous_namespace_::getAsyncActionInfo`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180029874`
- `0x18002ab6c`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x180021da8`
- `0x180024a34`
- `0x180025360`
- `0x18002ac90`
- `0x18002d9d8`
- `0x180098010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002acff`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002acff`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002ad0a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002ad0a`

## string_xrefs

- `0x18002acd5`: `TaskQueueImplWinRT::getAsyncActionInfo - QueryInterface failed for IAsyncInfo interface`

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
           v10,
           "TaskQueueImplWinRT::getAsyncActionInfo - QueryInterface failed for IAsyncInfo interface");
    v5 = std::operator<<<std::char_traits<char>>(v4, " (HRESULT: 0x");
    v6 = std::ostream::operator<<(v5, std::hex);
    v7 = std::ostream::operator<<(v6, v3);
    std::operator<<<std::char_traits<char>>(v7, ")");
    std::stringbuf::str(v11, v12);
    std::runtime_error::runtime_error((std::exception *)pExceptionObject);
    throw (std::runtime_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18002ac90  push    rbx
0x18002ac92  sub     rsp, 170h
0x18002ac99  mov     rax, cs:__security_cookie
0x18002aca0  xor     rax, rsp
0x18002aca3  mov     [rsp+178h+var_18], rax
0x18002acab  mov     rax, [rcx]
0x18002acae  mov     r8, rdx
0x18002acb1  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18002acb8  mov     rax, [rax]
0x18002acbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acc0  mov     ebx, eax
0x18002acc2  test    eax, eax
0x18002acc4  jns     loc_18002AD56
0x18002acca  lea     rcx, [rsp+178h+var_138]
0x18002accf  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002acd4  nop
0x18002acd5  lea     rdx, aTaskqueueimplw_1; "TaskQueueImplWinRT::getAsyncActionInfo "...
0x18002acdc  lea     rcx, [rsp+178h+var_128]
0x18002ace1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002ace6  mov     rcx, rax
0x18002ace9  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002acf0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002acf5  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002acfc  mov     rcx, rax
0x18002acff  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002ad05  mov     edx, ebx
0x18002ad07  mov     rcx, rax
0x18002ad0a  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002ad10  mov     rcx, rax
0x18002ad13  lea     rdx, asc_1800A4BE0; ")"
0x18002ad1a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002ad1f  lea     rdx, [rsp+178h+var_38]
0x18002ad27  lea     rcx, [rsp+178h+var_120]
0x18002ad2c  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002ad31  nop
0x18002ad32  lea     rdx, [rsp+178h+var_38]
0x18002ad3a  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18002ad3f  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002ad44  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002ad4b  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18002ad50  call    _CxxThrowException_0
0x18002ad56  mov     rcx, [rsp+178h+var_18]
0x18002ad5e  xor     rcx, rsp; StackCookie
0x18002ad61  call    __security_check_cookie
0x18002ad66  add     rsp, 170h
0x18002ad6d  pop     rbx
0x18002ad6e  retn
```
