# dllmain_crt_process_attach

- ea: `0x1800024a8`
- end: `0x1800025a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002450`

## callees

- `0x1800024a8`
- `0x1800027e4`
- `0x180002824`
- `0x180002860`
- `0x180002960`
- `0x180002a34`
- `0x180002ad4`
- `0x180002fe8`
- `0x180003010`
- `0x180003034`
- `0x180003044`
- `0x180003050`
- `0x180003176`
- `0x180003182`
- `0x180031010`

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
  ++dword_180049410;
  return 1;
}

```

## disassembly

```asm
0x1800024a8  push    rbx
0x1800024aa  push    rsi
0x1800024ab  push    rdi
0x1800024ac  push    r14
0x1800024ae  sub     rsp, 28h
0x1800024b2  mov     rsi, rdx
0x1800024b5  mov     r14, rcx
0x1800024b8  xor     ecx, ecx
0x1800024ba  call    __scrt_initialize_crt
0x1800024bf  test    al, al
0x1800024c1  jz      loc_18000258A
0x1800024c7  call    __scrt_acquire_startup_lock
0x1800024cc  mov     bl, al
0x1800024ce  mov     [rsp+48h+arg_10], al
0x1800024d2  mov     dil, 1
0x1800024d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800024dc  jnz     loc_180002596
0x1800024e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800024ec  call    __scrt_dllmain_before_initialize_c
0x1800024f1  test    al, al
0x1800024f3  jz      short loc_180002544
0x1800024f5  call    _RTC_Initialize
0x1800024fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800024ff  call    __scrt_initialize_default_local_stdio_options
0x180002504  lea     rdx, __xi_z; Last
0x18000250b  lea     rcx, __xi_a; First
0x180002512  call    _initterm_e_0
0x180002517  test    eax, eax
0x180002519  jnz     short loc_180002544
0x18000251b  call    __scrt_dllmain_after_initialize_c
0x180002520  test    al, al
0x180002522  jz      short loc_180002544
0x180002524  lea     rdx, __xc_z; Last
0x18000252b  lea     rcx, __xc_a; First
0x180002532  call    _initterm_0
0x180002537  mov     cs:__scrt_current_native_startup_state, 2
0x180002541  xor     dil, dil
0x180002544  mov     cl, bl
0x180002546  call    __scrt_release_startup_lock
0x18000254b  test    dil, dil
0x18000254e  jnz     short loc_18000258A
0x180002550  call    __scrt_get_dyn_tls_init_callback
0x180002555  mov     rbx, rax
0x180002558  cmp     qword ptr [rax], 0
0x18000255c  jz      short loc_18000257D
0x18000255e  mov     rcx, rax
0x180002561  call    __scrt_is_nonwritable_in_current_image
0x180002566  test    al, al
0x180002568  jz      short loc_18000257D
0x18000256a  mov     r8, rsi
0x18000256d  mov     edx, 2
0x180002572  mov     rcx, r14
0x180002575  mov     rax, [rbx]
0x180002578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257d  inc     cs:dword_180049410
0x180002583  mov     eax, 1
0x180002588  jmp     short loc_18000258C
0x18000258a  xor     eax, eax
0x18000258c  add     rsp, 28h
0x180002590  pop     r14
0x180002592  pop     rdi
0x180002593  pop     rsi
0x180002594  pop     rbx
0x180002595  retn
0x180002596  mov     ecx, 7
0x18000259b  call    __scrt_fastfail
0x18002e34c  push    rbp
0x18002e34e  sub     rsp, 20h
0x18002e352  mov     rbp, rdx
0x18002e355  mov     cl, [rbp+60h]
0x18002e358  add     rsp, 20h
0x18002e35c  pop     rbp
0x18002e35d  jmp     __scrt_release_startup_lock
```
