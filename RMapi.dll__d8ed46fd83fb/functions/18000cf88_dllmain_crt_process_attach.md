# dllmain_crt_process_attach

- ea: `0x18000cf88`
- end: `0x18000d082`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000cf30`

## callees

- `0x18000cf88`
- `0x18000d3cc`
- `0x18000d40c`
- `0x18000d448`
- `0x18000d548`
- `0x18000d61c`
- `0x18000d6bc`
- `0x18000dc5c`
- `0x18000dc84`
- `0x18000dca8`
- `0x18000dcb8`
- `0x18000dcc4`
- `0x18000de16`
- `0x18000de22`
- `0x180028010`

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
  ++dword_180037A90;
  return 1;
}

```

## disassembly

```asm
0x18000cf88  push    rbx
0x18000cf8a  push    rsi
0x18000cf8b  push    rdi
0x18000cf8c  push    r14
0x18000cf8e  sub     rsp, 28h
0x18000cf92  mov     rsi, rdx
0x18000cf95  mov     r14, rcx
0x18000cf98  xor     ecx, ecx
0x18000cf9a  call    __scrt_initialize_crt
0x18000cf9f  test    al, al
0x18000cfa1  jz      loc_18000D06A
0x18000cfa7  call    __scrt_acquire_startup_lock
0x18000cfac  mov     bl, al
0x18000cfae  mov     [rsp+48h+arg_10], al
0x18000cfb2  mov     dil, 1
0x18000cfb5  cmp     cs:__scrt_current_native_startup_state, 0
0x18000cfbc  jnz     loc_18000D076
0x18000cfc2  mov     cs:__scrt_current_native_startup_state, 1
0x18000cfcc  call    __scrt_dllmain_before_initialize_c
0x18000cfd1  test    al, al
0x18000cfd3  jz      short loc_18000D024
0x18000cfd5  call    _RTC_Initialize
0x18000cfda  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000cfdf  call    __scrt_initialize_default_local_stdio_options
0x18000cfe4  lea     rdx, __xi_z; Last
0x18000cfeb  lea     rcx, __xi_a; First
0x18000cff2  call    _initterm_e_0
0x18000cff7  test    eax, eax
0x18000cff9  jnz     short loc_18000D024
0x18000cffb  call    __scrt_dllmain_after_initialize_c
0x18000d000  test    al, al
0x18000d002  jz      short loc_18000D024
0x18000d004  lea     rdx, __xc_z; Last
0x18000d00b  lea     rcx, __xc_a; First
0x18000d012  call    _initterm_0
0x18000d017  mov     cs:__scrt_current_native_startup_state, 2
0x18000d021  xor     dil, dil
0x18000d024  mov     cl, bl
0x18000d026  call    __scrt_release_startup_lock
0x18000d02b  test    dil, dil
0x18000d02e  jnz     short loc_18000D06A
0x18000d030  call    __scrt_get_dyn_tls_init_callback
0x18000d035  mov     rbx, rax
0x18000d038  cmp     qword ptr [rax], 0
0x18000d03c  jz      short loc_18000D05D
0x18000d03e  mov     rcx, rax
0x18000d041  call    __scrt_is_nonwritable_in_current_image
0x18000d046  test    al, al
0x18000d048  jz      short loc_18000D05D
0x18000d04a  mov     r8, rsi
0x18000d04d  mov     edx, 2
0x18000d052  mov     rcx, r14
0x18000d055  mov     rax, [rbx]
0x18000d058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d05d  inc     cs:dword_180037A90
0x18000d063  mov     eax, 1
0x18000d068  jmp     short loc_18000D06C
0x18000d06a  xor     eax, eax
0x18000d06c  add     rsp, 28h
0x18000d070  pop     r14
0x18000d072  pop     rdi
0x18000d073  pop     rsi
0x18000d074  pop     rbx
0x18000d075  retn
0x18000d076  mov     ecx, 7
0x18000d07b  call    __scrt_fastfail
0x180025839  push    rbp
0x18002583b  sub     rsp, 20h
0x18002583f  mov     rbp, rdx
0x180025842  mov     cl, [rbp+60h]
0x180025845  add     rsp, 20h
0x180025849  pop     rbp
0x18002584a  jmp     __scrt_release_startup_lock
```
