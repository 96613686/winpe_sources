# dllmain_crt_process_attach

- ea: `0x180001bc8`
- end: `0x180001cc2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001b70`

## callees

- `0x180001bc8`
- `0x180001f84`
- `0x180001fc4`
- `0x180002000`
- `0x180002100`
- `0x1800021d4`
- `0x180002274`
- `0x18000244c`
- `0x180002474`
- `0x180002498`
- `0x1800024a8`
- `0x1800024b4`
- `0x180002836`
- `0x180002842`
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
  ++dword_180015430;
  return 1;
}

```

## disassembly

```asm
0x180001bc8  push    rbx
0x180001bca  push    rsi
0x180001bcb  push    rdi
0x180001bcc  push    r14
0x180001bce  sub     rsp, 28h
0x180001bd2  mov     rsi, rdx
0x180001bd5  mov     r14, rcx
0x180001bd8  xor     ecx, ecx
0x180001bda  call    __scrt_initialize_crt
0x180001bdf  test    al, al
0x180001be1  jz      loc_180001CAA
0x180001be7  call    __scrt_acquire_startup_lock
0x180001bec  mov     bl, al
0x180001bee  mov     [rsp+48h+arg_10], al
0x180001bf2  mov     dil, 1
0x180001bf5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001bfc  jnz     loc_180001CB6
0x180001c02  mov     cs:__scrt_current_native_startup_state, 1
0x180001c0c  call    __scrt_dllmain_before_initialize_c
0x180001c11  test    al, al
0x180001c13  jz      short loc_180001C64
0x180001c15  call    _RTC_Initialize
0x180001c1a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001c1f  call    __scrt_initialize_default_local_stdio_options
0x180001c24  lea     rdx, __xi_z; Last
0x180001c2b  lea     rcx, __xi_a; First
0x180001c32  call    _initterm_e_0
0x180001c37  test    eax, eax
0x180001c39  jnz     short loc_180001C64
0x180001c3b  call    __scrt_dllmain_after_initialize_c
0x180001c40  test    al, al
0x180001c42  jz      short loc_180001C64
0x180001c44  lea     rdx, __xc_z; Last
0x180001c4b  lea     rcx, __xc_a; First
0x180001c52  call    _initterm_0
0x180001c57  mov     cs:__scrt_current_native_startup_state, 2
0x180001c61  xor     dil, dil
0x180001c64  mov     cl, bl
0x180001c66  call    __scrt_release_startup_lock
0x180001c6b  test    dil, dil
0x180001c6e  jnz     short loc_180001CAA
0x180001c70  call    __scrt_get_dyn_tls_init_callback
0x180001c75  mov     rbx, rax
0x180001c78  cmp     qword ptr [rax], 0
0x180001c7c  jz      short loc_180001C9D
0x180001c7e  mov     rcx, rax
0x180001c81  call    __scrt_is_nonwritable_in_current_image
0x180001c86  test    al, al
0x180001c88  jz      short loc_180001C9D
0x180001c8a  mov     r8, rsi
0x180001c8d  mov     edx, 2
0x180001c92  mov     rcx, r14
0x180001c95  mov     rax, [rbx]
0x180001c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c9d  inc     cs:dword_180015430
0x180001ca3  mov     eax, 1
0x180001ca8  jmp     short loc_180001CAC
0x180001caa  xor     eax, eax
0x180001cac  add     rsp, 28h
0x180001cb0  pop     r14
0x180001cb2  pop     rdi
0x180001cb3  pop     rsi
0x180001cb4  pop     rbx
0x180001cb5  retn
0x180001cb6  mov     ecx, 7
0x180001cbb  call    __scrt_fastfail
0x18000e97c  push    rbp
0x18000e97e  sub     rsp, 20h
0x18000e982  mov     rbp, rdx
0x18000e985  mov     cl, [rbp+60h]
0x18000e988  add     rsp, 20h
0x18000e98c  pop     rbp
0x18000e98d  jmp     __scrt_release_startup_lock
```
