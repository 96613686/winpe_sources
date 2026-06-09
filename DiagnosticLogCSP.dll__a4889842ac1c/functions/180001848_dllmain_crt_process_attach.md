# dllmain_crt_process_attach

- ea: `0x180001848`
- end: `0x180001942`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800017f0`

## callees

- `0x180001848`
- `0x180001c90`
- `0x180001cb8`
- `0x180001cdc`
- `0x180001d1c`
- `0x180001d58`
- `0x180001e58`
- `0x180001f2c`
- `0x180001fcc`
- `0x180002088`
- `0x180002098`
- `0x1800020a4`
- `0x1800024b6`
- `0x1800024c2`
- `0x180037010`

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
  ++dword_180049450;
  return 1;
}

```

## disassembly

```asm
0x180001848  push    rbx
0x18000184a  push    rsi
0x18000184b  push    rdi
0x18000184c  push    r14
0x18000184e  sub     rsp, 28h
0x180001852  mov     rsi, rdx
0x180001855  mov     r14, rcx
0x180001858  xor     ecx, ecx
0x18000185a  call    __scrt_initialize_crt
0x18000185f  test    al, al
0x180001861  jz      loc_18000192A
0x180001867  call    __scrt_acquire_startup_lock
0x18000186c  mov     bl, al
0x18000186e  mov     [rsp+48h+arg_10], al
0x180001872  mov     dil, 1
0x180001875  cmp     cs:__scrt_current_native_startup_state, 0
0x18000187c  jnz     loc_180001936
0x180001882  mov     cs:__scrt_current_native_startup_state, 1
0x18000188c  call    __scrt_dllmain_before_initialize_c
0x180001891  test    al, al
0x180001893  jz      short loc_1800018E4
0x180001895  call    _RTC_Initialize
0x18000189a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000189f  call    __scrt_initialize_default_local_stdio_options
0x1800018a4  lea     rdx, __xi_z; Last
0x1800018ab  lea     rcx, __xi_a; First
0x1800018b2  call    _initterm_e_0
0x1800018b7  test    eax, eax
0x1800018b9  jnz     short loc_1800018E4
0x1800018bb  call    __scrt_dllmain_after_initialize_c
0x1800018c0  test    al, al
0x1800018c2  jz      short loc_1800018E4
0x1800018c4  lea     rdx, __xc_z; Last
0x1800018cb  lea     rcx, __xc_a; First
0x1800018d2  call    _initterm_0
0x1800018d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800018e1  xor     dil, dil
0x1800018e4  mov     cl, bl
0x1800018e6  call    __scrt_release_startup_lock
0x1800018eb  test    dil, dil
0x1800018ee  jnz     short loc_18000192A
0x1800018f0  call    __scrt_get_dyn_tls_init_callback
0x1800018f5  mov     rbx, rax
0x1800018f8  cmp     qword ptr [rax], 0
0x1800018fc  jz      short loc_18000191D
0x1800018fe  mov     rcx, rax
0x180001901  call    __scrt_is_nonwritable_in_current_image
0x180001906  test    al, al
0x180001908  jz      short loc_18000191D
0x18000190a  mov     r8, rsi
0x18000190d  mov     edx, 2
0x180001912  mov     rcx, r14
0x180001915  mov     rax, [rbx]
0x180001918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000191d  inc     cs:dword_180049450
0x180001923  mov     eax, 1
0x180001928  jmp     short loc_18000192C
0x18000192a  xor     eax, eax
0x18000192c  add     rsp, 28h
0x180001930  pop     r14
0x180001932  pop     rdi
0x180001933  pop     rsi
0x180001934  pop     rbx
0x180001935  retn
0x180001936  mov     ecx, 7
0x18000193b  call    __scrt_fastfail
0x18003591c  push    rbp
0x18003591e  sub     rsp, 20h
0x180035922  mov     rbp, rdx
0x180035925  mov     cl, [rbp+60h]
0x180035928  add     rsp, 20h
0x18003592c  pop     rbp
0x18003592d  jmp     __scrt_release_startup_lock
```
