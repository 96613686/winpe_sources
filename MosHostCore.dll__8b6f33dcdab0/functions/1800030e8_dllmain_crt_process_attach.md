# dllmain_crt_process_attach

- ea: `0x1800030e8`
- end: `0x1800031e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003090`

## callees

- `0x1800030e8`
- `0x180003440`
- `0x180003480`
- `0x1800034bc`
- `0x1800035bc`
- `0x180003690`
- `0x180003730`
- `0x180003c80`
- `0x180003ca8`
- `0x180003ccc`
- `0x180003cdc`
- `0x180003ce8`
- `0x180003e36`
- `0x180003e42`
- `0x180025010`

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
  ++dword_1800353D0;
  return 1;
}

```

## disassembly

```asm
0x1800030e8  push    rbx
0x1800030ea  push    rsi
0x1800030eb  push    rdi
0x1800030ec  push    r14
0x1800030ee  sub     rsp, 28h
0x1800030f2  mov     rsi, rdx
0x1800030f5  mov     r14, rcx
0x1800030f8  xor     ecx, ecx
0x1800030fa  call    __scrt_initialize_crt
0x1800030ff  test    al, al
0x180003101  jz      loc_1800031CA
0x180003107  call    __scrt_acquire_startup_lock
0x18000310c  mov     bl, al
0x18000310e  mov     [rsp+48h+arg_10], al
0x180003112  mov     dil, 1
0x180003115  cmp     cs:__scrt_current_native_startup_state, 0
0x18000311c  jnz     loc_1800031D6
0x180003122  mov     cs:__scrt_current_native_startup_state, 1
0x18000312c  call    __scrt_dllmain_before_initialize_c
0x180003131  test    al, al
0x180003133  jz      short loc_180003184
0x180003135  call    _RTC_Initialize
0x18000313a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000313f  call    __scrt_initialize_default_local_stdio_options
0x180003144  lea     rdx, __xi_z; Last
0x18000314b  lea     rcx, __xi_a; First
0x180003152  call    _initterm_e_0
0x180003157  test    eax, eax
0x180003159  jnz     short loc_180003184
0x18000315b  call    __scrt_dllmain_after_initialize_c
0x180003160  test    al, al
0x180003162  jz      short loc_180003184
0x180003164  lea     rdx, __xc_z; Last
0x18000316b  lea     rcx, __xc_a; First
0x180003172  call    _initterm_0
0x180003177  mov     cs:__scrt_current_native_startup_state, 2
0x180003181  xor     dil, dil
0x180003184  mov     cl, bl
0x180003186  call    __scrt_release_startup_lock
0x18000318b  test    dil, dil
0x18000318e  jnz     short loc_1800031CA
0x180003190  call    __scrt_get_dyn_tls_init_callback
0x180003195  mov     rbx, rax
0x180003198  cmp     qword ptr [rax], 0
0x18000319c  jz      short loc_1800031BD
0x18000319e  mov     rcx, rax
0x1800031a1  call    __scrt_is_nonwritable_in_current_image
0x1800031a6  test    al, al
0x1800031a8  jz      short loc_1800031BD
0x1800031aa  mov     r8, rsi
0x1800031ad  mov     edx, 2
0x1800031b2  mov     rcx, r14
0x1800031b5  mov     rax, [rbx]
0x1800031b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bd  inc     cs:dword_1800353D0
0x1800031c3  mov     eax, 1
0x1800031c8  jmp     short loc_1800031CC
0x1800031ca  xor     eax, eax
0x1800031cc  add     rsp, 28h
0x1800031d0  pop     r14
0x1800031d2  pop     rdi
0x1800031d3  pop     rsi
0x1800031d4  pop     rbx
0x1800031d5  retn
0x1800031d6  mov     ecx, 7
0x1800031db  call    __scrt_fastfail
0x180022fac  push    rbp
0x180022fae  sub     rsp, 20h
0x180022fb2  mov     rbp, rdx
0x180022fb5  mov     cl, [rbp+60h]
0x180022fb8  add     rsp, 20h
0x180022fbc  pop     rbp
0x180022fbd  jmp     __scrt_release_startup_lock
```
