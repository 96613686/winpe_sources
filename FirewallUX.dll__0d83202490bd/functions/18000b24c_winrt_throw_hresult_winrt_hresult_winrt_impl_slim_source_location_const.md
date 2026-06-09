# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18000b24c`
- end: `0x18000b470`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `87`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b478`
- `0x18000bc80`
- `0x18000ca50`
- `0x18000cba4`
- `0x18000ccf8`
- `0x18000ce4c`
- `0x18000cfe4`
- `0x18000d1b0`
- `0x18000d360`
- `0x18000d4d8`
- `0x18000d688`
- `0x18000d800`
- `0x18000d9cc`
- `0x18000e204`
- `0x18000e264`
- `0x18000e2c4`
- `0x18000f3bc`
- `0x18000f46c`
- `0x18000f660`
- `0x18000f708`
- `0x18000f7b0`
- `0x18000f858`
- `0x18000f900`
- `0x18000f9a8`
- `0x18000ff68`
- `0x18000ffac`
- `0x18001006c`
- `0x1800101bc`
- `0x180010464`
- `0x1800104a4`
- `0x1800104e8`
- `0x180011b80`
- `0x1800123e0`
- `0x180012a74`
- `0x180012b2c`
- `0x180012d04`
- `0x180012df8`
- `0x180013128`
- `0x180013188`
- `0x180013214`
- `0x1800132ac`
- `0x180013818`
- `0x180013860`
- `0x1800138a8`
- `0x180013954`
- `0x1800139a4`
- `0x180014058`
- `0x180014980`
- `0x1800179c8`
- `0x180017c70`

## callees

- `0x180002c10`
- `0x180004fd0`
- `0x180005084`
- `0x1800050ac`
- `0x1800050d4`
- `0x1800050fc`
- `0x180005124`
- `0x180005188`
- `0x1800053d0`
- `0x1800053f8`
- `0x180005420`
- `0x180005448`
- `0x180005470`
- `0x180005498`
- `0x1800054c0`
- `0x1800054e8`
- `0x18000b24c`
- `0x18002d010`

## pseudocode

```c
void __fastcall __noreturn winrt::throw_hresult(unsigned int a1, unsigned int *a2, __int64 a3)
{
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  void *retaddr; // [rsp+58h] [rbp+8h]

  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(*a2, *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2), retaddr, a1);
  switch ( a1 )
  {
    case 0x8007000E:
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    case 0x80070005:
      winrt::hresult_access_denied::hresult_access_denied((__int64)pExceptionObject, (__int64)a2, (__int64)a2);
      throw (winrt::hresult_access_denied *)pExceptionObject;
    case 0x8001010E:
      winrt::hresult_wrong_thread::hresult_wrong_thread((__int64)pExceptionObject, (__int64)a2, (__int64)a2);
      throw (winrt::hresult_wrong_thread *)pExceptionObject;
    case 0x80004001:
      winrt::hresult_not_implemented::hresult_not_implemented(pExceptionObject, a2, a2);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    case 0x80070057:
      winrt::hresult_invalid_argument::hresult_invalid_argument(pExceptionObject, a2, a2);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    case 0x8000000B:
      winrt::hresult_out_of_bounds::hresult_out_of_bounds(pExceptionObject, a2, a2);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    case 0x80004002:
      winrt::hresult_no_interface::hresult_no_interface(pExceptionObject, a2, a2);
      throw (winrt::hresult_no_interface *)pExceptionObject;
    case 0x80040111:
      winrt::hresult_class_not_available::hresult_class_not_available(pExceptionObject, a2, a2);
      throw (winrt::hresult_class_not_available *)pExceptionObject;
    case 0x80040154:
      winrt::hresult_class_not_registered::hresult_class_not_registered(pExceptionObject, a2, a2);
      throw (winrt::hresult_class_not_registered *)pExceptionObject;
    case 0x8000000C:
      winrt::hresult_changed_state::hresult_changed_state(pExceptionObject, a2, a2);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    case 0x8000000E:
      winrt::hresult_illegal_method_call::hresult_illegal_method_call(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_method_call *)pExceptionObject;
    case 0x8000000D:
      winrt::hresult_illegal_state_change::hresult_illegal_state_change(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_state_change *)pExceptionObject;
    case 0x80000018:
      winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
    case 0x800704C7:
      winrt::hresult_canceled::hresult_canceled(pExceptionObject, a2, a2);
      throw (winrt::hresult_canceled *)pExceptionObject;
  }
  winrt::hresult_error::hresult_error((__int64)pExceptionObject, a1, a3, (__int64)a2);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18000b24c  mov     [rsp-8+arg_0], rbx
0x18000b251  mov     [rsp-8+arg_8], rdi
0x18000b256  push    rbp
0x18000b257  mov     rbp, rsp
0x18000b25a  sub     rsp, 50h
0x18000b25e  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18000b265  mov     rdi, rdx
0x18000b268  mov     ebx, ecx
0x18000b26a  test    rax, rax
0x18000b26d  jz      short loc_18000B286
0x18000b26f  mov     r8, [rdx+10h]
0x18000b273  mov     rdx, [rdx+8]
0x18000b277  mov     r9, [rbp+8]
0x18000b27b  mov     [rsp+50h+var_30], ecx
0x18000b27f  mov     ecx, [rdi]
0x18000b281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b286  lea     rcx, [rbp+pExceptionObject]; this
0x18000b28a  cmp     ebx, 8007000Eh
0x18000b290  jnz     short loc_18000B2A8
0x18000b292  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000b297  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000b29e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b2a2  call    _CxxThrowException_0
0x18000b2a8  cmp     ebx, 80070005h
0x18000b2ae  jnz     short loc_18000B2C9
0x18000b2b0  mov     r8, rdi
0x18000b2b3  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b2b8  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18000b2bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b2c3  call    _CxxThrowException_0
0x18000b2c9  cmp     ebx, 8001010Eh
0x18000b2cf  jnz     short loc_18000B2EA
0x18000b2d1  mov     r8, rdi
0x18000b2d4  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b2d9  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18000b2e0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b2e4  call    _CxxThrowException_0
0x18000b2ea  cmp     ebx, 80004001h
0x18000b2f0  jnz     short loc_18000B30B
0x18000b2f2  mov     r8, rdi
0x18000b2f5  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b2fa  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18000b301  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b305  call    _CxxThrowException_0
0x18000b30b  cmp     ebx, 80070057h
0x18000b311  jnz     short loc_18000B32C
0x18000b313  mov     r8, rdi
0x18000b316  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b31b  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000b322  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b326  call    _CxxThrowException_0
0x18000b32c  cmp     ebx, 8000000Bh
0x18000b332  jnz     short loc_18000B34D
0x18000b334  mov     r8, rdi
0x18000b337  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b33c  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000b343  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b347  call    _CxxThrowException_0
0x18000b34d  cmp     ebx, 80004002h
0x18000b353  jnz     short loc_18000B36E
0x18000b355  mov     r8, rdi
0x18000b358  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b35d  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18000b364  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b368  call    _CxxThrowException_0
0x18000b36e  cmp     ebx, 80040111h
0x18000b374  jnz     short loc_18000B38F
0x18000b376  mov     r8, rdi
0x18000b379  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b37e  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18000b385  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b389  call    _CxxThrowException_0
0x18000b38f  cmp     ebx, 80040154h
0x18000b395  jnz     short loc_18000B3B0
0x18000b397  mov     r8, rdi
0x18000b39a  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b39f  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x18000b3a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b3aa  call    _CxxThrowException_0
0x18000b3b0  cmp     ebx, 8000000Ch
0x18000b3b6  jnz     short loc_18000B3D1
0x18000b3b8  mov     r8, rdi
0x18000b3bb  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b3c0  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18000b3c7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b3cb  call    _CxxThrowException_0
0x18000b3d1  cmp     ebx, 8000000Eh
0x18000b3d7  jnz     short loc_18000B3F2
0x18000b3d9  mov     r8, rdi
0x18000b3dc  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b3e1  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18000b3e8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b3ec  call    _CxxThrowException_0
0x18000b3f2  cmp     ebx, 8000000Dh
0x18000b3f8  jnz     short loc_18000B413
0x18000b3fa  mov     r8, rdi
0x18000b3fd  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b402  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x18000b409  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b40d  call    _CxxThrowException_0
0x18000b413  cmp     ebx, 80000018h
0x18000b419  jnz     short loc_18000B434
0x18000b41b  mov     r8, rdi
0x18000b41e  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b423  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18000b42a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b42e  call    _CxxThrowException_0
0x18000b434  cmp     ebx, 800704C7h
0x18000b43a  jnz     short loc_18000B455
0x18000b43c  mov     r8, rdi
0x18000b43f  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b444  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18000b44b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b44f  call    _CxxThrowException_0
0x18000b455  mov     r9, rdi
0x18000b458  mov     edx, ebx
0x18000b45a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000b45f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18000b466  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b46a  call    _CxxThrowException_0
```
