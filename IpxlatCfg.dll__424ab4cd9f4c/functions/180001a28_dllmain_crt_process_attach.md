# dllmain_crt_process_attach

- ea: `0x180001a28`
- end: `0x180001b22`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800019d0`

## callees

- `0x180001a28`
- `0x180001d64`
- `0x180001da4`
- `0x180001de0`
- `0x180001ee0`
- `0x180001fb4`
- `0x180002054`
- `0x180002508`
- `0x180002530`
- `0x180002554`
- `0x180002564`
- `0x180002570`
- `0x180002916`
- `0x180002922`
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
  ++dword_1800234D0;
  return 1;
}

```

## disassembly

```asm
0x180001a28  push    rbx
0x180001a2a  push    rsi
0x180001a2b  push    rdi
0x180001a2c  push    r14
0x180001a2e  sub     rsp, 28h
0x180001a32  mov     rsi, rdx
0x180001a35  mov     r14, rcx
0x180001a38  xor     ecx, ecx
0x180001a3a  call    __scrt_initialize_crt
0x180001a3f  test    al, al
0x180001a41  jz      loc_180001B0A
0x180001a47  call    __scrt_acquire_startup_lock
0x180001a4c  mov     bl, al
0x180001a4e  mov     [rsp+48h+arg_10], al
0x180001a52  mov     dil, 1
0x180001a55  cmp     cs:__scrt_current_native_startup_state, 0
0x180001a5c  jnz     loc_180001B16
0x180001a62  mov     cs:__scrt_current_native_startup_state, 1
0x180001a6c  call    __scrt_dllmain_before_initialize_c
0x180001a71  test    al, al
0x180001a73  jz      short loc_180001AC4
0x180001a75  call    _RTC_Initialize
0x180001a7a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001a7f  call    __scrt_initialize_default_local_stdio_options
0x180001a84  lea     rdx, __xi_z; Last
0x180001a8b  lea     rcx, __xi_a; First
0x180001a92  call    _initterm_e_0
0x180001a97  test    eax, eax
0x180001a99  jnz     short loc_180001AC4
0x180001a9b  call    __scrt_dllmain_after_initialize_c
0x180001aa0  test    al, al
0x180001aa2  jz      short loc_180001AC4
0x180001aa4  lea     rdx, __xc_z; Last
0x180001aab  lea     rcx, __xc_a; First
0x180001ab2  call    _initterm_0
0x180001ab7  mov     cs:__scrt_current_native_startup_state, 2
0x180001ac1  xor     dil, dil
0x180001ac4  mov     cl, bl
0x180001ac6  call    __scrt_release_startup_lock
0x180001acb  test    dil, dil
0x180001ace  jnz     short loc_180001B0A
0x180001ad0  call    __scrt_get_dyn_tls_init_callback
0x180001ad5  mov     rbx, rax
0x180001ad8  cmp     qword ptr [rax], 0
0x180001adc  jz      short loc_180001AFD
0x180001ade  mov     rcx, rax
0x180001ae1  call    __scrt_is_nonwritable_in_current_image
0x180001ae6  test    al, al
0x180001ae8  jz      short loc_180001AFD
0x180001aea  mov     r8, rsi
0x180001aed  mov     edx, 2
0x180001af2  mov     rcx, r14
0x180001af5  mov     rax, [rbx]
0x180001af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001afd  inc     cs:dword_1800234D0
0x180001b03  mov     eax, 1
0x180001b08  jmp     short loc_180001B0C
0x180001b0a  xor     eax, eax
0x180001b0c  add     rsp, 28h
0x180001b10  pop     r14
0x180001b12  pop     rdi
0x180001b13  pop     rsi
0x180001b14  pop     rbx
0x180001b15  retn
0x180001b16  mov     ecx, 7
0x180001b1b  call    __scrt_fastfail
0x180017efc  push    rbp
0x180017efe  sub     rsp, 20h
0x180017f02  mov     rbp, rdx
0x180017f05  mov     cl, [rbp+60h]
0x180017f08  add     rsp, 20h
0x180017f0c  pop     rbp
0x180017f0d  jmp     __scrt_release_startup_lock
```
