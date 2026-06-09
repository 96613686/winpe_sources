# _anonymous_namespace_::getAsyncActionId

- ea: `0x18001722c`
- end: `0x180017348`
- name: `_anonymous_namespace_::getAsyncActionId`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a208`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000b4b8`
- `0x18000cd80`
- `0x18001006c`
- `0x180010b18`
- `0x18001722c`
- `0x180017350`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800172cc`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800172cc`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800172d7`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800172d7`

## string_xrefs

- `0x1800172a2`: `TaskQueueImplWinRT::getAsyncActionId - get_Id failed`

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
    v3 = std::operator<<<std::char_traits<char>>(
           (__int64)v13,
           (__int64)"TaskQueueImplWinRT::getAsyncActionId - get_Id failed");
    v4 = std::operator<<<std::char_traits<char>>(v3, (__int64)" (HRESULT: 0x");
    v5 = std::ostream::operator<<(v4, std::hex);
    v6 = std::ostream::operator<<(v5, (unsigned int)v2);
    std::operator<<<std::char_traits<char>>(v6, (__int64)")");
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
0x18001722c  mov     [rsp-8+arg_8], rbx
0x180017231  push    rbp
0x180017232  lea     rbp, [rsp-80h]
0x180017237  sub     rsp, 180h
0x18001723e  mov     rax, cs:__security_cookie
0x180017245  xor     rax, rsp
0x180017248  mov     [rbp+80h+var_10], rax
0x18001724c  mov     rbx, rcx
0x18001724f  mov     [rsp+180h+var_158], 0
0x180017258  lea     rcx, [rsp+180h+var_158]
0x18001725d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017262  lea     rdx, [rsp+180h+var_158]
0x180017267  mov     rcx, rbx
0x18001726a  call    _anonymous_namespace___getAsyncActionInfo
0x18001726f  mov     [rsp+180h+var_160], 0
0x180017277  mov     rcx, [rsp+180h+var_158]
0x18001727c  mov     rax, [rcx]
0x18001727f  lea     rdx, [rsp+180h+var_160]
0x180017284  mov     rax, [rax+30h]
0x180017288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001728d  mov     ebx, eax
0x18001728f  test    eax, eax
0x180017291  jns     loc_18001731B
0x180017297  lea     rcx, [rsp+180h+var_130]
0x18001729c  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800172a1  nop
0x1800172a2  lea     rdx, aTaskqueueimplw_2; "TaskQueueImplWinRT::getAsyncActionId - "...
0x1800172a9  lea     rcx, [rsp+180h+var_120]
0x1800172ae  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800172b3  mov     rcx, rax
0x1800172b6  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x1800172bd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800172c2  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x1800172c9  mov     rcx, rax
0x1800172cc  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800172d2  mov     edx, ebx
0x1800172d4  mov     rcx, rax
0x1800172d7  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x1800172dd  mov     rcx, rax
0x1800172e0  lea     rdx, asc_180048470; ")"
0x1800172e7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800172ec  lea     rdx, [rbp+80h+var_30]
0x1800172f0  lea     rcx, [rsp+180h+var_118]
0x1800172f5  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800172fa  nop
0x1800172fb  lea     rdx, [rbp+80h+var_30]
0x1800172ff  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180017304  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180017309  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017310  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180017315  call    _CxxThrowException_0
0x18001731b  mov     ebx, [rsp+180h+var_160]
0x18001731f  lea     rcx, [rsp+180h+var_158]
0x180017324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017329  mov     eax, ebx
0x18001732b  mov     rcx, [rbp+80h+var_10]
0x18001732f  xor     rcx, rsp; StackCookie
0x180017332  call    __security_check_cookie
0x180017337  mov     rbx, [rsp+180h+arg_8]
0x18001733f  add     rsp, 180h
0x180017346  pop     rbp
0x180017347  retn
```
