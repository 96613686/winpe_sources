# pplx::task_from_exception<long,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x180023128`
- end: `0x1800231e0`
- name: `??$task_from_exception@JVexception_ptr@std@@@pplx@@YA?AV?$task@J@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const struct pplx::task_options *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022930`
- `0x180025a50`
- `0x18005afd4`

## callees

- `0x18001230c`
- `0x1800148ac`
- `0x180022a80`
- `0x180023128`
- `0x18002424c`
- `0x1800301d4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800231c4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800231c4`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023163`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023163`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall pplx::task_from_exception<long,std::exception_ptr>(
        _QWORD *a1,
        void *a2,
        const struct pplx::task_options *a3)
{
  __int64 v6; // rax
  std::_Ref_count_base *v7; // rbx
  __int128 v9; // [rsp+20h] [rbp-39h] BYREF
  __int64 v10; // [rsp+38h] [rbp-21h] BYREF
  std::_Ref_count_base *v11; // [rsp+40h] [rbp-19h]
  _BYTE v12[104]; // [rsp+48h] [rbp-11h] BYREF

  pplx::task_completion_event<long>::task_completion_event<long>(&v10);
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  pplx::task_completion_event<int>::set_exception(&v10, &v9);
  v6 = pplx::task_options::task_options((pplx::task_options *)v12, a3);
  v9 = 0;
  v7 = v11;
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
  *(_QWORD *)&v9 = v10;
  *((_QWORD *)&v9 + 1) = v7;
  pplx::create_task<pplx::task_completion_event<long>>(a1, &v9, v6);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x180023128  mov     [rsp-8+arg_10], rbx
0x18002312d  mov     [rsp-8+arg_8], rdx
0x180023132  push    rbp
0x180023133  push    rsi
0x180023134  push    rdi
0x180023135  lea     rbp, [rsp-47h]
0x18002313a  sub     rsp, 0A0h
0x180023141  mov     rbx, r8
0x180023144  mov     rsi, rdx
0x180023147  mov     rdi, rcx
0x18002314a  lea     rcx, [rbp+57h+var_78]
0x18002314e  call    ??0?$task_completion_event@J@pplx@@QEAA@XZ; pplx::task_completion_event<long>::task_completion_event<long>(void)
0x180023153  nop
0x180023154  xorps   xmm0, xmm0
0x180023157  movdqu  [rbp+57h+var_90], xmm0
0x18002315c  mov     rdx, rsi
0x18002315f  lea     rcx, [rbp+57h+var_90]
0x180023163  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180023169  lea     rdx, [rbp+57h+var_90]
0x18002316d  lea     rcx, [rbp+57h+var_78]
0x180023171  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x180023176  mov     rdx, rbx; struct pplx::task_options *
0x180023179  lea     rcx, [rbp+57h+var_68]; this
0x18002317d  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x180023182  xorps   xmm0, xmm0
0x180023185  movdqu  [rbp+57h+var_90], xmm0
0x18002318a  mov     rbx, [rbp+57h+var_70]
0x18002318e  test    rbx, rbx
0x180023191  jz      short loc_180023197
0x180023193  lock inc dword ptr [rbx+8]
0x180023197  mov     rdx, [rbp+57h+var_78]
0x18002319b  mov     qword ptr [rbp+57h+var_90], rdx
0x18002319f  mov     qword ptr [rbp+57h+var_90+8], rbx
0x1800231a3  mov     r8, rax
0x1800231a6  lea     rdx, [rbp+57h+var_90]
0x1800231aa  mov     rcx, rdi
0x1800231ad  call    ??$create_task@V?$task_completion_event@J@pplx@@@pplx@@YA?AV?$task@J@0@V?$task_completion_event@J@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<long>>(pplx::task_completion_event<long>,pplx::task_options)
0x1800231b2  nop
0x1800231b3  test    rbx, rbx
0x1800231b6  jz      short loc_1800231C1
0x1800231b8  mov     rcx, rbx; this
0x1800231bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800231c0  nop
0x1800231c1  mov     rcx, rsi
0x1800231c4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800231ca  mov     rax, rdi
0x1800231cd  mov     rbx, [rsp+0B0h+arg_10]
0x1800231d5  add     rsp, 0A0h
0x1800231dc  pop     rdi
0x1800231dd  pop     rsi
0x1800231de  pop     rbp
0x1800231df  retn
```
