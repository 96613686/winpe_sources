# dllmain_crt_process_attach

- ea: `0x180002758`
- end: `0x180002852`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002700`

## callees

- `0x180002758`
- `0x180002bcc`
- `0x180002c0c`
- `0x180002c48`
- `0x180002d48`
- `0x180002e1c`
- `0x180002ebc`
- `0x1800030f8`
- `0x180003120`
- `0x180003144`
- `0x180003154`
- `0x180003160`
- `0x180003516`
- `0x180003522`
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
  ++dword_18001C270;
  return 1;
}

```

## disassembly

```asm
0x180002758  push    rbx
0x18000275a  push    rsi
0x18000275b  push    rdi
0x18000275c  push    r14
0x18000275e  sub     rsp, 28h
0x180002762  mov     rsi, rdx
0x180002765  mov     r14, rcx
0x180002768  xor     ecx, ecx
0x18000276a  call    __scrt_initialize_crt
0x18000276f  test    al, al
0x180002771  jz      loc_18000283A
0x180002777  call    __scrt_acquire_startup_lock
0x18000277c  mov     bl, al
0x18000277e  mov     [rsp+48h+arg_10], al
0x180002782  mov     dil, 1
0x180002785  cmp     cs:__scrt_current_native_startup_state, 0
0x18000278c  jnz     loc_180002846
0x180002792  mov     cs:__scrt_current_native_startup_state, 1
0x18000279c  call    __scrt_dllmain_before_initialize_c
0x1800027a1  test    al, al
0x1800027a3  jz      short loc_1800027F4
0x1800027a5  call    _RTC_Initialize
0x1800027aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800027af  call    __scrt_initialize_default_local_stdio_options
0x1800027b4  lea     rdx, __xi_z; Last
0x1800027bb  lea     rcx, __xi_a; First
0x1800027c2  call    _initterm_e_0
0x1800027c7  test    eax, eax
0x1800027c9  jnz     short loc_1800027F4
0x1800027cb  call    __scrt_dllmain_after_initialize_c
0x1800027d0  test    al, al
0x1800027d2  jz      short loc_1800027F4
0x1800027d4  lea     rdx, __xc_z; Last
0x1800027db  lea     rcx, __xc_a; First
0x1800027e2  call    _initterm_0
0x1800027e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800027f1  xor     dil, dil
0x1800027f4  mov     cl, bl
0x1800027f6  call    __scrt_release_startup_lock
0x1800027fb  test    dil, dil
0x1800027fe  jnz     short loc_18000283A
0x180002800  call    __scrt_get_dyn_tls_init_callback
0x180002805  mov     rbx, rax
0x180002808  cmp     qword ptr [rax], 0
0x18000280c  jz      short loc_18000282D
0x18000280e  mov     rcx, rax
0x180002811  call    __scrt_is_nonwritable_in_current_image
0x180002816  test    al, al
0x180002818  jz      short loc_18000282D
0x18000281a  mov     r8, rsi
0x18000281d  mov     edx, 2
0x180002822  mov     rcx, r14
0x180002825  mov     rax, [rbx]
0x180002828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282d  inc     cs:dword_18001C270
0x180002833  mov     eax, 1
0x180002838  jmp     short loc_18000283C
0x18000283a  xor     eax, eax
0x18000283c  add     rsp, 28h
0x180002840  pop     r14
0x180002842  pop     rdi
0x180002843  pop     rsi
0x180002844  pop     rbx
0x180002845  retn
0x180002846  mov     ecx, 7
0x18000284b  call    __scrt_fastfail
0x180010edc  push    rbp
0x180010ede  sub     rsp, 20h
0x180010ee2  mov     rbp, rdx
0x180010ee5  mov     cl, [rbp+60h]
0x180010ee8  add     rsp, 20h
0x180010eec  pop     rbp
0x180010eed  jmp     __scrt_release_startup_lock
```
