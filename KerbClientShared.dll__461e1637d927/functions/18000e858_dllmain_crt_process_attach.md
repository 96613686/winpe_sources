# dllmain_crt_process_attach

- ea: `0x18000e858`
- end: `0x18000e952`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000e800`

## callees

- `0x18000e858`
- `0x18000eb94`
- `0x18000ebd4`
- `0x18000ec10`
- `0x18000ed10`
- `0x18000ede4`
- `0x18000ee84`
- `0x18000f058`
- `0x18000f080`
- `0x18000f0a4`
- `0x18000f0b4`
- `0x18000f0c0`
- `0x18000f416`
- `0x18000f422`
- `0x180029010`

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
  ++dword_1800331F0;
  return 1;
}

```

## disassembly

```asm
0x18000e858  push    rbx
0x18000e85a  push    rsi
0x18000e85b  push    rdi
0x18000e85c  push    r14
0x18000e85e  sub     rsp, 28h
0x18000e862  mov     rsi, rdx
0x18000e865  mov     r14, rcx
0x18000e868  xor     ecx, ecx
0x18000e86a  call    __scrt_initialize_crt
0x18000e86f  test    al, al
0x18000e871  jz      loc_18000E93A
0x18000e877  call    __scrt_acquire_startup_lock
0x18000e87c  mov     bl, al
0x18000e87e  mov     [rsp+48h+arg_10], al
0x18000e882  mov     dil, 1
0x18000e885  cmp     cs:__scrt_current_native_startup_state, 0
0x18000e88c  jnz     loc_18000E946
0x18000e892  mov     cs:__scrt_current_native_startup_state, 1
0x18000e89c  call    __scrt_dllmain_before_initialize_c
0x18000e8a1  test    al, al
0x18000e8a3  jz      short loc_18000E8F4
0x18000e8a5  call    _RTC_Initialize
0x18000e8aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000e8af  call    __scrt_initialize_default_local_stdio_options
0x18000e8b4  lea     rdx, __xi_z; Last
0x18000e8bb  lea     rcx, __xi_a; First
0x18000e8c2  call    _initterm_e_0
0x18000e8c7  test    eax, eax
0x18000e8c9  jnz     short loc_18000E8F4
0x18000e8cb  call    __scrt_dllmain_after_initialize_c
0x18000e8d0  test    al, al
0x18000e8d2  jz      short loc_18000E8F4
0x18000e8d4  lea     rdx, __xc_z; Last
0x18000e8db  lea     rcx, __xc_a; First
0x18000e8e2  call    _initterm_0
0x18000e8e7  mov     cs:__scrt_current_native_startup_state, 2
0x18000e8f1  xor     dil, dil
0x18000e8f4  mov     cl, bl
0x18000e8f6  call    __scrt_release_startup_lock
0x18000e8fb  test    dil, dil
0x18000e8fe  jnz     short loc_18000E93A
0x18000e900  call    __scrt_get_dyn_tls_init_callback
0x18000e905  mov     rbx, rax
0x18000e908  cmp     qword ptr [rax], 0
0x18000e90c  jz      short loc_18000E92D
0x18000e90e  mov     rcx, rax
0x18000e911  call    __scrt_is_nonwritable_in_current_image
0x18000e916  test    al, al
0x18000e918  jz      short loc_18000E92D
0x18000e91a  mov     r8, rsi
0x18000e91d  mov     edx, 2
0x18000e922  mov     rcx, r14
0x18000e925  mov     rax, [rbx]
0x18000e928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e92d  inc     cs:dword_1800331F0
0x18000e933  mov     eax, 1
0x18000e938  jmp     short loc_18000E93C
0x18000e93a  xor     eax, eax
0x18000e93c  add     rsp, 28h
0x18000e940  pop     r14
0x18000e942  pop     rdi
0x18000e943  pop     rsi
0x18000e944  pop     rbx
0x18000e945  retn
0x18000e946  mov     ecx, 7
0x18000e94b  call    __scrt_fastfail
0x1800284a2  push    rbp
0x1800284a4  sub     rsp, 20h
0x1800284a8  mov     rbp, rdx
0x1800284ab  mov     cl, [rbp+60h]
0x1800284ae  add     rsp, 20h
0x1800284b2  pop     rbp
0x1800284b3  jmp     __scrt_release_startup_lock
```
