# dllmain_crt_process_attach

- ea: `0x180001ea8`
- end: `0x180001fa2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001e50`

## callees

- `0x180001ea8`
- `0x18000224c`
- `0x18000228c`
- `0x1800022c8`
- `0x1800023c8`
- `0x18000249c`
- `0x18000253c`
- `0x1800026f8`
- `0x180002720`
- `0x180002744`
- `0x180002754`
- `0x180002760`
- `0x180002ae6`
- `0x180002af2`
- `0x18002d010`

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
  ++dword_18003BD10;
  return 1;
}

```

## disassembly

```asm
0x180001ea8  push    rbx
0x180001eaa  push    rsi
0x180001eab  push    rdi
0x180001eac  push    r14
0x180001eae  sub     rsp, 28h
0x180001eb2  mov     rsi, rdx
0x180001eb5  mov     r14, rcx
0x180001eb8  xor     ecx, ecx
0x180001eba  call    __scrt_initialize_crt
0x180001ebf  test    al, al
0x180001ec1  jz      loc_180001F8A
0x180001ec7  call    __scrt_acquire_startup_lock
0x180001ecc  mov     bl, al
0x180001ece  mov     [rsp+48h+arg_10], al
0x180001ed2  mov     dil, 1
0x180001ed5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001edc  jnz     loc_180001F96
0x180001ee2  mov     cs:__scrt_current_native_startup_state, 1
0x180001eec  call    __scrt_dllmain_before_initialize_c
0x180001ef1  test    al, al
0x180001ef3  jz      short loc_180001F44
0x180001ef5  call    _RTC_Initialize
0x180001efa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001eff  call    __scrt_initialize_default_local_stdio_options
0x180001f04  lea     rdx, __xi_z; Last
0x180001f0b  lea     rcx, __xi_a; First
0x180001f12  call    _initterm_e_0
0x180001f17  test    eax, eax
0x180001f19  jnz     short loc_180001F44
0x180001f1b  call    __scrt_dllmain_after_initialize_c
0x180001f20  test    al, al
0x180001f22  jz      short loc_180001F44
0x180001f24  lea     rdx, __xc_z; Last
0x180001f2b  lea     rcx, __xc_a; First
0x180001f32  call    _initterm_0
0x180001f37  mov     cs:__scrt_current_native_startup_state, 2
0x180001f41  xor     dil, dil
0x180001f44  mov     cl, bl
0x180001f46  call    __scrt_release_startup_lock
0x180001f4b  test    dil, dil
0x180001f4e  jnz     short loc_180001F8A
0x180001f50  call    __scrt_get_dyn_tls_init_callback
0x180001f55  mov     rbx, rax
0x180001f58  cmp     qword ptr [rax], 0
0x180001f5c  jz      short loc_180001F7D
0x180001f5e  mov     rcx, rax
0x180001f61  call    __scrt_is_nonwritable_in_current_image
0x180001f66  test    al, al
0x180001f68  jz      short loc_180001F7D
0x180001f6a  mov     r8, rsi
0x180001f6d  mov     edx, 2
0x180001f72  mov     rcx, r14
0x180001f75  mov     rax, [rbx]
0x180001f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f7d  inc     cs:dword_18003BD10
0x180001f83  mov     eax, 1
0x180001f88  jmp     short loc_180001F8C
0x180001f8a  xor     eax, eax
0x180001f8c  add     rsp, 28h
0x180001f90  pop     r14
0x180001f92  pop     rdi
0x180001f93  pop     rsi
0x180001f94  pop     rbx
0x180001f95  retn
0x180001f96  mov     ecx, 7
0x180001f9b  call    __scrt_fastfail
0x18002994c  push    rbp
0x18002994e  sub     rsp, 20h
0x180029952  mov     rbp, rdx
0x180029955  mov     cl, [rbp+60h]
0x180029958  add     rsp, 20h
0x18002995c  pop     rbp
0x18002995d  jmp     __scrt_release_startup_lock
```
