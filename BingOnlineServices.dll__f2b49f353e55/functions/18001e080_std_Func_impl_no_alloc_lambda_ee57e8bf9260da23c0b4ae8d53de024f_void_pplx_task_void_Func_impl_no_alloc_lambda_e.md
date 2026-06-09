# std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void_____lambda_ee57e8bf9260da23c0b4ae8d53de024f__0_

- ea: `0x18001e080`
- end: `0x18001e0d8`
- name: `std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void_____lambda_ee57e8bf9260da23c0b4ae8d53de024f__0_`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180029900`
- `0x18002a810`

## callees

- `0x18001e080`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001e0c9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001e0c9`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void_____lambda_ee57e8bf9260da23c0b4ae8d53de024f__0_(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v3; // rax
  _QWORD *v4; // rcx

  *a1 = &std::_Func_impl_no_alloc<_lambda_ee57e8bf9260da23c0b4ae8d53de024f_,void,pplx::task<void>>::`vftable';
  a1[1] = 0;
  a1[2] = 0;
  v3 = a2[1];
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  a1[1] = *a2;
  a1[2] = a2[1];
  v4 = a1 + 3;
  *v4 = 0;
  v4[1] = 0;
  __ExceptionPtrCopy(v4, a2 + 2);
  return a1;
}

```

## disassembly

```asm
0x18001e080  push    rbx
0x18001e082  sub     rsp, 20h
0x18001e086  xor     r8d, r8d
0x18001e089  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ee57e8bf9260da23c0b4ae8d53de024f_@@XV?$task@X@pplx@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_ee57e8bf9260da23c0b4ae8d53de024f_,void,pplx::task<void>>::`vftable'
0x18001e090  mov     [rcx], rax
0x18001e093  mov     rbx, rcx
0x18001e096  mov     [rcx+8], r8
0x18001e09a  mov     [rcx+10h], r8
0x18001e09e  mov     rax, [rdx+8]
0x18001e0a2  test    rax, rax
0x18001e0a5  jz      short loc_18001E0AB
0x18001e0a7  lock inc dword ptr [rax+8]
0x18001e0ab  mov     rax, [rdx]
0x18001e0ae  mov     [rcx+8], rax
0x18001e0b2  mov     rax, [rdx+8]
0x18001e0b6  add     rdx, 10h
0x18001e0ba  mov     [rcx+10h], rax
0x18001e0be  add     rcx, 18h
0x18001e0c2  mov     [rcx], r8
0x18001e0c5  mov     [rcx+8], r8
0x18001e0c9  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001e0cf  mov     rax, rbx
0x18001e0d2  add     rsp, 20h
0x18001e0d6  pop     rbx
0x18001e0d7  retn
```
