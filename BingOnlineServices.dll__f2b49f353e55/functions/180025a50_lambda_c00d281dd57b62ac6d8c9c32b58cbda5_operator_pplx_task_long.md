# _lambda_c00d281dd57b62ac6d8c9c32b58cbda5_::operator()(pplx::task<long>)

- ea: `0x180025a50`
- end: `0x180025c20`
- name: `??R_lambda_c00d281dd57b62ac6d8c9c32b58cbda5_@@QEBA?AV?$task@J@pplx@@V12@@Z`
- size: `464`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180022528`
- `0x1800273e4`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x180012034`
- `0x1800122dc`
- `0x18001235c`
- `0x180012cc0`
- `0x1800148ac`
- `0x18001588c`
- `0x180023128`
- `0x180025a50`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180025b4d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180025b4d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180025b67`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180025b67`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180025b08`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180025b08`

## string_xrefs

- `0x180025a9c`: `get() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall _lambda_c00d281dd57b62ac6d8c9c32b58cbda5_::operator()(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rsi
  char v6; // r12
  __int64 v7; // rcx
  const void *v8; // rax
  char v9; // bl
  const struct pplx::task_options *v10; // rbx
  void *v11; // rax
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx
  unsigned int *v15; // rsi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _BYTE *, _QWORD, _QWORD *); // rbx
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  const struct pplx::task_options *v20; // rbx
  void *v21; // rax
  _QWORD v22[2]; // [rsp+30h] [rbp-1B8h] BYREF
  int v23; // [rsp+40h] [rbp-1A8h] BYREF
  _QWORD *v24; // [rsp+48h] [rbp-1A0h] BYREF
  int v25; // [rsp+58h] [rbp-190h]
  _QWORD *v26; // [rsp+60h] [rbp-188h]
  _BYTE v27[16]; // [rsp+68h] [rbp-180h] BYREF
  _BYTE v28[88]; // [rsp+78h] [rbp-170h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+D0h] [rbp-118h] BYREF
  _BYTE v30[56]; // [rsp+108h] [rbp-E0h] BYREF
  _BYTE v31[56]; // [rsp+140h] [rbp-A8h] BYREF
  _BYTE v32[56]; // [rsp+178h] [rbp-70h] BYREF

  try
  {
    v4 = a2;
    v22[0] = a1;
    v24 = a2;
    v26 = a3;
    v6 = 0;
    v25 = 0;
    if ( !*a3 )
    {
      pplx::invalid_operation::invalid_operation(
        (pplx::invalid_operation *)pExceptionObject,
        "get() cannot be called on a default constructed task.");
      throw (pplx::invalid_operation *)pExceptionObject;
    }
    if ( (unsigned int)pplx::details::_Task_impl_base::_Wait(*a3) == 2 )
    {
      pplx::task_canceled::task_canceled((pplx::task_canceled *)v30);
      throw (pplx::task_canceled *)v30;
    }
    v23 = *(_DWORD *)(*a3 + 192LL);
    v7 = a1[9];
    if ( !v7 )
      std::_Xbad_function_call();
    *(_BYTE *)(*a1 + 42LL) = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 16LL))(v7, &v23);
  }
  catch ( ... )
  {
    v15 = (unsigned int *)v22[0];
    v16 = *(_QWORD *)v22[0];
    v17 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD *))(**(_QWORD **)v22[0] + 80LL);
    v18 = std::current_exception(v22);
    v19 = (_QWORD *)v17(v16, v27, v15[20], v18);
    if ( !*v19 )
    {
      pplx::invalid_operation::invalid_operation(
        (pplx::invalid_operation *)v31,
        "get() cannot be called on a default constructed task.");
      throw (pplx::invalid_operation *)v31;
    }
    if ( (unsigned int)pplx::details::_Task_impl_base::_Wait(*v19) == 2 )
    {
      pplx::task_canceled::task_canceled((pplx::task_canceled *)v32);
      throw (pplx::task_canceled *)v32;
    }
    pplx::task<long>::~task<long>(v27);
    v20 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v28);
    v21 = (void *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v15 + 256LL))(*(_QWORD *)v15, v27);
    pplx::task_from_exception<long,std::exception_ptr>(v24, v21, v20);
    pplx::task_options::~task_options((pplx::task_options *)v28);
    v13 = (std::_Ref_count_base *)v26[1];
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    return v24;
  }
  if ( !*(_BYTE *)(*a1 + 42LL)
    || (v8 = (const void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a1 + 256LL))(*a1, v22),
        v6 = 2,
        v9 = 1,
        !__ExceptionPtrToBool(v8)) )
  {
    v9 = 0;
  }
  if ( (v6 & 2) != 0 )
    __ExceptionPtrDestroy(v22);
  if ( v9 )
  {
    v10 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v28);
    v11 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a1 + 256LL))(*a1, &v24);
    pplx::task_from_exception<long,std::exception_ptr>(v4, v11, v10);
    pplx::task_options::~task_options((pplx::task_options *)v28);
    v12 = (std::_Ref_count_base *)a3[1];
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
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
0x180025a50  mov     [rsp+arg_18], rbx
0x180025a55  push    rsi
0x180025a56  push    rdi
0x180025a57  push    r12
0x180025a59  push    r14
0x180025a5b  push    r15
0x180025a5d  sub     rsp, 1C0h
0x180025a64  mov     rax, cs:__security_cookie
0x180025a6b  xor     rax, rsp
0x180025a6e  mov     [rsp+1E8h+var_38], rax
0x180025a76  mov     r14, r8
0x180025a79  mov     rsi, rdx
0x180025a7c  mov     r15, rcx
0x180025a7f  mov     [rsp+1E8h+var_1B8], rcx
0x180025a84  mov     [rsp+1E8h+var_1A0], rdx
0x180025a89  mov     [rsp+1E8h+var_188], r8
0x180025a8e  xor     edi, edi
0x180025a90  mov     r12d, edi
0x180025a93  mov     [rsp+1E8h+var_190], edi
0x180025a97  cmp     [r8], rdi
0x180025a9a  jnz     short loc_180025AC4
0x180025a9c  lea     rdx, aGetCannotBeCal; "get() cannot be called on a default con"...
0x180025aa3  lea     rcx, [rsp+1E8h+pExceptionObject]; this
0x180025aab  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x180025ab0  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180025ab7  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x180025abf  call    _CxxThrowException_0
0x180025ac4  mov     rcx, [r8]
0x180025ac7  call    ?_Wait@_Task_impl_base@details@pplx@@QEAA?AW4task_group_status@3@XZ; pplx::details::_Task_impl_base::_Wait(void)
0x180025acc  cmp     eax, 2
0x180025acf  jnz     short loc_180025AF2
0x180025ad1  lea     rcx, [rsp+1E8h+var_E0]; this
0x180025ad9  call    ??0task_canceled@pplx@@QEAA@XZ; pplx::task_canceled::task_canceled(void)
0x180025ade  lea     rdx, _TI2?AVtask_canceled@pplx@@; pThrowInfo
0x180025ae5  lea     rcx, [rsp+1E8h+var_E0]; pExceptionObject
0x180025aed  call    _CxxThrowException_0
0x180025af2  mov     rax, [r14]
0x180025af5  mov     ecx, [rax+0C0h]
0x180025afb  mov     [rsp+1E8h+var_1A8], ecx
0x180025aff  mov     rcx, [r15+48h]
0x180025b03  test    rcx, rcx
0x180025b06  jnz     short loc_180025B0E
0x180025b08  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180025b0e  mov     rax, [rcx]
0x180025b11  lea     rdx, [rsp+1E8h+var_1A8]
0x180025b16  mov     rax, [rax+10h]
0x180025b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b1f  mov     cl, al
0x180025b21  mov     rax, [r15]
0x180025b24  mov     [rax+2Ah], cl
0x180025b27  mov     rcx, [r15]
0x180025b2a  cmp     [rcx+2Ah], dil
0x180025b2e  jz      short loc_180025B59
0x180025b30  mov     rax, [rcx]
0x180025b33  lea     rdx, [rsp+1E8h+var_1B8]
0x180025b38  mov     rax, [rax+100h]
0x180025b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b44  mov     r12d, 2
0x180025b4a  mov     rcx, rax
0x180025b4d  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180025b53  test    al, al
0x180025b55  mov     bl, 1
0x180025b57  jnz     short loc_180025B5C
0x180025b59  mov     bl, dil
0x180025b5c  test    r12b, 2
0x180025b60  jz      short loc_180025B6D
0x180025b62  lea     rcx, [rsp+1E8h+var_1B8]
0x180025b67  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180025b6d  test    bl, bl
0x180025b6f  jz      short loc_180025BBF
0x180025b71  lea     rcx, [rsp+1E8h+var_170]; this
0x180025b76  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180025b7b  mov     rbx, rax
0x180025b7e  mov     rcx, [r15]
0x180025b81  mov     rax, [rcx]
0x180025b84  lea     rdx, [rsp+1E8h+var_1A0]
0x180025b89  mov     rax, [rax+100h]
0x180025b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b95  mov     r8, rbx
0x180025b98  mov     rdx, rax
0x180025b9b  mov     rcx, rsi
0x180025b9e  call    ??$task_from_exception@JVexception_ptr@std@@@pplx@@YA?AV?$task@J@0@Vexception_ptr@std@@AEBVtask_options@0@@Z; pplx::task_from_exception<long,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)
0x180025ba3  nop
0x180025ba4  lea     rcx, [rsp+1E8h+var_170]; this
0x180025ba9  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180025bae  nop
0x180025baf  mov     rcx, [r14+8]; this
0x180025bb3  test    rcx, rcx
0x180025bb6  jz      short loc_180025BF5
0x180025bb8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025bbd  jmp     short loc_180025BF5
0x180025bbf  mov     [rsi], rdi
0x180025bc2  mov     [rsi+8], rdi
0x180025bc6  mov     rcx, [r14]
0x180025bc9  mov     [rsi], rcx
0x180025bcc  mov     rcx, [r14+8]
0x180025bd0  mov     [rsi+8], rcx
0x180025bd4  mov     [r14], rdi
0x180025bd7  mov     [r14+8], rdi
0x180025bdb  jmp     short loc_180025BF5
0x180025bdd  mov     rax, [rsp+1E8h+var_188]
0x180025be2  mov     rcx, [rax+8]; this
0x180025be6  test    rcx, rcx
0x180025be9  jz      short loc_180025BF0
0x180025beb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025bf0  mov     rsi, [rsp+1E8h+var_1A0]
0x180025bf5  mov     rax, rsi
0x180025bf8  mov     rcx, [rsp+1E8h+var_38]
0x180025c00  xor     rcx, rsp; StackCookie
0x180025c03  call    __security_check_cookie
0x180025c08  mov     rbx, [rsp+1E8h+arg_18]
0x180025c10  add     rsp, 1C0h
0x180025c17  pop     r15
0x180025c19  pop     r14
0x180025c1b  pop     r12
0x180025c1d  pop     rdi
0x180025c1e  pop     rsi
0x180025c1f  retn
```
