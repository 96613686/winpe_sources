# dllmain_crt_process_attach

- ea: `0x180001eb8`
- end: `0x180001fb2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001e60`

## callees

- `0x180001eb8`
- `0x18000222c`
- `0x18000226c`
- `0x1800022a8`
- `0x1800023a8`
- `0x18000247c`
- `0x18000251c`
- `0x1800026d8`
- `0x180002700`
- `0x180002724`
- `0x180002734`
- `0x180002740`
- `0x180002af6`
- `0x180002b02`
- `0x180024010`

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
  ++dword_18002E650;
  return 1;
}

```

## disassembly

```asm
0x180001eb8  push    rbx
0x180001eba  push    rsi
0x180001ebb  push    rdi
0x180001ebc  push    r14
0x180001ebe  sub     rsp, 28h
0x180001ec2  mov     rsi, rdx
0x180001ec5  mov     r14, rcx
0x180001ec8  xor     ecx, ecx
0x180001eca  call    __scrt_initialize_crt
0x180001ecf  test    al, al
0x180001ed1  jz      loc_180001F9A
0x180001ed7  call    __scrt_acquire_startup_lock
0x180001edc  mov     bl, al
0x180001ede  mov     [rsp+48h+arg_10], al
0x180001ee2  mov     dil, 1
0x180001ee5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001eec  jnz     loc_180001FA6
0x180001ef2  mov     cs:__scrt_current_native_startup_state, 1
0x180001efc  call    __scrt_dllmain_before_initialize_c
0x180001f01  test    al, al
0x180001f03  jz      short loc_180001F54
0x180001f05  call    _RTC_Initialize
0x180001f0a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001f0f  call    __scrt_initialize_default_local_stdio_options
0x180001f14  lea     rdx, __xi_z; Last
0x180001f1b  lea     rcx, __xi_a; First
0x180001f22  call    _initterm_e_0
0x180001f27  test    eax, eax
0x180001f29  jnz     short loc_180001F54
0x180001f2b  call    __scrt_dllmain_after_initialize_c
0x180001f30  test    al, al
0x180001f32  jz      short loc_180001F54
0x180001f34  lea     rdx, __xc_z; Last
0x180001f3b  lea     rcx, __xc_a; First
0x180001f42  call    _initterm_0
0x180001f47  mov     cs:__scrt_current_native_startup_state, 2
0x180001f51  xor     dil, dil
0x180001f54  mov     cl, bl
0x180001f56  call    __scrt_release_startup_lock
0x180001f5b  test    dil, dil
0x180001f5e  jnz     short loc_180001F9A
0x180001f60  call    __scrt_get_dyn_tls_init_callback
0x180001f65  mov     rbx, rax
0x180001f68  cmp     qword ptr [rax], 0
0x180001f6c  jz      short loc_180001F8D
0x180001f6e  mov     rcx, rax
0x180001f71  call    __scrt_is_nonwritable_in_current_image
0x180001f76  test    al, al
0x180001f78  jz      short loc_180001F8D
0x180001f7a  mov     r8, rsi
0x180001f7d  mov     edx, 2
0x180001f82  mov     rcx, r14
0x180001f85  mov     rax, [rbx]
0x180001f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f8d  inc     cs:dword_18002E650
0x180001f93  mov     eax, 1
0x180001f98  jmp     short loc_180001F9C
0x180001f9a  xor     eax, eax
0x180001f9c  add     rsp, 28h
0x180001fa0  pop     r14
0x180001fa2  pop     rdi
0x180001fa3  pop     rsi
0x180001fa4  pop     rbx
0x180001fa5  retn
0x180001fa6  mov     ecx, 7
0x180001fab  call    __scrt_fastfail
0x180021fcc  push    rbp
0x180021fce  sub     rsp, 20h
0x180021fd2  mov     rbp, rdx
0x180021fd5  mov     cl, [rbp+60h]
0x180021fd8  add     rsp, 20h
0x180021fdc  pop     rbp
0x180021fdd  jmp     __scrt_release_startup_lock
```
