# dllmain_crt_process_attach

- ea: `0x180002e68`
- end: `0x180002f62`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002e10`

## callees

- `0x180002e68`
- `0x1800031c8`
- `0x180003208`
- `0x180003244`
- `0x180003344`
- `0x180003418`
- `0x1800034b8`
- `0x1800036b8`
- `0x1800036e0`
- `0x180003704`
- `0x180003714`
- `0x180003720`
- `0x180003af6`
- `0x180003b02`
- `0x1800c3010`

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
  ++dword_180129BD0;
  return 1;
}

```

## disassembly

```asm
0x180002e68  push    rbx
0x180002e6a  push    rsi
0x180002e6b  push    rdi
0x180002e6c  push    r14
0x180002e6e  sub     rsp, 28h
0x180002e72  mov     rsi, rdx
0x180002e75  mov     r14, rcx
0x180002e78  xor     ecx, ecx
0x180002e7a  call    __scrt_initialize_crt
0x180002e7f  test    al, al
0x180002e81  jz      loc_180002F4A
0x180002e87  call    __scrt_acquire_startup_lock
0x180002e8c  mov     bl, al
0x180002e8e  mov     [rsp+48h+arg_10], al
0x180002e92  mov     dil, 1
0x180002e95  cmp     cs:__scrt_current_native_startup_state, 0
0x180002e9c  jnz     loc_180002F56
0x180002ea2  mov     cs:__scrt_current_native_startup_state, 1
0x180002eac  call    __scrt_dllmain_before_initialize_c
0x180002eb1  test    al, al
0x180002eb3  jz      short loc_180002F04
0x180002eb5  call    _RTC_Initialize
0x180002eba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180002ebf  call    __scrt_initialize_default_local_stdio_options
0x180002ec4  lea     rdx, __xi_z; Last
0x180002ecb  lea     rcx, __xi_a; First
0x180002ed2  call    _initterm_e_0
0x180002ed7  test    eax, eax
0x180002ed9  jnz     short loc_180002F04
0x180002edb  call    __scrt_dllmain_after_initialize_c
0x180002ee0  test    al, al
0x180002ee2  jz      short loc_180002F04
0x180002ee4  lea     rdx, __xc_z; Last
0x180002eeb  lea     rcx, __xc_a; First
0x180002ef2  call    _initterm_0
0x180002ef7  mov     cs:__scrt_current_native_startup_state, 2
0x180002f01  xor     dil, dil
0x180002f04  mov     cl, bl
0x180002f06  call    __scrt_release_startup_lock
0x180002f0b  test    dil, dil
0x180002f0e  jnz     short loc_180002F4A
0x180002f10  call    __scrt_get_dyn_tls_init_callback
0x180002f15  mov     rbx, rax
0x180002f18  cmp     qword ptr [rax], 0
0x180002f1c  jz      short loc_180002F3D
0x180002f1e  mov     rcx, rax
0x180002f21  call    __scrt_is_nonwritable_in_current_image
0x180002f26  test    al, al
0x180002f28  jz      short loc_180002F3D
0x180002f2a  mov     r8, rsi
0x180002f2d  mov     edx, 2
0x180002f32  mov     rcx, r14
0x180002f35  mov     rax, [rbx]
0x180002f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3d  inc     cs:dword_180129BD0
0x180002f43  mov     eax, 1
0x180002f48  jmp     short loc_180002F4C
0x180002f4a  xor     eax, eax
0x180002f4c  add     rsp, 28h
0x180002f50  pop     r14
0x180002f52  pop     rdi
0x180002f53  pop     rsi
0x180002f54  pop     rbx
0x180002f55  retn
0x180002f56  mov     ecx, 7
0x180002f5b  call    __scrt_fastfail
0x1800bf3e0  push    rbp
0x1800bf3e2  sub     rsp, 20h
0x1800bf3e6  mov     rbp, rdx
0x1800bf3e9  mov     cl, [rbp+60h]
0x1800bf3ec  add     rsp, 20h
0x1800bf3f0  pop     rbp
0x1800bf3f1  jmp     __scrt_release_startup_lock
```
