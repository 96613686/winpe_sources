# _lambda_c6fdc32eb2a049594b0072a7c2a28a63_::operator()(pplx::task<int>)

- ea: `0x180048b68`
- end: `0x180048d1d`
- name: `??R_lambda_c6fdc32eb2a049594b0072a7c2a28a63_@@QEBA?AV?$task@H@pplx@@V12@@Z`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180046b30`
- `0x180049cac`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x180012034`
- `0x1800122dc`
- `0x18001235c`
- `0x180012cc0`
- `0x1800148ac`
- `0x18001588c`
- `0x18003d304`
- `0x180047234`
- `0x180048b68`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180048c4a`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180048c4a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048c64`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048c64`

## string_xrefs

- `0x180048bb4`: `get() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall _lambda_c6fdc32eb2a049594b0072a7c2a28a63_::operator()(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rsi
  char v6; // r12
  const void *v7; // rax
  char v8; // bl
  const struct pplx::task_options *v9; // rbx
  void *v10; // rax
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // rcx
  unsigned int *v14; // rsi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _BYTE *, _QWORD, _QWORD *); // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  const struct pplx::task_options *v19; // rbx
  void *v20; // rax
  _QWORD v21[2]; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-198h] BYREF
  int v23; // [rsp+50h] [rbp-188h]
  _QWORD *v24; // [rsp+58h] [rbp-180h]
  _BYTE v25[16]; // [rsp+60h] [rbp-178h] BYREF
  _BYTE v26[88]; // [rsp+70h] [rbp-168h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+C8h] [rbp-110h] BYREF
  _BYTE v28[56]; // [rsp+100h] [rbp-D8h] BYREF
  _BYTE v29[56]; // [rsp+138h] [rbp-A0h] BYREF
  _BYTE v30[56]; // [rsp+170h] [rbp-68h] BYREF

  try
  {
    v4 = a2;
    v21[0] = a1;
    v22 = a2;
    v24 = a3;
    v6 = 0;
    v23 = 0;
    if ( !*a3 )
    {
      pplx::invalid_operation::invalid_operation(
        (pplx::invalid_operation *)pExceptionObject,
        "get() cannot be called on a default constructed task.");
      throw (pplx::invalid_operation *)pExceptionObject;
    }
    if ( (unsigned int)pplx::details::_Task_impl_base::_Wait(*a3) == 2 )
    {
      pplx::task_canceled::task_canceled((pplx::task_canceled *)v28);
      throw (pplx::task_canceled *)v28;
    }
    *(_BYTE *)(*a1 + 42LL) = std::_Func_class<bool,int>::operator()(a1 + 2, *(unsigned int *)(*a3 + 192LL));
  }
  catch ( ... )
  {
    v14 = (unsigned int *)v21[0];
    v15 = *(_QWORD *)v21[0];
    v16 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD *))(**(_QWORD **)v21[0] + 80LL);
    v17 = std::current_exception(v21);
    v18 = (_QWORD *)v16(v15, v25, v14[20], v17);
    if ( !*v18 )
    {
      pplx::invalid_operation::invalid_operation(
        (pplx::invalid_operation *)v29,
        "get() cannot be called on a default constructed task.");
      throw (pplx::invalid_operation *)v29;
    }
    if ( (unsigned int)pplx::details::_Task_impl_base::_Wait(*v18) == 2 )
    {
      pplx::task_canceled::task_canceled((pplx::task_canceled *)v30);
      throw (pplx::task_canceled *)v30;
    }
    pplx::task<long>::~task<long>(v25);
    v19 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v26);
    v20 = (void *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v14 + 256LL))(*(_QWORD *)v14, v25);
    pplx::task_from_exception<int,std::exception_ptr>(v22, v20, v19);
    pplx::task_options::~task_options((pplx::task_options *)v26);
    v12 = (std::_Ref_count_base *)v24[1];
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    return v22;
  }
  if ( !*(_BYTE *)(*a1 + 42LL)
    || (v7 = (const void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a1 + 256LL))(*a1, v21),
        v6 = 2,
        v8 = 1,
        !__ExceptionPtrToBool(v7)) )
  {
    v8 = 0;
  }
  if ( (v6 & 2) != 0 )
    __ExceptionPtrDestroy(v21);
  if ( v8 )
  {
    v9 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v26);
    v10 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a1 + 256LL))(*a1, &v22);
    pplx::task_from_exception<int,std::exception_ptr>(v4, v10, v9);
    pplx::task_options::~task_options((pplx::task_options *)v26);
    v11 = (std::_Ref_count_base *)a3[1];
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
  }
  else
  {
    *v4 = 0;
    v4[1] = 0;
    *v4 = *a3;
    v4[1] = a3[1];
    *a3 = 0;
    a3[1] = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180048b68  mov     [rsp+arg_18], rbx
0x180048b6d  push    rsi
0x180048b6e  push    rdi
0x180048b6f  push    r12
0x180048b71  push    r14
0x180048b73  push    r15
0x180048b75  sub     rsp, 1B0h
0x180048b7c  mov     rax, cs:__security_cookie
0x180048b83  xor     rax, rsp
0x180048b86  mov     [rsp+1D8h+var_30], rax
0x180048b8e  mov     r14, r8
0x180048b91  mov     rsi, rdx
0x180048b94  mov     r15, rcx
0x180048b97  mov     [rsp+1D8h+var_1A8], rcx
0x180048b9c  mov     [rsp+1D8h+var_198], rdx
0x180048ba1  mov     [rsp+1D8h+var_180], r8
0x180048ba6  xor     edi, edi
0x180048ba8  mov     r12d, edi
0x180048bab  mov     [rsp+1D8h+var_188], edi
0x180048baf  cmp     [r8], rdi
0x180048bb2  jnz     short loc_180048BDC
0x180048bb4  lea     rdx, aGetCannotBeCal; "get() cannot be called on a default con"...
0x180048bbb  lea     rcx, [rsp+1D8h+pExceptionObject]; this
0x180048bc3  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180048bc8  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180048bcf  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x180048bd7  call    _CxxThrowException_0
0x180048bdc  mov     rcx, [r8]
0x180048bdf  call    ?_Wait@_Task_impl_base@details@pplx@@QEAA?AW4task_group_status@3@XZ; pplx::details::_Task_impl_base::_Wait(void)
0x180048be4  cmp     eax, 2
0x180048be7  jnz     short loc_180048C0A
0x180048be9  lea     rcx, [rsp+1D8h+var_D8]; this
0x180048bf1  call    ??0task_canceled@pplx@@QEAA@XZ; pplx::task_canceled::task_canceled(void)
0x180048bf6  lea     rdx, _TI2?AVtask_canceled@pplx@@; pThrowInfo
0x180048bfd  lea     rcx, [rsp+1D8h+var_D8]; pExceptionObject
0x180048c05  call    _CxxThrowException_0
0x180048c0a  mov     rdx, [r14]
0x180048c0d  lea     rcx, [r15+10h]
0x180048c11  mov     edx, [rdx+0C0h]
0x180048c17  call    ??R?$_Func_class@_NH@std@@QEBA_NH@Z; std::_Func_class<bool,int>::operator()(int)
0x180048c1c  mov     cl, al
0x180048c1e  mov     rax, [r15]
0x180048c21  mov     [rax+2Ah], cl
0x180048c24  mov     rcx, [r15]
0x180048c27  cmp     [rcx+2Ah], dil
0x180048c2b  jz      short loc_180048C56
0x180048c2d  mov     rax, [rcx]
0x180048c30  lea     rdx, [rsp+1D8h+var_1A8]
0x180048c35  mov     rax, [rax+100h]
0x180048c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c41  mov     r12d, 2
0x180048c47  mov     rcx, rax
0x180048c4a  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180048c50  test    al, al
0x180048c52  mov     bl, 1
0x180048c54  jnz     short loc_180048C59
0x180048c56  mov     bl, dil
0x180048c59  test    r12b, 2
0x180048c5d  jz      short loc_180048C6A
0x180048c5f  lea     rcx, [rsp+1D8h+var_1A8]
0x180048c64  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180048c6a  test    bl, bl
0x180048c6c  jz      short loc_180048CBC
0x180048c6e  lea     rcx, [rsp+1D8h+var_168]; this
0x180048c73  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180048c78  mov     rbx, rax
0x180048c7b  mov     rcx, [r15]
0x180048c7e  mov     rax, [rcx]
0x180048c81  lea     rdx, [rsp+1D8h+var_198]
0x180048c86  mov     rax, [rax+100h]
0x180048c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c92  mov     r8, rbx
0x180048c95  mov     rdx, rax
0x180048c98  mov     rcx, rsi
0x180048c9b  call    ??$task_from_exception@HVexception_ptr@std@@@pplx@@YA?AV?$task@H@0@Vexception_ptr@std@@AEBVtask_options@0@@Z; pplx::task_from_exception<int,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)
0x180048ca0  nop
0x180048ca1  lea     rcx, [rsp+1D8h+var_168]; this
0x180048ca6  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180048cab  nop
0x180048cac  mov     rcx, [r14+8]; this
0x180048cb0  test    rcx, rcx
0x180048cb3  jz      short loc_180048CF2
0x180048cb5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180048cba  jmp     short loc_180048CF2
0x180048cbc  mov     [rsi], rdi
0x180048cbf  mov     [rsi+8], rdi
0x180048cc3  mov     rcx, [r14]
0x180048cc6  mov     [rsi], rcx
0x180048cc9  mov     rcx, [r14+8]
0x180048ccd  mov     [rsi+8], rcx
0x180048cd1  mov     [r14], rdi
0x180048cd4  mov     [r14+8], rdi
0x180048cd8  jmp     short loc_180048CF2
0x180048cda  mov     rax, [rsp+1D8h+var_180]
0x180048cdf  mov     rcx, [rax+8]; this
0x180048ce3  test    rcx, rcx
0x180048ce6  jz      short loc_180048CED
0x180048ce8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180048ced  mov     rsi, [rsp+1D8h+var_198]
0x180048cf2  mov     rax, rsi
0x180048cf5  mov     rcx, [rsp+1D8h+var_30]
0x180048cfd  xor     rcx, rsp; StackCookie
0x180048d00  call    __security_check_cookie
0x180048d05  mov     rbx, [rsp+1D8h+arg_18]
0x180048d0d  add     rsp, 1B0h
0x180048d14  pop     r15
0x180048d16  pop     r14
0x180048d18  pop     r12
0x180048d1a  pop     rdi
0x180048d1b  pop     rsi
0x180048d1c  retn
```
