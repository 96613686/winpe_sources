# dllmain_crt_process_attach

- ea: `0x1800026d8`
- end: `0x1800027e9`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002680`

## callees

- `0x1800026d8`
- `0x180002a48`
- `0x180002a88`
- `0x180002ac4`
- `0x180002be8`
- `0x180002cbc`
- `0x180002d5c`
- `0x180002ef0`
- `0x180002f2c`
- `0x180002f50`
- `0x180002f60`
- `0x180002f6c`
- `0x180005c43`
- `0x180005c4f`
- `0x1800b4010`

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
  ++dword_180126240;
  return 1;
}

```

## disassembly

```asm
0x1800026d8  mov     [rsp+arg_0], rbx
0x1800026dd  mov     [rsp+arg_8], rsi
0x1800026e2  mov     [rsp+arg_18], rdi
0x1800026e7  push    r14
0x1800026e9  sub     rsp, 20h
0x1800026ed  mov     rsi, rdx
0x1800026f0  mov     r14, rcx
0x1800026f3  xor     ecx, ecx
0x1800026f5  call    __scrt_initialize_crt
0x1800026fa  test    al, al
0x1800026fc  jz      loc_1800027C5
0x180002702  call    __scrt_acquire_startup_lock
0x180002707  mov     bl, al
0x180002709  mov     [rsp+28h+arg_10], al
0x18000270d  mov     dil, 1
0x180002710  cmp     cs:__scrt_current_native_startup_state, 0
0x180002717  jnz     loc_1800027DD
0x18000271d  mov     cs:__scrt_current_native_startup_state, 1
0x180002727  call    __scrt_dllmain_before_initialize_c
0x18000272c  test    al, al
0x18000272e  jz      short loc_18000277F
0x180002730  call    _RTC_Initialize
0x180002735  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000273a  call    __scrt_initialize_default_local_stdio_options
0x18000273f  lea     rdx, __xi_z; Last
0x180002746  lea     rcx, __xi_a; First
0x18000274d  call    _initterm_e_0
0x180002752  test    eax, eax
0x180002754  jnz     short loc_18000277F
0x180002756  call    __scrt_dllmain_after_initialize_c
0x18000275b  test    al, al
0x18000275d  jz      short loc_18000277F
0x18000275f  lea     rdx, __xc_z; Last
0x180002766  lea     rcx, __xc_a; First
0x18000276d  call    _initterm_0
0x180002772  mov     cs:__scrt_current_native_startup_state, 2
0x18000277c  xor     dil, dil
0x18000277f  mov     cl, bl
0x180002781  call    __scrt_release_startup_lock
0x180002786  test    dil, dil
0x180002789  jnz     short loc_1800027C5
0x18000278b  call    __scrt_get_dyn_tls_init_callback
0x180002790  mov     rbx, rax
0x180002793  cmp     qword ptr [rax], 0
0x180002797  jz      short loc_1800027B8
0x180002799  mov     rcx, rax
0x18000279c  call    __scrt_is_nonwritable_in_current_image
0x1800027a1  test    al, al
0x1800027a3  jz      short loc_1800027B8
0x1800027a5  mov     r8, rsi
0x1800027a8  mov     edx, 2
0x1800027ad  mov     rcx, r14
0x1800027b0  mov     rax, [rbx]
0x1800027b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b8  inc     cs:dword_180126240
0x1800027be  mov     eax, 1
0x1800027c3  jmp     short loc_1800027C7
0x1800027c5  xor     eax, eax
0x1800027c7  mov     rbx, [rsp+28h+arg_0]
0x1800027cc  mov     rsi, [rsp+28h+arg_8]
0x1800027d1  mov     rdi, [rsp+28h+arg_18]
0x1800027d6  add     rsp, 20h
0x1800027da  pop     r14
0x1800027dc  retn
0x1800027dd  mov     ecx, 7
0x1800027e2  call    __scrt_fastfail
0x1800b1092  push    rbp
0x1800b1094  sub     rsp, 20h
0x1800b1098  mov     rbp, rdx
0x1800b109b  mov     cl, [rbp+40h]
0x1800b109e  add     rsp, 20h
0x1800b10a2  pop     rbp
0x1800b10a3  jmp     __scrt_release_startup_lock
```
