# dllmain_crt_process_attach

- ea: `0x1800073e0`
- end: `0x1800074f6`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180007390`

## callees

- `0x1800073e0`
- `0x180007720`
- `0x18000775c`
- `0x180007790`
- `0x18000788c`
- `0x180007954`
- `0x1800079ec`
- `0x180007e70`
- `0x180007e8c`
- `0x180007ea8`
- `0x180007eb8`
- `0x180008000`
- `0x18000d6ac`
- `0x18000d710`
- `0x1800241c0`

## pseudocode

```c
__int64 dllmain_crt_process_attach()
{
  char v0; // bl
  char v1; // di
  __int64 v2; // rcx
  _QWORD *dyn_tls_init_callback; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v0 = _scrt_acquire_startup_lock();
  v1 = 1;
  if ( _scrt_current_native_startup_state )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1800074F6LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( _scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( _scrt_dllmain_after_initialize_c() )
      {
        initterm((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v1 = 0;
      }
    }
  }
  LOBYTE(v2) = v0;
  _scrt_release_startup_lock(v2);
  if ( v1 )
    return 0;
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback();
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
  }
  ++dword_18003DBB0;
  return 1;
}

```

## disassembly

```asm
0x1800073e0  mov     [rsp+arg_0], rbx
0x1800073e5  mov     [rsp+arg_8], rsi
0x1800073ea  mov     [rsp+arg_18], rdi
0x1800073ef  push    r14
0x1800073f1  sub     rsp, 20h
0x1800073f5  mov     rsi, rdx
0x1800073f8  mov     r14, rcx
0x1800073fb  xor     ecx, ecx
0x1800073fd  call    __scrt_initialize_crt
0x180007402  test    al, al
0x180007404  jz      loc_1800074D2
0x18000740a  call    __scrt_acquire_startup_lock
0x18000740f  mov     bl, al
0x180007411  mov     [rsp+28h+arg_10], al
0x180007415  mov     dil, 1
0x180007418  cmp     cs:__scrt_current_native_startup_state, 0
0x18000741f  jnz     loc_1800074EA
0x180007425  mov     cs:__scrt_current_native_startup_state, 1
0x18000742f  call    __scrt_dllmain_before_initialize_c
0x180007434  test    al, al
0x180007436  jz      short loc_180007487
0x180007438  call    _RTC_Initialize
0x18000743d  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180007442  call    __scrt_initialize_default_local_stdio_options
0x180007447  lea     rdx, __xi_z; Last
0x18000744e  lea     rcx, __xi_a; First
0x180007455  call    _initterm_e
0x18000745a  test    eax, eax
0x18000745c  jnz     short loc_180007487
0x18000745e  call    __scrt_dllmain_after_initialize_c
0x180007463  test    al, al
0x180007465  jz      short loc_180007487
0x180007467  lea     rdx, __xc_z; Last
0x18000746e  lea     rcx, __xc_a; First
0x180007475  call    _initterm
0x18000747a  mov     cs:__scrt_current_native_startup_state, 2
0x180007484  xor     dil, dil
0x180007487  mov     cl, bl
0x180007489  call    __scrt_release_startup_lock
0x18000748e  test    dil, dil
0x180007491  jnz     short loc_1800074D2
0x180007493  call    __scrt_get_dyn_tls_init_callback
0x180007498  mov     rbx, rax
0x18000749b  cmp     qword ptr [rax], 0
0x18000749f  jz      short loc_1800074C5
0x1800074a1  mov     rcx, rax
0x1800074a4  call    __scrt_is_nonwritable_in_current_image
0x1800074a9  test    al, al
0x1800074ab  jz      short loc_1800074C5
0x1800074ad  mov     r8, rsi
0x1800074b0  mov     edx, 2
0x1800074b5  mov     rcx, r14
0x1800074b8  mov     rax, [rbx]
0x1800074bb  mov     r9, cs:__guard_dispatch_icall_fptr
0x1800074c2  call    r9 ; _guard_dispatch_icall_nop
0x1800074c5  inc     cs:dword_18003DBB0
0x1800074cb  mov     eax, 1
0x1800074d0  jmp     short loc_1800074D4
0x1800074d2  xor     eax, eax
0x1800074d4  mov     rbx, [rsp+28h+arg_0]
0x1800074d9  mov     rsi, [rsp+28h+arg_8]
0x1800074de  mov     rdi, [rsp+28h+arg_18]
0x1800074e3  add     rsp, 20h
0x1800074e7  pop     r14
0x1800074e9  retn
0x1800074ea  mov     ecx, 7
0x1800074ef  call    __scrt_fastfail
0x1800074f4  nop
0x1800074f5  int     3; Trap to Debugger
0x180024e7a  push    rbp
0x180024e7c  sub     rsp, 20h
0x180024e80  mov     rbp, rdx
0x180024e83  mov     cl, [rbp+40h]
0x180024e86  add     rsp, 20h
0x180024e8a  pop     rbp
0x180024e8b  jmp     __scrt_release_startup_lock
```
