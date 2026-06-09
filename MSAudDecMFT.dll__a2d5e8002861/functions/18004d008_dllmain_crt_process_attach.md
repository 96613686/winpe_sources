# dllmain_crt_process_attach

- ea: `0x18004d008`
- end: `0x18004d102`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18004cfb0`

## callees

- `0x18004d008`
- `0x18004d400`
- `0x18004d428`
- `0x18004d44c`
- `0x18004d48c`
- `0x18004d4c8`
- `0x18004d5c8`
- `0x18004d69c`
- `0x18004d73c`
- `0x18004d7f8`
- `0x18004d808`
- `0x18004d814`
- `0x18004db86`
- `0x18004db92`
- `0x180097010`

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
  ++dword_1800E57D0;
  return 1;
}

```

## disassembly

```asm
0x18004d008  push    rbx
0x18004d00a  push    rsi
0x18004d00b  push    rdi
0x18004d00c  push    r14
0x18004d00e  sub     rsp, 28h
0x18004d012  mov     rsi, rdx
0x18004d015  mov     r14, rcx
0x18004d018  xor     ecx, ecx
0x18004d01a  call    __scrt_initialize_crt
0x18004d01f  test    al, al
0x18004d021  jz      loc_18004D0EA
0x18004d027  call    __scrt_acquire_startup_lock
0x18004d02c  mov     bl, al
0x18004d02e  mov     [rsp+48h+arg_10], al
0x18004d032  mov     dil, 1
0x18004d035  cmp     cs:__scrt_current_native_startup_state, 0
0x18004d03c  jnz     loc_18004D0F6
0x18004d042  mov     cs:__scrt_current_native_startup_state, 1
0x18004d04c  call    __scrt_dllmain_before_initialize_c
0x18004d051  test    al, al
0x18004d053  jz      short loc_18004D0A4
0x18004d055  call    _RTC_Initialize
0x18004d05a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18004d05f  call    __scrt_initialize_default_local_stdio_options
0x18004d064  lea     rdx, __xi_z; Last
0x18004d06b  lea     rcx, __xi_a; First
0x18004d072  call    _initterm_e_0
0x18004d077  test    eax, eax
0x18004d079  jnz     short loc_18004D0A4
0x18004d07b  call    __scrt_dllmain_after_initialize_c
0x18004d080  test    al, al
0x18004d082  jz      short loc_18004D0A4
0x18004d084  lea     rdx, __xc_z; Last
0x18004d08b  lea     rcx, __xc_a; First
0x18004d092  call    _initterm_0
0x18004d097  mov     cs:__scrt_current_native_startup_state, 2
0x18004d0a1  xor     dil, dil
0x18004d0a4  mov     cl, bl
0x18004d0a6  call    __scrt_release_startup_lock
0x18004d0ab  test    dil, dil
0x18004d0ae  jnz     short loc_18004D0EA
0x18004d0b0  call    __scrt_get_dyn_tls_init_callback
0x18004d0b5  mov     rbx, rax
0x18004d0b8  cmp     qword ptr [rax], 0
0x18004d0bc  jz      short loc_18004D0DD
0x18004d0be  mov     rcx, rax
0x18004d0c1  call    __scrt_is_nonwritable_in_current_image
0x18004d0c6  test    al, al
0x18004d0c8  jz      short loc_18004D0DD
0x18004d0ca  mov     r8, rsi
0x18004d0cd  mov     edx, 2
0x18004d0d2  mov     rcx, r14
0x18004d0d5  mov     rax, [rbx]
0x18004d0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0dd  inc     cs:dword_1800E57D0
0x18004d0e3  mov     eax, 1
0x18004d0e8  jmp     short loc_18004D0EC
0x18004d0ea  xor     eax, eax
0x18004d0ec  add     rsp, 28h
0x18004d0f0  pop     r14
0x18004d0f2  pop     rdi
0x18004d0f3  pop     rsi
0x18004d0f4  pop     rbx
0x18004d0f5  retn
0x18004d0f6  mov     ecx, 7
0x18004d0fb  call    __scrt_fastfail
0x180096208  push    rbp
0x18009620a  sub     rsp, 20h
0x18009620e  mov     rbp, rdx
0x180096211  mov     cl, [rbp+60h]
0x180096214  add     rsp, 20h
0x180096218  pop     rbp
0x180096219  jmp     __scrt_release_startup_lock
```
