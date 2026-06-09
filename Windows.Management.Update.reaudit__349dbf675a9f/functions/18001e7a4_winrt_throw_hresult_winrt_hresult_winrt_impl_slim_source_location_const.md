# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18001e7a4`
- end: `0x18001e9c8`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `81`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013000`
- `0x180015920`
- `0x180018fc8`
- `0x180019020`
- `0x1800190a0`
- `0x180019118`
- `0x18001cac8`
- `0x18001cb24`
- `0x18001cb80`
- `0x18001d150`
- `0x18001d3c8`
- `0x18001d414`
- `0x18001d460`
- `0x18001d620`
- `0x18001d99c`
- `0x18001dce0`
- `0x18001dd60`
- `0x18001dde0`
- `0x18001de60`
- `0x18001dee0`
- `0x18001df60`
- `0x18001dfe0`
- `0x18001e060`
- `0x18001e0e0`
- `0x18001e150`
- `0x18001e1d0`
- `0x18001e240`
- `0x18001e2b0`
- `0x18001e330`
- `0x18001e3b0`
- `0x18001e430`
- `0x18001e4b0`
- `0x18001e530`
- `0x18001e5b0`
- `0x18001e630`
- `0x18001e6b0`
- `0x18001e730`
- `0x18001f628`
- `0x1800230a0`
- `0x180023118`
- `0x1800232c0`
- `0x180023e90`
- `0x180023f10`
- `0x180023f90`
- `0x180024000`
- `0x180024080`
- `0x1800240f0`
- `0x18002499c`
- `0x180024b50`
- `0x180024bd0`

## callees

- `0x1800035f0`
- `0x180011f80`
- `0x180018abc`
- `0x180018ae4`
- `0x180018b0c`
- `0x180018b34`
- `0x180018b5c`
- `0x180018b84`
- `0x180018dd0`
- `0x180018df8`
- `0x180018e20`
- `0x180018e48`
- `0x180018e70`
- `0x180018e98`
- `0x180018ec0`
- `0x180018ee8`
- `0x18001e7a4`
- `0x18002c010`

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
      winrt::hresult_access_denied::hresult_access_denied(pExceptionObject, a2, a2);
      throw (winrt::hresult_access_denied *)pExceptionObject;
    case 0x8001010E:
      winrt::hresult_wrong_thread::hresult_wrong_thread(pExceptionObject, a2, a2);
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
  winrt::hresult_error::hresult_error(pExceptionObject, a1, a3, a2);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18001e7a4  mov     [rsp-8+arg_0], rbx
0x18001e7a9  mov     [rsp-8+arg_8], rdi
0x18001e7ae  push    rbp
0x18001e7af  mov     rbp, rsp
0x18001e7b2  sub     rsp, 50h
0x18001e7b6  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18001e7bd  mov     rdi, rdx
0x18001e7c0  mov     ebx, ecx
0x18001e7c2  test    rax, rax
0x18001e7c5  jz      short loc_18001E7DE
0x18001e7c7  mov     r8, [rdx+10h]
0x18001e7cb  mov     rdx, [rdx+8]
0x18001e7cf  mov     r9, [rbp+8]
0x18001e7d3  mov     [rsp+50h+var_30], ecx
0x18001e7d7  mov     ecx, [rdi]
0x18001e7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7de  lea     rcx, [rbp+pExceptionObject]; this
0x18001e7e2  cmp     ebx, 8007000Eh
0x18001e7e8  jnz     short loc_18001E800
0x18001e7ea  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001e7ef  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001e7f6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e7fa  call    _CxxThrowException_0
0x18001e800  cmp     ebx, 80070005h
0x18001e806  jnz     short loc_18001E821
0x18001e808  mov     r8, rdi
0x18001e80b  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e810  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18001e817  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e81b  call    _CxxThrowException_0
0x18001e821  cmp     ebx, 8001010Eh
0x18001e827  jnz     short loc_18001E842
0x18001e829  mov     r8, rdi
0x18001e82c  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e831  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18001e838  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e83c  call    _CxxThrowException_0
0x18001e842  cmp     ebx, 80004001h
0x18001e848  jnz     short loc_18001E863
0x18001e84a  mov     r8, rdi
0x18001e84d  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e852  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001e859  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e85d  call    _CxxThrowException_0
0x18001e863  cmp     ebx, 80070057h
0x18001e869  jnz     short loc_18001E884
0x18001e86b  mov     r8, rdi
0x18001e86e  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e873  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001e87a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e87e  call    _CxxThrowException_0
0x18001e884  cmp     ebx, 8000000Bh
0x18001e88a  jnz     short loc_18001E8A5
0x18001e88c  mov     r8, rdi
0x18001e88f  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e894  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001e89b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e89f  call    _CxxThrowException_0
0x18001e8a5  cmp     ebx, 80004002h
0x18001e8ab  jnz     short loc_18001E8C6
0x18001e8ad  mov     r8, rdi
0x18001e8b0  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e8b5  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18001e8bc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e8c0  call    _CxxThrowException_0
0x18001e8c6  cmp     ebx, 80040111h
0x18001e8cc  jnz     short loc_18001E8E7
0x18001e8ce  mov     r8, rdi
0x18001e8d1  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e8d6  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18001e8dd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e8e1  call    _CxxThrowException_0
0x18001e8e7  cmp     ebx, 80040154h
0x18001e8ed  jnz     short loc_18001E908
0x18001e8ef  mov     r8, rdi
0x18001e8f2  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e8f7  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x18001e8fe  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e902  call    _CxxThrowException_0
0x18001e908  cmp     ebx, 8000000Ch
0x18001e90e  jnz     short loc_18001E929
0x18001e910  mov     r8, rdi
0x18001e913  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e918  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18001e91f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e923  call    _CxxThrowException_0
0x18001e929  cmp     ebx, 8000000Eh
0x18001e92f  jnz     short loc_18001E94A
0x18001e931  mov     r8, rdi
0x18001e934  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e939  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18001e940  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e944  call    _CxxThrowException_0
0x18001e94a  cmp     ebx, 8000000Dh
0x18001e950  jnz     short loc_18001E96B
0x18001e952  mov     r8, rdi
0x18001e955  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e95a  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x18001e961  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e965  call    _CxxThrowException_0
0x18001e96b  cmp     ebx, 80000018h
0x18001e971  jnz     short loc_18001E98C
0x18001e973  mov     r8, rdi
0x18001e976  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e97b  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18001e982  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e986  call    _CxxThrowException_0
0x18001e98c  cmp     ebx, 800704C7h
0x18001e992  jnz     short loc_18001E9AD
0x18001e994  mov     r8, rdi
0x18001e997  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e99c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001e9a3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e9a7  call    _CxxThrowException_0
0x18001e9ad  mov     r9, rdi
0x18001e9b0  mov     edx, ebx
0x18001e9b2  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001e9b7  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001e9be  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e9c2  call    _CxxThrowException_0
```
