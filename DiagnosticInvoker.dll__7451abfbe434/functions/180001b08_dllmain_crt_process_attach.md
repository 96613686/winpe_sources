# dllmain_crt_process_attach

- ea: `0x180001b08`
- end: `0x180001c02`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001ab0`

## callees

- `0x180001b08`
- `0x180001f14`
- `0x180001f54`
- `0x180001f90`
- `0x180002090`
- `0x180002164`
- `0x180002204`
- `0x1800023e8`
- `0x180002410`
- `0x180002434`
- `0x180002444`
- `0x180002450`
- `0x180002976`
- `0x180002982`
- `0x180011010`

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
  ++dword_18001D350;
  return 1;
}

```

## disassembly

```asm
0x180001b08  push    rbx
0x180001b0a  push    rsi
0x180001b0b  push    rdi
0x180001b0c  push    r14
0x180001b0e  sub     rsp, 28h
0x180001b12  mov     rsi, rdx
0x180001b15  mov     r14, rcx
0x180001b18  xor     ecx, ecx
0x180001b1a  call    __scrt_initialize_crt
0x180001b1f  test    al, al
0x180001b21  jz      loc_180001BEA
0x180001b27  call    __scrt_acquire_startup_lock
0x180001b2c  mov     bl, al
0x180001b2e  mov     [rsp+48h+arg_10], al
0x180001b32  mov     dil, 1
0x180001b35  cmp     cs:__scrt_current_native_startup_state, 0
0x180001b3c  jnz     loc_180001BF6
0x180001b42  mov     cs:__scrt_current_native_startup_state, 1
0x180001b4c  call    __scrt_dllmain_before_initialize_c
0x180001b51  test    al, al
0x180001b53  jz      short loc_180001BA4
0x180001b55  call    _RTC_Initialize
0x180001b5a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001b5f  call    __scrt_initialize_default_local_stdio_options
0x180001b64  lea     rdx, __xi_z; Last
0x180001b6b  lea     rcx, __xi_a; First
0x180001b72  call    _initterm_e_0
0x180001b77  test    eax, eax
0x180001b79  jnz     short loc_180001BA4
0x180001b7b  call    __scrt_dllmain_after_initialize_c
0x180001b80  test    al, al
0x180001b82  jz      short loc_180001BA4
0x180001b84  lea     rdx, __xc_z; Last
0x180001b8b  lea     rcx, __xc_a; First
0x180001b92  call    _initterm_0
0x180001b97  mov     cs:__scrt_current_native_startup_state, 2
0x180001ba1  xor     dil, dil
0x180001ba4  mov     cl, bl
0x180001ba6  call    __scrt_release_startup_lock
0x180001bab  test    dil, dil
0x180001bae  jnz     short loc_180001BEA
0x180001bb0  call    __scrt_get_dyn_tls_init_callback
0x180001bb5  mov     rbx, rax
0x180001bb8  cmp     qword ptr [rax], 0
0x180001bbc  jz      short loc_180001BDD
0x180001bbe  mov     rcx, rax
0x180001bc1  call    __scrt_is_nonwritable_in_current_image
0x180001bc6  test    al, al
0x180001bc8  jz      short loc_180001BDD
0x180001bca  mov     r8, rsi
0x180001bcd  mov     edx, 2
0x180001bd2  mov     rcx, r14
0x180001bd5  mov     rax, [rbx]
0x180001bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bdd  inc     cs:dword_18001D350
0x180001be3  mov     eax, 1
0x180001be8  jmp     short loc_180001BEC
0x180001bea  xor     eax, eax
0x180001bec  add     rsp, 28h
0x180001bf0  pop     r14
0x180001bf2  pop     rdi
0x180001bf3  pop     rsi
0x180001bf4  pop     rbx
0x180001bf5  retn
0x180001bf6  mov     ecx, 7
0x180001bfb  call    __scrt_fastfail
0x1800100ec  push    rbp
0x1800100ee  sub     rsp, 20h
0x1800100f2  mov     rbp, rdx
0x1800100f5  mov     cl, [rbp+60h]
0x1800100f8  add     rsp, 20h
0x1800100fc  pop     rbp
0x1800100fd  jmp     __scrt_release_startup_lock
```
