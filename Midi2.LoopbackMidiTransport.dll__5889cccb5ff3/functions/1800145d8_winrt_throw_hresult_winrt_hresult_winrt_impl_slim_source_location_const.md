# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x1800145d8`
- end: `0x1800147fc`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: ``
- caller_count: `35`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e920`
- `0x18000ee84`
- `0x18000efa8`
- `0x1800100a8`
- `0x180011018`
- `0x1800120b8`
- `0x1800122f0`
- `0x180013b14`
- `0x180014804`
- `0x180014e40`
- `0x180014fec`
- `0x180015198`
- `0x1800152f8`
- `0x180015e90`
- `0x180016638`
- `0x1800166ec`
- `0x1800168a0`
- `0x180016ab4`
- `0x180016b60`
- `0x180016bd0`
- `0x180016ca0`
- `0x180016da4`
- `0x180016e7c`
- `0x180016f4c`
- `0x180017024`
- `0x1800170fc`
- `0x180017168`
- `0x180017620`
- `0x180017690`
- `0x1800176ec`
- `0x1800183a0`
- `0x1800184c4`
- `0x180018580`
- `0x18001863c`
- `0x180018710`

## callees

- `0x18000503c`
- `0x18000f228`
- `0x18000f298`
- `0x18000f304`
- `0x18000f370`
- `0x18000f398`
- `0x18000f3c0`
- `0x18000f3e8`
- `0x18000f664`
- `0x18000f68c`
- `0x18000f6b4`
- `0x18000f6dc`
- `0x18000f748`
- `0x18000f770`
- `0x18000f7dc`
- `0x18000f804`
- `0x1800145d8`
- `0x180032010`

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
0x1800145d8  mov     [rsp-8+arg_0], rbx
0x1800145dd  mov     [rsp-8+arg_8], rdi
0x1800145e2  push    rbp
0x1800145e3  mov     rbp, rsp
0x1800145e6  sub     rsp, 50h
0x1800145ea  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x1800145f1  mov     rdi, rdx
0x1800145f4  mov     ebx, ecx
0x1800145f6  test    rax, rax
0x1800145f9  jz      short loc_180014612
0x1800145fb  mov     r8, [rdx+10h]
0x1800145ff  mov     rdx, [rdx+8]
0x180014603  mov     r9, [rbp+8]
0x180014607  mov     [rsp+50h+var_30], ecx
0x18001460b  mov     ecx, [rdi]
0x18001460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014612  lea     rcx, [rbp+pExceptionObject]; this
0x180014616  cmp     ebx, 8007000Eh
0x18001461c  jnz     short loc_180014634
0x18001461e  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180014623  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001462a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001462e  call    _CxxThrowException_0
0x180014634  cmp     ebx, 80070005h
0x18001463a  jnz     short loc_180014655
0x18001463c  mov     r8, rdi
0x18001463f  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180014644  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18001464b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001464f  call    _CxxThrowException_0
0x180014655  cmp     ebx, 8001010Eh
0x18001465b  jnz     short loc_180014676
0x18001465d  mov     r8, rdi
0x180014660  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180014665  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18001466c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014670  call    _CxxThrowException_0
0x180014676  cmp     ebx, 80004001h
0x18001467c  jnz     short loc_180014697
0x18001467e  mov     r8, rdi
0x180014681  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180014686  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001468d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014691  call    _CxxThrowException_0
0x180014697  cmp     ebx, 80070057h
0x18001469d  jnz     short loc_1800146B8
0x18001469f  mov     r8, rdi
0x1800146a2  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800146a7  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800146ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800146b2  call    _CxxThrowException_0
0x1800146b8  cmp     ebx, 8000000Bh
0x1800146be  jnz     short loc_1800146D9
0x1800146c0  mov     r8, rdi
0x1800146c3  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800146c8  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800146cf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800146d3  call    _CxxThrowException_0
0x1800146d9  cmp     ebx, 80004002h
0x1800146df  jnz     short loc_1800146FA
0x1800146e1  mov     r8, rdi
0x1800146e4  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800146e9  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x1800146f0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800146f4  call    _CxxThrowException_0
0x1800146fa  cmp     ebx, 80040111h
0x180014700  jnz     short loc_18001471B
0x180014702  mov     r8, rdi
0x180014705  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001470a  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180014711  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014715  call    _CxxThrowException_0
0x18001471b  cmp     ebx, 80040154h
0x180014721  jnz     short loc_18001473C
0x180014723  mov     r8, rdi
0x180014726  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001472b  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180014732  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014736  call    _CxxThrowException_0
0x18001473c  cmp     ebx, 8000000Ch
0x180014742  jnz     short loc_18001475D
0x180014744  mov     r8, rdi
0x180014747  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001474c  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180014753  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014757  call    _CxxThrowException_0
0x18001475d  cmp     ebx, 8000000Eh
0x180014763  jnz     short loc_18001477E
0x180014765  mov     r8, rdi
0x180014768  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001476d  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180014774  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014778  call    _CxxThrowException_0
0x18001477e  cmp     ebx, 8000000Dh
0x180014784  jnz     short loc_18001479F
0x180014786  mov     r8, rdi
0x180014789  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001478e  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180014795  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014799  call    _CxxThrowException_0
0x18001479f  cmp     ebx, 80000018h
0x1800147a5  jnz     short loc_1800147C0
0x1800147a7  mov     r8, rdi
0x1800147aa  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800147af  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x1800147b6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800147ba  call    _CxxThrowException_0
0x1800147c0  cmp     ebx, 800704C7h
0x1800147c6  jnz     short loc_1800147E1
0x1800147c8  mov     r8, rdi
0x1800147cb  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800147d0  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1800147d7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800147db  call    _CxxThrowException_0
0x1800147e1  mov     r9, rdi
0x1800147e4  mov     edx, ebx
0x1800147e6  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x1800147eb  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800147f2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800147f6  call    _CxxThrowException_0
```
