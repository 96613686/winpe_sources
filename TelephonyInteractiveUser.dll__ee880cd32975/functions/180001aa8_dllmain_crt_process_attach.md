# dllmain_crt_process_attach

- ea: `0x180001aa8`
- end: `0x180001ba2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001aa8`
- `0x180001e08`
- `0x180001e48`
- `0x180001e84`
- `0x180001f84`
- `0x180002058`
- `0x1800020f8`
- `0x180002304`
- `0x18000232c`
- `0x180002350`
- `0x180002360`
- `0x18000236c`
- `0x1800026b6`
- `0x1800026c2`
- `0x180019010`

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
  ++dword_180025170;
  return 1;
}

```

## disassembly

```asm
0x180001aa8  push    rbx
0x180001aaa  push    rsi
0x180001aab  push    rdi
0x180001aac  push    r14
0x180001aae  sub     rsp, 28h
0x180001ab2  mov     rsi, rdx
0x180001ab5  mov     r14, rcx
0x180001ab8  xor     ecx, ecx
0x180001aba  call    __scrt_initialize_crt
0x180001abf  test    al, al
0x180001ac1  jz      loc_180001B8A
0x180001ac7  call    __scrt_acquire_startup_lock
0x180001acc  mov     bl, al
0x180001ace  mov     [rsp+48h+arg_10], al
0x180001ad2  mov     dil, 1
0x180001ad5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001adc  jnz     loc_180001B96
0x180001ae2  mov     cs:__scrt_current_native_startup_state, 1
0x180001aec  call    __scrt_dllmain_before_initialize_c
0x180001af1  test    al, al
0x180001af3  jz      short loc_180001B44
0x180001af5  call    _RTC_Initialize
0x180001afa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001aff  call    __scrt_initialize_default_local_stdio_options
0x180001b04  lea     rdx, __xi_z; Last
0x180001b0b  lea     rcx, __xi_a; First
0x180001b12  call    _initterm_e_0
0x180001b17  test    eax, eax
0x180001b19  jnz     short loc_180001B44
0x180001b1b  call    __scrt_dllmain_after_initialize_c
0x180001b20  test    al, al
0x180001b22  jz      short loc_180001B44
0x180001b24  lea     rdx, __xc_z; Last
0x180001b2b  lea     rcx, __xc_a; First
0x180001b32  call    _initterm_0
0x180001b37  mov     cs:__scrt_current_native_startup_state, 2
0x180001b41  xor     dil, dil
0x180001b44  mov     cl, bl
0x180001b46  call    __scrt_release_startup_lock
0x180001b4b  test    dil, dil
0x180001b4e  jnz     short loc_180001B8A
0x180001b50  call    __scrt_get_dyn_tls_init_callback
0x180001b55  mov     rbx, rax
0x180001b58  cmp     qword ptr [rax], 0
0x180001b5c  jz      short loc_180001B7D
0x180001b5e  mov     rcx, rax
0x180001b61  call    __scrt_is_nonwritable_in_current_image
0x180001b66  test    al, al
0x180001b68  jz      short loc_180001B7D
0x180001b6a  mov     r8, rsi
0x180001b6d  mov     edx, 2
0x180001b72  mov     rcx, r14
0x180001b75  mov     rax, [rbx]
0x180001b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b7d  inc     cs:dword_180025170
0x180001b83  mov     eax, 1
0x180001b88  jmp     short loc_180001B8C
0x180001b8a  xor     eax, eax
0x180001b8c  add     rsp, 28h
0x180001b90  pop     r14
0x180001b92  pop     rdi
0x180001b93  pop     rsi
0x180001b94  pop     rbx
0x180001b95  retn
0x180001b96  mov     ecx, 7
0x180001b9b  call    __scrt_fastfail
0x1800188bc  push    rbp
0x1800188be  sub     rsp, 20h
0x1800188c2  mov     rbp, rdx
0x1800188c5  mov     cl, [rbp+60h]
0x1800188c8  add     rsp, 20h
0x1800188cc  pop     rbp
0x1800188cd  jmp     __scrt_release_startup_lock
```
