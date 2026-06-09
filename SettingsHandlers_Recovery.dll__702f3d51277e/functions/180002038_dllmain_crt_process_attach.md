# dllmain_crt_process_attach

- ea: `0x180002038`
- end: `0x180002132`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001fe0`

## callees

- `0x180002038`
- `0x180002474`
- `0x1800024b4`
- `0x1800024f0`
- `0x1800025f0`
- `0x1800026c4`
- `0x180002764`
- `0x180002990`
- `0x1800029b8`
- `0x1800029dc`
- `0x1800029ec`
- `0x1800029f8`
- `0x180002d86`
- `0x180002d92`
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
  ++dword_180059B90;
  return 1;
}

```

## disassembly

```asm
0x180002038  push    rbx
0x18000203a  push    rsi
0x18000203b  push    rdi
0x18000203c  push    r14
0x18000203e  sub     rsp, 28h
0x180002042  mov     rsi, rdx
0x180002045  mov     r14, rcx
0x180002048  xor     ecx, ecx
0x18000204a  call    __scrt_initialize_crt
0x18000204f  test    al, al
0x180002051  jz      loc_18000211A
0x180002057  call    __scrt_acquire_startup_lock
0x18000205c  mov     bl, al
0x18000205e  mov     [rsp+48h+arg_10], al
0x180002062  mov     dil, 1
0x180002065  cmp     cs:__scrt_current_native_startup_state, 0
0x18000206c  jnz     loc_180002126
0x180002072  mov     cs:__scrt_current_native_startup_state, 1
0x18000207c  call    __scrt_dllmain_before_initialize_c
0x180002081  test    al, al
0x180002083  jz      short loc_1800020D4
0x180002085  call    _RTC_Initialize
0x18000208a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000208f  call    __scrt_initialize_default_local_stdio_options
0x180002094  lea     rdx, __xi_z; Last
0x18000209b  lea     rcx, __xi_a; First
0x1800020a2  call    _initterm_e_0
0x1800020a7  test    eax, eax
0x1800020a9  jnz     short loc_1800020D4
0x1800020ab  call    __scrt_dllmain_after_initialize_c
0x1800020b0  test    al, al
0x1800020b2  jz      short loc_1800020D4
0x1800020b4  lea     rdx, __xc_z; Last
0x1800020bb  lea     rcx, __xc_a; First
0x1800020c2  call    _initterm_0
0x1800020c7  mov     cs:__scrt_current_native_startup_state, 2
0x1800020d1  xor     dil, dil
0x1800020d4  mov     cl, bl
0x1800020d6  call    __scrt_release_startup_lock
0x1800020db  test    dil, dil
0x1800020de  jnz     short loc_18000211A
0x1800020e0  call    __scrt_get_dyn_tls_init_callback
0x1800020e5  mov     rbx, rax
0x1800020e8  cmp     qword ptr [rax], 0
0x1800020ec  jz      short loc_18000210D
0x1800020ee  mov     rcx, rax
0x1800020f1  call    __scrt_is_nonwritable_in_current_image
0x1800020f6  test    al, al
0x1800020f8  jz      short loc_18000210D
0x1800020fa  mov     r8, rsi
0x1800020fd  mov     edx, 2
0x180002102  mov     rcx, r14
0x180002105  mov     rax, [rbx]
0x180002108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000210d  inc     cs:dword_180059B90
0x180002113  mov     eax, 1
0x180002118  jmp     short loc_18000211C
0x18000211a  xor     eax, eax
0x18000211c  add     rsp, 28h
0x180002120  pop     r14
0x180002122  pop     rdi
0x180002123  pop     rsi
0x180002124  pop     rbx
0x180002125  retn
0x180002126  mov     ecx, 7
0x18000212b  call    __scrt_fastfail
0x18002929c  push    rbp
0x18002929e  sub     rsp, 20h
0x1800292a2  mov     rbp, rdx
0x1800292a5  mov     cl, [rbp+60h]
0x1800292a8  add     rsp, 20h
0x1800292ac  pop     rbp
0x1800292ad  jmp     __scrt_release_startup_lock
```
