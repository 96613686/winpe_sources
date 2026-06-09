# Concurrency::streams::streambuf<char>::close(int,std::exception_ptr)

- ea: `0x18002c3b0`
- end: `0x18002c4ed`
- name: `?close@?$streambuf@D@streams@Concurrency@@UEAA?AV?$task@X@pplx@@HVexception_ptr@std@@@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18000fa74`
- `0x18001235c`
- `0x180012430`
- `0x180012cc0`
- `0x1800148ac`
- `0x18002c3b0`
- `0x18002deb8`
- `0x1800305f8`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002c4cd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002c4cd`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002c40e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002c40e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Concurrency::streams::streambuf<char>::close(__int64 a1, _QWORD *a2, unsigned int a3, void *a4)
{
  _QWORD *base; // rax
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, _BYTE *, _QWORD, __int128 *); // rbx
  _QWORD *v10; // rcx
  char v11; // bl
  __int64 v12; // rax
  char v13; // bl
  __int128 v15; // [rsp+38h] [rbp-61h] BYREF
  __int64 v16; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v17; // [rsp+50h] [rbp-49h]
  _BYTE v18[16]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v19[16]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v20[120]; // [rsp+78h] [rbp-21h] BYREF

  base = (_QWORD *)Concurrency::streams::streambuf<char>::get_base();
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v16, base);
  v8 = v16;
  if ( v16 )
  {
    v9 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int128 *))(*(_QWORD *)v16 + 80LL);
    v15 = 0;
    __ExceptionPtrCopy(&v15, a4);
    v10 = (_QWORD *)v9(v8, v19, a3, &v15);
    v11 = 1;
  }
  else
  {
    v12 = pplx::task_options::task_options((pplx::task_options *)v20);
    v10 = (_QWORD *)pplx::task_from_result(v18, v12);
    v11 = 6;
  }
  *a2 = 0;
  a2[1] = 0;
  *a2 = *v10;
  a2[1] = v10[1];
  *v10 = 0;
  v10[1] = 0;
  v13 = v11 | 8;
  if ( (v13 & 4) != 0 )
  {
    v13 &= ~4u;
    pplx::task<long>::~task<long>(v18);
  }
  if ( (v13 & 2) != 0 )
  {
    v13 &= ~2u;
    pplx::task_options::~task_options((pplx::task_options *)v20);
  }
  if ( (v13 & 1) != 0 )
    pplx::task<long>::~task<long>(v19);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  __ExceptionPtrDestroy(a4);
  return a2;
}

```

## disassembly

```asm
0x18002c3b0  mov     [rsp-8+arg_0], rbx
0x18002c3b5  mov     [rsp-8+arg_18], r9
0x18002c3ba  push    rbp
0x18002c3bb  push    rsi
0x18002c3bc  push    rdi
0x18002c3bd  push    r14
0x18002c3bf  push    r15
0x18002c3c1  lea     rbp, [rsp-37h]
0x18002c3c6  sub     rsp, 0D0h
0x18002c3cd  mov     rsi, r9
0x18002c3d0  mov     r15d, r8d
0x18002c3d3  mov     rdi, rdx
0x18002c3d6  mov     [rbp+57h+var_C0], 0
0x18002c3dd  call    ?get_base@?$streambuf@D@streams@Concurrency@@QEBAAEBV?$shared_ptr@V?$basic_streambuf@D@details@streams@Concurrency@@@std@@XZ; Concurrency::streams::streambuf<char>::get_base(void)
0x18002c3e2  mov     rdx, rax
0x18002c3e5  lea     rcx, [rbp+57h+var_A8]
0x18002c3e9  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18002c3ee  nop
0x18002c3ef  mov     r14, [rbp+57h+var_A8]
0x18002c3f3  test    r14, r14
0x18002c3f6  jz      short loc_18002C434
0x18002c3f8  mov     rax, [r14]
0x18002c3fb  mov     rbx, [rax+50h]
0x18002c3ff  xorps   xmm0, xmm0
0x18002c402  movdqu  [rbp+57h+var_B8], xmm0
0x18002c407  mov     rdx, rsi
0x18002c40a  lea     rcx, [rbp+57h+var_B8]
0x18002c40e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002c414  lea     r9, [rbp+57h+var_B8]
0x18002c418  mov     r8d, r15d
0x18002c41b  lea     rdx, [rbp+57h+var_88]
0x18002c41f  mov     rcx, r14
0x18002c422  mov     rax, rbx
0x18002c425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c42a  mov     rcx, rax
0x18002c42d  mov     ebx, 1
0x18002c432  jmp     short loc_18002C459
0x18002c434  lea     rcx, [rbp+57h+var_78]; this
0x18002c438  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18002c43d  nop
0x18002c43e  mov     [rbp+57h+var_C0], 2
0x18002c445  mov     rdx, rax
0x18002c448  lea     rcx, [rbp+57h+var_98]
0x18002c44c  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x18002c451  mov     rcx, rax
0x18002c454  mov     ebx, 6
0x18002c459  mov     qword ptr [rdi], 0
0x18002c460  mov     qword ptr [rdi+8], 0
0x18002c468  mov     rax, [rcx]
0x18002c46b  mov     [rdi], rax
0x18002c46e  mov     rax, [rcx+8]
0x18002c472  mov     [rdi+8], rax
0x18002c476  mov     qword ptr [rcx], 0
0x18002c47d  mov     qword ptr [rcx+8], 0
0x18002c485  or      ebx, 8
0x18002c488  test    bl, 4
0x18002c48b  jz      short loc_18002C49A
0x18002c48d  and     ebx, 0FFFFFFFBh
0x18002c490  lea     rcx, [rbp+57h+var_98]; void *
0x18002c494  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c499  nop
0x18002c49a  test    bl, 2
0x18002c49d  jz      short loc_18002C4AC
0x18002c49f  and     ebx, 0FFFFFFFDh
0x18002c4a2  lea     rcx, [rbp+57h+var_78]; this
0x18002c4a6  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18002c4ab  nop
0x18002c4ac  test    bl, 1
0x18002c4af  jz      short loc_18002C4BB
0x18002c4b1  lea     rcx, [rbp+57h+var_88]; void *
0x18002c4b5  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002c4ba  nop
0x18002c4bb  mov     rcx, [rbp+57h+var_A0]; this
0x18002c4bf  test    rcx, rcx
0x18002c4c2  jz      short loc_18002C4CA
0x18002c4c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c4c9  nop
0x18002c4ca  mov     rcx, rsi
0x18002c4cd  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002c4d3  mov     rax, rdi
0x18002c4d6  mov     rbx, [rsp+0F0h+arg_0]
0x18002c4de  add     rsp, 0D0h
0x18002c4e5  pop     r15
0x18002c4e7  pop     r14
0x18002c4e9  pop     rdi
0x18002c4ea  pop     rsi
0x18002c4eb  pop     rbp
0x18002c4ec  retn
```
