# dllmain_crt_process_attach

- ea: `0x180002880`
- end: `0x180002996`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180002830`

## callees

- `0x180002880`
- `0x18000308c`
- `0x1800030b8`
- `0x180003178`
- `0x1800031b4`
- `0x1800031e8`
- `0x1800032e4`
- `0x1800033ac`
- `0x180003444`
- `0x180003508`
- `0x18000351c`
- `0x180003784`
- `0x180003d80`
- `0x180003db8`
- `0x1800603f0`

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
    JUMPOUT(0x180002996LL);
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
  ++dword_18007B2CC;
  return 1;
}

```

## disassembly

```asm
0x180002880  mov     [rsp+arg_0], rbx
0x180002885  mov     [rsp+arg_8], rsi
0x18000288a  mov     [rsp+arg_18], rdi
0x18000288f  push    r14
0x180002891  sub     rsp, 20h
0x180002895  mov     rsi, rdx
0x180002898  mov     r14, rcx
0x18000289b  xor     ecx, ecx
0x18000289d  call    __scrt_initialize_crt
0x1800028a2  test    al, al
0x1800028a4  jz      loc_180002972
0x1800028aa  call    __scrt_acquire_startup_lock
0x1800028af  mov     bl, al
0x1800028b1  mov     [rsp+28h+arg_10], al
0x1800028b5  mov     dil, 1
0x1800028b8  cmp     cs:__scrt_current_native_startup_state, 0
0x1800028bf  jnz     loc_18000298A
0x1800028c5  mov     cs:__scrt_current_native_startup_state, 1
0x1800028cf  call    __scrt_dllmain_before_initialize_c
0x1800028d4  test    al, al
0x1800028d6  jz      short loc_180002927
0x1800028d8  call    _RTC_Initialize
0x1800028dd  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800028e2  call    __scrt_initialize_default_local_stdio_options
0x1800028e7  lea     rdx, __xi_z; Last
0x1800028ee  lea     rcx, __xi_a; First
0x1800028f5  call    _initterm_e
0x1800028fa  test    eax, eax
0x1800028fc  jnz     short loc_180002927
0x1800028fe  call    __scrt_dllmain_after_initialize_c
0x180002903  test    al, al
0x180002905  jz      short loc_180002927
0x180002907  lea     rdx, __xc_z; Last
0x18000290e  lea     rcx, __xc_a; First
0x180002915  call    _initterm
0x18000291a  mov     cs:__scrt_current_native_startup_state, 2
0x180002924  xor     dil, dil
0x180002927  mov     cl, bl
0x180002929  call    __scrt_release_startup_lock
0x18000292e  test    dil, dil
0x180002931  jnz     short loc_180002972
0x180002933  call    __scrt_get_dyn_tls_init_callback
0x180002938  mov     rbx, rax
0x18000293b  cmp     qword ptr [rax], 0
0x18000293f  jz      short loc_180002965
0x180002941  mov     rcx, rax
0x180002944  call    __scrt_is_nonwritable_in_current_image
0x180002949  test    al, al
0x18000294b  jz      short loc_180002965
0x18000294d  mov     r8, rsi
0x180002950  mov     edx, 2
0x180002955  mov     rcx, r14
0x180002958  mov     rax, [rbx]
0x18000295b  mov     r9, cs:__guard_dispatch_icall_fptr
0x180002962  call    r9 ; _guard_dispatch_icall_nop
0x180002965  inc     cs:dword_18007B2CC
0x18000296b  mov     eax, 1
0x180002970  jmp     short loc_180002974
0x180002972  xor     eax, eax
0x180002974  mov     rbx, [rsp+28h+arg_0]
0x180002979  mov     rsi, [rsp+28h+arg_8]
0x18000297e  mov     rdi, [rsp+28h+arg_18]
0x180002983  add     rsp, 20h
0x180002987  pop     r14
0x180002989  retn
0x18000298a  mov     ecx, 7
0x18000298f  call    __scrt_fastfail
0x180002994  nop
0x180002995  int     3; Trap to Debugger
0x180061170  push    rbp
0x180061172  sub     rsp, 20h
0x180061176  mov     rbp, rdx
0x180061179  mov     cl, [rbp+40h]
0x18006117c  add     rsp, 20h
0x180061180  pop     rbp
0x180061181  jmp     __scrt_release_startup_lock
```
