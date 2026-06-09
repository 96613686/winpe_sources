# dllmain_crt_process_attach

- ea: `0x180068568`
- end: `0x180068662`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180068510`

## callees

- `0x180068568`
- `0x1800689b8`
- `0x1800689e0`
- `0x180068a04`
- `0x180068a44`
- `0x180068a80`
- `0x180068b80`
- `0x180068c54`
- `0x180068cf4`
- `0x180068d50`
- `0x180068d60`
- `0x180068d6c`
- `0x180069096`
- `0x1800690a2`
- `0x18009a010`

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
  ++dword_1800B5A50;
  return 1;
}

```

## disassembly

```asm
0x180068568  push    rbx
0x18006856a  push    rsi
0x18006856b  push    rdi
0x18006856c  push    r14
0x18006856e  sub     rsp, 28h
0x180068572  mov     rsi, rdx
0x180068575  mov     r14, rcx
0x180068578  xor     ecx, ecx
0x18006857a  call    __scrt_initialize_crt
0x18006857f  test    al, al
0x180068581  jz      loc_18006864A
0x180068587  call    __scrt_acquire_startup_lock
0x18006858c  mov     bl, al
0x18006858e  mov     [rsp+48h+arg_10], al
0x180068592  mov     dil, 1
0x180068595  cmp     cs:__scrt_current_native_startup_state, 0
0x18006859c  jnz     loc_180068656
0x1800685a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800685ac  call    __scrt_dllmain_before_initialize_c
0x1800685b1  test    al, al
0x1800685b3  jz      short loc_180068604
0x1800685b5  call    _RTC_Initialize
0x1800685ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800685bf  call    __scrt_initialize_default_local_stdio_options
0x1800685c4  lea     rdx, __xi_z; Last
0x1800685cb  lea     rcx, __xi_a; First
0x1800685d2  call    _initterm_e_0
0x1800685d7  test    eax, eax
0x1800685d9  jnz     short loc_180068604
0x1800685db  call    __scrt_dllmain_after_initialize_c
0x1800685e0  test    al, al
0x1800685e2  jz      short loc_180068604
0x1800685e4  lea     rdx, __xc_z; Last
0x1800685eb  lea     rcx, __xc_a; First
0x1800685f2  call    _initterm_0
0x1800685f7  mov     cs:__scrt_current_native_startup_state, 2
0x180068601  xor     dil, dil
0x180068604  mov     cl, bl
0x180068606  call    __scrt_release_startup_lock
0x18006860b  test    dil, dil
0x18006860e  jnz     short loc_18006864A
0x180068610  call    __scrt_get_dyn_tls_init_callback
0x180068615  mov     rbx, rax
0x180068618  cmp     qword ptr [rax], 0
0x18006861c  jz      short loc_18006863D
0x18006861e  mov     rcx, rax
0x180068621  call    __scrt_is_nonwritable_in_current_image
0x180068626  test    al, al
0x180068628  jz      short loc_18006863D
0x18006862a  mov     r8, rsi
0x18006862d  mov     edx, 2
0x180068632  mov     rcx, r14
0x180068635  mov     rax, [rbx]
0x180068638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006863d  inc     cs:dword_1800B5A50
0x180068643  mov     eax, 1
0x180068648  jmp     short loc_18006864C
0x18006864a  xor     eax, eax
0x18006864c  add     rsp, 28h
0x180068650  pop     r14
0x180068652  pop     rdi
0x180068653  pop     rsi
0x180068654  pop     rbx
0x180068655  retn
0x180068656  mov     ecx, 7
0x18006865b  call    __scrt_fastfail
0x18009998f  push    rbp
0x180099991  sub     rsp, 20h
0x180099995  mov     rbp, rdx
0x180099998  mov     cl, [rbp+60h]
0x18009999b  add     rsp, 20h
0x18009999f  pop     rbp
0x1800999a0  jmp     __scrt_release_startup_lock
```
