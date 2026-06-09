# dllmain_crt_process_attach

- ea: `0x1800246d8`
- end: `0x1800247d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180024680`

## callees

- `0x1800246d8`
- `0x180024a4c`
- `0x180024a8c`
- `0x180024ac8`
- `0x180024bc8`
- `0x180024c9c`
- `0x180024d3c`
- `0x180024ff8`
- `0x180025020`
- `0x180025044`
- `0x180025054`
- `0x180025060`
- `0x1800253b6`
- `0x1800253c2`
- `0x18003c010`

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
  ++dword_18004B290;
  return 1;
}

```

## disassembly

```asm
0x1800246d8  push    rbx
0x1800246da  push    rsi
0x1800246db  push    rdi
0x1800246dc  push    r14
0x1800246de  sub     rsp, 28h
0x1800246e2  mov     rsi, rdx
0x1800246e5  mov     r14, rcx
0x1800246e8  xor     ecx, ecx
0x1800246ea  call    __scrt_initialize_crt
0x1800246ef  test    al, al
0x1800246f1  jz      loc_1800247BA
0x1800246f7  call    __scrt_acquire_startup_lock
0x1800246fc  mov     bl, al
0x1800246fe  mov     [rsp+48h+arg_10], al
0x180024702  mov     dil, 1
0x180024705  cmp     cs:__scrt_current_native_startup_state, 0
0x18002470c  jnz     loc_1800247C6
0x180024712  mov     cs:__scrt_current_native_startup_state, 1
0x18002471c  call    __scrt_dllmain_before_initialize_c
0x180024721  test    al, al
0x180024723  jz      short loc_180024774
0x180024725  call    _RTC_Initialize
0x18002472a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18002472f  call    __scrt_initialize_default_local_stdio_options
0x180024734  lea     rdx, __xi_z; Last
0x18002473b  lea     rcx, __xi_a; First
0x180024742  call    _initterm_e_0
0x180024747  test    eax, eax
0x180024749  jnz     short loc_180024774
0x18002474b  call    __scrt_dllmain_after_initialize_c
0x180024750  test    al, al
0x180024752  jz      short loc_180024774
0x180024754  lea     rdx, __xc_z; Last
0x18002475b  lea     rcx, __xc_a; First
0x180024762  call    _initterm_0
0x180024767  mov     cs:__scrt_current_native_startup_state, 2
0x180024771  xor     dil, dil
0x180024774  mov     cl, bl
0x180024776  call    __scrt_release_startup_lock
0x18002477b  test    dil, dil
0x18002477e  jnz     short loc_1800247BA
0x180024780  call    __scrt_get_dyn_tls_init_callback
0x180024785  mov     rbx, rax
0x180024788  cmp     qword ptr [rax], 0
0x18002478c  jz      short loc_1800247AD
0x18002478e  mov     rcx, rax
0x180024791  call    __scrt_is_nonwritable_in_current_image
0x180024796  test    al, al
0x180024798  jz      short loc_1800247AD
0x18002479a  mov     r8, rsi
0x18002479d  mov     edx, 2
0x1800247a2  mov     rcx, r14
0x1800247a5  mov     rax, [rbx]
0x1800247a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ad  inc     cs:dword_18004B290
0x1800247b3  mov     eax, 1
0x1800247b8  jmp     short loc_1800247BC
0x1800247ba  xor     eax, eax
0x1800247bc  add     rsp, 28h
0x1800247c0  pop     r14
0x1800247c2  pop     rdi
0x1800247c3  pop     rsi
0x1800247c4  pop     rbx
0x1800247c5  retn
0x1800247c6  mov     ecx, 7
0x1800247cb  call    __scrt_fastfail
0x18003a817  push    rbp
0x18003a819  sub     rsp, 20h
0x18003a81d  mov     rbp, rdx
0x18003a820  mov     cl, [rbp+60h]
0x18003a823  add     rsp, 20h
0x18003a827  pop     rbp
0x18003a828  jmp     __scrt_release_startup_lock
```
