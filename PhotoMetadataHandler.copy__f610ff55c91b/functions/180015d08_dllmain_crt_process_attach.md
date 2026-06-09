# dllmain_crt_process_attach

- ea: `0x180015d08`
- end: `0x180015e02`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180015cb0`

## callees

- `0x180015d08`
- `0x18001609c`
- `0x1800160dc`
- `0x180016118`
- `0x180016218`
- `0x1800162ec`
- `0x18001638c`
- `0x180016504`
- `0x18001652c`
- `0x180016550`
- `0x180016560`
- `0x18001656c`
- `0x180016896`
- `0x1800168a2`
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
  ++dword_180098DB0;
  return 1;
}

```

## disassembly

```asm
0x180015d08  push    rbx
0x180015d0a  push    rsi
0x180015d0b  push    rdi
0x180015d0c  push    r14
0x180015d0e  sub     rsp, 28h
0x180015d12  mov     rsi, rdx
0x180015d15  mov     r14, rcx
0x180015d18  xor     ecx, ecx
0x180015d1a  call    __scrt_initialize_crt
0x180015d1f  test    al, al
0x180015d21  jz      loc_180015DEA
0x180015d27  call    __scrt_acquire_startup_lock
0x180015d2c  mov     bl, al
0x180015d2e  mov     [rsp+48h+arg_10], al
0x180015d32  mov     dil, 1
0x180015d35  cmp     cs:__scrt_current_native_startup_state, 0
0x180015d3c  jnz     loc_180015DF6
0x180015d42  mov     cs:__scrt_current_native_startup_state, 1
0x180015d4c  call    __scrt_dllmain_before_initialize_c
0x180015d51  test    al, al
0x180015d53  jz      short loc_180015DA4
0x180015d55  call    _RTC_Initialize
0x180015d5a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180015d5f  call    __scrt_initialize_default_local_stdio_options
0x180015d64  lea     rdx, __xi_z; Last
0x180015d6b  lea     rcx, __xi_a; First
0x180015d72  call    _initterm_e_0
0x180015d77  test    eax, eax
0x180015d79  jnz     short loc_180015DA4
0x180015d7b  call    __scrt_dllmain_after_initialize_c
0x180015d80  test    al, al
0x180015d82  jz      short loc_180015DA4
0x180015d84  lea     rdx, __xc_z; Last
0x180015d8b  lea     rcx, __xc_a; First
0x180015d92  call    _initterm_0
0x180015d97  mov     cs:__scrt_current_native_startup_state, 2
0x180015da1  xor     dil, dil
0x180015da4  mov     cl, bl
0x180015da6  call    __scrt_release_startup_lock
0x180015dab  test    dil, dil
0x180015dae  jnz     short loc_180015DEA
0x180015db0  call    __scrt_get_dyn_tls_init_callback
0x180015db5  mov     rbx, rax
0x180015db8  cmp     qword ptr [rax], 0
0x180015dbc  jz      short loc_180015DDD
0x180015dbe  mov     rcx, rax
0x180015dc1  call    __scrt_is_nonwritable_in_current_image
0x180015dc6  test    al, al
0x180015dc8  jz      short loc_180015DDD
0x180015dca  mov     r8, rsi
0x180015dcd  mov     edx, 2
0x180015dd2  mov     rcx, r14
0x180015dd5  mov     rax, [rbx]
0x180015dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ddd  inc     cs:dword_180098DB0
0x180015de3  mov     eax, 1
0x180015de8  jmp     short loc_180015DEC
0x180015dea  xor     eax, eax
0x180015dec  add     rsp, 28h
0x180015df0  pop     r14
0x180015df2  pop     rdi
0x180015df3  pop     rsi
0x180015df4  pop     rbx
0x180015df5  retn
0x180015df6  mov     ecx, 7
0x180015dfb  call    __scrt_fastfail
0x180026dca  push    rbp
0x180026dcc  sub     rsp, 20h
0x180026dd0  mov     rbp, rdx
0x180026dd3  mov     cl, [rbp+60h]
0x180026dd6  add     rsp, 20h
0x180026dda  pop     rbp
0x180026ddb  jmp     __scrt_release_startup_lock
```
