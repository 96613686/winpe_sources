# winrt::throw_hresult(winrt::hresult)

- ea: `0x180035a50`
- end: `0x180035c3f`
- name: `?throw_hresult@winrt@@YAXUhresult@1@@Z`
- size: `495`
- prototype: `void __fastcall __noreturn(_QWORD)`
- caller_count: `43`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bdd0`
- `0x18000bff8`
- `0x18000c218`
- `0x18000c3c8`
- `0x18000c5e8`
- `0x18000c808`
- `0x18000fd78`
- `0x180010328`
- `0x18001043c`
- `0x1800105d8`
- `0x1800114f0`
- `0x1800115c0`
- `0x18001162c`
- `0x180011684`
- `0x1800116e0`
- `0x18001174c`
- `0x1800120a0`
- `0x180012a64`
- `0x180012b78`
- `0x180012c48`
- `0x180013224`
- `0x180018068`
- `0x18002ef78`
- `0x18003a7dc`
- `0x18003a888`
- `0x18003aa20`
- `0x18003aae0`
- `0x18003aeb0`
- `0x180040f10`
- `0x1800411f0`
- `0x180041334`
- `0x180041480`
- `0x180041540`
- `0x180041bf8`
- `0x180041d00`
- `0x1800476e4`
- `0x180047864`
- `0x180047a20`
- `0x180047bc0`
- `0x180047d54`
- `0x180047e08`
- `0x180047e78`
- `0x180047ff8`

## callees

- `0x180034c04`
- `0x180034ca8`
- `0x180034ccc`
- `0x180034cf0`
- `0x180034d14`
- `0x180034d38`
- `0x180034d5c`
- `0x180034d80`
- `0x180034da4`
- `0x180034dc8`
- `0x180034dec`
- `0x180034e10`
- `0x180034e34`
- `0x1800352ac`
- `0x1800357fc`
- `0x180035a50`
- `0x180058abc`
- `0x18005c5e0`

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
      winrt::hresult_access_denied::hresult_access_denied(pExceptionObject);
      throw (winrt::hresult_access_denied *)pExceptionObject;
    case 0x8001010E:
      winrt::hresult_wrong_thread::hresult_wrong_thread(pExceptionObject);
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
  winrt::hresult_error::hresult_error(pExceptionObject, a1);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180035a50  mov     [rsp-8+arg_0], rbx
0x180035a55  push    rbp
0x180035a56  mov     rbp, rsp
0x180035a59  sub     rsp, 50h
0x180035a5d  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180035a64  mov     ebx, ecx
0x180035a66  test    rax, rax
0x180035a69  jz      short loc_180035A7F
0x180035a6b  mov     r9, [rbp+8]
0x180035a6f  xor     r8d, r8d
0x180035a72  mov     [rsp+50h+var_30], ecx
0x180035a76  xor     edx, edx
0x180035a78  xor     ecx, ecx
0x180035a7a  call    _guard_dispatch_icall
0x180035a7f  lea     rcx, [rbp+pExceptionObject]; this
0x180035a83  cmp     ebx, 8007000Eh
0x180035a89  jnz     short loc_180035AA1
0x180035a8b  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180035a90  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180035a97  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035a9b  call    _CxxThrowException
0x180035aa1  cmp     ebx, 80070005h
0x180035aa7  jnz     short loc_180035ABF
0x180035aa9  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t)
0x180035aae  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180035ab5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035ab9  call    _CxxThrowException
0x180035abf  cmp     ebx, 8001010Eh
0x180035ac5  jnz     short loc_180035ADD
0x180035ac7  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t)
0x180035acc  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180035ad3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035ad7  call    _CxxThrowException
0x180035add  cmp     ebx, 80004001h
0x180035ae3  jnz     short loc_180035AFB
0x180035ae5  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t)
0x180035aea  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180035af1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035af5  call    _CxxThrowException
0x180035afb  cmp     ebx, 80070057h
0x180035b01  jnz     short loc_180035B19
0x180035b03  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t)
0x180035b08  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180035b0f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035b13  call    _CxxThrowException
0x180035b19  cmp     ebx, 8000000Bh
0x180035b1f  jnz     short loc_180035B37
0x180035b21  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t)
0x180035b26  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180035b2d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035b31  call    _CxxThrowException
0x180035b37  cmp     ebx, 80004002h
0x180035b3d  jnz     short loc_180035B55
0x180035b3f  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t)
0x180035b44  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180035b4b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035b4f  call    _CxxThrowException
0x180035b55  cmp     ebx, 80040111h
0x180035b5b  jnz     short loc_180035B73
0x180035b5d  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t)
0x180035b62  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180035b69  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035b6d  call    _CxxThrowException
0x180035b73  cmp     ebx, 80040154h
0x180035b79  jnz     short loc_180035B91
0x180035b7b  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t)
0x180035b80  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180035b87  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035b8b  call    _CxxThrowException
0x180035b91  cmp     ebx, 8000000Ch
0x180035b97  jnz     short loc_180035BAF
0x180035b99  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t)
0x180035b9e  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180035ba5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035ba9  call    _CxxThrowException
0x180035baf  cmp     ebx, 8000000Eh
0x180035bb5  jnz     short loc_180035BCD
0x180035bb7  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t)
0x180035bbc  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180035bc3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035bc7  call    _CxxThrowException
0x180035bcd  cmp     ebx, 8000000Dh
0x180035bd3  jnz     short loc_180035BEB
0x180035bd5  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t)
0x180035bda  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180035be1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035be5  call    _CxxThrowException
0x180035beb  cmp     ebx, 80000018h
0x180035bf1  jnz     short loc_180035C09
0x180035bf3  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t)
0x180035bf8  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180035bff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035c03  call    _CxxThrowException
0x180035c09  cmp     ebx, 800704C7h
0x180035c0f  jnz     short loc_180035C27
0x180035c11  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t)
0x180035c16  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180035c1d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035c21  call    _CxxThrowException
0x180035c27  mov     edx, ebx
0x180035c29  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)
0x180035c2e  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180035c35  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035c39  call    _CxxThrowException
```
