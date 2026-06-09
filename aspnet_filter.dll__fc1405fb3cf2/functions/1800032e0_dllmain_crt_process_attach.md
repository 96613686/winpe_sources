# dllmain_crt_process_attach

- ea: `0x1800032e0`
- end: `0x1800033f6`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180003290`

## callees

- `0x1800032e0`
- `0x180003a28`
- `0x180003a4c`
- `0x180003a68`
- `0x180003aa4`
- `0x180003ad8`
- `0x180003bd4`
- `0x180003cac`
- `0x180003d44`
- `0x180003de8`
- `0x180003df8`
- `0x180003f44`
- `0x180004326`
- `0x18000432c`
- `0x1800043b0`

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
    JUMPOUT(0x1800033F6LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
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
  ++dword_1800071D8;
  return 1;
}

```

## disassembly

```asm
0x1800032e0  mov     [rsp+arg_0], rbx
0x1800032e5  mov     [rsp+arg_8], rsi
0x1800032ea  mov     [rsp+arg_18], rdi
0x1800032ef  push    r14
0x1800032f1  sub     rsp, 20h
0x1800032f5  mov     rsi, rdx
0x1800032f8  mov     r14, rcx
0x1800032fb  xor     ecx, ecx
0x1800032fd  call    __scrt_initialize_crt
0x180003302  test    al, al
0x180003304  jz      loc_1800033D2
0x18000330a  call    __scrt_acquire_startup_lock
0x18000330f  mov     bl, al
0x180003311  mov     [rsp+28h+arg_10], al
0x180003315  mov     dil, 1
0x180003318  cmp     cs:__scrt_current_native_startup_state, 0
0x18000331f  jnz     loc_1800033EA
0x180003325  mov     cs:__scrt_current_native_startup_state, 1
0x18000332f  call    __scrt_dllmain_before_initialize_c
0x180003334  test    al, al
0x180003336  jz      short loc_180003387
0x180003338  call    _RTC_Initialize
0x18000333d  call    ?__scrt_initialize_type_info@@YAXXZ
0x180003342  call    __scrt_initialize_default_local_stdio_options
0x180003347  lea     rdx, __xi_z; Last
0x18000334e  lea     rcx, __xi_a; First
0x180003355  call    _initterm_e_0
0x18000335a  test    eax, eax
0x18000335c  jnz     short loc_180003387
0x18000335e  call    __scrt_dllmain_after_initialize_c
0x180003363  test    al, al
0x180003365  jz      short loc_180003387
0x180003367  lea     rdx, __xc_z; Last
0x18000336e  lea     rcx, __xc_a; First
0x180003375  call    _initterm_0
0x18000337a  mov     cs:__scrt_current_native_startup_state, 2
0x180003384  xor     dil, dil
0x180003387  mov     cl, bl
0x180003389  call    __scrt_release_startup_lock
0x18000338e  test    dil, dil
0x180003391  jnz     short loc_1800033D2
0x180003393  call    __scrt_get_dyn_tls_init_callback
0x180003398  mov     rbx, rax
0x18000339b  cmp     qword ptr [rax], 0
0x18000339f  jz      short loc_1800033C5
0x1800033a1  mov     rcx, rax
0x1800033a4  call    __scrt_is_nonwritable_in_current_image
0x1800033a9  test    al, al
0x1800033ab  jz      short loc_1800033C5
0x1800033ad  mov     r8, rsi
0x1800033b0  mov     edx, 2
0x1800033b5  mov     rcx, r14
0x1800033b8  mov     rax, [rbx]
0x1800033bb  mov     r9, cs:__guard_dispatch_icall_fptr
0x1800033c2  call    r9 ; _guard_dispatch_icall_nop
0x1800033c5  inc     cs:dword_1800071D8
0x1800033cb  mov     eax, 1
0x1800033d0  jmp     short loc_1800033D4
0x1800033d2  xor     eax, eax
0x1800033d4  mov     rbx, [rsp+28h+arg_0]
0x1800033d9  mov     rsi, [rsp+28h+arg_8]
0x1800033de  mov     rdi, [rsp+28h+arg_18]
0x1800033e3  add     rsp, 20h
0x1800033e7  pop     r14
0x1800033e9  retn
0x1800033ea  mov     ecx, 7
0x1800033ef  call    __scrt_fastfail
0x1800033f4  nop
0x1800033f5  int     3; Trap to Debugger
0x1800043d6  push    rbp
0x1800043d8  sub     rsp, 20h
0x1800043dc  mov     rbp, rdx
0x1800043df  mov     cl, [rbp+40h]
0x1800043e2  add     rsp, 20h
0x1800043e6  pop     rbp
0x1800043e7  jmp     __scrt_release_startup_lock
```
