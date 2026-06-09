# dllmain_crt_process_attach

- ea: `0x180001ee8`
- end: `0x180001fe2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001e90`

## callees

- `0x180001ee8`
- `0x180002224`
- `0x180002264`
- `0x1800022a0`
- `0x1800023a0`
- `0x180002474`
- `0x180002514`
- `0x180002a68`
- `0x180002a90`
- `0x180002ab4`
- `0x180002ac4`
- `0x180002ad0`
- `0x180002e76`
- `0x180002e82`
- `0x18000d010`

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
  ++dword_1800133B0;
  return 1;
}

```

## disassembly

```asm
0x180001ee8  push    rbx
0x180001eea  push    rsi
0x180001eeb  push    rdi
0x180001eec  push    r14
0x180001eee  sub     rsp, 28h
0x180001ef2  mov     rsi, rdx
0x180001ef5  mov     r14, rcx
0x180001ef8  xor     ecx, ecx
0x180001efa  call    __scrt_initialize_crt
0x180001eff  test    al, al
0x180001f01  jz      loc_180001FCA
0x180001f07  call    __scrt_acquire_startup_lock
0x180001f0c  mov     bl, al
0x180001f0e  mov     [rsp+48h+arg_10], al
0x180001f12  mov     dil, 1
0x180001f15  cmp     cs:__scrt_current_native_startup_state, 0
0x180001f1c  jnz     loc_180001FD6
0x180001f22  mov     cs:__scrt_current_native_startup_state, 1
0x180001f2c  call    __scrt_dllmain_before_initialize_c
0x180001f31  test    al, al
0x180001f33  jz      short loc_180001F84
0x180001f35  call    _RTC_Initialize
0x180001f3a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001f3f  call    __scrt_initialize_default_local_stdio_options
0x180001f44  lea     rdx, __xi_z; Last
0x180001f4b  lea     rcx, __xi_a; First
0x180001f52  call    _initterm_e_0
0x180001f57  test    eax, eax
0x180001f59  jnz     short loc_180001F84
0x180001f5b  call    __scrt_dllmain_after_initialize_c
0x180001f60  test    al, al
0x180001f62  jz      short loc_180001F84
0x180001f64  lea     rdx, __xc_z; Last
0x180001f6b  lea     rcx, __xc_a; First
0x180001f72  call    _initterm_0
0x180001f77  mov     cs:__scrt_current_native_startup_state, 2
0x180001f81  xor     dil, dil
0x180001f84  mov     cl, bl
0x180001f86  call    __scrt_release_startup_lock
0x180001f8b  test    dil, dil
0x180001f8e  jnz     short loc_180001FCA
0x180001f90  call    __scrt_get_dyn_tls_init_callback
0x180001f95  mov     rbx, rax
0x180001f98  cmp     qword ptr [rax], 0
0x180001f9c  jz      short loc_180001FBD
0x180001f9e  mov     rcx, rax
0x180001fa1  call    __scrt_is_nonwritable_in_current_image
0x180001fa6  test    al, al
0x180001fa8  jz      short loc_180001FBD
0x180001faa  mov     r8, rsi
0x180001fad  mov     edx, 2
0x180001fb2  mov     rcx, r14
0x180001fb5  mov     rax, [rbx]
0x180001fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fbd  inc     cs:dword_1800133B0
0x180001fc3  mov     eax, 1
0x180001fc8  jmp     short loc_180001FCC
0x180001fca  xor     eax, eax
0x180001fcc  add     rsp, 28h
0x180001fd0  pop     r14
0x180001fd2  pop     rdi
0x180001fd3  pop     rsi
0x180001fd4  pop     rbx
0x180001fd5  retn
0x180001fd6  mov     ecx, 7
0x180001fdb  call    __scrt_fastfail
0x18000be1c  push    rbp
0x18000be1e  sub     rsp, 20h
0x18000be22  mov     rbp, rdx
0x18000be25  mov     cl, [rbp+60h]
0x18000be28  add     rsp, 20h
0x18000be2c  pop     rbp
0x18000be2d  jmp     __scrt_release_startup_lock
```
