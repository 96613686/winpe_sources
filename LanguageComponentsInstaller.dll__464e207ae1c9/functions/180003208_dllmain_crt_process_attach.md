# dllmain_crt_process_attach

- ea: `0x180003208`
- end: `0x180003302`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800031b0`

## callees

- `0x180003208`
- `0x18000367c`
- `0x1800036bc`
- `0x1800036f8`
- `0x1800037f8`
- `0x1800038cc`
- `0x18000396c`
- `0x180003e50`
- `0x180003e78`
- `0x180003e9c`
- `0x180003eac`
- `0x180003eb8`
- `0x180003fc6`
- `0x180003fd2`
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
  ++dword_180037518;
  return 1;
}

```

## disassembly

```asm
0x180003208  push    rbx
0x18000320a  push    rsi
0x18000320b  push    rdi
0x18000320c  push    r14
0x18000320e  sub     rsp, 28h
0x180003212  mov     rsi, rdx
0x180003215  mov     r14, rcx
0x180003218  xor     ecx, ecx
0x18000321a  call    __scrt_initialize_crt
0x18000321f  test    al, al
0x180003221  jz      loc_1800032EA
0x180003227  call    __scrt_acquire_startup_lock
0x18000322c  mov     bl, al
0x18000322e  mov     [rsp+48h+arg_10], al
0x180003232  mov     dil, 1
0x180003235  cmp     cs:__scrt_current_native_startup_state, 0
0x18000323c  jnz     loc_1800032F6
0x180003242  mov     cs:__scrt_current_native_startup_state, 1
0x18000324c  call    __scrt_dllmain_before_initialize_c
0x180003251  test    al, al
0x180003253  jz      short loc_1800032A4
0x180003255  call    _RTC_Initialize
0x18000325a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000325f  call    __scrt_initialize_default_local_stdio_options
0x180003264  lea     rdx, __xi_z; Last
0x18000326b  lea     rcx, __xi_a; First
0x180003272  call    _initterm_e_0
0x180003277  test    eax, eax
0x180003279  jnz     short loc_1800032A4
0x18000327b  call    __scrt_dllmain_after_initialize_c
0x180003280  test    al, al
0x180003282  jz      short loc_1800032A4
0x180003284  lea     rdx, __xc_z; Last
0x18000328b  lea     rcx, __xc_a; First
0x180003292  call    _initterm_0
0x180003297  mov     cs:__scrt_current_native_startup_state, 2
0x1800032a1  xor     dil, dil
0x1800032a4  mov     cl, bl
0x1800032a6  call    __scrt_release_startup_lock
0x1800032ab  test    dil, dil
0x1800032ae  jnz     short loc_1800032EA
0x1800032b0  call    __scrt_get_dyn_tls_init_callback
0x1800032b5  mov     rbx, rax
0x1800032b8  cmp     qword ptr [rax], 0
0x1800032bc  jz      short loc_1800032DD
0x1800032be  mov     rcx, rax
0x1800032c1  call    __scrt_is_nonwritable_in_current_image
0x1800032c6  test    al, al
0x1800032c8  jz      short loc_1800032DD
0x1800032ca  mov     r8, rsi
0x1800032cd  mov     edx, 2
0x1800032d2  mov     rcx, r14
0x1800032d5  mov     rax, [rbx]
0x1800032d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032dd  inc     cs:dword_180037518
0x1800032e3  mov     eax, 1
0x1800032e8  jmp     short loc_1800032EC
0x1800032ea  xor     eax, eax
0x1800032ec  add     rsp, 28h
0x1800032f0  pop     r14
0x1800032f2  pop     rdi
0x1800032f3  pop     rsi
0x1800032f4  pop     rbx
0x1800032f5  retn
0x1800032f6  mov     ecx, 7
0x1800032fb  call    __scrt_fastfail
0x180027d6c  push    rbp
0x180027d6e  sub     rsp, 20h
0x180027d72  mov     rbp, rdx
0x180027d75  mov     cl, [rbp+60h]
0x180027d78  add     rsp, 20h
0x180027d7c  pop     rbp
0x180027d7d  jmp     __scrt_release_startup_lock
```
