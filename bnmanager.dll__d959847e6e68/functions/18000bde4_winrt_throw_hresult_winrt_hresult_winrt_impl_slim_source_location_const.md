# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18000bde4`
- end: `0x18000c008`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(unsigned int, unsigned int *, __int64)`
- caller_count: `14`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002570`
- `0x1800033c0`
- `0x18000355c`
- `0x180003730`
- `0x1800038cc`
- `0x180003a28`
- `0x180003b84`
- `0x180005854`
- `0x1800062e0`
- `0x180006920`
- `0x1800071ac`
- `0x180007250`
- `0x1800082fc`
- `0x180008364`

## callees

- `0x1800022b4`
- `0x18000490c`
- `0x180004a20`
- `0x180004a48`
- `0x180004a70`
- `0x180004a98`
- `0x180004ac0`
- `0x180004ae8`
- `0x180004e40`
- `0x180004e68`
- `0x180004e90`
- `0x180004eb8`
- `0x180004ee0`
- `0x180004f08`
- `0x180004f30`
- `0x180004f58`
- `0x18000bde4`
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
      winrt::hresult_wrong_thread::hresult_wrong_thread((__int64)pExceptionObject, (__int64)a2, a2);
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
  winrt::hresult_error::hresult_error((__int64)pExceptionObject, a1, a3, a2);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18000bde4  mov     [rsp-8+arg_0], rbx
0x18000bde9  mov     [rsp-8+arg_8], rdi
0x18000bdee  push    rbp
0x18000bdef  mov     rbp, rsp
0x18000bdf2  sub     rsp, 50h
0x18000bdf6  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18000bdfd  mov     rdi, rdx
0x18000be00  mov     ebx, ecx
0x18000be02  test    rax, rax
0x18000be05  jz      short loc_18000BE1E
0x18000be07  mov     r8, [rdx+10h]
0x18000be0b  mov     rdx, [rdx+8]
0x18000be0f  mov     r9, [rbp+8]
0x18000be13  mov     [rsp+50h+var_30], ecx
0x18000be17  mov     ecx, [rdi]
0x18000be19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be1e  lea     rcx, [rbp+pExceptionObject]; this
0x18000be22  cmp     ebx, 8007000Eh
0x18000be28  jnz     short loc_18000BE40
0x18000be2a  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000be2f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000be36  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be3a  call    _CxxThrowException_0
0x18000be40  cmp     ebx, 80070005h
0x18000be46  jnz     short loc_18000BE61
0x18000be48  mov     r8, rdi
0x18000be4b  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000be50  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18000be57  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be5b  call    _CxxThrowException_0
0x18000be61  cmp     ebx, 8001010Eh
0x18000be67  jnz     short loc_18000BE82
0x18000be69  mov     r8, rdi
0x18000be6c  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000be71  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18000be78  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be7c  call    _CxxThrowException_0
0x18000be82  cmp     ebx, 80004001h
0x18000be88  jnz     short loc_18000BEA3
0x18000be8a  mov     r8, rdi
0x18000be8d  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000be92  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18000be99  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be9d  call    _CxxThrowException_0
0x18000bea3  cmp     ebx, 80070057h
0x18000bea9  jnz     short loc_18000BEC4
0x18000beab  mov     r8, rdi
0x18000beae  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000beb3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000beba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bebe  call    _CxxThrowException_0
0x18000bec4  cmp     ebx, 8000000Bh
0x18000beca  jnz     short loc_18000BEE5
0x18000becc  mov     r8, rdi
0x18000becf  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bed4  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000bedb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bedf  call    _CxxThrowException_0
0x18000bee5  cmp     ebx, 80004002h
0x18000beeb  jnz     short loc_18000BF06
0x18000beed  mov     r8, rdi
0x18000bef0  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bef5  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18000befc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bf00  call    _CxxThrowException_0
0x18000bf06  cmp     ebx, 80040111h
0x18000bf0c  jnz     short loc_18000BF27
0x18000bf0e  mov     r8, rdi
0x18000bf11  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bf16  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18000bf1d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bf21  call    _CxxThrowException_0
0x18000bf27  cmp     ebx, 80040154h
0x18000bf2d  jnz     short loc_18000BF48
0x18000bf2f  mov     r8, rdi
0x18000bf32  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bf37  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x18000bf3e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bf42  call    _CxxThrowException_0
0x18000bf48  cmp     ebx, 8000000Ch
0x18000bf4e  jnz     short loc_18000BF69
0x18000bf50  mov     r8, rdi
0x18000bf53  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bf58  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18000bf5f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bf63  call    _CxxThrowException_0
0x18000bf69  cmp     ebx, 8000000Eh
0x18000bf6f  jnz     short loc_18000BF8A
0x18000bf71  mov     r8, rdi
0x18000bf74  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bf79  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18000bf80  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bf84  call    _CxxThrowException_0
0x18000bf8a  cmp     ebx, 8000000Dh
0x18000bf90  jnz     short loc_18000BFAB
0x18000bf92  mov     r8, rdi
0x18000bf95  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bf9a  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x18000bfa1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bfa5  call    _CxxThrowException_0
0x18000bfab  cmp     ebx, 80000018h
0x18000bfb1  jnz     short loc_18000BFCC
0x18000bfb3  mov     r8, rdi
0x18000bfb6  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bfbb  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18000bfc2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bfc6  call    _CxxThrowException_0
0x18000bfcc  cmp     ebx, 800704C7h
0x18000bfd2  jnz     short loc_18000BFED
0x18000bfd4  mov     r8, rdi
0x18000bfd7  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bfdc  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18000bfe3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bfe7  call    _CxxThrowException_0
0x18000bfed  mov     r9, rdi
0x18000bff0  mov     edx, ebx
0x18000bff2  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000bff7  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18000bffe  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c002  call    _CxxThrowException_0
```
