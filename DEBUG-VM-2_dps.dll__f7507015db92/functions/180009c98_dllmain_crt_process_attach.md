# dllmain_crt_process_attach

- ea: `0x180009c98`
- end: `0x180009d92`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180009c40`

## callees

- `0x180009c98`
- `0x18000a0bc`
- `0x18000a0e4`
- `0x18000a108`
- `0x18000a148`
- `0x18000a184`
- `0x18000a284`
- `0x18000a358`
- `0x18000a3f8`
- `0x18000a454`
- `0x18000a464`
- `0x18000a470`
- `0x18000a7c6`
- `0x18000a7d2`
- `0x180019010`

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
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
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
  ++dword_180022090;
  return 1;
}

```

## disassembly

```asm
0x180009c98  push    rbx
0x180009c9a  push    rsi
0x180009c9b  push    rdi
0x180009c9c  push    r14
0x180009c9e  sub     rsp, 28h
0x180009ca2  mov     rsi, rdx
0x180009ca5  mov     r14, rcx
0x180009ca8  xor     ecx, ecx
0x180009caa  call    __scrt_initialize_crt
0x180009caf  test    al, al
0x180009cb1  jz      loc_180009D7A
0x180009cb7  call    __scrt_acquire_startup_lock
0x180009cbc  mov     bl, al
0x180009cbe  mov     [rsp+48h+arg_10], al
0x180009cc2  mov     dil, 1
0x180009cc5  cmp     cs:__scrt_current_native_startup_state, 0
0x180009ccc  jnz     loc_180009D86
0x180009cd2  mov     cs:__scrt_current_native_startup_state, 1
0x180009cdc  call    __scrt_dllmain_before_initialize_c
0x180009ce1  test    al, al
0x180009ce3  jz      short loc_180009D34
0x180009ce5  call    _RTC_Initialize
0x180009cea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180009cef  call    __scrt_initialize_default_local_stdio_options
0x180009cf4  lea     rdx, __xi_z; Last
0x180009cfb  lea     rcx, __xi_a; First
0x180009d02  call    _initterm_e_0
0x180009d07  test    eax, eax
0x180009d09  jnz     short loc_180009D34
0x180009d0b  call    __scrt_dllmain_after_initialize_c
0x180009d10  test    al, al
0x180009d12  jz      short loc_180009D34
0x180009d14  lea     rdx, __xc_z; Last
0x180009d1b  lea     rcx, __xc_a; First
0x180009d22  call    _initterm_0
0x180009d27  mov     cs:__scrt_current_native_startup_state, 2
0x180009d31  xor     dil, dil
0x180009d34  mov     cl, bl
0x180009d36  call    __scrt_release_startup_lock
0x180009d3b  test    dil, dil
0x180009d3e  jnz     short loc_180009D7A
0x180009d40  call    __scrt_get_dyn_tls_init_callback
0x180009d45  mov     rbx, rax
0x180009d48  cmp     qword ptr [rax], 0
0x180009d4c  jz      short loc_180009D6D
0x180009d4e  mov     rcx, rax
0x180009d51  call    __scrt_is_nonwritable_in_current_image
0x180009d56  test    al, al
0x180009d58  jz      short loc_180009D6D
0x180009d5a  mov     r8, rsi
0x180009d5d  mov     edx, 2
0x180009d62  mov     rcx, r14
0x180009d65  mov     rax, [rbx]
0x180009d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d6d  inc     cs:dword_180022090
0x180009d73  mov     eax, 1
0x180009d78  jmp     short loc_180009D7C
0x180009d7a  xor     eax, eax
0x180009d7c  add     rsp, 28h
0x180009d80  pop     r14
0x180009d82  pop     rdi
0x180009d83  pop     rsi
0x180009d84  pop     rbx
0x180009d85  retn
0x180009d86  mov     ecx, 7
0x180009d8b  call    __scrt_fastfail
0x180018bbc  push    rbp
0x180018bbe  sub     rsp, 20h
0x180018bc2  mov     rbp, rdx
0x180018bc5  mov     cl, [rbp+60h]
0x180018bc8  add     rsp, 20h
0x180018bcc  pop     rbp
0x180018bcd  jmp     __scrt_release_startup_lock
```
