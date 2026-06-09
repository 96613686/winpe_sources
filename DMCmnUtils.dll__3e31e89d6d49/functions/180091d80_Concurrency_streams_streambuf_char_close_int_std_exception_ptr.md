# Concurrency::streams::streambuf<char>::close(int,std::exception_ptr)

- ea: `0x180091d80`
- end: `0x180091ec5`
- name: `?close@?$streambuf@D@streams@Concurrency@@UEAA?AV?$task@X@pplx@@HVexception_ptr@std@@@Z`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18006f824`
- `0x18007b18c`
- `0x180082208`
- `0x180083d18`
- `0x180085138`
- `0x180091d80`
- `0x18009284c`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180091e9e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180091e9e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180091dde`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180091dde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Concurrency::streams::streambuf<char>::close(__int64 a1, _QWORD *a2, unsigned int a3, void *a4)
{
  __int64 base; // rax
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, _BYTE *, _QWORD, __int128 *); // rbx
  _QWORD *v10; // rcx
  char v11; // bl
  __int64 v12; // rax
  char v13; // bl
  __int128 v15; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v16[2]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v17[16]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v18[16]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v19[120]; // [rsp+78h] [rbp-21h] BYREF

  base = Concurrency::streams::streambuf<char>::get_base();
  std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(v16, base);
  v8 = v16[0];
  if ( v16[0] )
  {
    v9 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int128 *))(*(_QWORD *)v16[0] + 80LL);
    v15 = 0;
    __ExceptionPtrCopy(&v15, a4);
    v10 = (_QWORD *)v9(v8, v18, a3, &v15);
    v11 = 1;
  }
  else
  {
    v12 = pplx::task_options::task_options((pplx::task_options *)v19);
    v10 = (_QWORD *)pplx::task_from_result<void>(v17, v12);
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
    std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v17);
  }
  if ( (v13 & 2) != 0 )
  {
    v13 &= ~2u;
    pplx::task_options::~task_options((pplx::task_options *)v19);
  }
  if ( (v13 & 1) != 0 )
    std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v18);
  std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(v16);
  __ExceptionPtrDestroy(a4);
  return a2;
}

```

## disassembly

```asm
0x180091d80  mov     [rsp-8+arg_0], rbx
0x180091d85  mov     [rsp-8+arg_18], r9
0x180091d8a  push    rbp
0x180091d8b  push    rsi
0x180091d8c  push    rdi
0x180091d8d  push    r14
0x180091d8f  push    r15
0x180091d91  lea     rbp, [rsp-37h]
0x180091d96  sub     rsp, 0D0h
0x180091d9d  mov     rsi, r9
0x180091da0  mov     r15d, r8d
0x180091da3  mov     rdi, rdx
0x180091da6  mov     [rbp+57h+var_C0], 0
0x180091dad  call    ?get_base@?$streambuf@D@streams@Concurrency@@QEBAAEBV?$shared_ptr@V?$basic_streambuf@D@details@streams@Concurrency@@@std@@XZ; Concurrency::streams::streambuf<char>::get_base(void)
0x180091db2  mov     rdx, rax
0x180091db5  lea     rcx, [rbp+57h+var_A8]
0x180091db9  call    ??0?$shared_ptr@U?$_Task_impl@_N@details@pplx@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<pplx::details::_Task_impl<bool>>::shared_ptr<pplx::details::_Task_impl<bool>>(std::shared_ptr<pplx::details::_Task_impl<bool>> const &)
0x180091dbe  nop
0x180091dbf  mov     r14, [rbp+57h+var_A8]
0x180091dc3  test    r14, r14
0x180091dc6  jz      short loc_180091E0A
0x180091dc8  mov     rax, [r14]
0x180091dcb  mov     rbx, [rax+50h]
0x180091dcf  xorps   xmm0, xmm0
0x180091dd2  movdqu  [rbp+57h+var_B8], xmm0
0x180091dd7  mov     rdx, rsi
0x180091dda  lea     rcx, [rbp+57h+var_B8]
0x180091dde  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180091de5  nop     dword ptr [rax+rax+00h]
0x180091dea  lea     r9, [rbp+57h+var_B8]
0x180091dee  mov     r8d, r15d
0x180091df1  lea     rdx, [rbp+57h+var_88]
0x180091df5  mov     rcx, r14
0x180091df8  mov     rax, rbx
0x180091dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e00  mov     rcx, rax
0x180091e03  mov     ebx, 1
0x180091e08  jmp     short loc_180091E2F
0x180091e0a  lea     rcx, [rbp+57h+var_78]; this
0x180091e0e  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180091e13  nop
0x180091e14  mov     [rbp+57h+var_C0], 2
0x180091e1b  mov     rdx, rax
0x180091e1e  lea     rcx, [rbp+57h+var_98]
0x180091e22  call    ??$task_from_result@X@pplx@@YA?AV?$task@X@0@AEBVtask_options@0@@Z; pplx::task_from_result<void>(pplx::task_options const &)
0x180091e27  mov     rcx, rax
0x180091e2a  mov     ebx, 6
0x180091e2f  mov     qword ptr [rdi], 0
0x180091e36  mov     qword ptr [rdi+8], 0
0x180091e3e  mov     rax, [rcx]
0x180091e41  mov     [rdi], rax
0x180091e44  mov     rax, [rcx+8]
0x180091e48  mov     [rdi+8], rax
0x180091e4c  mov     qword ptr [rcx], 0
0x180091e53  mov     qword ptr [rcx+8], 0
0x180091e5b  or      ebx, 8
0x180091e5e  test    bl, 4
0x180091e61  jz      short loc_180091E70
0x180091e63  and     ebx, 0FFFFFFFBh
0x180091e66  lea     rcx, [rbp+57h+var_98]
0x180091e6a  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x180091e6f  nop
0x180091e70  test    bl, 2
0x180091e73  jz      short loc_180091E82
0x180091e75  and     ebx, 0FFFFFFFDh
0x180091e78  lea     rcx, [rbp+57h+var_78]; this
0x180091e7c  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180091e81  nop
0x180091e82  test    bl, 1
0x180091e85  jz      short loc_180091E91
0x180091e87  lea     rcx, [rbp+57h+var_88]
0x180091e8b  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x180091e90  nop
0x180091e91  lea     rcx, [rbp+57h+var_A8]
0x180091e95  call    ?_Decref@?$_Ptr_base@U?$_Task_impl@H@details@pplx@@@std@@IEAAXXZ; std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(void)
0x180091e9a  nop
0x180091e9b  mov     rcx, rsi
0x180091e9e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180091ea5  nop     dword ptr [rax+rax+00h]
0x180091eaa  mov     rax, rdi
0x180091ead  mov     rbx, [rsp+0F0h+arg_0]
0x180091eb5  add     rsp, 0D0h
0x180091ebc  pop     r15
0x180091ebe  pop     r14
0x180091ec0  pop     rdi
0x180091ec1  pop     rsi
0x180091ec2  pop     rbp
0x180091ec3  retn
```
