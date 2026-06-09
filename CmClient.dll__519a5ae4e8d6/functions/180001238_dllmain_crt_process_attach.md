# dllmain_crt_process_attach

- ea: `0x180001238`
- end: `0x180001332`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800011e0`

## callees

- `0x180001238`
- `0x180001598`
- `0x1800015d8`
- `0x180001614`
- `0x180001714`
- `0x1800017e8`
- `0x180001888`
- `0x180001a18`
- `0x180001a40`
- `0x180001a64`
- `0x180001a74`
- `0x180001a80`
- `0x18000203c`
- `0x180002048`
- `0x180010010`

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
  ++dword_18001B1B0;
  return 1;
}

```

## disassembly

```asm
0x180001238  push    rbx
0x18000123a  push    rsi
0x18000123b  push    rdi
0x18000123c  push    r14
0x18000123e  sub     rsp, 28h
0x180001242  mov     rsi, rdx
0x180001245  mov     r14, rcx
0x180001248  xor     ecx, ecx
0x18000124a  call    __scrt_initialize_crt
0x18000124f  test    al, al
0x180001251  jz      loc_18000131A
0x180001257  call    __scrt_acquire_startup_lock
0x18000125c  mov     bl, al
0x18000125e  mov     [rsp+48h+arg_10], al
0x180001262  mov     dil, 1
0x180001265  cmp     cs:__scrt_current_native_startup_state, 0
0x18000126c  jnz     loc_180001326
0x180001272  mov     cs:__scrt_current_native_startup_state, 1
0x18000127c  call    __scrt_dllmain_before_initialize_c
0x180001281  test    al, al
0x180001283  jz      short loc_1800012D4
0x180001285  call    _RTC_Initialize
0x18000128a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000128f  call    __scrt_initialize_default_local_stdio_options
0x180001294  lea     rdx, __xi_z; Last
0x18000129b  lea     rcx, __xi_a; First
0x1800012a2  call    _initterm_e_0
0x1800012a7  test    eax, eax
0x1800012a9  jnz     short loc_1800012D4
0x1800012ab  call    __scrt_dllmain_after_initialize_c
0x1800012b0  test    al, al
0x1800012b2  jz      short loc_1800012D4
0x1800012b4  lea     rdx, __xc_z; Last
0x1800012bb  lea     rcx, __xc_a; First
0x1800012c2  call    _initterm_0
0x1800012c7  mov     cs:__scrt_current_native_startup_state, 2
0x1800012d1  xor     dil, dil
0x1800012d4  mov     cl, bl
0x1800012d6  call    __scrt_release_startup_lock
0x1800012db  test    dil, dil
0x1800012de  jnz     short loc_18000131A
0x1800012e0  call    __scrt_get_dyn_tls_init_callback
0x1800012e5  mov     rbx, rax
0x1800012e8  cmp     qword ptr [rax], 0
0x1800012ec  jz      short loc_18000130D
0x1800012ee  mov     rcx, rax
0x1800012f1  call    __scrt_is_nonwritable_in_current_image
0x1800012f6  test    al, al
0x1800012f8  jz      short loc_18000130D
0x1800012fa  mov     r8, rsi
0x1800012fd  mov     edx, 2
0x180001302  mov     rcx, r14
0x180001305  mov     rax, [rbx]
0x180001308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000130d  inc     cs:dword_18001B1B0
0x180001313  mov     eax, 1
0x180001318  jmp     short loc_18000131C
0x18000131a  xor     eax, eax
0x18000131c  add     rsp, 28h
0x180001320  pop     r14
0x180001322  pop     rdi
0x180001323  pop     rsi
0x180001324  pop     rbx
0x180001325  retn
0x180001326  mov     ecx, 7
0x18000132b  call    __scrt_fastfail
0x18000ee7c  push    rbp
0x18000ee7e  sub     rsp, 20h
0x18000ee82  mov     rbp, rdx
0x18000ee85  mov     cl, [rbp+60h]
0x18000ee88  add     rsp, 20h
0x18000ee8c  pop     rbp
0x18000ee8d  jmp     __scrt_release_startup_lock
```
