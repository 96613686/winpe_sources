# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18001a3fc`
- end: `0x18001a620`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: ``
- caller_count: `30`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f70`
- `0x1800134d0`
- `0x1800135f4`
- `0x180014980`
- `0x180015ae4`
- `0x180016504`
- `0x180017edc`
- `0x1800199b4`
- `0x18001a628`
- `0x18001ba70`
- `0x18001bb50`
- `0x18001bcfc`
- `0x18001bea8`
- `0x18001c250`
- `0x18001c3bc`
- `0x18001c428`
- `0x18001c8f4`
- `0x18001c9a8`
- `0x18001ca5c`
- `0x18001caf8`
- `0x18001cbb4`
- `0x18001cc70`
- `0x18001cd1c`
- `0x18001cdf4`
- `0x18001cec4`
- `0x18001d184`
- `0x18001d3d8`
- `0x18001d4f4`
- `0x18001d5b0`
- `0x18001d680`

## callees

- `0x1800046b8`
- `0x180013960`
- `0x1800139d0`
- `0x180013a3c`
- `0x180013aa8`
- `0x180013ad0`
- `0x180013af8`
- `0x180013b20`
- `0x180013d9c`
- `0x180013dc4`
- `0x180013dec`
- `0x180013e14`
- `0x180013e80`
- `0x180013ea8`
- `0x180013f14`
- `0x180013f3c`
- `0x18001a3fc`
- `0x180021010`

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
0x18001a3fc  mov     [rsp-8+arg_0], rbx
0x18001a401  mov     [rsp-8+arg_8], rdi
0x18001a406  push    rbp
0x18001a407  mov     rbp, rsp
0x18001a40a  sub     rsp, 50h
0x18001a40e  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18001a415  mov     rdi, rdx
0x18001a418  mov     ebx, ecx
0x18001a41a  test    rax, rax
0x18001a41d  jz      short loc_18001A436
0x18001a41f  mov     r8, [rdx+10h]
0x18001a423  mov     rdx, [rdx+8]
0x18001a427  mov     r9, [rbp+8]
0x18001a42b  mov     [rsp+50h+var_30], ecx
0x18001a42f  mov     ecx, [rdi]
0x18001a431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a436  lea     rcx, [rbp+pExceptionObject]; this
0x18001a43a  cmp     ebx, 8007000Eh
0x18001a440  jnz     short loc_18001A458
0x18001a442  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001a447  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a44e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a452  call    _CxxThrowException_0
0x18001a458  cmp     ebx, 80070005h
0x18001a45e  jnz     short loc_18001A479
0x18001a460  mov     r8, rdi
0x18001a463  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a468  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18001a46f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a473  call    _CxxThrowException_0
0x18001a479  cmp     ebx, 8001010Eh
0x18001a47f  jnz     short loc_18001A49A
0x18001a481  mov     r8, rdi
0x18001a484  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a489  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18001a490  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a494  call    _CxxThrowException_0
0x18001a49a  cmp     ebx, 80004001h
0x18001a4a0  jnz     short loc_18001A4BB
0x18001a4a2  mov     r8, rdi
0x18001a4a5  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a4aa  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001a4b1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a4b5  call    _CxxThrowException_0
0x18001a4bb  cmp     ebx, 80070057h
0x18001a4c1  jnz     short loc_18001A4DC
0x18001a4c3  mov     r8, rdi
0x18001a4c6  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a4cb  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001a4d2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a4d6  call    _CxxThrowException_0
0x18001a4dc  cmp     ebx, 8000000Bh
0x18001a4e2  jnz     short loc_18001A4FD
0x18001a4e4  mov     r8, rdi
0x18001a4e7  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a4ec  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001a4f3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a4f7  call    _CxxThrowException_0
0x18001a4fd  cmp     ebx, 80004002h
0x18001a503  jnz     short loc_18001A51E
0x18001a505  mov     r8, rdi
0x18001a508  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a50d  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18001a514  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a518  call    _CxxThrowException_0
0x18001a51e  cmp     ebx, 80040111h
0x18001a524  jnz     short loc_18001A53F
0x18001a526  mov     r8, rdi
0x18001a529  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a52e  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18001a535  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a539  call    _CxxThrowException_0
0x18001a53f  cmp     ebx, 80040154h
0x18001a545  jnz     short loc_18001A560
0x18001a547  mov     r8, rdi
0x18001a54a  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a54f  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x18001a556  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a55a  call    _CxxThrowException_0
0x18001a560  cmp     ebx, 8000000Ch
0x18001a566  jnz     short loc_18001A581
0x18001a568  mov     r8, rdi
0x18001a56b  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a570  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18001a577  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a57b  call    _CxxThrowException_0
0x18001a581  cmp     ebx, 8000000Eh
0x18001a587  jnz     short loc_18001A5A2
0x18001a589  mov     r8, rdi
0x18001a58c  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a591  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18001a598  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a59c  call    _CxxThrowException_0
0x18001a5a2  cmp     ebx, 8000000Dh
0x18001a5a8  jnz     short loc_18001A5C3
0x18001a5aa  mov     r8, rdi
0x18001a5ad  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a5b2  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x18001a5b9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a5bd  call    _CxxThrowException_0
0x18001a5c3  cmp     ebx, 80000018h
0x18001a5c9  jnz     short loc_18001A5E4
0x18001a5cb  mov     r8, rdi
0x18001a5ce  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a5d3  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18001a5da  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a5de  call    _CxxThrowException_0
0x18001a5e4  cmp     ebx, 800704C7h
0x18001a5ea  jnz     short loc_18001A605
0x18001a5ec  mov     r8, rdi
0x18001a5ef  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a5f4  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001a5fb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a5ff  call    _CxxThrowException_0
0x18001a605  mov     r9, rdi
0x18001a608  mov     edx, ebx
0x18001a60a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001a60f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001a616  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a61a  call    _CxxThrowException_0
```
