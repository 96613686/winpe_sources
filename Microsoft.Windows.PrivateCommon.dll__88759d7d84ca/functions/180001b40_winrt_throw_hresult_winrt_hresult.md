# winrt::throw_hresult(winrt::hresult)

- ea: `0x180001b40`
- end: `0x180001d30`
- name: `?throw_hresult@winrt@@YAXUhresult@1@@Z`
- size: `496`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d90`
- `0x180005d90`
- `0x180006630`

## callees

- `0x180001160`
- `0x180001530`
- `0x180001960`
- `0x1800019c0`
- `0x1800019e0`
- `0x180001a00`
- `0x180001a20`
- `0x180001a40`
- `0x180001a60`
- `0x180001a80`
- `0x180001aa0`
- `0x180001ac0`
- `0x180001ae0`
- `0x180001b00`
- `0x180001b20`
- `0x180001b40`
- `0x180008e5c`
- `0x18000b930`

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
0x180001b40  mov     [rsp-8+arg_0], rbx
0x180001b45  push    rbp
0x180001b46  mov     rbp, rsp
0x180001b49  sub     rsp, 50h
0x180001b4d  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180001b54  mov     ebx, ecx
0x180001b56  test    rax, rax
0x180001b59  jz      short loc_180001B70
0x180001b5b  mov     r9, [rbp+8]
0x180001b5f  xor     r8d, r8d
0x180001b62  mov     [rsp+50h+var_30], ecx
0x180001b66  xor     edx, edx
0x180001b68  xor     ecx, ecx
0x180001b6a  call    cs:__guard_dispatch_icall_fptr
0x180001b70  lea     rcx, [rbp+pExceptionObject]; this
0x180001b74  cmp     ebx, 8007000Eh
0x180001b7a  jnz     short loc_180001B92
0x180001b7c  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180001b81  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001b88  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001b8c  call    _CxxThrowException
0x180001b92  cmp     ebx, 80070005h
0x180001b98  jnz     short loc_180001BB0
0x180001b9a  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t)
0x180001b9f  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180001ba6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001baa  call    _CxxThrowException
0x180001bb0  cmp     ebx, 8001010Eh
0x180001bb6  jnz     short loc_180001BCE
0x180001bb8  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t)
0x180001bbd  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180001bc4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001bc8  call    _CxxThrowException
0x180001bce  cmp     ebx, 80004001h
0x180001bd4  jnz     short loc_180001BEC
0x180001bd6  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t)
0x180001bdb  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180001be2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001be6  call    _CxxThrowException
0x180001bec  cmp     ebx, 80070057h
0x180001bf2  jnz     short loc_180001C0A
0x180001bf4  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t)
0x180001bf9  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180001c00  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001c04  call    _CxxThrowException
0x180001c0a  cmp     ebx, 8000000Bh
0x180001c10  jnz     short loc_180001C28
0x180001c12  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t)
0x180001c17  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180001c1e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001c22  call    _CxxThrowException
0x180001c28  cmp     ebx, 80004002h
0x180001c2e  jnz     short loc_180001C46
0x180001c30  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t)
0x180001c35  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180001c3c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001c40  call    _CxxThrowException
0x180001c46  cmp     ebx, 80040111h
0x180001c4c  jnz     short loc_180001C64
0x180001c4e  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t)
0x180001c53  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180001c5a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001c5e  call    _CxxThrowException
0x180001c64  cmp     ebx, 80040154h
0x180001c6a  jnz     short loc_180001C82
0x180001c6c  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t)
0x180001c71  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180001c78  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001c7c  call    _CxxThrowException
0x180001c82  cmp     ebx, 8000000Ch
0x180001c88  jnz     short loc_180001CA0
0x180001c8a  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t)
0x180001c8f  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180001c96  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001c9a  call    _CxxThrowException
0x180001ca0  cmp     ebx, 8000000Eh
0x180001ca6  jnz     short loc_180001CBE
0x180001ca8  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t)
0x180001cad  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180001cb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001cb8  call    _CxxThrowException
0x180001cbe  cmp     ebx, 8000000Dh
0x180001cc4  jnz     short loc_180001CDC
0x180001cc6  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t)
0x180001ccb  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180001cd2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001cd6  call    _CxxThrowException
0x180001cdc  cmp     ebx, 80000018h
0x180001ce2  jnz     short loc_180001CFA
0x180001ce4  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t)
0x180001ce9  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180001cf0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001cf4  call    _CxxThrowException
0x180001cfa  cmp     ebx, 800704C7h
0x180001d00  jnz     short loc_180001D18
0x180001d02  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t)
0x180001d07  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180001d0e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001d12  call    _CxxThrowException
0x180001d18  mov     edx, ebx
0x180001d1a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)
0x180001d1f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180001d26  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001d2a  call    _CxxThrowException
```
