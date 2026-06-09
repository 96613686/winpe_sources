# dllmain_crt_process_attach

- ea: `0x180003748`
- end: `0x180003842`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800036f0`

## callees

- `0x180003748`
- `0x180003b08`
- `0x180003b48`
- `0x180003b84`
- `0x180003c84`
- `0x180003d58`
- `0x180003df8`
- `0x1800042f4`
- `0x18000431c`
- `0x180004340`
- `0x180004350`
- `0x18000435c`
- `0x180004486`
- `0x180004492`
- `0x18002b010`

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
  ++dword_18003F4D0;
  return 1;
}

```

## disassembly

```asm
0x180003748  push    rbx
0x18000374a  push    rsi
0x18000374b  push    rdi
0x18000374c  push    r14
0x18000374e  sub     rsp, 28h
0x180003752  mov     rsi, rdx
0x180003755  mov     r14, rcx
0x180003758  xor     ecx, ecx
0x18000375a  call    __scrt_initialize_crt
0x18000375f  test    al, al
0x180003761  jz      loc_18000382A
0x180003767  call    __scrt_acquire_startup_lock
0x18000376c  mov     bl, al
0x18000376e  mov     [rsp+48h+arg_10], al
0x180003772  mov     dil, 1
0x180003775  cmp     cs:__scrt_current_native_startup_state, 0
0x18000377c  jnz     loc_180003836
0x180003782  mov     cs:__scrt_current_native_startup_state, 1
0x18000378c  call    __scrt_dllmain_before_initialize_c
0x180003791  test    al, al
0x180003793  jz      short loc_1800037E4
0x180003795  call    _RTC_Initialize
0x18000379a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000379f  call    __scrt_initialize_default_local_stdio_options
0x1800037a4  lea     rdx, __xi_z; Last
0x1800037ab  lea     rcx, __xi_a; First
0x1800037b2  call    _initterm_e_0
0x1800037b7  test    eax, eax
0x1800037b9  jnz     short loc_1800037E4
0x1800037bb  call    __scrt_dllmain_after_initialize_c
0x1800037c0  test    al, al
0x1800037c2  jz      short loc_1800037E4
0x1800037c4  lea     rdx, __xc_z; Last
0x1800037cb  lea     rcx, __xc_a; First
0x1800037d2  call    _initterm_0
0x1800037d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800037e1  xor     dil, dil
0x1800037e4  mov     cl, bl
0x1800037e6  call    __scrt_release_startup_lock
0x1800037eb  test    dil, dil
0x1800037ee  jnz     short loc_18000382A
0x1800037f0  call    __scrt_get_dyn_tls_init_callback
0x1800037f5  mov     rbx, rax
0x1800037f8  cmp     qword ptr [rax], 0
0x1800037fc  jz      short loc_18000381D
0x1800037fe  mov     rcx, rax
0x180003801  call    __scrt_is_nonwritable_in_current_image
0x180003806  test    al, al
0x180003808  jz      short loc_18000381D
0x18000380a  mov     r8, rsi
0x18000380d  mov     edx, 2
0x180003812  mov     rcx, r14
0x180003815  mov     rax, [rbx]
0x180003818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381d  inc     cs:dword_18003F4D0
0x180003823  mov     eax, 1
0x180003828  jmp     short loc_18000382C
0x18000382a  xor     eax, eax
0x18000382c  add     rsp, 28h
0x180003830  pop     r14
0x180003832  pop     rdi
0x180003833  pop     rsi
0x180003834  pop     rbx
0x180003835  retn
0x180003836  mov     ecx, 7
0x18000383b  call    __scrt_fastfail
0x1800279ec  push    rbp
0x1800279ee  sub     rsp, 20h
0x1800279f2  mov     rbp, rdx
0x1800279f5  mov     cl, [rbp+60h]
0x1800279f8  add     rsp, 20h
0x1800279fc  pop     rbp
0x1800279fd  jmp     __scrt_release_startup_lock
```
