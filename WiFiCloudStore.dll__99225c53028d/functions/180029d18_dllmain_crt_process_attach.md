# dllmain_crt_process_attach

- ea: `0x180029d18`
- end: `0x180029e12`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180029cc0`

## callees

- `0x180029d18`
- `0x18002a054`
- `0x18002a094`
- `0x18002a0d0`
- `0x18002a1d0`
- `0x18002a2a4`
- `0x18002a344`
- `0x18002a528`
- `0x18002a550`
- `0x18002a574`
- `0x18002a584`
- `0x18002a590`
- `0x18002a996`
- `0x18002a9a2`
- `0x180041010`

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
  ++dword_1800524B0;
  return 1;
}

```

## disassembly

```asm
0x180029d18  push    rbx
0x180029d1a  push    rsi
0x180029d1b  push    rdi
0x180029d1c  push    r14
0x180029d1e  sub     rsp, 28h
0x180029d22  mov     rsi, rdx
0x180029d25  mov     r14, rcx
0x180029d28  xor     ecx, ecx
0x180029d2a  call    __scrt_initialize_crt
0x180029d2f  test    al, al
0x180029d31  jz      loc_180029DFA
0x180029d37  call    __scrt_acquire_startup_lock
0x180029d3c  mov     bl, al
0x180029d3e  mov     [rsp+48h+arg_10], al
0x180029d42  mov     dil, 1
0x180029d45  cmp     cs:__scrt_current_native_startup_state, 0
0x180029d4c  jnz     loc_180029E06
0x180029d52  mov     cs:__scrt_current_native_startup_state, 1
0x180029d5c  call    __scrt_dllmain_before_initialize_c
0x180029d61  test    al, al
0x180029d63  jz      short loc_180029DB4
0x180029d65  call    _RTC_Initialize
0x180029d6a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180029d6f  call    __scrt_initialize_default_local_stdio_options
0x180029d74  lea     rdx, __xi_z; Last
0x180029d7b  lea     rcx, __xi_a; First
0x180029d82  call    _initterm_e_0
0x180029d87  test    eax, eax
0x180029d89  jnz     short loc_180029DB4
0x180029d8b  call    __scrt_dllmain_after_initialize_c
0x180029d90  test    al, al
0x180029d92  jz      short loc_180029DB4
0x180029d94  lea     rdx, __xc_z; Last
0x180029d9b  lea     rcx, __xc_a; First
0x180029da2  call    _initterm_0
0x180029da7  mov     cs:__scrt_current_native_startup_state, 2
0x180029db1  xor     dil, dil
0x180029db4  mov     cl, bl
0x180029db6  call    __scrt_release_startup_lock
0x180029dbb  test    dil, dil
0x180029dbe  jnz     short loc_180029DFA
0x180029dc0  call    __scrt_get_dyn_tls_init_callback
0x180029dc5  mov     rbx, rax
0x180029dc8  cmp     qword ptr [rax], 0
0x180029dcc  jz      short loc_180029DED
0x180029dce  mov     rcx, rax
0x180029dd1  call    __scrt_is_nonwritable_in_current_image
0x180029dd6  test    al, al
0x180029dd8  jz      short loc_180029DED
0x180029dda  mov     r8, rsi
0x180029ddd  mov     edx, 2
0x180029de2  mov     rcx, r14
0x180029de5  mov     rax, [rbx]
0x180029de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ded  inc     cs:dword_1800524B0
0x180029df3  mov     eax, 1
0x180029df8  jmp     short loc_180029DFC
0x180029dfa  xor     eax, eax
0x180029dfc  add     rsp, 28h
0x180029e00  pop     r14
0x180029e02  pop     rdi
0x180029e03  pop     rsi
0x180029e04  pop     rbx
0x180029e05  retn
0x180029e06  mov     ecx, 7
0x180029e0b  call    __scrt_fastfail
0x18004001e  push    rbp
0x180040020  sub     rsp, 20h
0x180040024  mov     rbp, rdx
0x180040027  mov     cl, [rbp+60h]
0x18004002a  add     rsp, 20h
0x18004002e  pop     rbp
0x18004002f  jmp     __scrt_release_startup_lock
```
