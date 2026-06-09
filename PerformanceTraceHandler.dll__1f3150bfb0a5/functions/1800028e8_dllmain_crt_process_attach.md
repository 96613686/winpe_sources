# dllmain_crt_process_attach

- ea: `0x1800028e8`
- end: `0x1800029e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002890`

## callees

- `0x1800028e8`
- `0x180002c24`
- `0x180002c64`
- `0x180002ca0`
- `0x180002da0`
- `0x180002e74`
- `0x180002f14`
- `0x180003464`
- `0x18000348c`
- `0x1800034b0`
- `0x1800034c0`
- `0x1800034cc`
- `0x1800035d6`
- `0x1800035e2`
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
  ++dword_180027718;
  return 1;
}

```

## disassembly

```asm
0x1800028e8  push    rbx
0x1800028ea  push    rsi
0x1800028eb  push    rdi
0x1800028ec  push    r14
0x1800028ee  sub     rsp, 28h
0x1800028f2  mov     rsi, rdx
0x1800028f5  mov     r14, rcx
0x1800028f8  xor     ecx, ecx
0x1800028fa  call    __scrt_initialize_crt
0x1800028ff  test    al, al
0x180002901  jz      loc_1800029CA
0x180002907  call    __scrt_acquire_startup_lock
0x18000290c  mov     bl, al
0x18000290e  mov     [rsp+48h+arg_10], al
0x180002912  mov     dil, 1
0x180002915  cmp     cs:__scrt_current_native_startup_state, 0
0x18000291c  jnz     loc_1800029D6
0x180002922  mov     cs:__scrt_current_native_startup_state, 1
0x18000292c  call    __scrt_dllmain_before_initialize_c
0x180002931  test    al, al
0x180002933  jz      short loc_180002984
0x180002935  call    _RTC_Initialize
0x18000293a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000293f  call    __scrt_initialize_default_local_stdio_options
0x180002944  lea     rdx, __xi_z; Last
0x18000294b  lea     rcx, __xi_a; First
0x180002952  call    _initterm_e_0
0x180002957  test    eax, eax
0x180002959  jnz     short loc_180002984
0x18000295b  call    __scrt_dllmain_after_initialize_c
0x180002960  test    al, al
0x180002962  jz      short loc_180002984
0x180002964  lea     rdx, __xc_z; Last
0x18000296b  lea     rcx, __xc_a; First
0x180002972  call    _initterm_0
0x180002977  mov     cs:__scrt_current_native_startup_state, 2
0x180002981  xor     dil, dil
0x180002984  mov     cl, bl
0x180002986  call    __scrt_release_startup_lock
0x18000298b  test    dil, dil
0x18000298e  jnz     short loc_1800029CA
0x180002990  call    __scrt_get_dyn_tls_init_callback
0x180002995  mov     rbx, rax
0x180002998  cmp     qword ptr [rax], 0
0x18000299c  jz      short loc_1800029BD
0x18000299e  mov     rcx, rax
0x1800029a1  call    __scrt_is_nonwritable_in_current_image
0x1800029a6  test    al, al
0x1800029a8  jz      short loc_1800029BD
0x1800029aa  mov     r8, rsi
0x1800029ad  mov     edx, 2
0x1800029b2  mov     rcx, r14
0x1800029b5  mov     rax, [rbx]
0x1800029b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bd  inc     cs:dword_180027718
0x1800029c3  mov     eax, 1
0x1800029c8  jmp     short loc_1800029CC
0x1800029ca  xor     eax, eax
0x1800029cc  add     rsp, 28h
0x1800029d0  pop     r14
0x1800029d2  pop     rdi
0x1800029d3  pop     rsi
0x1800029d4  pop     rbx
0x1800029d5  retn
0x1800029d6  mov     ecx, 7
0x1800029db  call    __scrt_fastfail
0x18001a5fc  push    rbp
0x18001a5fe  sub     rsp, 20h
0x18001a602  mov     rbp, rdx
0x18001a605  mov     cl, [rbp+60h]
0x18001a608  add     rsp, 20h
0x18001a60c  pop     rbp
0x18001a60d  jmp     __scrt_release_startup_lock
```
