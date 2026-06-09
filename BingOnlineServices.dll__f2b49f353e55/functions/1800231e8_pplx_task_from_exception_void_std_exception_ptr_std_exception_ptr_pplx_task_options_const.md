# pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800231e8`
- end: `0x18002329c`
- name: `??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `180`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const struct pplx::task_options *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800304f0`
- `0x18004e450`

## callees

- `0x18001230c`
- `0x180012430`
- `0x180022b4c`
- `0x1800231e8`
- `0x1800241d8`
- `0x180030280`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023280`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023280`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023223`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023223`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall pplx::task_from_exception<void,std::exception_ptr>(
        _QWORD *a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  __int64 v10; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h]
  _BYTE v12[104]; // [rsp+48h] [rbp-11h] BYREF

  pplx::task_completion_event<unsigned char>::task_completion_event<unsigned char>(&v10);
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  pplx::task_completion_event<void>::set_exception(&v10, &v9);
  v6 = pplx::task_options::task_options((pplx::task_options *)v12, a3);
  v9 = 0;
  v7 = v11;
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)&v9 = v10;
  *((_QWORD *)&v9 + 1) = v7;
  pplx::create_task<pplx::task_completion_event<void>>(a1, &v9, v6);
  pplx::task<long>::~task<long>(&v10);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800231e8  mov     [rsp-8+arg_10], rbx
0x1800231ed  mov     [rsp-8+arg_8], rdx
0x1800231f2  push    rbp
0x1800231f3  push    rsi
0x1800231f4  push    rdi
0x1800231f5  lea     rbp, [rsp-47h]
0x1800231fa  sub     rsp, 0A0h
0x180023201  mov     rbx, r8
0x180023204  mov     rsi, rdx
0x180023207  mov     rdi, rcx
0x18002320a  lea     rcx, [rbp+57h+var_80]
0x18002320e  call    ??0?$task_completion_event@E@pplx@@QEAA@XZ; pplx::task_completion_event<uchar>::task_completion_event<uchar>(void)
0x180023213  nop
0x180023214  xorps   xmm0, xmm0
0x180023217  movdqu  [rbp+57h+var_90], xmm0
0x18002321c  mov     rdx, rsi
0x18002321f  lea     rcx, [rbp+57h+var_90]
0x180023223  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180023229  lea     rdx, [rbp+57h+var_90]
0x18002322d  lea     rcx, [rbp+57h+var_80]
0x180023231  call    ?set_exception@?$task_completion_event@X@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<void>::set_exception(std::exception_ptr)
0x180023236  mov     rdx, rbx; struct pplx::task_options *
0x180023239  lea     rcx, [rbp+57h+var_68]; this
0x18002323d  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x180023242  xorps   xmm0, xmm0
0x180023245  movdqu  [rbp+57h+var_90], xmm0
0x18002324a  mov     rdx, [rbp+57h+var_78]
0x18002324e  test    rdx, rdx
0x180023251  jz      short loc_180023257
0x180023253  lock inc dword ptr [rdx+8]
0x180023257  mov     rcx, [rbp+57h+var_80]
0x18002325b  mov     qword ptr [rbp+57h+var_90], rcx
0x18002325f  mov     qword ptr [rbp+57h+var_90+8], rdx
0x180023263  mov     r8, rax
0x180023266  lea     rdx, [rbp+57h+var_90]
0x18002326a  mov     rcx, rdi
0x18002326d  call    ??$create_task@V?$task_completion_event@X@pplx@@@pplx@@YA?AV?$task@X@0@V?$task_completion_event@X@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<void>>(pplx::task_completion_event<void>,pplx::task_options)
0x180023272  nop
0x180023273  lea     rcx, [rbp+57h+var_80]; void *
0x180023277  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002327c  nop
0x18002327d  mov     rcx, rsi
0x180023280  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180023286  mov     rax, rdi
0x180023289  mov     rbx, [rsp+0B0h+arg_10]
0x180023291  add     rsp, 0A0h
0x180023298  pop     rdi
0x180023299  pop     rsi
0x18002329a  pop     rbp
0x18002329b  retn
```
