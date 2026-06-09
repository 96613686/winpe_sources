# pplx::task_from_exception<unsigned __int64,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x1800232a4`
- end: `0x18002335c`
- name: `??$task_from_exception@_KVexception_ptr@std@@@pplx@@YA?AV?$task@_K@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const struct pplx::task_options *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800229d8`
- `0x180025dc4`
- `0x18005b0cb`

## callees

- `0x18001230c`
- `0x1800148ac`
- `0x180019c9c`
- `0x1800232a4`
- `0x180024334`
- `0x1800301d4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023340`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023340`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800232df`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800232df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall pplx::task_from_exception<unsigned __int64,std::exception_ptr>(
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

  pplx::task_completion_event<unsigned __int64>::task_completion_event<unsigned __int64>(&v10);
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
  pplx::create_task<pplx::task_completion_event<unsigned __int64>>(a1, &v9, v6);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x1800232a4  mov     [rsp-8+arg_10], rbx
0x1800232a9  mov     [rsp-8+arg_8], rdx
0x1800232ae  push    rbp
0x1800232af  push    rsi
0x1800232b0  push    rdi
0x1800232b1  lea     rbp, [rsp-47h]
0x1800232b6  sub     rsp, 0A0h
0x1800232bd  mov     rbx, r8
0x1800232c0  mov     rsi, rdx
0x1800232c3  mov     rdi, rcx
0x1800232c6  lea     rcx, [rbp+57h+var_78]
0x1800232ca  call    ??0?$task_completion_event@_K@pplx@@QEAA@XZ; pplx::task_completion_event<unsigned __int64>::task_completion_event<unsigned __int64>(void)
0x1800232cf  nop
0x1800232d0  xorps   xmm0, xmm0
0x1800232d3  movdqu  [rbp+57h+var_90], xmm0
0x1800232d8  mov     rdx, rsi
0x1800232db  lea     rcx, [rbp+57h+var_90]
0x1800232df  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800232e5  lea     rdx, [rbp+57h+var_90]
0x1800232e9  lea     rcx, [rbp+57h+var_78]
0x1800232ed  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x1800232f2  mov     rdx, rbx; struct pplx::task_options *
0x1800232f5  lea     rcx, [rbp+57h+var_68]; this
0x1800232f9  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x1800232fe  xorps   xmm0, xmm0
0x180023301  movdqu  [rbp+57h+var_90], xmm0
0x180023306  mov     rbx, [rbp+57h+var_70]
0x18002330a  test    rbx, rbx
0x18002330d  jz      short loc_180023313
0x18002330f  lock inc dword ptr [rbx+8]
0x180023313  mov     rdx, [rbp+57h+var_78]
0x180023317  mov     qword ptr [rbp+57h+var_90], rdx
0x18002331b  mov     qword ptr [rbp+57h+var_90+8], rbx
0x18002331f  mov     r8, rax
0x180023322  lea     rdx, [rbp+57h+var_90]
0x180023326  mov     rcx, rdi
0x180023329  call    ??$create_task@V?$task_completion_event@_K@pplx@@@pplx@@YA?AV?$task@_K@0@V?$task_completion_event@_K@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<unsigned __int64>>(pplx::task_completion_event<unsigned __int64>,pplx::task_options)
0x18002332e  nop
0x18002332f  test    rbx, rbx
0x180023332  jz      short loc_18002333D
0x180023334  mov     rcx, rbx; this
0x180023337  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002333c  nop
0x18002333d  mov     rcx, rsi
0x180023340  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180023346  mov     rax, rdi
0x180023349  mov     rbx, [rsp+0B0h+arg_10]
0x180023351  add     rsp, 0A0h
0x180023358  pop     rdi
0x180023359  pop     rsi
0x18002335a  pop     rbp
0x18002335b  retn
```
