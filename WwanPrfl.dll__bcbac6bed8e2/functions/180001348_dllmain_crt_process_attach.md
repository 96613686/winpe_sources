# dllmain_crt_process_attach

- ea: `0x180001348`
- end: `0x180001442`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800012f0`

## callees

- `0x180001348`
- `0x1800016cc`
- `0x18000170c`
- `0x180001748`
- `0x180001848`
- `0x18000191c`
- `0x1800019bc`
- `0x180001b78`
- `0x180001ba0`
- `0x180001bc4`
- `0x180001bd4`
- `0x180001be0`
- `0x180001f16`
- `0x180001f22`
- `0x180014010`

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
  ++dword_18001F590;
  return 1;
}

```

## disassembly

```asm
0x180001348  push    rbx
0x18000134a  push    rsi
0x18000134b  push    rdi
0x18000134c  push    r14
0x18000134e  sub     rsp, 28h
0x180001352  mov     rsi, rdx
0x180001355  mov     r14, rcx
0x180001358  xor     ecx, ecx
0x18000135a  call    __scrt_initialize_crt
0x18000135f  test    al, al
0x180001361  jz      loc_18000142A
0x180001367  call    __scrt_acquire_startup_lock
0x18000136c  mov     bl, al
0x18000136e  mov     [rsp+48h+arg_10], al
0x180001372  mov     dil, 1
0x180001375  cmp     cs:__scrt_current_native_startup_state, 0
0x18000137c  jnz     loc_180001436
0x180001382  mov     cs:__scrt_current_native_startup_state, 1
0x18000138c  call    __scrt_dllmain_before_initialize_c
0x180001391  test    al, al
0x180001393  jz      short loc_1800013E4
0x180001395  call    _RTC_Initialize
0x18000139a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000139f  call    __scrt_initialize_default_local_stdio_options
0x1800013a4  lea     rdx, __xi_z; Last
0x1800013ab  lea     rcx, __xi_a; First
0x1800013b2  call    _initterm_e_0
0x1800013b7  test    eax, eax
0x1800013b9  jnz     short loc_1800013E4
0x1800013bb  call    __scrt_dllmain_after_initialize_c
0x1800013c0  test    al, al
0x1800013c2  jz      short loc_1800013E4
0x1800013c4  lea     rdx, __xc_z; Last
0x1800013cb  lea     rcx, __xc_a; First
0x1800013d2  call    _initterm_0
0x1800013d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800013e1  xor     dil, dil
0x1800013e4  mov     cl, bl
0x1800013e6  call    __scrt_release_startup_lock
0x1800013eb  test    dil, dil
0x1800013ee  jnz     short loc_18000142A
0x1800013f0  call    __scrt_get_dyn_tls_init_callback
0x1800013f5  mov     rbx, rax
0x1800013f8  cmp     qword ptr [rax], 0
0x1800013fc  jz      short loc_18000141D
0x1800013fe  mov     rcx, rax
0x180001401  call    __scrt_is_nonwritable_in_current_image
0x180001406  test    al, al
0x180001408  jz      short loc_18000141D
0x18000140a  mov     r8, rsi
0x18000140d  mov     edx, 2
0x180001412  mov     rcx, r14
0x180001415  mov     rax, [rbx]
0x180001418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000141d  inc     cs:dword_18001F590
0x180001423  mov     eax, 1
0x180001428  jmp     short loc_18000142C
0x18000142a  xor     eax, eax
0x18000142c  add     rsp, 28h
0x180001430  pop     r14
0x180001432  pop     rdi
0x180001433  pop     rsi
0x180001434  pop     rbx
0x180001435  retn
0x180001436  mov     ecx, 7
0x18000143b  call    __scrt_fastfail
0x18001378c  push    rbp
0x18001378e  sub     rsp, 20h
0x180013792  mov     rbp, rdx
0x180013795  mov     cl, [rbp+60h]
0x180013798  add     rsp, 20h
0x18001379c  pop     rbp
0x18001379d  jmp     __scrt_release_startup_lock
```
