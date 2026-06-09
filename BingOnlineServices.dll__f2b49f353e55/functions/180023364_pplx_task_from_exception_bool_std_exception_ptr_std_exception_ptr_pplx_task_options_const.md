# pplx::task_from_exception<bool,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)

- ea: `0x180023364`
- end: `0x18002341c`
- name: `??$task_from_exception@_NVexception_ptr@std@@@pplx@@YA?AV?$task@_N@0@Vexception_ptr@std@@AEBVtask_options@0@@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, const struct pplx::task_options *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800258ec`
- `0x18005aecb`

## callees

- `0x18001230c`
- `0x1800148ac`
- `0x180022c10`
- `0x180023364`
- `0x1800243a8`
- `0x1800301d4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023400`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023400`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002339f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002339f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall pplx::task_from_exception<bool,std::exception_ptr>(
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

  pplx::task_completion_event<bool>::task_completion_event<bool>(&v10);
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
  pplx::create_task<pplx::task_completion_event<bool>>(a1, &v9, v6);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x180023364  mov     [rsp-8+arg_10], rbx
0x180023369  mov     [rsp-8+arg_8], rdx
0x18002336e  push    rbp
0x18002336f  push    rsi
0x180023370  push    rdi
0x180023371  lea     rbp, [rsp-47h]
0x180023376  sub     rsp, 0A0h
0x18002337d  mov     rbx, r8
0x180023380  mov     rsi, rdx
0x180023383  mov     rdi, rcx
0x180023386  lea     rcx, [rbp+57h+var_78]
0x18002338a  call    ??0?$task_completion_event@_N@pplx@@QEAA@XZ; pplx::task_completion_event<bool>::task_completion_event<bool>(void)
0x18002338f  nop
0x180023390  xorps   xmm0, xmm0
0x180023393  movdqu  [rbp+57h+var_90], xmm0
0x180023398  mov     rdx, rsi
0x18002339b  lea     rcx, [rbp+57h+var_90]
0x18002339f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800233a5  lea     rdx, [rbp+57h+var_90]
0x1800233a9  lea     rcx, [rbp+57h+var_78]
0x1800233ad  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x1800233b2  mov     rdx, rbx; struct pplx::task_options *
0x1800233b5  lea     rcx, [rbp+57h+var_68]; this
0x1800233b9  call    ??0task_options@pplx@@QEAA@AEBV01@@Z; pplx::task_options::task_options(pplx::task_options const &)
0x1800233be  xorps   xmm0, xmm0
0x1800233c1  movdqu  [rbp+57h+var_90], xmm0
0x1800233c6  mov     rbx, [rbp+57h+var_70]
0x1800233ca  test    rbx, rbx
0x1800233cd  jz      short loc_1800233D3
0x1800233cf  lock inc dword ptr [rbx+8]
0x1800233d3  mov     rdx, [rbp+57h+var_78]
0x1800233d7  mov     qword ptr [rbp+57h+var_90], rdx
0x1800233db  mov     qword ptr [rbp+57h+var_90+8], rbx
0x1800233df  mov     r8, rax
0x1800233e2  lea     rdx, [rbp+57h+var_90]
0x1800233e6  mov     rcx, rdi
0x1800233e9  call    ??$create_task@V?$task_completion_event@_N@pplx@@@pplx@@YA?AV?$task@_N@0@V?$task_completion_event@_N@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<bool>>(pplx::task_completion_event<bool>,pplx::task_options)
0x1800233ee  nop
0x1800233ef  test    rbx, rbx
0x1800233f2  jz      short loc_1800233FD
0x1800233f4  mov     rcx, rbx; this
0x1800233f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800233fc  nop
0x1800233fd  mov     rcx, rsi
0x180023400  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180023406  mov     rax, rdi
0x180023409  mov     rbx, [rsp+0B0h+arg_10]
0x180023411  add     rsp, 0A0h
0x180023418  pop     rdi
0x180023419  pop     rsi
0x18002341a  pop     rbp
0x18002341b  retn
```
