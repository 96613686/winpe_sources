# _lambda_ee57e8bf9260da23c0b4ae8d53de024f_::operator()

- ea: `0x180025c6c`
- end: `0x180025dbd`
- name: `_lambda_ee57e8bf9260da23c0b4ae8d53de024f_::operator()`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029120`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x180012034`
- `0x1800122dc`
- `0x18001235c`
- `0x180012430`
- `0x1800148ac`
- `0x18001588c`
- `0x180019c9c`
- `0x180023864`
- `0x180025c6c`
- `0x1800301d4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180025d15`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180025d15`

## string_xrefs

- `0x180025ca3`: `get() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall lambda_ee57e8bf9260da23c0b4ae8d53de024f_::operator()(__int64 *a1, _QWORD *a2)
{
  void *v2; // rbx
  __int64 *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int128 v7; // [rsp+20h] [rbp-118h] BYREF
  _QWORD *v8; // [rsp+30h] [rbp-108h]
  _BYTE v9[16]; // [rsp+38h] [rbp-100h] BYREF
  __int64 v10; // [rsp+48h] [rbp-F0h] BYREF
  std::_Ref_count_base *v11; // [rsp+50h] [rbp-E8h]
  _BYTE v12[88]; // [rsp+58h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+B0h] [rbp-88h] BYREF
  _BYTE v14[56]; // [rsp+E8h] [rbp-50h] BYREF

  try
  {
    v2 = a2;
    v3 = a1;
    *(_QWORD *)&v7 = a1;
    v8 = a2;
    if ( !*a2 )
    {
      pplx::invalid_operation::invalid_operation(
        (pplx::invalid_operation *)pExceptionObject,
        "get() cannot be called on a default constructed task.");
      throw (pplx::invalid_operation *)pExceptionObject;
    }
    if ( (unsigned int)pplx::details::_Task_impl_base::_Wait(*a2) == 2 )
    {
      pplx::task_canceled::task_canceled((pplx::task_canceled *)v14);
      throw (pplx::task_canceled *)v14;
    }
  }
  catch ( ... )
  {
    v3 = (__int64 *)v7;
    v2 = v8;
  }
  v7 = 0;
  __ExceptionPtrCopy(&v7, v3 + 2);
  pplx::task_completion_event<int>::set_exception(v3, &v7);
  v4 = pplx::task_options::task_options((pplx::task_options *)v12);
  v7 = 0;
  v5 = v3[1];
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v7 = *(_OWORD *)v3;
  v6 = pplx::create_task<pplx::task_completion_event<unsigned __int64>>(&v10, &v7, v4);
  pplx::task_unsigned___int64_::then__lambda_96762bf1fe472a5ecda1578f6e6c94d4___(v6, v9);
  pplx::task<long>::~task<long>(v9);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  pplx::task<long>::~task<long>(v2);
}

```

## disassembly

```asm
0x180025c6c  mov     [rsp+arg_10], rbx
0x180025c71  push    rdi
0x180025c72  sub     rsp, 130h
0x180025c79  mov     rax, cs:__security_cookie
0x180025c80  xor     rax, rsp
0x180025c83  mov     [rsp+138h+var_18], rax
0x180025c8b  mov     rbx, rdx
0x180025c8e  mov     rdi, rcx
0x180025c91  mov     qword ptr [rsp+138h+var_118], rcx
0x180025c96  mov     [rsp+138h+var_108], rdx
0x180025c9b  mov     rcx, [rdx]
0x180025c9e  test    rcx, rcx
0x180025ca1  jnz     short loc_180025CCB
0x180025ca3  lea     rdx, aGetCannotBeCal; "get() cannot be called on a default con"...
0x180025caa  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180025cb2  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180025cb7  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180025cbe  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180025cc6  call    _CxxThrowException_0
0x180025ccb  call    ?_Wait@_Task_impl_base@details@pplx@@QEAA?AW4task_group_status@3@XZ; pplx::details::_Task_impl_base::_Wait(void)
0x180025cd0  cmp     eax, 2
0x180025cd3  jnz     short loc_180025CF7
0x180025cd5  lea     rcx, [rsp+138h+var_50]; this
0x180025cdd  call    ??0task_canceled@pplx@@QEAA@XZ; pplx::task_canceled::task_canceled(void)
0x180025ce2  lea     rdx, _TI2?AVtask_canceled@pplx@@; pThrowInfo
0x180025ce9  lea     rcx, [rsp+138h+var_50]; pExceptionObject
0x180025cf1  call    _CxxThrowException_0
0x180025cf7  jmp     short loc_180025D03
0x180025cf9  mov     rdi, qword ptr [rsp+138h+var_118]
0x180025cfe  mov     rbx, [rsp+138h+var_108]
0x180025d03  xorps   xmm0, xmm0
0x180025d06  movdqu  [rsp+138h+var_118], xmm0
0x180025d0c  lea     rdx, [rdi+10h]
0x180025d10  lea     rcx, [rsp+138h+var_118]
0x180025d15  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180025d1b  lea     rdx, [rsp+138h+var_118]
0x180025d20  mov     rcx, rdi
0x180025d23  call    ?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<int>::set_exception(std::exception_ptr)
0x180025d28  lea     rcx, [rsp+138h+var_E0]; this
0x180025d2d  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180025d32  mov     r8, rax
0x180025d35  xorps   xmm0, xmm0
0x180025d38  movdqu  [rsp+138h+var_118], xmm0
0x180025d3e  mov     rcx, [rdi+8]
0x180025d42  test    rcx, rcx
0x180025d45  jz      short loc_180025D4B
0x180025d47  lock inc dword ptr [rcx+8]
0x180025d4b  mov     rax, [rdi]
0x180025d4e  mov     qword ptr [rsp+138h+var_118], rax
0x180025d53  mov     rax, [rdi+8]
0x180025d57  mov     qword ptr [rsp+138h+var_118+8], rax
0x180025d5c  lea     rdx, [rsp+138h+var_118]
0x180025d61  lea     rcx, [rsp+138h+var_F0]
0x180025d66  call    ??$create_task@V?$task_completion_event@_K@pplx@@@pplx@@YA?AV?$task@_K@0@V?$task_completion_event@_K@0@Vtask_options@0@@Z; pplx::create_task<pplx::task_completion_event<unsigned __int64>>(pplx::task_completion_event<unsigned __int64>,pplx::task_options)
0x180025d6b  nop
0x180025d6c  lea     rdx, [rsp+138h+var_100]
0x180025d71  mov     rcx, rax
0x180025d74  call    pplx__task_unsigned___int64___then__lambda_96762bf1fe472a5ecda1578f6e6c94d4___
0x180025d79  lea     rcx, [rsp+138h+var_100]; void *
0x180025d7e  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x180025d83  nop
0x180025d84  mov     rcx, [rsp+138h+var_E8]; this
0x180025d89  test    rcx, rcx
0x180025d8c  jz      short loc_180025D94
0x180025d8e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025d93  nop
0x180025d94  mov     rcx, rbx; void *
0x180025d97  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x180025d9c  mov     rcx, [rsp+138h+var_18]
0x180025da4  xor     rcx, rsp; StackCookie
0x180025da7  call    __security_check_cookie
0x180025dac  mov     rbx, [rsp+138h+arg_10]
0x180025db4  add     rsp, 130h
0x180025dbb  pop     rdi
0x180025dbc  retn
```
