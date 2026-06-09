# dllmain_crt_process_attach

- ea: `0x180001b38`
- end: `0x180001c32`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001ae0`

## callees

- `0x180001b38`
- `0x180001ef4`
- `0x180001f34`
- `0x180001f70`
- `0x180002070`
- `0x180002144`
- `0x1800021e4`
- `0x1800023bc`
- `0x1800023e4`
- `0x180002408`
- `0x180002418`
- `0x180002424`
- `0x1800027a6`
- `0x1800027b2`
- `0x18000c010`

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
  ++dword_180012390;
  return 1;
}

```

## disassembly

```asm
0x180001b38  push    rbx
0x180001b3a  push    rsi
0x180001b3b  push    rdi
0x180001b3c  push    r14
0x180001b3e  sub     rsp, 28h
0x180001b42  mov     rsi, rdx
0x180001b45  mov     r14, rcx
0x180001b48  xor     ecx, ecx
0x180001b4a  call    __scrt_initialize_crt
0x180001b4f  test    al, al
0x180001b51  jz      loc_180001C1A
0x180001b57  call    __scrt_acquire_startup_lock
0x180001b5c  mov     bl, al
0x180001b5e  mov     [rsp+48h+arg_10], al
0x180001b62  mov     dil, 1
0x180001b65  cmp     cs:__scrt_current_native_startup_state, 0
0x180001b6c  jnz     loc_180001C26
0x180001b72  mov     cs:__scrt_current_native_startup_state, 1
0x180001b7c  call    __scrt_dllmain_before_initialize_c
0x180001b81  test    al, al
0x180001b83  jz      short loc_180001BD4
0x180001b85  call    _RTC_Initialize
0x180001b8a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001b8f  call    __scrt_initialize_default_local_stdio_options
0x180001b94  lea     rdx, __xi_z; Last
0x180001b9b  lea     rcx, __xi_a; First
0x180001ba2  call    _initterm_e_0
0x180001ba7  test    eax, eax
0x180001ba9  jnz     short loc_180001BD4
0x180001bab  call    __scrt_dllmain_after_initialize_c
0x180001bb0  test    al, al
0x180001bb2  jz      short loc_180001BD4
0x180001bb4  lea     rdx, __xc_z; Last
0x180001bbb  lea     rcx, __xc_a; First
0x180001bc2  call    _initterm_0
0x180001bc7  mov     cs:__scrt_current_native_startup_state, 2
0x180001bd1  xor     dil, dil
0x180001bd4  mov     cl, bl
0x180001bd6  call    __scrt_release_startup_lock
0x180001bdb  test    dil, dil
0x180001bde  jnz     short loc_180001C1A
0x180001be0  call    __scrt_get_dyn_tls_init_callback
0x180001be5  mov     rbx, rax
0x180001be8  cmp     qword ptr [rax], 0
0x180001bec  jz      short loc_180001C0D
0x180001bee  mov     rcx, rax
0x180001bf1  call    __scrt_is_nonwritable_in_current_image
0x180001bf6  test    al, al
0x180001bf8  jz      short loc_180001C0D
0x180001bfa  mov     r8, rsi
0x180001bfd  mov     edx, 2
0x180001c02  mov     rcx, r14
0x180001c05  mov     rax, [rbx]
0x180001c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c0d  inc     cs:dword_180012390
0x180001c13  mov     eax, 1
0x180001c18  jmp     short loc_180001C1C
0x180001c1a  xor     eax, eax
0x180001c1c  add     rsp, 28h
0x180001c20  pop     r14
0x180001c22  pop     rdi
0x180001c23  pop     rsi
0x180001c24  pop     rbx
0x180001c25  retn
0x180001c26  mov     ecx, 7
0x180001c2b  call    __scrt_fastfail
0x18000b47c  push    rbp
0x18000b47e  sub     rsp, 20h
0x18000b482  mov     rbp, rdx
0x18000b485  mov     cl, [rbp+60h]
0x18000b488  add     rsp, 20h
0x18000b48c  pop     rbp
0x18000b48d  jmp     __scrt_release_startup_lock
```
