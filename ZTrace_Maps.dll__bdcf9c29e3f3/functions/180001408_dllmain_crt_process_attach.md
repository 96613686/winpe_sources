# dllmain_crt_process_attach

- ea: `0x180001408`
- end: `0x180001502`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800013b0`

## callees

- `0x180001408`
- `0x180001798`
- `0x1800017d8`
- `0x180001814`
- `0x180001914`
- `0x1800019e8`
- `0x180001a88`
- `0x180001c00`
- `0x180001c28`
- `0x180001c4c`
- `0x180001c5c`
- `0x180001c68`
- `0x1800021e6`
- `0x1800021f2`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v7)(__int64, __int64, __int64); // rbx

  if ( !_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7u);
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
  _scrt_release_startup_lock(v4);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( _scrt_is_nonwritable_in_current_image((__int64)dyn_tls_init_callback) )
      (*v7)(a1, 2, a2);
  }
  ++dword_1800071D0;
  return 1;
}

```

## disassembly

```asm
0x180001408  push    rbx
0x18000140a  push    rsi
0x18000140b  push    rdi
0x18000140c  push    r14
0x18000140e  sub     rsp, 28h
0x180001412  mov     rsi, rdx
0x180001415  mov     r14, rcx
0x180001418  xor     ecx, ecx
0x18000141a  call    __scrt_initialize_crt
0x18000141f  test    al, al
0x180001421  jz      loc_1800014EA
0x180001427  call    __scrt_acquire_startup_lock
0x18000142c  mov     bl, al
0x18000142e  mov     [rsp+48h+arg_10], al
0x180001432  mov     dil, 1
0x180001435  cmp     cs:__scrt_current_native_startup_state, 0
0x18000143c  jnz     loc_1800014F6
0x180001442  mov     cs:__scrt_current_native_startup_state, 1
0x18000144c  call    __scrt_dllmain_before_initialize_c
0x180001451  test    al, al
0x180001453  jz      short loc_1800014A4
0x180001455  call    _RTC_Initialize
0x18000145a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000145f  call    __scrt_initialize_default_local_stdio_options
0x180001464  lea     rdx, __xi_z; Last
0x18000146b  lea     rcx, __xi_a; First
0x180001472  call    _initterm_e_0
0x180001477  test    eax, eax
0x180001479  jnz     short loc_1800014A4
0x18000147b  call    __scrt_dllmain_after_initialize_c
0x180001480  test    al, al
0x180001482  jz      short loc_1800014A4
0x180001484  lea     rdx, __xc_z; Last
0x18000148b  lea     rcx, __xc_a; First
0x180001492  call    _initterm_0
0x180001497  mov     cs:__scrt_current_native_startup_state, 2
0x1800014a1  xor     dil, dil
0x1800014a4  mov     cl, bl
0x1800014a6  call    __scrt_release_startup_lock
0x1800014ab  test    dil, dil
0x1800014ae  jnz     short loc_1800014EA
0x1800014b0  call    __scrt_get_dyn_tls_init_callback
0x1800014b5  mov     rbx, rax
0x1800014b8  cmp     qword ptr [rax], 0
0x1800014bc  jz      short loc_1800014DD
0x1800014be  mov     rcx, rax
0x1800014c1  call    __scrt_is_nonwritable_in_current_image
0x1800014c6  test    al, al
0x1800014c8  jz      short loc_1800014DD
0x1800014ca  mov     r8, rsi
0x1800014cd  mov     edx, 2
0x1800014d2  mov     rcx, r14
0x1800014d5  mov     rax, [rbx]
0x1800014d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014dd  inc     cs:dword_1800071D0
0x1800014e3  mov     eax, 1
0x1800014e8  jmp     short loc_1800014EC
0x1800014ea  xor     eax, eax
0x1800014ec  add     rsp, 28h
0x1800014f0  pop     r14
0x1800014f2  pop     rdi
0x1800014f3  pop     rsi
0x1800014f4  pop     rbx
0x1800014f5  retn
0x1800014f6  mov     ecx, 7
0x1800014fb  call    __scrt_fastfail
0x180003bac  push    rbp
0x180003bae  sub     rsp, 20h
0x180003bb2  mov     rbp, rdx
0x180003bb5  mov     cl, [rbp+60h]
0x180003bb8  add     rsp, 20h
0x180003bbc  pop     rbp
0x180003bbd  jmp     __scrt_release_startup_lock
```
