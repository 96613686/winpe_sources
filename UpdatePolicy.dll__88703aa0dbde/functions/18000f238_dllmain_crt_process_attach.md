# dllmain_crt_process_attach

- ea: `0x18000f238`
- end: `0x18000f349`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000f1e0`

## callees

- `0x18000ede0`
- `0x18000ee20`
- `0x18000ee5c`
- `0x18000ef80`
- `0x18000f054`
- `0x18000f0f4`
- `0x18000f238`
- `0x18000fa08`
- `0x18000fc48`
- `0x18000fc80`
- `0x18000fca4`
- `0x18000fcb4`
- `0x1800150f0`
- `0x1800150fc`
- `0x180015430`

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
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x18000F349LL);
  }
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
  ++dword_18001F814;
  return 1;
}

```

## disassembly

```asm
0x18000f238  mov     [rsp+arg_0], rbx
0x18000f23d  mov     [rsp+arg_8], rsi
0x18000f242  mov     [rsp+arg_18], rdi
0x18000f247  push    r14
0x18000f249  sub     rsp, 20h
0x18000f24d  mov     rsi, rdx
0x18000f250  mov     r14, rcx
0x18000f253  xor     ecx, ecx
0x18000f255  call    __scrt_initialize_crt
0x18000f25a  test    al, al
0x18000f25c  jz      loc_18000F325
0x18000f262  call    __scrt_acquire_startup_lock
0x18000f267  mov     bl, al
0x18000f269  mov     [rsp+28h+arg_10], al
0x18000f26d  mov     dil, 1
0x18000f270  cmp     cs:__scrt_current_native_startup_state, 0
0x18000f277  jnz     loc_18000F33D
0x18000f27d  mov     cs:__scrt_current_native_startup_state, 1
0x18000f287  call    __scrt_dllmain_before_initialize_c
0x18000f28c  test    al, al
0x18000f28e  jz      short loc_18000F2DF
0x18000f290  call    _RTC_Initialize
0x18000f295  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000f29a  call    __scrt_initialize_default_local_stdio_options
0x18000f29f  lea     rdx, __xi_z; Last
0x18000f2a6  lea     rcx, __xi_a; First
0x18000f2ad  call    _initterm_e_0
0x18000f2b2  test    eax, eax
0x18000f2b4  jnz     short loc_18000F2DF
0x18000f2b6  call    __scrt_dllmain_after_initialize_c
0x18000f2bb  test    al, al
0x18000f2bd  jz      short loc_18000F2DF
0x18000f2bf  lea     rdx, __xc_z; Last
0x18000f2c6  lea     rcx, __xc_a; First
0x18000f2cd  call    _initterm_0
0x18000f2d2  mov     cs:__scrt_current_native_startup_state, 2
0x18000f2dc  xor     dil, dil
0x18000f2df  mov     cl, bl
0x18000f2e1  call    __scrt_release_startup_lock
0x18000f2e6  test    dil, dil
0x18000f2e9  jnz     short loc_18000F325
0x18000f2eb  call    __scrt_get_dyn_tls_init_callback
0x18000f2f0  mov     rbx, rax
0x18000f2f3  cmp     qword ptr [rax], 0
0x18000f2f7  jz      short loc_18000F318
0x18000f2f9  mov     rcx, rax
0x18000f2fc  call    __scrt_is_nonwritable_in_current_image
0x18000f301  test    al, al
0x18000f303  jz      short loc_18000F318
0x18000f305  mov     r8, rsi
0x18000f308  mov     edx, 2
0x18000f30d  mov     rcx, r14
0x18000f310  mov     rax, [rbx]
0x18000f313  call    _guard_dispatch_icall
0x18000f318  inc     cs:dword_18001F814
0x18000f31e  mov     eax, 1
0x18000f323  jmp     short loc_18000F327
0x18000f325  xor     eax, eax
0x18000f327  mov     rbx, [rsp+28h+arg_0]
0x18000f32c  mov     rsi, [rsp+28h+arg_8]
0x18000f331  mov     rdi, [rsp+28h+arg_18]
0x18000f336  add     rsp, 20h
0x18000f33a  pop     r14
0x18000f33c  retn
0x18000f33d  mov     ecx, 7
0x18000f342  call    __scrt_fastfail
0x18000f347  nop
0x18000f348  int     3; Trap to Debugger
0x180016637  push    rbp
0x180016639  sub     rsp, 20h
0x18001663d  mov     rbp, rdx
0x180016640  mov     cl, [rbp+40h]
0x180016643  add     rsp, 20h
0x180016647  pop     rbp
0x180016648  jmp     __scrt_release_startup_lock
```
