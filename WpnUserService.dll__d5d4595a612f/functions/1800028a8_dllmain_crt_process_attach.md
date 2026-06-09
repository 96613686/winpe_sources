# dllmain_crt_process_attach

- ea: `0x1800028a8`
- end: `0x1800029a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002850`

## callees

- `0x1800028a8`
- `0x180002be4`
- `0x180002c24`
- `0x180002c60`
- `0x180002d60`
- `0x180002e34`
- `0x180002ed4`
- `0x180003088`
- `0x1800030b0`
- `0x1800030d4`
- `0x1800030e4`
- `0x1800030f0`
- `0x180003456`
- `0x180003462`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 v6; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v8)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( _scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v5 = 0;
      }
    }
  }
  LOBYTE(v6) = v4;
  _scrt_release_startup_lock(v6);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v8 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v8)(a1, 2, a2);
  }
  ++dword_180019430;
  return 1;
}

```

## disassembly

```asm
0x1800028a8  push    rbx
0x1800028aa  push    rsi
0x1800028ab  push    rdi
0x1800028ac  push    r14
0x1800028ae  sub     rsp, 28h
0x1800028b2  mov     rsi, rdx
0x1800028b5  mov     r14, rcx
0x1800028b8  xor     ecx, ecx
0x1800028ba  call    __scrt_initialize_crt
0x1800028bf  test    al, al
0x1800028c1  jz      loc_18000298A
0x1800028c7  call    __scrt_acquire_startup_lock
0x1800028cc  mov     bl, al
0x1800028ce  mov     [rsp+48h+arg_10], al
0x1800028d2  mov     dil, 1
0x1800028d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800028dc  jnz     loc_180002996
0x1800028e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800028ec  call    __scrt_dllmain_before_initialize_c
0x1800028f1  test    al, al
0x1800028f3  jz      short loc_180002944
0x1800028f5  call    _RTC_Initialize
0x1800028fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800028ff  call    __scrt_initialize_default_local_stdio_options
0x180002904  lea     rdx, __xi_z; Last
0x18000290b  lea     rcx, __xi_a; First
0x180002912  call    _initterm_e_0
0x180002917  test    eax, eax
0x180002919  jnz     short loc_180002944
0x18000291b  call    __scrt_dllmain_after_initialize_c
0x180002920  test    al, al
0x180002922  jz      short loc_180002944
0x180002924  lea     rdx, __xc_z; Last
0x18000292b  lea     rcx, __xc_a; First
0x180002932  call    _initterm_0
0x180002937  mov     cs:__scrt_current_native_startup_state, 2
0x180002941  xor     dil, dil
0x180002944  mov     cl, bl
0x180002946  call    __scrt_release_startup_lock
0x18000294b  test    dil, dil
0x18000294e  jnz     short loc_18000298A
0x180002950  call    __scrt_get_dyn_tls_init_callback
0x180002955  mov     rbx, rax
0x180002958  cmp     qword ptr [rax], 0
0x18000295c  jz      short loc_18000297D
0x18000295e  mov     rcx, rax
0x180002961  call    __scrt_is_nonwritable_in_current_image
0x180002966  test    al, al
0x180002968  jz      short loc_18000297D
0x18000296a  mov     r8, rsi
0x18000296d  mov     edx, 2
0x180002972  mov     rcx, r14
0x180002975  mov     rax, [rbx]
0x180002978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297d  inc     cs:dword_180019430
0x180002983  mov     eax, 1
0x180002988  jmp     short loc_18000298C
0x18000298a  xor     eax, eax
0x18000298c  add     rsp, 28h
0x180002990  pop     r14
0x180002992  pop     rdi
0x180002993  pop     rsi
0x180002994  pop     rbx
0x180002995  retn
0x180002996  mov     ecx, 7
0x18000299b  call    __scrt_fastfail
0x180010c8c  push    rbp
0x180010c8e  sub     rsp, 20h
0x180010c92  mov     rbp, rdx
0x180010c95  mov     cl, [rbp+60h]
0x180010c98  add     rsp, 20h
0x180010c9c  pop     rbp
0x180010c9d  jmp     __scrt_release_startup_lock
```
