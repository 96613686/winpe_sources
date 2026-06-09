# dllmain_crt_process_attach

- ea: `0x180008518`
- end: `0x180008612`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800084c0`

## callees

- `0x180008518`
- `0x180008898`
- `0x1800088d8`
- `0x180008914`
- `0x180008a14`
- `0x180008ae8`
- `0x180008b88`
- `0x180009084`
- `0x1800090ac`
- `0x1800090d0`
- `0x1800090e0`
- `0x1800090ec`
- `0x180009206`
- `0x180009212`
- `0x18004a010`

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
  ++dword_180057410;
  return 1;
}

```

## disassembly

```asm
0x180008518  push    rbx
0x18000851a  push    rsi
0x18000851b  push    rdi
0x18000851c  push    r14
0x18000851e  sub     rsp, 28h
0x180008522  mov     rsi, rdx
0x180008525  mov     r14, rcx
0x180008528  xor     ecx, ecx
0x18000852a  call    __scrt_initialize_crt
0x18000852f  test    al, al
0x180008531  jz      loc_1800085FA
0x180008537  call    __scrt_acquire_startup_lock
0x18000853c  mov     bl, al
0x18000853e  mov     [rsp+48h+arg_10], al
0x180008542  mov     dil, 1
0x180008545  cmp     cs:__scrt_current_native_startup_state, 0
0x18000854c  jnz     loc_180008606
0x180008552  mov     cs:__scrt_current_native_startup_state, 1
0x18000855c  call    __scrt_dllmain_before_initialize_c
0x180008561  test    al, al
0x180008563  jz      short loc_1800085B4
0x180008565  call    _RTC_Initialize
0x18000856a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000856f  call    __scrt_initialize_default_local_stdio_options
0x180008574  lea     rdx, __xi_z; Last
0x18000857b  lea     rcx, __xi_a; First
0x180008582  call    _initterm_e_0
0x180008587  test    eax, eax
0x180008589  jnz     short loc_1800085B4
0x18000858b  call    __scrt_dllmain_after_initialize_c
0x180008590  test    al, al
0x180008592  jz      short loc_1800085B4
0x180008594  lea     rdx, __xc_z; Last
0x18000859b  lea     rcx, __xc_a; First
0x1800085a2  call    _initterm_0
0x1800085a7  mov     cs:__scrt_current_native_startup_state, 2
0x1800085b1  xor     dil, dil
0x1800085b4  mov     cl, bl
0x1800085b6  call    __scrt_release_startup_lock
0x1800085bb  test    dil, dil
0x1800085be  jnz     short loc_1800085FA
0x1800085c0  call    __scrt_get_dyn_tls_init_callback
0x1800085c5  mov     rbx, rax
0x1800085c8  cmp     qword ptr [rax], 0
0x1800085cc  jz      short loc_1800085ED
0x1800085ce  mov     rcx, rax
0x1800085d1  call    __scrt_is_nonwritable_in_current_image
0x1800085d6  test    al, al
0x1800085d8  jz      short loc_1800085ED
0x1800085da  mov     r8, rsi
0x1800085dd  mov     edx, 2
0x1800085e2  mov     rcx, r14
0x1800085e5  mov     rax, [rbx]
0x1800085e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ed  inc     cs:dword_180057410
0x1800085f3  mov     eax, 1
0x1800085f8  jmp     short loc_1800085FC
0x1800085fa  xor     eax, eax
0x1800085fc  add     rsp, 28h
0x180008600  pop     r14
0x180008602  pop     rdi
0x180008603  pop     rsi
0x180008604  pop     rbx
0x180008605  retn
0x180008606  mov     ecx, 7
0x18000860b  call    __scrt_fastfail
0x18004722c  push    rbp
0x18004722e  sub     rsp, 20h
0x180047232  mov     rbp, rdx
0x180047235  mov     cl, [rbp+60h]
0x180047238  add     rsp, 20h
0x18004723c  pop     rbp
0x18004723d  jmp     __scrt_release_startup_lock
```
