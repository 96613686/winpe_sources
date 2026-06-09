# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x180009c90`
- end: `0x180009eb4`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b18`
- `0x180008030`
- `0x180009ebc`

## callees

- `0x180001fea`
- `0x180005f28`
- `0x180006040`
- `0x1800060ac`
- `0x1800060d4`
- `0x1800060fc`
- `0x180006124`
- `0x18000614c`
- `0x18000640c`
- `0x180006478`
- `0x1800064a0`
- `0x1800064c8`
- `0x1800064f0`
- `0x180006518`
- `0x180006540`
- `0x180006568`
- `0x180009c90`
- `0x18000d010`

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
0x180009c90  mov     [rsp-8+arg_0], rbx
0x180009c95  mov     [rsp-8+arg_8], rdi
0x180009c9a  push    rbp
0x180009c9b  mov     rbp, rsp
0x180009c9e  sub     rsp, 50h
0x180009ca2  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180009ca9  mov     rdi, rdx
0x180009cac  mov     ebx, ecx
0x180009cae  test    rax, rax
0x180009cb1  jz      short loc_180009CCA
0x180009cb3  mov     r8, [rdx+10h]
0x180009cb7  mov     rdx, [rdx+8]
0x180009cbb  mov     r9, [rbp+8]
0x180009cbf  mov     [rsp+50h+var_30], ecx
0x180009cc3  mov     ecx, [rdi]
0x180009cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cca  lea     rcx, [rbp+pExceptionObject]; this
0x180009cce  cmp     ebx, 8007000Eh
0x180009cd4  jnz     short loc_180009CEC
0x180009cd6  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180009cdb  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180009ce2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009ce6  call    _CxxThrowException_0
0x180009cec  cmp     ebx, 80070005h
0x180009cf2  jnz     short loc_180009D0D
0x180009cf4  mov     r8, rdi
0x180009cf7  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009cfc  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180009d03  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009d07  call    _CxxThrowException_0
0x180009d0d  cmp     ebx, 8001010Eh
0x180009d13  jnz     short loc_180009D2E
0x180009d15  mov     r8, rdi
0x180009d18  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009d1d  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180009d24  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009d28  call    _CxxThrowException_0
0x180009d2e  cmp     ebx, 80004001h
0x180009d34  jnz     short loc_180009D4F
0x180009d36  mov     r8, rdi
0x180009d39  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009d3e  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180009d45  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009d49  call    _CxxThrowException_0
0x180009d4f  cmp     ebx, 80070057h
0x180009d55  jnz     short loc_180009D70
0x180009d57  mov     r8, rdi
0x180009d5a  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009d5f  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180009d66  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009d6a  call    _CxxThrowException_0
0x180009d70  cmp     ebx, 8000000Bh
0x180009d76  jnz     short loc_180009D91
0x180009d78  mov     r8, rdi
0x180009d7b  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009d80  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180009d87  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009d8b  call    _CxxThrowException_0
0x180009d91  cmp     ebx, 80004002h
0x180009d97  jnz     short loc_180009DB2
0x180009d99  mov     r8, rdi
0x180009d9c  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009da1  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180009da8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009dac  call    _CxxThrowException_0
0x180009db2  cmp     ebx, 80040111h
0x180009db8  jnz     short loc_180009DD3
0x180009dba  mov     r8, rdi
0x180009dbd  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009dc2  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180009dc9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009dcd  call    _CxxThrowException_0
0x180009dd3  cmp     ebx, 80040154h
0x180009dd9  jnz     short loc_180009DF4
0x180009ddb  mov     r8, rdi
0x180009dde  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009de3  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180009dea  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009dee  call    _CxxThrowException_0
0x180009df4  cmp     ebx, 8000000Ch
0x180009dfa  jnz     short loc_180009E15
0x180009dfc  mov     r8, rdi
0x180009dff  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009e04  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180009e0b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009e0f  call    _CxxThrowException_0
0x180009e15  cmp     ebx, 8000000Eh
0x180009e1b  jnz     short loc_180009E36
0x180009e1d  mov     r8, rdi
0x180009e20  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009e25  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180009e2c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009e30  call    _CxxThrowException_0
0x180009e36  cmp     ebx, 8000000Dh
0x180009e3c  jnz     short loc_180009E57
0x180009e3e  mov     r8, rdi
0x180009e41  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009e46  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180009e4d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009e51  call    _CxxThrowException_0
0x180009e57  cmp     ebx, 80000018h
0x180009e5d  jnz     short loc_180009E78
0x180009e5f  mov     r8, rdi
0x180009e62  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009e67  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180009e6e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009e72  call    _CxxThrowException_0
0x180009e78  cmp     ebx, 800704C7h
0x180009e7e  jnz     short loc_180009E99
0x180009e80  mov     r8, rdi
0x180009e83  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009e88  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180009e8f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009e93  call    _CxxThrowException_0
0x180009e99  mov     r9, rdi
0x180009e9c  mov     edx, ebx
0x180009e9e  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009ea3  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180009eaa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009eae  call    _CxxThrowException_0
```
