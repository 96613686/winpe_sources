# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x180011a4c`
- end: `0x180011c70`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: ``
- caller_count: `15`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b10c`
- `0x18000b8fc`
- `0x18000bafc`
- `0x18000c050`
- `0x18000c140`
- `0x18000c264`
- `0x18000c354`
- `0x18000d70c`
- `0x18000e950`
- `0x18000f7f4`
- `0x18000fac0`
- `0x18000fe40`
- `0x18000feac`
- `0x180011044`
- `0x180011c78`

## callees

- `0x180003a50`
- `0x18000c78c`
- `0x18000c868`
- `0x18000c8d4`
- `0x18000c8fc`
- `0x18000c924`
- `0x18000c94c`
- `0x18000c974`
- `0x18000cbbc`
- `0x18000cc28`
- `0x18000cc50`
- `0x18000cc78`
- `0x18000cce4`
- `0x18000cd0c`
- `0x18000cd78`
- `0x18000cda0`
- `0x180011a4c`
- `0x180013010`

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
0x180011a4c  mov     [rsp-8+arg_0], rbx
0x180011a51  mov     [rsp-8+arg_8], rdi
0x180011a56  push    rbp
0x180011a57  mov     rbp, rsp
0x180011a5a  sub     rsp, 50h
0x180011a5e  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180011a65  mov     rdi, rdx
0x180011a68  mov     ebx, ecx
0x180011a6a  test    rax, rax
0x180011a6d  jz      short loc_180011A86
0x180011a6f  mov     r8, [rdx+10h]
0x180011a73  mov     rdx, [rdx+8]
0x180011a77  mov     r9, [rbp+8]
0x180011a7b  mov     [rsp+50h+var_30], ecx
0x180011a7f  mov     ecx, [rdi]
0x180011a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a86  lea     rcx, [rbp+pExceptionObject]; this
0x180011a8a  cmp     ebx, 8007000Eh
0x180011a90  jnz     short loc_180011AA8
0x180011a92  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180011a97  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180011a9e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011aa2  call    _CxxThrowException_0
0x180011aa8  cmp     ebx, 80070005h
0x180011aae  jnz     short loc_180011AC9
0x180011ab0  mov     r8, rdi
0x180011ab3  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011ab8  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180011abf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011ac3  call    _CxxThrowException_0
0x180011ac9  cmp     ebx, 8001010Eh
0x180011acf  jnz     short loc_180011AEA
0x180011ad1  mov     r8, rdi
0x180011ad4  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011ad9  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180011ae0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011ae4  call    _CxxThrowException_0
0x180011aea  cmp     ebx, 80004001h
0x180011af0  jnz     short loc_180011B0B
0x180011af2  mov     r8, rdi
0x180011af5  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011afa  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180011b01  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011b05  call    _CxxThrowException_0
0x180011b0b  cmp     ebx, 80070057h
0x180011b11  jnz     short loc_180011B2C
0x180011b13  mov     r8, rdi
0x180011b16  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011b1b  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180011b22  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011b26  call    _CxxThrowException_0
0x180011b2c  cmp     ebx, 8000000Bh
0x180011b32  jnz     short loc_180011B4D
0x180011b34  mov     r8, rdi
0x180011b37  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011b3c  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180011b43  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011b47  call    _CxxThrowException_0
0x180011b4d  cmp     ebx, 80004002h
0x180011b53  jnz     short loc_180011B6E
0x180011b55  mov     r8, rdi
0x180011b58  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011b5d  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180011b64  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011b68  call    _CxxThrowException_0
0x180011b6e  cmp     ebx, 80040111h
0x180011b74  jnz     short loc_180011B8F
0x180011b76  mov     r8, rdi
0x180011b79  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011b7e  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180011b85  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011b89  call    _CxxThrowException_0
0x180011b8f  cmp     ebx, 80040154h
0x180011b95  jnz     short loc_180011BB0
0x180011b97  mov     r8, rdi
0x180011b9a  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011b9f  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180011ba6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011baa  call    _CxxThrowException_0
0x180011bb0  cmp     ebx, 8000000Ch
0x180011bb6  jnz     short loc_180011BD1
0x180011bb8  mov     r8, rdi
0x180011bbb  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011bc0  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180011bc7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011bcb  call    _CxxThrowException_0
0x180011bd1  cmp     ebx, 8000000Eh
0x180011bd7  jnz     short loc_180011BF2
0x180011bd9  mov     r8, rdi
0x180011bdc  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011be1  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180011be8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011bec  call    _CxxThrowException_0
0x180011bf2  cmp     ebx, 8000000Dh
0x180011bf8  jnz     short loc_180011C13
0x180011bfa  mov     r8, rdi
0x180011bfd  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011c02  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180011c09  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011c0d  call    _CxxThrowException_0
0x180011c13  cmp     ebx, 80000018h
0x180011c19  jnz     short loc_180011C34
0x180011c1b  mov     r8, rdi
0x180011c1e  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011c23  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180011c2a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011c2e  call    _CxxThrowException_0
0x180011c34  cmp     ebx, 800704C7h
0x180011c3a  jnz     short loc_180011C55
0x180011c3c  mov     r8, rdi
0x180011c3f  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011c44  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180011c4b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011c4f  call    _CxxThrowException_0
0x180011c55  mov     r9, rdi
0x180011c58  mov     edx, ebx
0x180011c5a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180011c5f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180011c66  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011c6a  call    _CxxThrowException_0
```
