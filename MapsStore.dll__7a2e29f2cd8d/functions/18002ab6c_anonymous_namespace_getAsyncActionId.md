# _anonymous_namespace_::getAsyncActionId

- ea: `0x18002ab6c`
- end: `0x18002ac88`
- name: `_anonymous_namespace_::getAsyncActionId`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d438`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x180019f3c`
- `0x180021da8`
- `0x180024a34`
- `0x180025360`
- `0x18002ab6c`
- `0x18002ac90`
- `0x18002d9d8`
- `0x180098010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002ac0c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002ac0c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002ac17`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002ac17`

## string_xrefs

- `0x18002abe2`: `TaskQueueImplWinRT::getAsyncActionId - get_Id failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::getAsyncActionId(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[232]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v15[32]; // [rsp+150h] [rbp+50h] BYREF

  v10 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  anonymous_namespace_::getAsyncActionInfo(a1, &v10);
  v9 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v10 + 48LL))(v10, &v9);
  if ( v2 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v12);
    v3 = std::operator<<<std::char_traits<char>>(v13, "TaskQueueImplWinRT::getAsyncActionId - get_Id failed");
    v4 = std::operator<<<std::char_traits<char>>(v3, " (HRESULT: 0x");
    v5 = std::ostream::operator<<(v4, std::hex);
    v6 = std::ostream::operator<<(v5, (unsigned int)v2);
    std::operator<<<std::char_traits<char>>(v6, ")");
    std::stringbuf::str(v14, v15);
    std::runtime_error::runtime_error((std::exception *)pExceptionObject);
    throw (std::runtime_error *)pExceptionObject;
  }
  v7 = v9;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  return v7;
}

```

## disassembly

```asm
0x18002ab6c  mov     [rsp-8+arg_8], rbx
0x18002ab71  push    rbp
0x18002ab72  lea     rbp, [rsp-80h]
0x18002ab77  sub     rsp, 180h
0x18002ab7e  mov     rax, cs:__security_cookie
0x18002ab85  xor     rax, rsp
0x18002ab88  mov     [rbp+80h+var_10], rax
0x18002ab8c  mov     rbx, rcx
0x18002ab8f  mov     [rsp+180h+var_158], 0
0x18002ab98  lea     rcx, [rsp+180h+var_158]
0x18002ab9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002aba2  lea     rdx, [rsp+180h+var_158]
0x18002aba7  mov     rcx, rbx
0x18002abaa  call    _anonymous_namespace___getAsyncActionInfo
0x18002abaf  mov     [rsp+180h+var_160], 0
0x18002abb7  mov     rcx, [rsp+180h+var_158]
0x18002abbc  mov     rax, [rcx]
0x18002abbf  lea     rdx, [rsp+180h+var_160]
0x18002abc4  mov     rax, [rax+30h]
0x18002abc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abcd  mov     ebx, eax
0x18002abcf  test    eax, eax
0x18002abd1  jns     loc_18002AC5B
0x18002abd7  lea     rcx, [rsp+180h+var_130]
0x18002abdc  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002abe1  nop
0x18002abe2  lea     rdx, aTaskqueueimplw_2; "TaskQueueImplWinRT::getAsyncActionId - "...
0x18002abe9  lea     rcx, [rsp+180h+var_120]
0x18002abee  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002abf3  mov     rcx, rax
0x18002abf6  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002abfd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002ac02  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002ac09  mov     rcx, rax
0x18002ac0c  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002ac12  mov     edx, ebx
0x18002ac14  mov     rcx, rax
0x18002ac17  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002ac1d  mov     rcx, rax
0x18002ac20  lea     rdx, asc_1800A4BE0; ")"
0x18002ac27  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002ac2c  lea     rdx, [rbp+80h+var_30]
0x18002ac30  lea     rcx, [rsp+180h+var_118]
0x18002ac35  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002ac3a  nop
0x18002ac3b  lea     rdx, [rbp+80h+var_30]
0x18002ac3f  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18002ac44  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002ac49  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002ac50  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18002ac55  call    _CxxThrowException_0
0x18002ac5b  mov     ebx, [rsp+180h+var_160]
0x18002ac5f  lea     rcx, [rsp+180h+var_158]
0x18002ac64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ac69  mov     eax, ebx
0x18002ac6b  mov     rcx, [rbp+80h+var_10]
0x18002ac6f  xor     rcx, rsp; StackCookie
0x18002ac72  call    __security_check_cookie
0x18002ac77  mov     rbx, [rsp+180h+arg_8]
0x18002ac7f  add     rsp, 180h
0x18002ac86  pop     rbp
0x18002ac87  retn
```
