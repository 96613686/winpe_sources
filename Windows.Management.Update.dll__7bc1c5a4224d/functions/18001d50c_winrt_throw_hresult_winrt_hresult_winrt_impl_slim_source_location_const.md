# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18001d50c`
- end: `0x18001d730`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `81`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012430`
- `0x180014d10`
- `0x1800182e8`
- `0x180018340`
- `0x1800183c0`
- `0x180018440`
- `0x18001b864`
- `0x18001b8c4`
- `0x18001b924`
- `0x18001bf00`
- `0x18001c174`
- `0x18001c1c8`
- `0x18001c21c`
- `0x18001c43c`
- `0x18001c780`
- `0x18001ca10`
- `0x18001ca90`
- `0x18001cb10`
- `0x18001cb90`
- `0x18001cc10`
- `0x18001cc90`
- `0x18001cd10`
- `0x18001cd90`
- `0x18001ce10`
- `0x18001ce90`
- `0x18001cf10`
- `0x18001cf90`
- `0x18001d010`
- `0x18001d090`
- `0x18001d110`
- `0x18001d190`
- `0x18001d210`
- `0x18001d290`
- `0x18001d310`
- `0x18001d390`
- `0x18001d410`
- `0x18001d490`
- `0x18001e414`
- `0x18001faf4`
- `0x180021e10`
- `0x180021e90`
- `0x180022030`
- `0x180022ad0`
- `0x180022b50`
- `0x180022bd0`
- `0x180022c50`
- `0x180022cd0`
- `0x180022d50`
- `0x1800236ec`
- `0x1800238a0`

## callees

- `0x18000340c`
- `0x1800113e0`
- `0x180017db4`
- `0x180017ddc`
- `0x180017e04`
- `0x180017e2c`
- `0x180017e54`
- `0x180017e7c`
- `0x1800180f8`
- `0x180018120`
- `0x180018148`
- `0x180018170`
- `0x180018198`
- `0x1800181c0`
- `0x1800181e8`
- `0x180018210`
- `0x18001d50c`
- `0x18002a010`

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
0x18001d50c  mov     [rsp-8+arg_0], rbx
0x18001d511  mov     [rsp-8+arg_8], rdi
0x18001d516  push    rbp
0x18001d517  mov     rbp, rsp
0x18001d51a  sub     rsp, 50h
0x18001d51e  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18001d525  mov     rdi, rdx
0x18001d528  mov     ebx, ecx
0x18001d52a  test    rax, rax
0x18001d52d  jz      short loc_18001D546
0x18001d52f  mov     r8, [rdx+10h]
0x18001d533  mov     rdx, [rdx+8]
0x18001d537  mov     r9, [rbp+8]
0x18001d53b  mov     [rsp+50h+var_30], ecx
0x18001d53f  mov     ecx, [rdi]
0x18001d541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d546  lea     rcx, [rbp+pExceptionObject]; this
0x18001d54a  cmp     ebx, 8007000Eh
0x18001d550  jnz     short loc_18001D568
0x18001d552  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001d557  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001d55e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d562  call    _CxxThrowException_0
0x18001d568  cmp     ebx, 80070005h
0x18001d56e  jnz     short loc_18001D589
0x18001d570  mov     r8, rdi
0x18001d573  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d578  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18001d57f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d583  call    _CxxThrowException_0
0x18001d589  cmp     ebx, 8001010Eh
0x18001d58f  jnz     short loc_18001D5AA
0x18001d591  mov     r8, rdi
0x18001d594  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d599  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x18001d5a0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d5a4  call    _CxxThrowException_0
0x18001d5aa  cmp     ebx, 80004001h
0x18001d5b0  jnz     short loc_18001D5CB
0x18001d5b2  mov     r8, rdi
0x18001d5b5  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d5ba  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x18001d5c1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d5c5  call    _CxxThrowException_0
0x18001d5cb  cmp     ebx, 80070057h
0x18001d5d1  jnz     short loc_18001D5EC
0x18001d5d3  mov     r8, rdi
0x18001d5d6  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d5db  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001d5e2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d5e6  call    _CxxThrowException_0
0x18001d5ec  cmp     ebx, 8000000Bh
0x18001d5f2  jnz     short loc_18001D60D
0x18001d5f4  mov     r8, rdi
0x18001d5f7  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d5fc  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18001d603  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d607  call    _CxxThrowException_0
0x18001d60d  cmp     ebx, 80004002h
0x18001d613  jnz     short loc_18001D62E
0x18001d615  mov     r8, rdi
0x18001d618  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d61d  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18001d624  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d628  call    _CxxThrowException_0
0x18001d62e  cmp     ebx, 80040111h
0x18001d634  jnz     short loc_18001D64F
0x18001d636  mov     r8, rdi
0x18001d639  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d63e  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18001d645  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d649  call    _CxxThrowException_0
0x18001d64f  cmp     ebx, 80040154h
0x18001d655  jnz     short loc_18001D670
0x18001d657  mov     r8, rdi
0x18001d65a  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d65f  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x18001d666  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d66a  call    _CxxThrowException_0
0x18001d670  cmp     ebx, 8000000Ch
0x18001d676  jnz     short loc_18001D691
0x18001d678  mov     r8, rdi
0x18001d67b  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d680  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18001d687  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d68b  call    _CxxThrowException_0
0x18001d691  cmp     ebx, 8000000Eh
0x18001d697  jnz     short loc_18001D6B2
0x18001d699  mov     r8, rdi
0x18001d69c  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d6a1  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x18001d6a8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d6ac  call    _CxxThrowException_0
0x18001d6b2  cmp     ebx, 8000000Dh
0x18001d6b8  jnz     short loc_18001D6D3
0x18001d6ba  mov     r8, rdi
0x18001d6bd  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d6c2  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x18001d6c9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d6cd  call    _CxxThrowException_0
0x18001d6d3  cmp     ebx, 80000018h
0x18001d6d9  jnz     short loc_18001D6F4
0x18001d6db  mov     r8, rdi
0x18001d6de  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d6e3  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x18001d6ea  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d6ee  call    _CxxThrowException_0
0x18001d6f4  cmp     ebx, 800704C7h
0x18001d6fa  jnz     short loc_18001D715
0x18001d6fc  mov     r8, rdi
0x18001d6ff  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d704  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001d70b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d70f  call    _CxxThrowException_0
0x18001d715  mov     r9, rdi
0x18001d718  mov     edx, ebx
0x18001d71a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18001d71f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001d726  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d72a  call    _CxxThrowException_0
```
