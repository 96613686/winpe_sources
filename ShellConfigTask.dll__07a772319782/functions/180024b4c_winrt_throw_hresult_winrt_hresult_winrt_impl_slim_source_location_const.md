# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x180024b4c`
- end: `0x180024d70`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `44`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d400`
- `0x18000d450`
- `0x18000d4b0`
- `0x18000d510`
- `0x18000d570`
- `0x18000fd20`
- `0x18000fee0`
- `0x18001008c`
- `0x18001023c`
- `0x180010524`
- `0x1800106d4`
- `0x180010870`
- `0x180011114`
- `0x180011384`
- `0x1800114cc`
- `0x180011c78`
- `0x180011cd8`
- `0x180011d38`
- `0x180011d98`
- `0x180011df8`
- `0x180011e58`
- `0x180011eb8`
- `0x180011f18`
- `0x180012d1c`
- `0x180012e0c`
- `0x180014efc`
- `0x180014f9c`
- `0x180015130`
- `0x18001a51c`
- `0x18001a654`
- `0x18001ac8c`
- `0x18001c1b0`
- `0x18001c244`
- `0x18001c550`
- `0x18001c81c`
- `0x18001cb74`
- `0x18001ce58`
- `0x18001d388`
- `0x18001d63c`
- `0x18001d6d0`
- `0x18001d768`
- `0x180022f08`
- `0x180023024`
- `0x180024d78`

## callees

- `0x180002fa4`
- `0x180013030`
- `0x180013118`
- `0x180013184`
- `0x1800131ac`
- `0x1800131d4`
- `0x1800131fc`
- `0x180013224`
- `0x18001346c`
- `0x180013494`
- `0x1800134bc`
- `0x1800134e4`
- `0x18001350c`
- `0x180013534`
- `0x18001355c`
- `0x180013584`
- `0x180024b4c`
- `0x180033010`

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
0x180024b4c  mov     [rsp-8+arg_0], rbx
0x180024b51  mov     [rsp-8+arg_8], rdi
0x180024b56  push    rbp
0x180024b57  mov     rbp, rsp
0x180024b5a  sub     rsp, 50h
0x180024b5e  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180024b65  mov     rdi, rdx
0x180024b68  mov     ebx, ecx
0x180024b6a  test    rax, rax
0x180024b6d  jz      short loc_180024B86
0x180024b6f  mov     r8, [rdx+10h]
0x180024b73  mov     rdx, [rdx+8]
0x180024b77  mov     r9, [rbp+8]
0x180024b7b  mov     [rsp+50h+var_30], ecx
0x180024b7f  mov     ecx, [rdi]
0x180024b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b86  lea     rcx, [rbp+pExceptionObject]; this
0x180024b8a  cmp     ebx, 8007000Eh
0x180024b90  jnz     short loc_180024BA8
0x180024b92  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180024b97  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180024b9e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024ba2  call    _CxxThrowException_0
0x180024ba8  cmp     ebx, 80070005h
0x180024bae  jnz     short loc_180024BC9
0x180024bb0  mov     r8, rdi
0x180024bb3  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024bb8  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180024bbf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024bc3  call    _CxxThrowException_0
0x180024bc9  cmp     ebx, 8001010Eh
0x180024bcf  jnz     short loc_180024BEA
0x180024bd1  mov     r8, rdi
0x180024bd4  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024bd9  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180024be0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024be4  call    _CxxThrowException_0
0x180024bea  cmp     ebx, 80004001h
0x180024bf0  jnz     short loc_180024C0B
0x180024bf2  mov     r8, rdi
0x180024bf5  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024bfa  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180024c01  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024c05  call    _CxxThrowException_0
0x180024c0b  cmp     ebx, 80070057h
0x180024c11  jnz     short loc_180024C2C
0x180024c13  mov     r8, rdi
0x180024c16  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024c1b  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180024c22  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024c26  call    _CxxThrowException_0
0x180024c2c  cmp     ebx, 8000000Bh
0x180024c32  jnz     short loc_180024C4D
0x180024c34  mov     r8, rdi
0x180024c37  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024c3c  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180024c43  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024c47  call    _CxxThrowException_0
0x180024c4d  cmp     ebx, 80004002h
0x180024c53  jnz     short loc_180024C6E
0x180024c55  mov     r8, rdi
0x180024c58  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024c5d  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180024c64  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024c68  call    _CxxThrowException_0
0x180024c6e  cmp     ebx, 80040111h
0x180024c74  jnz     short loc_180024C8F
0x180024c76  mov     r8, rdi
0x180024c79  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024c7e  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180024c85  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024c89  call    _CxxThrowException_0
0x180024c8f  cmp     ebx, 80040154h
0x180024c95  jnz     short loc_180024CB0
0x180024c97  mov     r8, rdi
0x180024c9a  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024c9f  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180024ca6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024caa  call    _CxxThrowException_0
0x180024cb0  cmp     ebx, 8000000Ch
0x180024cb6  jnz     short loc_180024CD1
0x180024cb8  mov     r8, rdi
0x180024cbb  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024cc0  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180024cc7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024ccb  call    _CxxThrowException_0
0x180024cd1  cmp     ebx, 8000000Eh
0x180024cd7  jnz     short loc_180024CF2
0x180024cd9  mov     r8, rdi
0x180024cdc  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024ce1  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180024ce8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024cec  call    _CxxThrowException_0
0x180024cf2  cmp     ebx, 8000000Dh
0x180024cf8  jnz     short loc_180024D13
0x180024cfa  mov     r8, rdi
0x180024cfd  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024d02  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180024d09  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024d0d  call    _CxxThrowException_0
0x180024d13  cmp     ebx, 80000018h
0x180024d19  jnz     short loc_180024D34
0x180024d1b  mov     r8, rdi
0x180024d1e  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024d23  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180024d2a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024d2e  call    _CxxThrowException_0
0x180024d34  cmp     ebx, 800704C7h
0x180024d3a  jnz     short loc_180024D55
0x180024d3c  mov     r8, rdi
0x180024d3f  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024d44  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180024d4b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024d4f  call    _CxxThrowException_0
0x180024d55  mov     r9, rdi
0x180024d58  mov     edx, ebx
0x180024d5a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180024d5f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180024d66  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024d6a  call    _CxxThrowException_0
```
