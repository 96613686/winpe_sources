# std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Copy

- ea: `0x180028790`
- end: `0x1800287ec`
- name: `std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Copy`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180028790`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800287dd`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800287dd`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Copy(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v3; // rax

  *a2 = &std::_Func_impl_no_alloc<_lambda_ee57e8bf9260da23c0b4ae8d53de024f_,void,pplx::task<void>>::`vftable';
  a2[1] = 0;
  a2[2] = 0;
  v3 = a1[2];
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  a2[1] = a1[1];
  a2[2] = a1[2];
  a2[3] = 0;
  a2[4] = 0;
  __ExceptionPtrCopy(a2 + 3, a1 + 3);
  return a2;
}

```

## disassembly

```asm
0x180028790  push    rbx
0x180028792  sub     rsp, 20h
0x180028796  mov     rbx, rdx
0x180028799  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ee57e8bf9260da23c0b4ae8d53de024f_@@XV?$task@X@pplx@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_ee57e8bf9260da23c0b4ae8d53de024f_,void,pplx::task<void>>::`vftable'
0x1800287a0  xor     r8d, r8d
0x1800287a3  mov     rdx, rcx
0x1800287a6  mov     [rbx], rax
0x1800287a9  mov     [rbx+8], r8
0x1800287ad  mov     [rbx+10h], r8
0x1800287b1  mov     rax, [rcx+10h]
0x1800287b5  test    rax, rax
0x1800287b8  jz      short loc_1800287BE
0x1800287ba  lock inc dword ptr [rax+8]
0x1800287be  mov     rax, [rcx+8]
0x1800287c2  add     rdx, 18h
0x1800287c6  mov     [rbx+8], rax
0x1800287ca  mov     rax, [rcx+10h]
0x1800287ce  lea     rcx, [rbx+18h]
0x1800287d2  mov     [rbx+10h], rax
0x1800287d6  mov     [rcx], r8
0x1800287d9  mov     [rcx+8], r8
0x1800287dd  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800287e3  mov     rax, rbx
0x1800287e6  add     rsp, 20h
0x1800287ea  pop     rbx
0x1800287eb  retn
```
