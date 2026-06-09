# dllmain_crt_process_attach

- ea: `0x180003248`
- end: `0x180003342`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800031f0`

## callees

- `0x180003248`
- `0x180003584`
- `0x1800035c4`
- `0x180003600`
- `0x180003700`
- `0x1800037d4`
- `0x180003874`
- `0x180003a58`
- `0x180003a80`
- `0x180003aa4`
- `0x180003ab4`
- `0x180003ac0`
- `0x180003ea6`
- `0x180003eb2`
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
  ++dword_180043570;
  return 1;
}

```

## disassembly

```asm
0x180003248  push    rbx
0x18000324a  push    rsi
0x18000324b  push    rdi
0x18000324c  push    r14
0x18000324e  sub     rsp, 28h
0x180003252  mov     rsi, rdx
0x180003255  mov     r14, rcx
0x180003258  xor     ecx, ecx
0x18000325a  call    __scrt_initialize_crt
0x18000325f  test    al, al
0x180003261  jz      loc_18000332A
0x180003267  call    __scrt_acquire_startup_lock
0x18000326c  mov     bl, al
0x18000326e  mov     [rsp+48h+arg_10], al
0x180003272  mov     dil, 1
0x180003275  cmp     cs:__scrt_current_native_startup_state, 0
0x18000327c  jnz     loc_180003336
0x180003282  mov     cs:__scrt_current_native_startup_state, 1
0x18000328c  call    __scrt_dllmain_before_initialize_c
0x180003291  test    al, al
0x180003293  jz      short loc_1800032E4
0x180003295  call    _RTC_Initialize
0x18000329a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000329f  call    __scrt_initialize_default_local_stdio_options
0x1800032a4  lea     rdx, __xi_z; Last
0x1800032ab  lea     rcx, __xi_a; First
0x1800032b2  call    _initterm_e_0
0x1800032b7  test    eax, eax
0x1800032b9  jnz     short loc_1800032E4
0x1800032bb  call    __scrt_dllmain_after_initialize_c
0x1800032c0  test    al, al
0x1800032c2  jz      short loc_1800032E4
0x1800032c4  lea     rdx, __xc_z; Last
0x1800032cb  lea     rcx, __xc_a; First
0x1800032d2  call    _initterm_0
0x1800032d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800032e1  xor     dil, dil
0x1800032e4  mov     cl, bl
0x1800032e6  call    __scrt_release_startup_lock
0x1800032eb  test    dil, dil
0x1800032ee  jnz     short loc_18000332A
0x1800032f0  call    __scrt_get_dyn_tls_init_callback
0x1800032f5  mov     rbx, rax
0x1800032f8  cmp     qword ptr [rax], 0
0x1800032fc  jz      short loc_18000331D
0x1800032fe  mov     rcx, rax
0x180003301  call    __scrt_is_nonwritable_in_current_image
0x180003306  test    al, al
0x180003308  jz      short loc_18000331D
0x18000330a  mov     r8, rsi
0x18000330d  mov     edx, 2
0x180003312  mov     rcx, r14
0x180003315  mov     rax, [rbx]
0x180003318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331d  inc     cs:dword_180043570
0x180003323  mov     eax, 1
0x180003328  jmp     short loc_18000332C
0x18000332a  xor     eax, eax
0x18000332c  add     rsp, 28h
0x180003330  pop     r14
0x180003332  pop     rdi
0x180003333  pop     rsi
0x180003334  pop     rbx
0x180003335  retn
0x180003336  mov     ecx, 7
0x18000333b  call    __scrt_fastfail
0x18002e71c  push    rbp
0x18002e71e  sub     rsp, 20h
0x18002e722  mov     rbp, rdx
0x18002e725  mov     cl, [rbp+60h]
0x18002e728  add     rsp, 20h
0x18002e72c  pop     rbp
0x18002e72d  jmp     __scrt_release_startup_lock
```
