# dllmain_crt_process_attach

- ea: `0x180001598`
- end: `0x180001692`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001540`

## callees

- `0x180001598`
- `0x180001990`
- `0x1800019b8`
- `0x1800019dc`
- `0x180001a1c`
- `0x180001a58`
- `0x180001b58`
- `0x180001c2c`
- `0x180001ccc`
- `0x180001d28`
- `0x180001d38`
- `0x180001d44`
- `0x1800020a6`
- `0x1800020b2`
- `0x180022010`

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
  ++dword_180039650;
  return 1;
}

```

## disassembly

```asm
0x180001598  push    rbx
0x18000159a  push    rsi
0x18000159b  push    rdi
0x18000159c  push    r14
0x18000159e  sub     rsp, 28h
0x1800015a2  mov     rsi, rdx
0x1800015a5  mov     r14, rcx
0x1800015a8  xor     ecx, ecx
0x1800015aa  call    __scrt_initialize_crt
0x1800015af  test    al, al
0x1800015b1  jz      loc_18000167A
0x1800015b7  call    __scrt_acquire_startup_lock
0x1800015bc  mov     bl, al
0x1800015be  mov     [rsp+48h+arg_10], al
0x1800015c2  mov     dil, 1
0x1800015c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800015cc  jnz     loc_180001686
0x1800015d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800015dc  call    __scrt_dllmain_before_initialize_c
0x1800015e1  test    al, al
0x1800015e3  jz      short loc_180001634
0x1800015e5  call    _RTC_Initialize
0x1800015ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800015ef  call    __scrt_initialize_default_local_stdio_options
0x1800015f4  lea     rdx, __xi_z; Last
0x1800015fb  lea     rcx, __xi_a; First
0x180001602  call    _initterm_e_0
0x180001607  test    eax, eax
0x180001609  jnz     short loc_180001634
0x18000160b  call    __scrt_dllmain_after_initialize_c
0x180001610  test    al, al
0x180001612  jz      short loc_180001634
0x180001614  lea     rdx, __xc_z; Last
0x18000161b  lea     rcx, __xc_a; First
0x180001622  call    _initterm_0
0x180001627  mov     cs:__scrt_current_native_startup_state, 2
0x180001631  xor     dil, dil
0x180001634  mov     cl, bl
0x180001636  call    __scrt_release_startup_lock
0x18000163b  test    dil, dil
0x18000163e  jnz     short loc_18000167A
0x180001640  call    __scrt_get_dyn_tls_init_callback
0x180001645  mov     rbx, rax
0x180001648  cmp     qword ptr [rax], 0
0x18000164c  jz      short loc_18000166D
0x18000164e  mov     rcx, rax
0x180001651  call    __scrt_is_nonwritable_in_current_image
0x180001656  test    al, al
0x180001658  jz      short loc_18000166D
0x18000165a  mov     r8, rsi
0x18000165d  mov     edx, 2
0x180001662  mov     rcx, r14
0x180001665  mov     rax, [rbx]
0x180001668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000166d  inc     cs:dword_180039650
0x180001673  mov     eax, 1
0x180001678  jmp     short loc_18000167C
0x18000167a  xor     eax, eax
0x18000167c  add     rsp, 28h
0x180001680  pop     r14
0x180001682  pop     rdi
0x180001683  pop     rsi
0x180001684  pop     rbx
0x180001685  retn
0x180001686  mov     ecx, 7
0x18000168b  call    __scrt_fastfail
0x18002107c  push    rbp
0x18002107e  sub     rsp, 20h
0x180021082  mov     rbp, rdx
0x180021085  mov     cl, [rbp+60h]
0x180021088  add     rsp, 20h
0x18002108c  pop     rbp
0x18002108d  jmp     __scrt_release_startup_lock
```
