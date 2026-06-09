# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x180015348`
- end: `0x18001556c`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: ``
- caller_count: `50`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f9fc`
- `0x18000ff14`
- `0x180010008`
- `0x180010108`
- `0x18001022c`
- `0x18001137c`
- `0x180011704`
- `0x1800136e8`
- `0x180013920`
- `0x1800149d4`
- `0x180015574`
- `0x1800161c0`
- `0x180017854`
- `0x180017a00`
- `0x18001ac64`
- `0x18001acd0`
- `0x18001ad40`
- `0x18001b728`
- `0x18001e8a0`
- `0x18001f460`
- `0x180020998`
- `0x180020bb4`
- `0x180020d60`
- `0x180020f0c`
- `0x1800218f4`
- `0x180021960`
- `0x180021e4c`
- `0x180021f58`
- `0x180022080`
- `0x18002213c`
- `0x1800221e8`
- `0x1800222c0`
- `0x180022330`
- `0x180022408`
- `0x180022478`
- `0x180022550`
- `0x1800225bc`
- `0x180022860`
- `0x1800228d0`
- `0x1800237f4`
- `0x180023930`
- `0x1800239ec`
- `0x180024bbc`
- `0x18002af94`
- `0x18002ba50`
- `0x18002bb20`
- `0x1800356b0`
- `0x1800376c0`
- `0x1800378b8`
- `0x1800395b4`

## callees

- `0x18000529c`
- `0x18001036c`
- `0x180010448`
- `0x1800104b4`
- `0x180010520`
- `0x180010548`
- `0x180010570`
- `0x180010598`
- `0x180010830`
- `0x180010858`
- `0x180010880`
- `0x1800108a8`
- `0x180010914`
- `0x18001093c`
- `0x1800109a8`
- `0x1800109d0`
- `0x180015348`
- `0x180041010`

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
0x180015348  mov     [rsp-8+arg_0], rbx
0x18001534d  mov     [rsp-8+arg_8], rdi
0x180015352  push    rbp
0x180015353  mov     rbp, rsp
0x180015356  sub     rsp, 50h
0x18001535a  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180015361  mov     rdi, rdx
0x180015364  mov     ebx, ecx
0x180015366  test    rax, rax
0x180015369  jz      short loc_180015382
0x18001536b  mov     r8, [rdx+10h]
0x18001536f  mov     rdx, [rdx+8]
0x180015373  mov     r9, [rbp+8]
0x180015377  mov     [rsp+50h+var_30], ecx
0x18001537b  mov     ecx, [rdi]
0x18001537d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015382  lea     rcx, [rbp+pExceptionObject]; this
0x180015386  cmp     ebx, 8007000Eh
0x18001538c  jnz     short loc_1800153A4
0x18001538e  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180015393  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001539a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001539e  call    _CxxThrowException_0
0x1800153a4  cmp     ebx, 80070005h
0x1800153aa  jnz     short loc_1800153C5
0x1800153ac  mov     r8, rdi
0x1800153af  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800153b4  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x1800153bb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800153bf  call    _CxxThrowException_0
0x1800153c5  cmp     ebx, 8001010Eh
0x1800153cb  jnz     short loc_1800153E6
0x1800153cd  mov     r8, rdi
0x1800153d0  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800153d5  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x1800153dc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800153e0  call    _CxxThrowException_0
0x1800153e6  cmp     ebx, 80004001h
0x1800153ec  jnz     short loc_180015407
0x1800153ee  mov     r8, rdi
0x1800153f1  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800153f6  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800153fd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015401  call    _CxxThrowException_0
0x180015407  cmp     ebx, 80070057h
0x18001540d  jnz     short loc_180015428
0x18001540f  mov     r8, rdi
0x180015412  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180015417  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001541e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015422  call    _CxxThrowException_0
0x180015428  cmp     ebx, 8000000Bh
0x18001542e  jnz     short loc_180015449
0x180015430  mov     r8, rdi
0x180015433  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180015438  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001543f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015443  call    _CxxThrowException_0
0x180015449  cmp     ebx, 80004002h
0x18001544f  jnz     short loc_18001546A
0x180015451  mov     r8, rdi
0x180015454  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180015459  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180015460  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015464  call    _CxxThrowException_0
0x18001546a  cmp     ebx, 80040111h
0x180015470  jnz     short loc_18001548B
0x180015472  mov     r8, rdi
0x180015475  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001547a  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180015481  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015485  call    _CxxThrowException_0
0x18001548b  cmp     ebx, 80040154h
0x180015491  jnz     short loc_1800154AC
0x180015493  mov     r8, rdi
0x180015496  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001549b  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x1800154a2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800154a6  call    _CxxThrowException_0
0x1800154ac  cmp     ebx, 8000000Ch
0x1800154b2  jnz     short loc_1800154CD
0x1800154b4  mov     r8, rdi
0x1800154b7  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800154bc  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x1800154c3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800154c7  call    _CxxThrowException_0
0x1800154cd  cmp     ebx, 8000000Eh
0x1800154d3  jnz     short loc_1800154EE
0x1800154d5  mov     r8, rdi
0x1800154d8  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800154dd  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x1800154e4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800154e8  call    _CxxThrowException_0
0x1800154ee  cmp     ebx, 8000000Dh
0x1800154f4  jnz     short loc_18001550F
0x1800154f6  mov     r8, rdi
0x1800154f9  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800154fe  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180015505  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015509  call    _CxxThrowException_0
0x18001550f  cmp     ebx, 80000018h
0x180015515  jnz     short loc_180015530
0x180015517  mov     r8, rdi
0x18001551a  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001551f  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180015526  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001552a  call    _CxxThrowException_0
0x180015530  cmp     ebx, 800704C7h
0x180015536  jnz     short loc_180015551
0x180015538  mov     r8, rdi
0x18001553b  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180015540  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180015547  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001554b  call    _CxxThrowException_0
0x180015551  mov     r9, rdi
0x180015554  mov     edx, ebx
0x180015556  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001555b  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180015562  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015566  call    _CxxThrowException_0
```
