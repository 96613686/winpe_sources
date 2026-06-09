# pplx::task_from_exception<int,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x180047234`
- end: `0x1800472ec`
- name: `??$task_from_exception@HVexception_ptr@std@@@pplx@@YA?AV?$task@H@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const struct pplx::task_options *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046f38`
- `0x180048b68`
- `0x18005c751`

## callees

- `0x18001230c`
- `0x1800148ac`
- `0x1800301d4`
- `0x180046fe0`
- `0x180047234`
- `0x180048114`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800472d0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800472d0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004726f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004726f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall pplx::task_from_exception<int,std::exception_ptr>(
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

  pplx::task_completion_event<int>::task_completion_event<int>(&v10);
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
  pplx::create_task<pplx::task_completion_event<int>>(a1, &v9, v6);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x180047234  mov     [rsp-8+arg_10], rbx
0x180047239  mov     [rsp-8+arg_8], rdx
0x18004723e  push    rbp
0x18004723f  push    rsi
0x180047240  push    rdi
0x180047241  lea     rbp, [rsp-47h]
0x180047246  sub     rsp, 0A0h
0x18004724d  mov     rbx, r8
0x180047250  mov     rsi, rdx
0x180047253  mov     rdi, rcx
0x180047256  lea     rcx, [rbp+57h+var_78]
0x18004725a  call    ??0?$task_completion_event@H@pplx@@QEAA@XZ; pplx::task_completion_event<int>::task_completion_event<int>(void)
0x18004725f  nop
0x180047260  xorps   xmm0, xmm0
0x180047263  movdqu  [rbp+57h+var_90], xmm0
0x180047268  mov     rdx, rsi
0x18004726b  lea     rcx, [rbp+57h+var_90]
0x18004726f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180047275  lea     rdx, [rbp+57h+var_90]
0x180047279  lea     rcx, [rbp+57h+var_78]
0x18004727d  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x180047282  mov     rdx, rbx; struct pplx::task_options *
0x180047285  lea     rcx, [rbp+57h+var_68]; this
0x180047289  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x18004728e  xorps   xmm0, xmm0
0x180047291  movdqu  [rbp+57h+var_90], xmm0
0x180047296  mov     rbx, [rbp+57h+var_70]
0x18004729a  test    rbx, rbx
0x18004729d  jz      short loc_1800472A3
0x18004729f  lock inc dword ptr [rbx+8]
0x1800472a3  mov     rdx, [rbp+57h+var_78]
0x1800472a7  mov     qword ptr [rbp+57h+var_90], rdx
0x1800472ab  mov     qword ptr [rbp+57h+var_90+8], rbx
0x1800472af  mov     r8, rax
0x1800472b2  lea     rdx, [rbp+57h+var_90]
0x1800472b6  mov     rcx, rdi
0x1800472b9  call    ??$create_task@V?$task_completion_event@H@pplx@@@pplx@@YA?AV?$task@H@0@V?$task_completion_event@H@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<int>>(pplx::task_completion_event<int>,pplx::task_options)
0x1800472be  nop
0x1800472bf  test    rbx, rbx
0x1800472c2  jz      short loc_1800472CD
0x1800472c4  mov     rcx, rbx; this
0x1800472c7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800472cc  nop
0x1800472cd  mov     rcx, rsi
0x1800472d0  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800472d6  mov     rax, rdi
0x1800472d9  mov     rbx, [rsp+0B0h+arg_10]
0x1800472e1  add     rsp, 0A0h
0x1800472e8  pop     rdi
0x1800472e9  pop     rsi
0x1800472ea  pop     rbp
0x1800472eb  retn
```
