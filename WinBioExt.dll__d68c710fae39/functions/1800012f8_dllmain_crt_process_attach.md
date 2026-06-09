# dllmain_crt_process_attach

- ea: `0x1800012f8`
- end: `0x1800013f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800012a0`

## callees

- `0x1800012f8`
- `0x180001634`
- `0x180001674`
- `0x1800016b0`
- `0x1800017b0`
- `0x180001884`
- `0x180001924`
- `0x180001afc`
- `0x180001b24`
- `0x180001b48`
- `0x180001b58`
- `0x180001b64`
- `0x180001f66`
- `0x180001f72`
- `0x18000b010`

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
  ++dword_180010370;
  return 1;
}

```

## disassembly

```asm
0x1800012f8  push    rbx
0x1800012fa  push    rsi
0x1800012fb  push    rdi
0x1800012fc  push    r14
0x1800012fe  sub     rsp, 28h
0x180001302  mov     rsi, rdx
0x180001305  mov     r14, rcx
0x180001308  xor     ecx, ecx
0x18000130a  call    __scrt_initialize_crt
0x18000130f  test    al, al
0x180001311  jz      loc_1800013DA
0x180001317  call    __scrt_acquire_startup_lock
0x18000131c  mov     bl, al
0x18000131e  mov     [rsp+48h+arg_10], al
0x180001322  mov     dil, 1
0x180001325  cmp     cs:__scrt_current_native_startup_state, 0
0x18000132c  jnz     loc_1800013E6
0x180001332  mov     cs:__scrt_current_native_startup_state, 1
0x18000133c  call    __scrt_dllmain_before_initialize_c
0x180001341  test    al, al
0x180001343  jz      short loc_180001394
0x180001345  call    _RTC_Initialize
0x18000134a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000134f  call    __scrt_initialize_default_local_stdio_options
0x180001354  lea     rdx, __xi_z; Last
0x18000135b  lea     rcx, __xi_a; First
0x180001362  call    _initterm_e_0
0x180001367  test    eax, eax
0x180001369  jnz     short loc_180001394
0x18000136b  call    __scrt_dllmain_after_initialize_c
0x180001370  test    al, al
0x180001372  jz      short loc_180001394
0x180001374  lea     rdx, __xc_z; Last
0x18000137b  lea     rcx, __xc_a; First
0x180001382  call    _initterm_0
0x180001387  mov     cs:__scrt_current_native_startup_state, 2
0x180001391  xor     dil, dil
0x180001394  mov     cl, bl
0x180001396  call    __scrt_release_startup_lock
0x18000139b  test    dil, dil
0x18000139e  jnz     short loc_1800013DA
0x1800013a0  call    __scrt_get_dyn_tls_init_callback
0x1800013a5  mov     rbx, rax
0x1800013a8  cmp     qword ptr [rax], 0
0x1800013ac  jz      short loc_1800013CD
0x1800013ae  mov     rcx, rax
0x1800013b1  call    __scrt_is_nonwritable_in_current_image
0x1800013b6  test    al, al
0x1800013b8  jz      short loc_1800013CD
0x1800013ba  mov     r8, rsi
0x1800013bd  mov     edx, 2
0x1800013c2  mov     rcx, r14
0x1800013c5  mov     rax, [rbx]
0x1800013c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013cd  inc     cs:dword_180010370
0x1800013d3  mov     eax, 1
0x1800013d8  jmp     short loc_1800013DC
0x1800013da  xor     eax, eax
0x1800013dc  add     rsp, 28h
0x1800013e0  pop     r14
0x1800013e2  pop     rdi
0x1800013e3  pop     rsi
0x1800013e4  pop     rbx
0x1800013e5  retn
0x1800013e6  mov     ecx, 7
0x1800013eb  call    __scrt_fastfail
0x18000a03c  push    rbp
0x18000a03e  sub     rsp, 20h
0x18000a042  mov     rbp, rdx
0x18000a045  mov     cl, [rbp+60h]
0x18000a048  add     rsp, 20h
0x18000a04c  pop     rbp
0x18000a04d  jmp     __scrt_release_startup_lock
```
