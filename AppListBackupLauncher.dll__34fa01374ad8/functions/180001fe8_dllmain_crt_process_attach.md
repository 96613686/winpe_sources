# dllmain_crt_process_attach

- ea: `0x180001fe8`
- end: `0x1800020e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001f90`

## callees

- `0x180001fe8`
- `0x18000238c`
- `0x1800023cc`
- `0x180002408`
- `0x180002508`
- `0x1800025dc`
- `0x18000267c`
- `0x180002b54`
- `0x180002b7c`
- `0x180002ba0`
- `0x180002bb0`
- `0x180002bbc`
- `0x180002cb6`
- `0x180002cc2`
- `0x180012010`

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
  ++dword_180019750;
  return 1;
}

```

## disassembly

```asm
0x180001fe8  push    rbx
0x180001fea  push    rsi
0x180001feb  push    rdi
0x180001fec  push    r14
0x180001fee  sub     rsp, 28h
0x180001ff2  mov     rsi, rdx
0x180001ff5  mov     r14, rcx
0x180001ff8  xor     ecx, ecx
0x180001ffa  call    __scrt_initialize_crt
0x180001fff  test    al, al
0x180002001  jz      loc_1800020CA
0x180002007  call    __scrt_acquire_startup_lock
0x18000200c  mov     bl, al
0x18000200e  mov     [rsp+48h+arg_10], al
0x180002012  mov     dil, 1
0x180002015  cmp     cs:__scrt_current_native_startup_state, 0
0x18000201c  jnz     loc_1800020D6
0x180002022  mov     cs:__scrt_current_native_startup_state, 1
0x18000202c  call    __scrt_dllmain_before_initialize_c
0x180002031  test    al, al
0x180002033  jz      short loc_180002084
0x180002035  call    _RTC_Initialize
0x18000203a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000203f  call    __scrt_initialize_default_local_stdio_options
0x180002044  lea     rdx, __xi_z; Last
0x18000204b  lea     rcx, __xi_a; First
0x180002052  call    _initterm_e_0
0x180002057  test    eax, eax
0x180002059  jnz     short loc_180002084
0x18000205b  call    __scrt_dllmain_after_initialize_c
0x180002060  test    al, al
0x180002062  jz      short loc_180002084
0x180002064  lea     rdx, __xc_z; Last
0x18000206b  lea     rcx, __xc_a; First
0x180002072  call    _initterm_0
0x180002077  mov     cs:__scrt_current_native_startup_state, 2
0x180002081  xor     dil, dil
0x180002084  mov     cl, bl
0x180002086  call    __scrt_release_startup_lock
0x18000208b  test    dil, dil
0x18000208e  jnz     short loc_1800020CA
0x180002090  call    __scrt_get_dyn_tls_init_callback
0x180002095  mov     rbx, rax
0x180002098  cmp     qword ptr [rax], 0
0x18000209c  jz      short loc_1800020BD
0x18000209e  mov     rcx, rax
0x1800020a1  call    __scrt_is_nonwritable_in_current_image
0x1800020a6  test    al, al
0x1800020a8  jz      short loc_1800020BD
0x1800020aa  mov     r8, rsi
0x1800020ad  mov     edx, 2
0x1800020b2  mov     rcx, r14
0x1800020b5  mov     rax, [rbx]
0x1800020b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020bd  inc     cs:dword_180019750
0x1800020c3  mov     eax, 1
0x1800020c8  jmp     short loc_1800020CC
0x1800020ca  xor     eax, eax
0x1800020cc  add     rsp, 28h
0x1800020d0  pop     r14
0x1800020d2  pop     rdi
0x1800020d3  pop     rsi
0x1800020d4  pop     rbx
0x1800020d5  retn
0x1800020d6  mov     ecx, 7
0x1800020db  call    __scrt_fastfail
0x18001034c  push    rbp
0x18001034e  sub     rsp, 20h
0x180010352  mov     rbp, rdx
0x180010355  mov     cl, [rbp+60h]
0x180010358  add     rsp, 20h
0x18001035c  pop     rbp
0x18001035d  jmp     __scrt_release_startup_lock
```
