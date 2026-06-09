# dllmain_crt_process_attach

- ea: `0x180077d48`
- end: `0x180077e42`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180077cf0`

## callees

- `0x180077d48`
- `0x18007813c`
- `0x180078164`
- `0x180078188`
- `0x1800781c8`
- `0x180078204`
- `0x180078304`
- `0x1800783d8`
- `0x180078478`
- `0x180078534`
- `0x180078544`
- `0x180078550`
- `0x180078876`
- `0x180078882`
- `0x1800b0010`

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
  ++dword_1800D0CF0;
  return 1;
}

```

## disassembly

```asm
0x180077d48  push    rbx
0x180077d4a  push    rsi
0x180077d4b  push    rdi
0x180077d4c  push    r14
0x180077d4e  sub     rsp, 28h
0x180077d52  mov     rsi, rdx
0x180077d55  mov     r14, rcx
0x180077d58  xor     ecx, ecx
0x180077d5a  call    __scrt_initialize_crt
0x180077d5f  test    al, al
0x180077d61  jz      loc_180077E2A
0x180077d67  call    __scrt_acquire_startup_lock
0x180077d6c  mov     bl, al
0x180077d6e  mov     [rsp+48h+arg_10], al
0x180077d72  mov     dil, 1
0x180077d75  cmp     cs:__scrt_current_native_startup_state, 0
0x180077d7c  jnz     loc_180077E36
0x180077d82  mov     cs:__scrt_current_native_startup_state, 1
0x180077d8c  call    __scrt_dllmain_before_initialize_c
0x180077d91  test    al, al
0x180077d93  jz      short loc_180077DE4
0x180077d95  call    _RTC_Initialize
0x180077d9a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180077d9f  call    __scrt_initialize_default_local_stdio_options
0x180077da4  lea     rdx, __xi_z; Last
0x180077dab  lea     rcx, __xi_a; First
0x180077db2  call    _initterm_e_0
0x180077db7  test    eax, eax
0x180077db9  jnz     short loc_180077DE4
0x180077dbb  call    __scrt_dllmain_after_initialize_c
0x180077dc0  test    al, al
0x180077dc2  jz      short loc_180077DE4
0x180077dc4  lea     rdx, __xc_z; Last
0x180077dcb  lea     rcx, __xc_a; First
0x180077dd2  call    _initterm_0
0x180077dd7  mov     cs:__scrt_current_native_startup_state, 2
0x180077de1  xor     dil, dil
0x180077de4  mov     cl, bl
0x180077de6  call    __scrt_release_startup_lock
0x180077deb  test    dil, dil
0x180077dee  jnz     short loc_180077E2A
0x180077df0  call    __scrt_get_dyn_tls_init_callback
0x180077df5  mov     rbx, rax
0x180077df8  cmp     qword ptr [rax], 0
0x180077dfc  jz      short loc_180077E1D
0x180077dfe  mov     rcx, rax
0x180077e01  call    __scrt_is_nonwritable_in_current_image
0x180077e06  test    al, al
0x180077e08  jz      short loc_180077E1D
0x180077e0a  mov     r8, rsi
0x180077e0d  mov     edx, 2
0x180077e12  mov     rcx, r14
0x180077e15  mov     rax, [rbx]
0x180077e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077e1d  inc     cs:dword_1800D0CF0
0x180077e23  mov     eax, 1
0x180077e28  jmp     short loc_180077E2C
0x180077e2a  xor     eax, eax
0x180077e2c  add     rsp, 28h
0x180077e30  pop     r14
0x180077e32  pop     rdi
0x180077e33  pop     rsi
0x180077e34  pop     rbx
0x180077e35  retn
0x180077e36  mov     ecx, 7
0x180077e3b  call    __scrt_fastfail
0x1800af79f  push    rbp
0x1800af7a1  sub     rsp, 20h
0x1800af7a5  mov     rbp, rdx
0x1800af7a8  mov     cl, [rbp+60h]
0x1800af7ab  add     rsp, 20h
0x1800af7af  pop     rbp
0x1800af7b0  jmp     __scrt_release_startup_lock
```
