# winrt::throw_hresult(winrt::hresult)

- ea: `0x180004810`
- end: `0x180004a00`
- name: `?throw_hresult@winrt@@YAXUhresult@1@@Z`
- size: `496`
- prototype: `void __fastcall __noreturn(_QWORD)`
- caller_count: `89`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800025f0`
- `0x180004a20`
- `0x180004c70`
- `0x1800052e0`
- `0x1800056e0`
- `0x1800058e0`
- `0x180006110`
- `0x1800067b0`
- `0x1800067e0`
- `0x180006810`
- `0x180006840`
- `0x180006870`
- `0x1800068a0`
- `0x180006910`
- `0x180006940`
- `0x180006b70`
- `0x180007150`
- `0x180007820`
- `0x180008c60`
- `0x180009860`
- `0x1800098d0`
- `0x18000a7b0`
- `0x180013c10`
- `0x180013d70`
- `0x180014230`
- `0x180014bb0`
- `0x180014d10`
- `0x180015b30`
- `0x180015e40`
- `0x1800166c0`
- `0x180016760`
- `0x180017030`
- `0x180017070`
- `0x1800170d0`
- `0x180017340`
- `0x180017910`
- `0x180018260`
- `0x180018f00`
- `0x180019270`
- `0x1800196b0`
- `0x180019860`
- `0x18001ac00`
- `0x18001acb0`
- `0x18001b040`
- `0x18001c100`
- `0x18001c260`
- `0x18001c400`
- `0x18001c560`
- `0x18001c640`
- `0x18001c7a0`

## callees

- `0x180003e80`
- `0x180003f20`
- `0x180003f40`
- `0x180003f60`
- `0x180003f80`
- `0x180003fa0`
- `0x180003fc0`
- `0x180003fe0`
- `0x180004000`
- `0x180004020`
- `0x180004040`
- `0x180004060`
- `0x180004080`
- `0x180004280`
- `0x180004590`
- `0x180004810`
- `0x180036f4c`
- `0x18003bed0`

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
0x180004810  mov     [rsp-8+arg_0], rbx
0x180004815  push    rbp
0x180004816  mov     rbp, rsp
0x180004819  sub     rsp, 50h
0x18000481d  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180004824  mov     ebx, ecx
0x180004826  test    rax, rax
0x180004829  jz      short loc_180004840
0x18000482b  mov     r9, [rbp+8]
0x18000482f  xor     r8d, r8d
0x180004832  mov     [rsp+50h+var_30], ecx
0x180004836  xor     edx, edx
0x180004838  xor     ecx, ecx
0x18000483a  call    cs:__guard_dispatch_icall_fptr
0x180004840  lea     rcx, [rbp+pExceptionObject]; this
0x180004844  cmp     ebx, 8007000Eh
0x18000484a  jnz     short loc_180004862
0x18000484c  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180004851  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180004858  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000485c  call    _CxxThrowException
0x180004862  cmp     ebx, 80070005h
0x180004868  jnz     short loc_180004880
0x18000486a  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t)
0x18000486f  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180004876  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000487a  call    _CxxThrowException
0x180004880  cmp     ebx, 8001010Eh
0x180004886  jnz     short loc_18000489E
0x180004888  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t)
0x18000488d  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180004894  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004898  call    _CxxThrowException
0x18000489e  cmp     ebx, 80004001h
0x1800048a4  jnz     short loc_1800048BC
0x1800048a6  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t)
0x1800048ab  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x1800048b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800048b6  call    _CxxThrowException
0x1800048bc  cmp     ebx, 80070057h
0x1800048c2  jnz     short loc_1800048DA
0x1800048c4  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t)
0x1800048c9  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800048d0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800048d4  call    _CxxThrowException
0x1800048da  cmp     ebx, 8000000Bh
0x1800048e0  jnz     short loc_1800048F8
0x1800048e2  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t)
0x1800048e7  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800048ee  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800048f2  call    _CxxThrowException
0x1800048f8  cmp     ebx, 80004002h
0x1800048fe  jnz     short loc_180004916
0x180004900  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t)
0x180004905  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x18000490c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004910  call    _CxxThrowException
0x180004916  cmp     ebx, 80040111h
0x18000491c  jnz     short loc_180004934
0x18000491e  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t)
0x180004923  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x18000492a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000492e  call    _CxxThrowException
0x180004934  cmp     ebx, 80040154h
0x18000493a  jnz     short loc_180004952
0x18000493c  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t)
0x180004941  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180004948  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000494c  call    _CxxThrowException
0x180004952  cmp     ebx, 8000000Ch
0x180004958  jnz     short loc_180004970
0x18000495a  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t)
0x18000495f  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180004966  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000496a  call    _CxxThrowException
0x180004970  cmp     ebx, 8000000Eh
0x180004976  jnz     short loc_18000498E
0x180004978  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t)
0x18000497d  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180004984  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004988  call    _CxxThrowException
0x18000498e  cmp     ebx, 8000000Dh
0x180004994  jnz     short loc_1800049AC
0x180004996  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t)
0x18000499b  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x1800049a2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800049a6  call    _CxxThrowException
0x1800049ac  cmp     ebx, 80000018h
0x1800049b2  jnz     short loc_1800049CA
0x1800049b4  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t)
0x1800049b9  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x1800049c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800049c4  call    _CxxThrowException
0x1800049ca  cmp     ebx, 800704C7h
0x1800049d0  jnz     short loc_1800049E8
0x1800049d2  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t)
0x1800049d7  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1800049de  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800049e2  call    _CxxThrowException
0x1800049e8  mov     edx, ebx
0x1800049ea  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)
0x1800049ef  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800049f6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800049fa  call    _CxxThrowException
```
