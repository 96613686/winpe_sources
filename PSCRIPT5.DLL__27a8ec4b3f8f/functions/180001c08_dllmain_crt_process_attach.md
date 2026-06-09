# dllmain_crt_process_attach

- ea: `0x180001c08`
- end: `0x180001d02`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001bb0`

## callees

- `0x180001c08`
- `0x180001f7c`
- `0x180001fbc`
- `0x180001ff8`
- `0x1800020f8`
- `0x1800021cc`
- `0x18000226c`
- `0x1800023e4`
- `0x18000240c`
- `0x180002430`
- `0x180002440`
- `0x18000244c`
- `0x1800027a6`
- `0x1800027b2`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 *dyn_tls_init_callback; // rax
  __int64 *v7; // rbx

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
  dyn_tls_init_callback = _scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( _scrt_is_nonwritable_in_current_image((__int64)dyn_tls_init_callback) )
      ((void (__fastcall *)(__int64, __int64, __int64))*v7)(a1, 2, a2);
  }
  ++dword_180076350;
  return 1;
}

```

## disassembly

```asm
0x180001c08  push    rbx
0x180001c0a  push    rsi
0x180001c0b  push    rdi
0x180001c0c  push    r14
0x180001c0e  sub     rsp, 28h
0x180001c12  mov     rsi, rdx
0x180001c15  mov     r14, rcx
0x180001c18  xor     ecx, ecx
0x180001c1a  call    __scrt_initialize_crt
0x180001c1f  test    al, al
0x180001c21  jz      loc_180001CEA
0x180001c27  call    __scrt_acquire_startup_lock
0x180001c2c  mov     bl, al
0x180001c2e  mov     [rsp+48h+arg_10], al
0x180001c32  mov     dil, 1
0x180001c35  cmp     cs:__scrt_current_native_startup_state, 0
0x180001c3c  jnz     loc_180001CF6
0x180001c42  mov     cs:__scrt_current_native_startup_state, 1
0x180001c4c  call    __scrt_dllmain_before_initialize_c
0x180001c51  test    al, al
0x180001c53  jz      short loc_180001CA4
0x180001c55  call    _RTC_Initialize
0x180001c5a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001c5f  call    __scrt_initialize_default_local_stdio_options
0x180001c64  lea     rdx, __xi_z; Last
0x180001c6b  lea     rcx, __xi_a; First
0x180001c72  call    _initterm_e_0
0x180001c77  test    eax, eax
0x180001c79  jnz     short loc_180001CA4
0x180001c7b  call    __scrt_dllmain_after_initialize_c
0x180001c80  test    al, al
0x180001c82  jz      short loc_180001CA4
0x180001c84  lea     rdx, __xc_z; Last
0x180001c8b  lea     rcx, __xc_a; First
0x180001c92  call    _initterm_0
0x180001c97  mov     cs:__scrt_current_native_startup_state, 2
0x180001ca1  xor     dil, dil
0x180001ca4  mov     cl, bl
0x180001ca6  call    __scrt_release_startup_lock
0x180001cab  test    dil, dil
0x180001cae  jnz     short loc_180001CEA
0x180001cb0  call    __scrt_get_dyn_tls_init_callback
0x180001cb5  mov     rbx, rax
0x180001cb8  cmp     qword ptr [rax], 0
0x180001cbc  jz      short loc_180001CDD
0x180001cbe  mov     rcx, rax
0x180001cc1  call    __scrt_is_nonwritable_in_current_image
0x180001cc6  test    al, al
0x180001cc8  jz      short loc_180001CDD
0x180001cca  mov     r8, rsi
0x180001ccd  mov     edx, 2
0x180001cd2  mov     rcx, r14
0x180001cd5  mov     rax, [rbx]
0x180001cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cdd  inc     cs:dword_180076350
0x180001ce3  mov     eax, 1
0x180001ce8  jmp     short loc_180001CEC
0x180001cea  xor     eax, eax
0x180001cec  add     rsp, 28h
0x180001cf0  pop     r14
0x180001cf2  pop     rdi
0x180001cf3  pop     rsi
0x180001cf4  pop     rbx
0x180001cf5  retn
0x180001cf6  mov     ecx, 7
0x180001cfb  call    __scrt_fastfail
0x18005e15c  push    rbp
0x18005e15e  sub     rsp, 20h
0x18005e162  mov     rbp, rdx
0x18005e165  mov     cl, [rbp+60h]
0x18005e168  add     rsp, 20h
0x18005e16c  pop     rbp
0x18005e16d  jmp     __scrt_release_startup_lock
```
