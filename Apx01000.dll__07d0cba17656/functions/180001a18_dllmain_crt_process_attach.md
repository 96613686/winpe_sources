# dllmain_crt_process_attach

- ea: `0x180001a18`
- end: `0x180001b12`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800019c0`

## callees

- `0x180001a18`
- `0x180001d54`
- `0x180001d94`
- `0x180001dd0`
- `0x180001ed0`
- `0x180001fa4`
- `0x180002044`
- `0x180002284`
- `0x1800022ac`
- `0x1800022d0`
- `0x1800022e0`
- `0x1800022ec`
- `0x1800026a6`
- `0x1800026b2`
- `0x18002a010`

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
  ++dword_1800333B0;
  return 1;
}

```

## disassembly

```asm
0x180001a18  push    rbx
0x180001a1a  push    rsi
0x180001a1b  push    rdi
0x180001a1c  push    r14
0x180001a1e  sub     rsp, 28h
0x180001a22  mov     rsi, rdx
0x180001a25  mov     r14, rcx
0x180001a28  xor     ecx, ecx
0x180001a2a  call    __scrt_initialize_crt
0x180001a2f  test    al, al
0x180001a31  jz      loc_180001AFA
0x180001a37  call    __scrt_acquire_startup_lock
0x180001a3c  mov     bl, al
0x180001a3e  mov     [rsp+48h+arg_10], al
0x180001a42  mov     dil, 1
0x180001a45  cmp     cs:__scrt_current_native_startup_state, 0
0x180001a4c  jnz     loc_180001B06
0x180001a52  mov     cs:__scrt_current_native_startup_state, 1
0x180001a5c  call    __scrt_dllmain_before_initialize_c
0x180001a61  test    al, al
0x180001a63  jz      short loc_180001AB4
0x180001a65  call    _RTC_Initialize
0x180001a6a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001a6f  call    __scrt_initialize_default_local_stdio_options
0x180001a74  lea     rdx, __xi_z; Last
0x180001a7b  lea     rcx, __xi_a; First
0x180001a82  call    _initterm_e_0
0x180001a87  test    eax, eax
0x180001a89  jnz     short loc_180001AB4
0x180001a8b  call    __scrt_dllmain_after_initialize_c
0x180001a90  test    al, al
0x180001a92  jz      short loc_180001AB4
0x180001a94  lea     rdx, __xc_z; Last
0x180001a9b  lea     rcx, __xc_a; First
0x180001aa2  call    _initterm_0
0x180001aa7  mov     cs:__scrt_current_native_startup_state, 2
0x180001ab1  xor     dil, dil
0x180001ab4  mov     cl, bl
0x180001ab6  call    __scrt_release_startup_lock
0x180001abb  test    dil, dil
0x180001abe  jnz     short loc_180001AFA
0x180001ac0  call    __scrt_get_dyn_tls_init_callback
0x180001ac5  mov     rbx, rax
0x180001ac8  cmp     qword ptr [rax], 0
0x180001acc  jz      short loc_180001AED
0x180001ace  mov     rcx, rax
0x180001ad1  call    __scrt_is_nonwritable_in_current_image
0x180001ad6  test    al, al
0x180001ad8  jz      short loc_180001AED
0x180001ada  mov     r8, rsi
0x180001add  mov     edx, 2
0x180001ae2  mov     rcx, r14
0x180001ae5  mov     rax, [rbx]
0x180001ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aed  inc     cs:dword_1800333B0
0x180001af3  mov     eax, 1
0x180001af8  jmp     short loc_180001AFC
0x180001afa  xor     eax, eax
0x180001afc  add     rsp, 28h
0x180001b00  pop     r14
0x180001b02  pop     rdi
0x180001b03  pop     rsi
0x180001b04  pop     rbx
0x180001b05  retn
0x180001b06  mov     ecx, 7
0x180001b0b  call    __scrt_fastfail
0x18002990c  push    rbp
0x18002990e  sub     rsp, 20h
0x180029912  mov     rbp, rdx
0x180029915  mov     cl, [rbp+60h]
0x180029918  add     rsp, 20h
0x18002991c  pop     rbp
0x18002991d  jmp     __scrt_release_startup_lock
```
