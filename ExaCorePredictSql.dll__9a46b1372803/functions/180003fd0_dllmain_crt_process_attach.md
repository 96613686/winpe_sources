# dllmain_crt_process_attach

- ea: `0x180003fd0`
- end: `0x1800040fb`
- name: `dllmain_crt_process_attach`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x180003f80`

## callees

- `0x180003b64`
- `0x180003ba0`
- `0x180003bd4`
- `0x180003cd4`
- `0x180003dec`
- `0x180003e88`
- `0x180003f28`
- `0x180003fd0`
- `0x180004498`
- `0x18000467c`
- `0x180004870`
- `0x180004894`
- `0x1800048b0`
- `0x1800048b8`
- `0x1800049a8`
- `0x1800049ae`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v5; // bl
  char v6; // di
  __int64 v7; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v9)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v5 = _scrt_acquire_startup_lock();
  v6 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    atexit(RTC_Terminate);
    __scrt_initialize_type_info();
    atexit(__scrt_uninitialize_type_info);
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v6 = 0;
      }
    }
  }
  LOBYTE(v7) = v5;
  _scrt_release_startup_lock(v7);
  if ( v6 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v9 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v9)(a1, 2, a2);
  }
  ++dword_1800081A4;
  return 1;
}

```

## disassembly

```asm
0x180003fd0  mov     [rsp+arg_0], rbx
0x180003fd5  mov     [rsp+arg_8], rsi
0x180003fda  mov     [rsp+arg_18], rdi
0x180003fdf  push    r14
0x180003fe1  sub     rsp, 20h
0x180003fe5  mov     rsi, rdx
0x180003fe8  mov     r14, rcx
0x180003feb  xor     ecx, ecx
0x180003fed  call    __scrt_initialize_crt
0x180003ff2  test    al, al
0x180003ff4  jnz     short loc_180003FFD
0x180003ff6  xor     eax, eax
0x180003ff8  jmp     loc_1800040E5
0x180003ffd  call    __scrt_acquire_startup_lock
0x180004002  mov     bl, al
0x180004004  mov     [rsp+28h+arg_10], al
0x180004008  mov     dil, 1
0x18000400b  cmp     cs:__scrt_current_native_startup_state, 0
0x180004012  jz      short loc_18000401E
0x180004014  mov     ecx, 7
0x180004019  call    __scrt_fastfail
0x18000401e  mov     cs:__scrt_current_native_startup_state, 1
0x180004028  call    __scrt_dllmain_before_initialize_c
0x18000402d  test    al, al
0x18000402f  jz      short loc_180004098
0x180004031  call    _RTC_Initialize
0x180004036  lea     rcx, _RTC_Terminate; void (__cdecl *)()
0x18000403d  call    atexit
0x180004042  call    ?__scrt_initialize_type_info@@YAXXZ
0x180004047  lea     rcx, ?__scrt_uninitialize_type_info@@YAXXZ; void (__cdecl *)()
0x18000404e  call    atexit
0x180004053  call    __scrt_initialize_default_local_stdio_options
0x180004058  lea     rdx, __xi_z; Last
0x18000405f  lea     rcx, __xi_a; First
0x180004066  call    _initterm_e_0
0x18000406b  test    eax, eax
0x18000406d  jnz     short loc_180004098
0x18000406f  call    __scrt_dllmain_after_initialize_c
0x180004074  test    al, al
0x180004076  jz      short loc_180004098
0x180004078  lea     rdx, __xc_z; Last
0x18000407f  lea     rcx, __xc_a; First
0x180004086  call    _initterm_0
0x18000408b  mov     cs:__scrt_current_native_startup_state, 2
0x180004095  xor     dil, dil
0x180004098  mov     cl, bl
0x18000409a  call    __scrt_release_startup_lock
0x18000409f  test    dil, dil
0x1800040a2  jnz     loc_180003FF6
0x1800040a8  call    __scrt_get_dyn_tls_init_callback
0x1800040ad  mov     rbx, rax
0x1800040b0  cmp     qword ptr [rax], 0
0x1800040b4  jz      short loc_1800040DA
0x1800040b6  mov     rcx, rax
0x1800040b9  call    __scrt_is_nonwritable_in_current_image
0x1800040be  test    al, al
0x1800040c0  jz      short loc_1800040DA
0x1800040c2  mov     rbx, [rbx]
0x1800040c5  mov     rcx, rbx; Target
0x1800040c8  call    _guard_check_icall
0x1800040cd  mov     r8, rsi
0x1800040d0  mov     edx, 2
0x1800040d5  mov     rcx, r14
0x1800040d8  call    rbx
0x1800040da  inc     cs:dword_1800081A4
0x1800040e0  mov     eax, 1
0x1800040e5  mov     rbx, [rsp+28h+arg_0]
0x1800040ea  mov     rsi, [rsp+28h+arg_8]
0x1800040ef  mov     rdi, [rsp+28h+arg_18]
0x1800040f4  add     rsp, 20h
0x1800040f8  pop     r14
0x1800040fa  retn
0x180004ed1  push    rbp
0x180004ed3  sub     rsp, 20h
0x180004ed7  mov     rbp, rdx
0x180004eda  mov     cl, [rbp+40h]
0x180004edd  add     rsp, 20h
0x180004ee1  pop     rbp
0x180004ee2  jmp     __scrt_release_startup_lock
```
