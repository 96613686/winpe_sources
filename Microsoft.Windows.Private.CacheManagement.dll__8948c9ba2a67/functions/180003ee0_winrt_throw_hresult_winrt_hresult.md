# winrt::throw_hresult(winrt::hresult)

- ea: `0x180003ee0`
- end: `0x1800040d0`
- name: `?throw_hresult@winrt@@YAXUhresult@1@@Z`
- size: `496`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `14`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800040f0`
- `0x180004c30`
- `0x180004e10`
- `0x180005200`
- `0x1800060e0`
- `0x180006750`
- `0x180007190`
- `0x180007330`
- `0x180007410`
- `0x180007c40`
- `0x18000a420`
- `0x18000be70`
- `0x180011aa0`
- `0x180011c00`

## callees

- `0x180003620`
- `0x1800036c0`
- `0x1800036e0`
- `0x180003700`
- `0x180003720`
- `0x180003740`
- `0x180003760`
- `0x180003780`
- `0x1800037a0`
- `0x1800037c0`
- `0x1800037e0`
- `0x180003800`
- `0x180003820`
- `0x180003950`
- `0x180003c60`
- `0x180003ee0`
- `0x180019c0c`
- `0x18001cdf0`

## pseudocode

```c
void __fastcall __noreturn winrt::throw_hresult(unsigned int a1)
{
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  void *retaddr; // [rsp+58h] [rbp+8h]

  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(0, 0, 0, retaddr, a1);
  switch ( a1 )
  {
    case 0x8007000E:
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    case 0x80070005:
      winrt::hresult_access_denied::hresult_access_denied((__int64)pExceptionObject);
      throw (winrt::hresult_access_denied *)pExceptionObject;
    case 0x8001010E:
      winrt::hresult_wrong_thread::hresult_wrong_thread((__int64)pExceptionObject);
      throw (winrt::hresult_wrong_thread *)pExceptionObject;
    case 0x80004001:
      winrt::hresult_not_implemented::hresult_not_implemented(pExceptionObject);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    case 0x80070057:
      winrt::hresult_invalid_argument::hresult_invalid_argument(pExceptionObject);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    case 0x8000000B:
      winrt::hresult_out_of_bounds::hresult_out_of_bounds(pExceptionObject);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    case 0x80004002:
      winrt::hresult_no_interface::hresult_no_interface(pExceptionObject);
      throw (winrt::hresult_no_interface *)pExceptionObject;
    case 0x80040111:
      winrt::hresult_class_not_available::hresult_class_not_available(pExceptionObject);
      throw (winrt::hresult_class_not_available *)pExceptionObject;
    case 0x80040154:
      winrt::hresult_class_not_registered::hresult_class_not_registered(pExceptionObject);
      throw (winrt::hresult_class_not_registered *)pExceptionObject;
    case 0x8000000C:
      winrt::hresult_changed_state::hresult_changed_state(pExceptionObject);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    case 0x8000000E:
      winrt::hresult_illegal_method_call::hresult_illegal_method_call(pExceptionObject);
      throw (winrt::hresult_illegal_method_call *)pExceptionObject;
    case 0x8000000D:
      winrt::hresult_illegal_state_change::hresult_illegal_state_change(pExceptionObject);
      throw (winrt::hresult_illegal_state_change *)pExceptionObject;
    case 0x80000018:
      winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(pExceptionObject);
      throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
    case 0x800704C7:
      winrt::hresult_canceled::hresult_canceled(pExceptionObject);
      throw (winrt::hresult_canceled *)pExceptionObject;
  }
  winrt::hresult_error::hresult_error((__int64)pExceptionObject, a1);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp-8+arg_0], rbx
0x180003ee5  push    rbp
0x180003ee6  mov     rbp, rsp
0x180003ee9  sub     rsp, 50h
0x180003eed  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180003ef4  mov     ebx, ecx
0x180003ef6  test    rax, rax
0x180003ef9  jz      short loc_180003F10
0x180003efb  mov     r9, [rbp+8]
0x180003eff  xor     r8d, r8d
0x180003f02  mov     [rsp+50h+var_30], ecx
0x180003f06  xor     edx, edx
0x180003f08  xor     ecx, ecx
0x180003f0a  call    cs:__guard_dispatch_icall_fptr
0x180003f10  lea     rcx, [rbp+pExceptionObject]; this
0x180003f14  cmp     ebx, 8007000Eh
0x180003f1a  jnz     short loc_180003F32
0x180003f1c  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180003f21  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180003f28  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003f2c  call    _CxxThrowException
0x180003f32  cmp     ebx, 80070005h
0x180003f38  jnz     short loc_180003F50
0x180003f3a  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t)
0x180003f3f  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180003f46  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003f4a  call    _CxxThrowException
0x180003f50  cmp     ebx, 8001010Eh
0x180003f56  jnz     short loc_180003F6E
0x180003f58  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t)
0x180003f5d  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180003f64  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003f68  call    _CxxThrowException
0x180003f6e  cmp     ebx, 80004001h
0x180003f74  jnz     short loc_180003F8C
0x180003f76  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t)
0x180003f7b  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180003f82  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003f86  call    _CxxThrowException
0x180003f8c  cmp     ebx, 80070057h
0x180003f92  jnz     short loc_180003FAA
0x180003f94  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t)
0x180003f99  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180003fa0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003fa4  call    _CxxThrowException
0x180003faa  cmp     ebx, 8000000Bh
0x180003fb0  jnz     short loc_180003FC8
0x180003fb2  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t)
0x180003fb7  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180003fbe  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003fc2  call    _CxxThrowException
0x180003fc8  cmp     ebx, 80004002h
0x180003fce  jnz     short loc_180003FE6
0x180003fd0  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t)
0x180003fd5  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180003fdc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003fe0  call    _CxxThrowException
0x180003fe6  cmp     ebx, 80040111h
0x180003fec  jnz     short loc_180004004
0x180003fee  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t)
0x180003ff3  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180003ffa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003ffe  call    _CxxThrowException
0x180004004  cmp     ebx, 80040154h
0x18000400a  jnz     short loc_180004022
0x18000400c  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t)
0x180004011  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180004018  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000401c  call    _CxxThrowException
0x180004022  cmp     ebx, 8000000Ch
0x180004028  jnz     short loc_180004040
0x18000402a  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t)
0x18000402f  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180004036  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000403a  call    _CxxThrowException
0x180004040  cmp     ebx, 8000000Eh
0x180004046  jnz     short loc_18000405E
0x180004048  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t)
0x18000404d  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180004054  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004058  call    _CxxThrowException
0x18000405e  cmp     ebx, 8000000Dh
0x180004064  jnz     short loc_18000407C
0x180004066  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t)
0x18000406b  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180004072  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004076  call    _CxxThrowException
0x18000407c  cmp     ebx, 80000018h
0x180004082  jnz     short loc_18000409A
0x180004084  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t)
0x180004089  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180004090  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004094  call    _CxxThrowException
0x18000409a  cmp     ebx, 800704C7h
0x1800040a0  jnz     short loc_1800040B8
0x1800040a2  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t)
0x1800040a7  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1800040ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800040b2  call    _CxxThrowException
0x1800040b8  mov     edx, ebx
0x1800040ba  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)
0x1800040bf  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800040c6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800040ca  call    _CxxThrowException
```
