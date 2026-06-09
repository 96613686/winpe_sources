# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18000f214`
- end: `0x18000f438`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(unsigned int, unsigned int *, __int64)`
- caller_count: `6`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800047c0`
- `0x180004d78`
- `0x180008564`
- `0x18000dfe0`
- `0x18000ec24`
- `0x18000f440`

## callees

- `0x180002e04`
- `0x1800050e8`
- `0x180005208`
- `0x180005274`
- `0x18000529c`
- `0x1800052c4`
- `0x1800052ec`
- `0x180005314`
- `0x18000555c`
- `0x180005584`
- `0x1800055ac`
- `0x1800055d4`
- `0x1800055fc`
- `0x180005624`
- `0x18000564c`
- `0x180005674`
- `0x18000f214`
- `0x180012010`

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
0x18000f214  mov     [rsp-8+arg_0], rbx
0x18000f219  mov     [rsp-8+arg_8], rdi
0x18000f21e  push    rbp
0x18000f21f  mov     rbp, rsp
0x18000f222  sub     rsp, 50h
0x18000f226  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18000f22d  mov     rdi, rdx
0x18000f230  mov     ebx, ecx
0x18000f232  test    rax, rax
0x18000f235  jz      short loc_18000F24E
0x18000f237  mov     r8, [rdx+10h]
0x18000f23b  mov     rdx, [rdx+8]
0x18000f23f  mov     r9, [rbp+8]
0x18000f243  mov     [rsp+50h+var_30], ecx
0x18000f247  mov     ecx, [rdi]
0x18000f249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f24e  lea     rcx, [rbp+pExceptionObject]; this
0x18000f252  cmp     ebx, 8007000Eh
0x18000f258  jnz     short loc_18000F270
0x18000f25a  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000f25f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f266  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f26a  call    _CxxThrowException_0
0x18000f270  cmp     ebx, 80070005h
0x18000f276  jnz     short loc_18000F291
0x18000f278  mov     r8, rdi
0x18000f27b  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f280  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18000f287  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f28b  call    _CxxThrowException_0
0x18000f291  cmp     ebx, 8001010Eh
0x18000f297  jnz     short loc_18000F2B2
0x18000f299  mov     r8, rdi
0x18000f29c  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f2a1  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18000f2a8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f2ac  call    _CxxThrowException_0
0x18000f2b2  cmp     ebx, 80004001h
0x18000f2b8  jnz     short loc_18000F2D3
0x18000f2ba  mov     r8, rdi
0x18000f2bd  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f2c2  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18000f2c9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f2cd  call    _CxxThrowException_0
0x18000f2d3  cmp     ebx, 80070057h
0x18000f2d9  jnz     short loc_18000F2F4
0x18000f2db  mov     r8, rdi
0x18000f2de  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f2e3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000f2ea  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f2ee  call    _CxxThrowException_0
0x18000f2f4  cmp     ebx, 8000000Bh
0x18000f2fa  jnz     short loc_18000F315
0x18000f2fc  mov     r8, rdi
0x18000f2ff  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f304  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000f30b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f30f  call    _CxxThrowException_0
0x18000f315  cmp     ebx, 80004002h
0x18000f31b  jnz     short loc_18000F336
0x18000f31d  mov     r8, rdi
0x18000f320  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f325  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18000f32c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f330  call    _CxxThrowException_0
0x18000f336  cmp     ebx, 80040111h
0x18000f33c  jnz     short loc_18000F357
0x18000f33e  mov     r8, rdi
0x18000f341  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f346  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18000f34d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f351  call    _CxxThrowException_0
0x18000f357  cmp     ebx, 80040154h
0x18000f35d  jnz     short loc_18000F378
0x18000f35f  mov     r8, rdi
0x18000f362  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f367  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x18000f36e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f372  call    _CxxThrowException_0
0x18000f378  cmp     ebx, 8000000Ch
0x18000f37e  jnz     short loc_18000F399
0x18000f380  mov     r8, rdi
0x18000f383  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f388  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18000f38f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f393  call    _CxxThrowException_0
0x18000f399  cmp     ebx, 8000000Eh
0x18000f39f  jnz     short loc_18000F3BA
0x18000f3a1  mov     r8, rdi
0x18000f3a4  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f3a9  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18000f3b0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f3b4  call    _CxxThrowException_0
0x18000f3ba  cmp     ebx, 8000000Dh
0x18000f3c0  jnz     short loc_18000F3DB
0x18000f3c2  mov     r8, rdi
0x18000f3c5  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f3ca  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x18000f3d1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f3d5  call    _CxxThrowException_0
0x18000f3db  cmp     ebx, 80000018h
0x18000f3e1  jnz     short loc_18000F3FC
0x18000f3e3  mov     r8, rdi
0x18000f3e6  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f3eb  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18000f3f2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f3f6  call    _CxxThrowException_0
0x18000f3fc  cmp     ebx, 800704C7h
0x18000f402  jnz     short loc_18000F41D
0x18000f404  mov     r8, rdi
0x18000f407  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f40c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18000f413  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f417  call    _CxxThrowException_0
0x18000f41d  mov     r9, rdi
0x18000f420  mov     edx, ebx
0x18000f422  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000f427  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18000f42e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f432  call    _CxxThrowException_0
```
