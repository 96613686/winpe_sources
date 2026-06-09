# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x14000b0a8`
- end: `0x14000b2cc`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(unsigned int, unsigned int *, __int64)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400093c0`
- `0x1400098ec`
- `0x14000b410`

## callees

- `0x14000224c`
- `0x140009dd0`
- `0x140009eac`
- `0x140009ed4`
- `0x140009efc`
- `0x140009f24`
- `0x140009f4c`
- `0x140009f74`
- `0x14000a244`
- `0x14000a26c`
- `0x14000a294`
- `0x14000a2bc`
- `0x14000a2e4`
- `0x14000a30c`
- `0x14000a334`
- `0x14000a35c`
- `0x14000b0a8`
- `0x14000c010`

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
0x14000b0a8  mov     [rsp-8+arg_0], rbx
0x14000b0ad  mov     [rsp-8+arg_8], rdi
0x14000b0b2  push    rbp
0x14000b0b3  mov     rbp, rsp
0x14000b0b6  sub     rsp, 50h
0x14000b0ba  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x14000b0c1  mov     rdi, rdx
0x14000b0c4  mov     ebx, ecx
0x14000b0c6  test    rax, rax
0x14000b0c9  jz      short loc_14000B0E2
0x14000b0cb  mov     r8, [rdx+10h]
0x14000b0cf  mov     rdx, [rdx+8]
0x14000b0d3  mov     r9, [rbp+8]
0x14000b0d7  mov     [rsp+50h+var_30], ecx
0x14000b0db  mov     ecx, [rdi]
0x14000b0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0e2  lea     rcx, [rbp+pExceptionObject]; this
0x14000b0e6  cmp     ebx, 8007000Eh
0x14000b0ec  jnz     short loc_14000B104
0x14000b0ee  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x14000b0f3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000b0fa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b0fe  call    _CxxThrowException_0
0x14000b104  cmp     ebx, 80070005h
0x14000b10a  jnz     short loc_14000B125
0x14000b10c  mov     r8, rdi
0x14000b10f  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b114  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x14000b11b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b11f  call    _CxxThrowException_0
0x14000b125  cmp     ebx, 8001010Eh
0x14000b12b  jnz     short loc_14000B146
0x14000b12d  mov     r8, rdi
0x14000b130  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b135  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x14000b13c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b140  call    _CxxThrowException_0
0x14000b146  cmp     ebx, 80004001h
0x14000b14c  jnz     short loc_14000B167
0x14000b14e  mov     r8, rdi
0x14000b151  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b156  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x14000b15d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b161  call    _CxxThrowException_0
0x14000b167  cmp     ebx, 80070057h
0x14000b16d  jnz     short loc_14000B188
0x14000b16f  mov     r8, rdi
0x14000b172  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b177  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x14000b17e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b182  call    _CxxThrowException_0
0x14000b188  cmp     ebx, 8000000Bh
0x14000b18e  jnz     short loc_14000B1A9
0x14000b190  mov     r8, rdi
0x14000b193  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b198  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x14000b19f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b1a3  call    _CxxThrowException_0
0x14000b1a9  cmp     ebx, 80004002h
0x14000b1af  jnz     short loc_14000B1CA
0x14000b1b1  mov     r8, rdi
0x14000b1b4  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b1b9  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x14000b1c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b1c4  call    _CxxThrowException_0
0x14000b1ca  cmp     ebx, 80040111h
0x14000b1d0  jnz     short loc_14000B1EB
0x14000b1d2  mov     r8, rdi
0x14000b1d5  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b1da  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x14000b1e1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b1e5  call    _CxxThrowException_0
0x14000b1eb  cmp     ebx, 80040154h
0x14000b1f1  jnz     short loc_14000B20C
0x14000b1f3  mov     r8, rdi
0x14000b1f6  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b1fb  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x14000b202  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b206  call    _CxxThrowException_0
0x14000b20c  cmp     ebx, 8000000Ch
0x14000b212  jnz     short loc_14000B22D
0x14000b214  mov     r8, rdi
0x14000b217  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b21c  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x14000b223  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b227  call    _CxxThrowException_0
0x14000b22d  cmp     ebx, 8000000Eh
0x14000b233  jnz     short loc_14000B24E
0x14000b235  mov     r8, rdi
0x14000b238  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b23d  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x14000b244  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b248  call    _CxxThrowException_0
0x14000b24e  cmp     ebx, 8000000Dh
0x14000b254  jnz     short loc_14000B26F
0x14000b256  mov     r8, rdi
0x14000b259  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b25e  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x14000b265  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b269  call    _CxxThrowException_0
0x14000b26f  cmp     ebx, 80000018h
0x14000b275  jnz     short loc_14000B290
0x14000b277  mov     r8, rdi
0x14000b27a  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b27f  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x14000b286  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b28a  call    _CxxThrowException_0
0x14000b290  cmp     ebx, 800704C7h
0x14000b296  jnz     short loc_14000B2B1
0x14000b298  mov     r8, rdi
0x14000b29b  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b2a0  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x14000b2a7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b2ab  call    _CxxThrowException_0
0x14000b2b1  mov     r9, rdi
0x14000b2b4  mov     edx, ebx
0x14000b2b6  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000b2bb  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x14000b2c2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000b2c6  call    _CxxThrowException_0
```
