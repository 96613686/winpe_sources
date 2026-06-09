# dllmain_crt_process_attach

- ea: `0x180003ca8`
- end: `0x180003da2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003c50`

## callees

- `0x180003ca8`
- `0x1800040c0`
- `0x180004100`
- `0x18000413c`
- `0x18000423c`
- `0x180004310`
- `0x1800043b0`
- `0x1800045b0`
- `0x1800045d8`
- `0x1800045fc`
- `0x18000460c`
- `0x180004618`
- `0x180004a16`
- `0x180004a22`
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
  ++dword_1800397B0;
  return 1;
}

```

## disassembly

```asm
0x180003ca8  push    rbx
0x180003caa  push    rsi
0x180003cab  push    rdi
0x180003cac  push    r14
0x180003cae  sub     rsp, 28h
0x180003cb2  mov     rsi, rdx
0x180003cb5  mov     r14, rcx
0x180003cb8  xor     ecx, ecx
0x180003cba  call    __scrt_initialize_crt
0x180003cbf  test    al, al
0x180003cc1  jz      loc_180003D8A
0x180003cc7  call    __scrt_acquire_startup_lock
0x180003ccc  mov     bl, al
0x180003cce  mov     [rsp+48h+arg_10], al
0x180003cd2  mov     dil, 1
0x180003cd5  cmp     cs:__scrt_current_native_startup_state, 0
0x180003cdc  jnz     loc_180003D96
0x180003ce2  mov     cs:__scrt_current_native_startup_state, 1
0x180003cec  call    __scrt_dllmain_before_initialize_c
0x180003cf1  test    al, al
0x180003cf3  jz      short loc_180003D44
0x180003cf5  call    _RTC_Initialize
0x180003cfa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180003cff  call    __scrt_initialize_default_local_stdio_options
0x180003d04  lea     rdx, __xi_z; Last
0x180003d0b  lea     rcx, __xi_a; First
0x180003d12  call    _initterm_e_0
0x180003d17  test    eax, eax
0x180003d19  jnz     short loc_180003D44
0x180003d1b  call    __scrt_dllmain_after_initialize_c
0x180003d20  test    al, al
0x180003d22  jz      short loc_180003D44
0x180003d24  lea     rdx, __xc_z; Last
0x180003d2b  lea     rcx, __xc_a; First
0x180003d32  call    _initterm_0
0x180003d37  mov     cs:__scrt_current_native_startup_state, 2
0x180003d41  xor     dil, dil
0x180003d44  mov     cl, bl
0x180003d46  call    __scrt_release_startup_lock
0x180003d4b  test    dil, dil
0x180003d4e  jnz     short loc_180003D8A
0x180003d50  call    __scrt_get_dyn_tls_init_callback
0x180003d55  mov     rbx, rax
0x180003d58  cmp     qword ptr [rax], 0
0x180003d5c  jz      short loc_180003D7D
0x180003d5e  mov     rcx, rax
0x180003d61  call    __scrt_is_nonwritable_in_current_image
0x180003d66  test    al, al
0x180003d68  jz      short loc_180003D7D
0x180003d6a  mov     r8, rsi
0x180003d6d  mov     edx, 2
0x180003d72  mov     rcx, r14
0x180003d75  mov     rax, [rbx]
0x180003d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7d  inc     cs:dword_1800397B0
0x180003d83  mov     eax, 1
0x180003d88  jmp     short loc_180003D8C
0x180003d8a  xor     eax, eax
0x180003d8c  add     rsp, 28h
0x180003d90  pop     r14
0x180003d92  pop     rdi
0x180003d93  pop     rsi
0x180003d94  pop     rbx
0x180003d95  retn
0x180003d96  mov     ecx, 7
0x180003d9b  call    __scrt_fastfail
0x1800261dc  push    rbp
0x1800261de  sub     rsp, 20h
0x1800261e2  mov     rbp, rdx
0x1800261e5  mov     cl, [rbp+60h]
0x1800261e8  add     rsp, 20h
0x1800261ec  pop     rbp
0x1800261ed  jmp     __scrt_release_startup_lock
```
