# dllmain_crt_process_attach

- ea: `0x1800012b8`
- end: `0x1800013b2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001260`

## callees

- `0x1800012b8`
- `0x1800015f4`
- `0x180001634`
- `0x180001670`
- `0x180001770`
- `0x180001844`
- `0x1800018e4`
- `0x180001a6c`
- `0x180001a94`
- `0x180001ab8`
- `0x180001ac8`
- `0x180001ad4`
- `0x180001e06`
- `0x180001e12`
- `0x180040010`

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
  ++dword_18004A5D0;
  return 1;
}

```

## disassembly

```asm
0x1800012b8  push    rbx
0x1800012ba  push    rsi
0x1800012bb  push    rdi
0x1800012bc  push    r14
0x1800012be  sub     rsp, 28h
0x1800012c2  mov     rsi, rdx
0x1800012c5  mov     r14, rcx
0x1800012c8  xor     ecx, ecx
0x1800012ca  call    __scrt_initialize_crt
0x1800012cf  test    al, al
0x1800012d1  jz      loc_18000139A
0x1800012d7  call    __scrt_acquire_startup_lock
0x1800012dc  mov     bl, al
0x1800012de  mov     [rsp+48h+arg_10], al
0x1800012e2  mov     dil, 1
0x1800012e5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800012ec  jnz     loc_1800013A6
0x1800012f2  mov     cs:__scrt_current_native_startup_state, 1
0x1800012fc  call    __scrt_dllmain_before_initialize_c
0x180001301  test    al, al
0x180001303  jz      short loc_180001354
0x180001305  call    _RTC_Initialize
0x18000130a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000130f  call    __scrt_initialize_default_local_stdio_options
0x180001314  lea     rdx, __xi_z; Last
0x18000131b  lea     rcx, __xi_a; First
0x180001322  call    _initterm_e_0
0x180001327  test    eax, eax
0x180001329  jnz     short loc_180001354
0x18000132b  call    __scrt_dllmain_after_initialize_c
0x180001330  test    al, al
0x180001332  jz      short loc_180001354
0x180001334  lea     rdx, __xc_z; Last
0x18000133b  lea     rcx, __xc_a; First
0x180001342  call    _initterm_0
0x180001347  mov     cs:__scrt_current_native_startup_state, 2
0x180001351  xor     dil, dil
0x180001354  mov     cl, bl
0x180001356  call    __scrt_release_startup_lock
0x18000135b  test    dil, dil
0x18000135e  jnz     short loc_18000139A
0x180001360  call    __scrt_get_dyn_tls_init_callback
0x180001365  mov     rbx, rax
0x180001368  cmp     qword ptr [rax], 0
0x18000136c  jz      short loc_18000138D
0x18000136e  mov     rcx, rax
0x180001371  call    __scrt_is_nonwritable_in_current_image
0x180001376  test    al, al
0x180001378  jz      short loc_18000138D
0x18000137a  mov     r8, rsi
0x18000137d  mov     edx, 2
0x180001382  mov     rcx, r14
0x180001385  mov     rax, [rbx]
0x180001388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000138d  inc     cs:dword_18004A5D0
0x180001393  mov     eax, 1
0x180001398  jmp     short loc_18000139C
0x18000139a  xor     eax, eax
0x18000139c  add     rsp, 28h
0x1800013a0  pop     r14
0x1800013a2  pop     rdi
0x1800013a3  pop     rsi
0x1800013a4  pop     rbx
0x1800013a5  retn
0x1800013a6  mov     ecx, 7
0x1800013ab  call    __scrt_fastfail
0x18003f32c  push    rbp
0x18003f32e  sub     rsp, 20h
0x18003f332  mov     rbp, rdx
0x18003f335  mov     cl, [rbp+60h]
0x18003f338  add     rsp, 20h
0x18003f33c  pop     rbp
0x18003f33d  jmp     __scrt_release_startup_lock
```
