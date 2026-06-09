# dllmain_crt_process_attach

- ea: `0x18001cc38`
- end: `0x18001cd32`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001cbe0`

## callees

- `0x18001cc38`
- `0x18001cfb8`
- `0x18001cff8`
- `0x18001d034`
- `0x18001d134`
- `0x18001d208`
- `0x18001d2a8`
- `0x18001d464`
- `0x18001d48c`
- `0x18001d4b0`
- `0x18001d4c0`
- `0x18001d4cc`
- `0x18001d896`
- `0x18001d8a2`
- `0x180027010`

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
  ++dword_180036D58;
  return 1;
}

```

## disassembly

```asm
0x18001cc38  push    rbx
0x18001cc3a  push    rsi
0x18001cc3b  push    rdi
0x18001cc3c  push    r14
0x18001cc3e  sub     rsp, 28h
0x18001cc42  mov     rsi, rdx
0x18001cc45  mov     r14, rcx
0x18001cc48  xor     ecx, ecx
0x18001cc4a  call    __scrt_initialize_crt
0x18001cc4f  test    al, al
0x18001cc51  jz      loc_18001CD1A
0x18001cc57  call    __scrt_acquire_startup_lock
0x18001cc5c  mov     bl, al
0x18001cc5e  mov     [rsp+48h+arg_10], al
0x18001cc62  mov     dil, 1
0x18001cc65  cmp     cs:__scrt_current_native_startup_state, 0
0x18001cc6c  jnz     loc_18001CD26
0x18001cc72  mov     cs:__scrt_current_native_startup_state, 1
0x18001cc7c  call    __scrt_dllmain_before_initialize_c
0x18001cc81  test    al, al
0x18001cc83  jz      short loc_18001CCD4
0x18001cc85  call    _RTC_Initialize
0x18001cc8a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001cc8f  call    __scrt_initialize_default_local_stdio_options
0x18001cc94  lea     rdx, __xi_z; Last
0x18001cc9b  lea     rcx, __xi_a; First
0x18001cca2  call    _initterm_e_0
0x18001cca7  test    eax, eax
0x18001cca9  jnz     short loc_18001CCD4
0x18001ccab  call    __scrt_dllmain_after_initialize_c
0x18001ccb0  test    al, al
0x18001ccb2  jz      short loc_18001CCD4
0x18001ccb4  lea     rdx, __xc_z; Last
0x18001ccbb  lea     rcx, __xc_a; First
0x18001ccc2  call    _initterm_0
0x18001ccc7  mov     cs:__scrt_current_native_startup_state, 2
0x18001ccd1  xor     dil, dil
0x18001ccd4  mov     cl, bl
0x18001ccd6  call    __scrt_release_startup_lock
0x18001ccdb  test    dil, dil
0x18001ccde  jnz     short loc_18001CD1A
0x18001cce0  call    __scrt_get_dyn_tls_init_callback
0x18001cce5  mov     rbx, rax
0x18001cce8  cmp     qword ptr [rax], 0
0x18001ccec  jz      short loc_18001CD0D
0x18001ccee  mov     rcx, rax
0x18001ccf1  call    __scrt_is_nonwritable_in_current_image
0x18001ccf6  test    al, al
0x18001ccf8  jz      short loc_18001CD0D
0x18001ccfa  mov     r8, rsi
0x18001ccfd  mov     edx, 2
0x18001cd02  mov     rcx, r14
0x18001cd05  mov     rax, [rbx]
0x18001cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd0d  inc     cs:dword_180036D58
0x18001cd13  mov     eax, 1
0x18001cd18  jmp     short loc_18001CD1C
0x18001cd1a  xor     eax, eax
0x18001cd1c  add     rsp, 28h
0x18001cd20  pop     r14
0x18001cd22  pop     rdi
0x18001cd23  pop     rsi
0x18001cd24  pop     rbx
0x18001cd25  retn
0x18001cd26  mov     ecx, 7
0x18001cd2b  call    __scrt_fastfail
0x180025b97  push    rbp
0x180025b99  sub     rsp, 20h
0x180025b9d  mov     rbp, rdx
0x180025ba0  mov     cl, [rbp+60h]
0x180025ba3  add     rsp, 20h
0x180025ba7  pop     rbp
0x180025ba8  jmp     __scrt_release_startup_lock
```
