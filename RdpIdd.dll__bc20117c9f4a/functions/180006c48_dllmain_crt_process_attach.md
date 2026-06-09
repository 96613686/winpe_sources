# dllmain_crt_process_attach

- ea: `0x180006c48`
- end: `0x180006d42`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180006bf0`

## callees

- `0x180006c48`
- `0x180006fc8`
- `0x180007008`
- `0x180007044`
- `0x180007144`
- `0x180007218`
- `0x1800072b8`
- `0x18000785c`
- `0x180007884`
- `0x1800078a8`
- `0x1800078b8`
- `0x1800078c4`
- `0x1800079d6`
- `0x1800079e2`
- `0x18003f010`

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
  ++dword_180057AB0;
  return 1;
}

```

## disassembly

```asm
0x180006c48  push    rbx
0x180006c4a  push    rsi
0x180006c4b  push    rdi
0x180006c4c  push    r14
0x180006c4e  sub     rsp, 28h
0x180006c52  mov     rsi, rdx
0x180006c55  mov     r14, rcx
0x180006c58  xor     ecx, ecx
0x180006c5a  call    __scrt_initialize_crt
0x180006c5f  test    al, al
0x180006c61  jz      loc_180006D2A
0x180006c67  call    __scrt_acquire_startup_lock
0x180006c6c  mov     bl, al
0x180006c6e  mov     [rsp+48h+arg_10], al
0x180006c72  mov     dil, 1
0x180006c75  cmp     cs:__scrt_current_native_startup_state, 0
0x180006c7c  jnz     loc_180006D36
0x180006c82  mov     cs:__scrt_current_native_startup_state, 1
0x180006c8c  call    __scrt_dllmain_before_initialize_c
0x180006c91  test    al, al
0x180006c93  jz      short loc_180006CE4
0x180006c95  call    _RTC_Initialize
0x180006c9a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180006c9f  call    __scrt_initialize_default_local_stdio_options
0x180006ca4  lea     rdx, __xi_z; Last
0x180006cab  lea     rcx, __xi_a; First
0x180006cb2  call    _initterm_e_0
0x180006cb7  test    eax, eax
0x180006cb9  jnz     short loc_180006CE4
0x180006cbb  call    __scrt_dllmain_after_initialize_c
0x180006cc0  test    al, al
0x180006cc2  jz      short loc_180006CE4
0x180006cc4  lea     rdx, __xc_z; Last
0x180006ccb  lea     rcx, __xc_a; First
0x180006cd2  call    _initterm_0
0x180006cd7  mov     cs:__scrt_current_native_startup_state, 2
0x180006ce1  xor     dil, dil
0x180006ce4  mov     cl, bl
0x180006ce6  call    __scrt_release_startup_lock
0x180006ceb  test    dil, dil
0x180006cee  jnz     short loc_180006D2A
0x180006cf0  call    __scrt_get_dyn_tls_init_callback
0x180006cf5  mov     rbx, rax
0x180006cf8  cmp     qword ptr [rax], 0
0x180006cfc  jz      short loc_180006D1D
0x180006cfe  mov     rcx, rax
0x180006d01  call    __scrt_is_nonwritable_in_current_image
0x180006d06  test    al, al
0x180006d08  jz      short loc_180006D1D
0x180006d0a  mov     r8, rsi
0x180006d0d  mov     edx, 2
0x180006d12  mov     rcx, r14
0x180006d15  mov     rax, [rbx]
0x180006d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1d  inc     cs:dword_180057AB0
0x180006d23  mov     eax, 1
0x180006d28  jmp     short loc_180006D2C
0x180006d2a  xor     eax, eax
0x180006d2c  add     rsp, 28h
0x180006d30  pop     r14
0x180006d32  pop     rdi
0x180006d33  pop     rsi
0x180006d34  pop     rbx
0x180006d35  retn
0x180006d36  mov     ecx, 7
0x180006d3b  call    __scrt_fastfail
0x18003b54c  push    rbp
0x18003b54e  sub     rsp, 20h
0x18003b552  mov     rbp, rdx
0x18003b555  mov     cl, [rbp+60h]
0x18003b558  add     rsp, 20h
0x18003b55c  pop     rbp
0x18003b55d  jmp     __scrt_release_startup_lock
```
