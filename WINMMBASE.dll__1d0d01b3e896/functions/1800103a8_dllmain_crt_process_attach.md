# dllmain_crt_process_attach

- ea: `0x1800103a8`
- end: `0x1800104a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180010350`

## callees

- `0x1800103a8`
- `0x180010710`
- `0x180010750`
- `0x18001078c`
- `0x18001088c`
- `0x180010960`
- `0x180010a00`
- `0x180010bb8`
- `0x180010be0`
- `0x180010c04`
- `0x180010c14`
- `0x180010c20`
- `0x180010f46`
- `0x180010f52`
- `0x180021010`

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
  ++dword_18002C450;
  return 1;
}

```

## disassembly

```asm
0x1800103a8  push    rbx
0x1800103aa  push    rsi
0x1800103ab  push    rdi
0x1800103ac  push    r14
0x1800103ae  sub     rsp, 28h
0x1800103b2  mov     rsi, rdx
0x1800103b5  mov     r14, rcx
0x1800103b8  xor     ecx, ecx
0x1800103ba  call    __scrt_initialize_crt
0x1800103bf  test    al, al
0x1800103c1  jz      loc_18001048A
0x1800103c7  call    __scrt_acquire_startup_lock
0x1800103cc  mov     bl, al
0x1800103ce  mov     [rsp+48h+arg_10], al
0x1800103d2  mov     dil, 1
0x1800103d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800103dc  jnz     loc_180010496
0x1800103e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800103ec  call    __scrt_dllmain_before_initialize_c
0x1800103f1  test    al, al
0x1800103f3  jz      short loc_180010444
0x1800103f5  call    _RTC_Initialize
0x1800103fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800103ff  call    __scrt_initialize_default_local_stdio_options
0x180010404  lea     rdx, __xi_z; Last
0x18001040b  lea     rcx, __xi_a; First
0x180010412  call    _initterm_e_0
0x180010417  test    eax, eax
0x180010419  jnz     short loc_180010444
0x18001041b  call    __scrt_dllmain_after_initialize_c
0x180010420  test    al, al
0x180010422  jz      short loc_180010444
0x180010424  lea     rdx, __xc_z; Last
0x18001042b  lea     rcx, __xc_a; First
0x180010432  call    _initterm_0
0x180010437  mov     cs:__scrt_current_native_startup_state, 2
0x180010441  xor     dil, dil
0x180010444  mov     cl, bl
0x180010446  call    __scrt_release_startup_lock
0x18001044b  test    dil, dil
0x18001044e  jnz     short loc_18001048A
0x180010450  call    __scrt_get_dyn_tls_init_callback
0x180010455  mov     rbx, rax
0x180010458  cmp     qword ptr [rax], 0
0x18001045c  jz      short loc_18001047D
0x18001045e  mov     rcx, rax
0x180010461  call    __scrt_is_nonwritable_in_current_image
0x180010466  test    al, al
0x180010468  jz      short loc_18001047D
0x18001046a  mov     r8, rsi
0x18001046d  mov     edx, 2
0x180010472  mov     rcx, r14
0x180010475  mov     rax, [rbx]
0x180010478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001047d  inc     cs:dword_18002C450
0x180010483  mov     eax, 1
0x180010488  jmp     short loc_18001048C
0x18001048a  xor     eax, eax
0x18001048c  add     rsp, 28h
0x180010490  pop     r14
0x180010492  pop     rdi
0x180010493  pop     rsi
0x180010494  pop     rbx
0x180010495  retn
0x180010496  mov     ecx, 7
0x18001049b  call    __scrt_fastfail
0x180020a48  push    rbp
0x180020a4a  sub     rsp, 20h
0x180020a4e  mov     rbp, rdx
0x180020a51  mov     cl, [rbp+60h]
0x180020a54  add     rsp, 20h
0x180020a58  pop     rbp
0x180020a59  jmp     __scrt_release_startup_lock
```
