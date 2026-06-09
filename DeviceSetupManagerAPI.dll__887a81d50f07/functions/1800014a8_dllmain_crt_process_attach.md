# dllmain_crt_process_attach

- ea: `0x1800014a8`
- end: `0x1800015a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x1800014a8`
- `0x1800018c0`
- `0x180001900`
- `0x18000193c`
- `0x180001a3c`
- `0x180001b10`
- `0x180001bb0`
- `0x180002070`
- `0x180002098`
- `0x1800020bc`
- `0x1800020cc`
- `0x1800020d8`
- `0x180002436`
- `0x180002442`
- `0x18000f010`

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
    _scrt_fastfail(7u);
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
  ++dword_180017610;
  return 1;
}

```

## disassembly

```asm
0x1800014a8  push    rbx
0x1800014aa  push    rsi
0x1800014ab  push    rdi
0x1800014ac  push    r14
0x1800014ae  sub     rsp, 28h
0x1800014b2  mov     rsi, rdx
0x1800014b5  mov     r14, rcx
0x1800014b8  xor     ecx, ecx
0x1800014ba  call    __scrt_initialize_crt
0x1800014bf  test    al, al
0x1800014c1  jz      loc_18000158A
0x1800014c7  call    __scrt_acquire_startup_lock
0x1800014cc  mov     bl, al
0x1800014ce  mov     [rsp+48h+arg_10], al
0x1800014d2  mov     dil, 1
0x1800014d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800014dc  jnz     loc_180001596
0x1800014e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800014ec  call    __scrt_dllmain_before_initialize_c
0x1800014f1  test    al, al
0x1800014f3  jz      short loc_180001544
0x1800014f5  call    _RTC_Initialize
0x1800014fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800014ff  call    __scrt_initialize_default_local_stdio_options
0x180001504  lea     rdx, __xi_z; Last
0x18000150b  lea     rcx, __xi_a; First
0x180001512  call    _initterm_e_0
0x180001517  test    eax, eax
0x180001519  jnz     short loc_180001544
0x18000151b  call    __scrt_dllmain_after_initialize_c
0x180001520  test    al, al
0x180001522  jz      short loc_180001544
0x180001524  lea     rdx, __xc_z; Last
0x18000152b  lea     rcx, __xc_a; First
0x180001532  call    _initterm_0
0x180001537  mov     cs:__scrt_current_native_startup_state, 2
0x180001541  xor     dil, dil
0x180001544  mov     cl, bl
0x180001546  call    __scrt_release_startup_lock
0x18000154b  test    dil, dil
0x18000154e  jnz     short loc_18000158A
0x180001550  call    __scrt_get_dyn_tls_init_callback
0x180001555  mov     rbx, rax
0x180001558  cmp     qword ptr [rax], 0
0x18000155c  jz      short loc_18000157D
0x18000155e  mov     rcx, rax
0x180001561  call    __scrt_is_nonwritable_in_current_image
0x180001566  test    al, al
0x180001568  jz      short loc_18000157D
0x18000156a  mov     r8, rsi
0x18000156d  mov     edx, 2
0x180001572  mov     rcx, r14
0x180001575  mov     rax, [rbx]
0x180001578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000157d  inc     cs:dword_180017610
0x180001583  mov     eax, 1
0x180001588  jmp     short loc_18000158C
0x18000158a  xor     eax, eax
0x18000158c  add     rsp, 28h
0x180001590  pop     r14
0x180001592  pop     rdi
0x180001593  pop     rsi
0x180001594  pop     rbx
0x180001595  retn
0x180001596  mov     ecx, 7
0x18000159b  call    __scrt_fastfail
0x18000e4dc  push    rbp
0x18000e4de  sub     rsp, 20h
0x18000e4e2  mov     rbp, rdx
0x18000e4e5  mov     cl, [rbp+60h]
0x18000e4e8  add     rsp, 20h
0x18000e4ec  pop     rbp
0x18000e4ed  jmp     __scrt_release_startup_lock
```
