# dllmain_crt_process_attach

- ea: `0x1800024f0`
- end: `0x180002606`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1800024a0`

## callees

- `0x1800024f0`
- `0x180002940`
- `0x18000296c`
- `0x180002a2c`
- `0x180002a68`
- `0x180002a9c`
- `0x180002b98`
- `0x180002c60`
- `0x180002cf8`
- `0x180002dbc`
- `0x180002dd0`
- `0x180003034`
- `0x180003624`
- `0x18000365c`
- `0x180060110`

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
    JUMPOUT(0x180002606LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
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
  ++dword_180077D88;
  return 1;
}

```

## disassembly

```asm
0x1800024f0  mov     [rsp+arg_0], rbx
0x1800024f5  mov     [rsp+arg_8], rsi
0x1800024fa  mov     [rsp+arg_18], rdi
0x1800024ff  push    r14
0x180002501  sub     rsp, 20h
0x180002505  mov     rsi, rdx
0x180002508  mov     r14, rcx
0x18000250b  xor     ecx, ecx
0x18000250d  call    __scrt_initialize_crt
0x180002512  test    al, al
0x180002514  jz      loc_1800025E2
0x18000251a  call    __scrt_acquire_startup_lock
0x18000251f  mov     bl, al
0x180002521  mov     [rsp+28h+arg_10], al
0x180002525  mov     dil, 1
0x180002528  cmp     cs:__scrt_current_native_startup_state, 0
0x18000252f  jnz     loc_1800025FA
0x180002535  mov     cs:__scrt_current_native_startup_state, 1
0x18000253f  call    __scrt_dllmain_before_initialize_c
0x180002544  test    al, al
0x180002546  jz      short loc_180002597
0x180002548  call    _RTC_Initialize
0x18000254d  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180002552  call    __scrt_initialize_default_local_stdio_options
0x180002557  lea     rdx, __xi_z; Last
0x18000255e  lea     rcx, __xi_a; First
0x180002565  call    _initterm_e
0x18000256a  test    eax, eax
0x18000256c  jnz     short loc_180002597
0x18000256e  call    __scrt_dllmain_after_initialize_c
0x180002573  test    al, al
0x180002575  jz      short loc_180002597
0x180002577  lea     rdx, __xc_z; Last
0x18000257e  lea     rcx, __xc_a; First
0x180002585  call    _initterm
0x18000258a  mov     cs:__scrt_current_native_startup_state, 2
0x180002594  xor     dil, dil
0x180002597  mov     cl, bl
0x180002599  call    __scrt_release_startup_lock
0x18000259e  test    dil, dil
0x1800025a1  jnz     short loc_1800025E2
0x1800025a3  call    __scrt_get_dyn_tls_init_callback
0x1800025a8  mov     rbx, rax
0x1800025ab  cmp     qword ptr [rax], 0
0x1800025af  jz      short loc_1800025D5
0x1800025b1  mov     rcx, rax
0x1800025b4  call    __scrt_is_nonwritable_in_current_image
0x1800025b9  test    al, al
0x1800025bb  jz      short loc_1800025D5
0x1800025bd  mov     r8, rsi
0x1800025c0  mov     edx, 2
0x1800025c5  mov     rcx, r14
0x1800025c8  mov     rax, [rbx]
0x1800025cb  mov     r9, cs:__guard_dispatch_icall_fptr
0x1800025d2  call    r9 ; _guard_dispatch_icall_nop
0x1800025d5  inc     cs:dword_180077D88
0x1800025db  mov     eax, 1
0x1800025e0  jmp     short loc_1800025E4
0x1800025e2  xor     eax, eax
0x1800025e4  mov     rbx, [rsp+28h+arg_0]
0x1800025e9  mov     rsi, [rsp+28h+arg_8]
0x1800025ee  mov     rdi, [rsp+28h+arg_18]
0x1800025f3  add     rsp, 20h
0x1800025f7  pop     r14
0x1800025f9  retn
0x1800025fa  mov     ecx, 7
0x1800025ff  call    __scrt_fastfail
0x180002604  nop
0x180002605  int     3; Trap to Debugger
0x180060e90  push    rbp
0x180060e92  sub     rsp, 20h
0x180060e96  mov     rbp, rdx
0x180060e99  mov     cl, [rbp+40h]
0x180060e9c  add     rsp, 20h
0x180060ea0  pop     rbp
0x180060ea1  jmp     __scrt_release_startup_lock
```
