# dllmain_crt_process_attach

- ea: `0x180003388`
- end: `0x180003482`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003330`

## callees

- `0x180003388`
- `0x1800036c4`
- `0x180003704`
- `0x180003740`
- `0x180003840`
- `0x180003914`
- `0x1800039b4`
- `0x180003b68`
- `0x180003b90`
- `0x180003bb4`
- `0x180003bc4`
- `0x180003bd0`
- `0x180003f36`
- `0x180003f42`
- `0x18001c010`

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
  ++dword_1800253F0;
  return 1;
}

```

## disassembly

```asm
0x180003388  push    rbx
0x18000338a  push    rsi
0x18000338b  push    rdi
0x18000338c  push    r14
0x18000338e  sub     rsp, 28h
0x180003392  mov     rsi, rdx
0x180003395  mov     r14, rcx
0x180003398  xor     ecx, ecx
0x18000339a  call    __scrt_initialize_crt
0x18000339f  test    al, al
0x1800033a1  jz      loc_18000346A
0x1800033a7  call    __scrt_acquire_startup_lock
0x1800033ac  mov     bl, al
0x1800033ae  mov     [rsp+48h+arg_10], al
0x1800033b2  mov     dil, 1
0x1800033b5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800033bc  jnz     loc_180003476
0x1800033c2  mov     cs:__scrt_current_native_startup_state, 1
0x1800033cc  call    __scrt_dllmain_before_initialize_c
0x1800033d1  test    al, al
0x1800033d3  jz      short loc_180003424
0x1800033d5  call    _RTC_Initialize
0x1800033da  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800033df  call    __scrt_initialize_default_local_stdio_options
0x1800033e4  lea     rdx, __xi_z; Last
0x1800033eb  lea     rcx, __xi_a; First
0x1800033f2  call    _initterm_e_0
0x1800033f7  test    eax, eax
0x1800033f9  jnz     short loc_180003424
0x1800033fb  call    __scrt_dllmain_after_initialize_c
0x180003400  test    al, al
0x180003402  jz      short loc_180003424
0x180003404  lea     rdx, __xc_z; Last
0x18000340b  lea     rcx, __xc_a; First
0x180003412  call    _initterm_0
0x180003417  mov     cs:__scrt_current_native_startup_state, 2
0x180003421  xor     dil, dil
0x180003424  mov     cl, bl
0x180003426  call    __scrt_release_startup_lock
0x18000342b  test    dil, dil
0x18000342e  jnz     short loc_18000346A
0x180003430  call    __scrt_get_dyn_tls_init_callback
0x180003435  mov     rbx, rax
0x180003438  cmp     qword ptr [rax], 0
0x18000343c  jz      short loc_18000345D
0x18000343e  mov     rcx, rax
0x180003441  call    __scrt_is_nonwritable_in_current_image
0x180003446  test    al, al
0x180003448  jz      short loc_18000345D
0x18000344a  mov     r8, rsi
0x18000344d  mov     edx, 2
0x180003452  mov     rcx, r14
0x180003455  mov     rax, [rbx]
0x180003458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345d  inc     cs:dword_1800253F0
0x180003463  mov     eax, 1
0x180003468  jmp     short loc_18000346C
0x18000346a  xor     eax, eax
0x18000346c  add     rsp, 28h
0x180003470  pop     r14
0x180003472  pop     rdi
0x180003473  pop     rsi
0x180003474  pop     rbx
0x180003475  retn
0x180003476  mov     ecx, 7
0x18000347b  call    __scrt_fastfail
0x18001b4d0  push    rbp
0x18001b4d2  sub     rsp, 20h
0x18001b4d6  mov     rbp, rdx
0x18001b4d9  mov     cl, [rbp+60h]
0x18001b4dc  add     rsp, 20h
0x18001b4e0  pop     rbp
0x18001b4e1  jmp     __scrt_release_startup_lock
```
