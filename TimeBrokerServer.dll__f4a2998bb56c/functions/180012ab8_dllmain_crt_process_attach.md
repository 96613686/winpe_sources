# dllmain_crt_process_attach

- ea: `0x180012ab8`
- end: `0x180012bb2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180012a60`

## callees

- `0x180012ab8`
- `0x180012e38`
- `0x180012e78`
- `0x180012eb4`
- `0x180012fb4`
- `0x180013088`
- `0x180013128`
- `0x180013428`
- `0x180013450`
- `0x180013474`
- `0x180013484`
- `0x180013490`
- `0x180013846`
- `0x180013852`
- `0x18001c010`

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
  ++dword_180026550;
  return 1;
}

```

## disassembly

```asm
0x180012ab8  push    rbx
0x180012aba  push    rsi
0x180012abb  push    rdi
0x180012abc  push    r14
0x180012abe  sub     rsp, 28h
0x180012ac2  mov     rsi, rdx
0x180012ac5  mov     r14, rcx
0x180012ac8  xor     ecx, ecx
0x180012aca  call    __scrt_initialize_crt
0x180012acf  test    al, al
0x180012ad1  jz      loc_180012B9A
0x180012ad7  call    __scrt_acquire_startup_lock
0x180012adc  mov     bl, al
0x180012ade  mov     [rsp+48h+arg_10], al
0x180012ae2  mov     dil, 1
0x180012ae5  cmp     cs:__scrt_current_native_startup_state, 0
0x180012aec  jnz     loc_180012BA6
0x180012af2  mov     cs:__scrt_current_native_startup_state, 1
0x180012afc  call    __scrt_dllmain_before_initialize_c
0x180012b01  test    al, al
0x180012b03  jz      short loc_180012B54
0x180012b05  call    _RTC_Initialize
0x180012b0a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180012b0f  call    __scrt_initialize_default_local_stdio_options
0x180012b14  lea     rdx, __xi_z; Last
0x180012b1b  lea     rcx, __xi_a; First
0x180012b22  call    _initterm_e_0
0x180012b27  test    eax, eax
0x180012b29  jnz     short loc_180012B54
0x180012b2b  call    __scrt_dllmain_after_initialize_c
0x180012b30  test    al, al
0x180012b32  jz      short loc_180012B54
0x180012b34  lea     rdx, __xc_z; Last
0x180012b3b  lea     rcx, __xc_a; First
0x180012b42  call    _initterm_0
0x180012b47  mov     cs:__scrt_current_native_startup_state, 2
0x180012b51  xor     dil, dil
0x180012b54  mov     cl, bl
0x180012b56  call    __scrt_release_startup_lock
0x180012b5b  test    dil, dil
0x180012b5e  jnz     short loc_180012B9A
0x180012b60  call    __scrt_get_dyn_tls_init_callback
0x180012b65  mov     rbx, rax
0x180012b68  cmp     qword ptr [rax], 0
0x180012b6c  jz      short loc_180012B8D
0x180012b6e  mov     rcx, rax
0x180012b71  call    __scrt_is_nonwritable_in_current_image
0x180012b76  test    al, al
0x180012b78  jz      short loc_180012B8D
0x180012b7a  mov     r8, rsi
0x180012b7d  mov     edx, 2
0x180012b82  mov     rcx, r14
0x180012b85  mov     rax, [rbx]
0x180012b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b8d  inc     cs:dword_180026550
0x180012b93  mov     eax, 1
0x180012b98  jmp     short loc_180012B9C
0x180012b9a  xor     eax, eax
0x180012b9c  add     rsp, 28h
0x180012ba0  pop     r14
0x180012ba2  pop     rdi
0x180012ba3  pop     rsi
0x180012ba4  pop     rbx
0x180012ba5  retn
0x180012ba6  mov     ecx, 7
0x180012bab  call    __scrt_fastfail
0x18001b0cd  push    rbp
0x18001b0cf  sub     rsp, 20h
0x18001b0d3  mov     rbp, rdx
0x18001b0d6  mov     cl, [rbp+60h]
0x18001b0d9  add     rsp, 20h
0x18001b0dd  pop     rbp
0x18001b0de  jmp     __scrt_release_startup_lock
```
