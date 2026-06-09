# __scrt_common_main_seh

- ea: `0x140002440`
- end: `0x1400025bb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400025d0`

## callees

- `0x140002440`
- `0x140002668`
- `0x1400026a8`
- `0x14000277c`
- `0x14000281c`
- `0x140002848`
- `0x140002a40`
- `0x140002a50`
- `0x140002a60`
- `0x140002a78`
- `0x140002f06`
- `0x140002f12`
- `0x140002f1e`
- `0x140002f2a`
- `0x140002f4e`
- `0x140002f5a`
- `0x140002fc6`
- `0x140002ff6`
- `0x140003002`
- `0x140003058`
- `0x140003088`
- `0x140009698`
- `0x14001d010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // si
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v10; // rbx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = 0;
  v2 = _scrt_acquire_startup_lock(v0);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
    v1 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v2;
  _scrt_release_startup_lock(v3);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v8)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v7);
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  get_initial_wide_environment();
  _p___wargv();
  _p___argc();
  v11 = wmain();
  if ( !(unsigned __int8)_scrt_is_managed_app(v12) )
    o_exit_0(v11);
  if ( !v1 )
    o__cexit_0(v13);
  LOBYTE(v13) = 1;
  _scrt_uninitialize_crt(v13, 0);
  return v11;
}

```

## disassembly

```asm
0x140002440  mov     [rsp+arg_0], rbx
0x140002445  mov     [rsp+arg_8], rsi
0x14000244a  push    rdi
0x14000244b  sub     rsp, 30h
0x14000244f  mov     ecx, 1
0x140002454  call    __scrt_initialize_crt
0x140002459  test    al, al
0x14000245b  jz      loc_140002596
0x140002461  xor     sil, sil
0x140002464  mov     [rsp+38h+var_18], sil
0x140002469  call    __scrt_acquire_startup_lock
0x14000246e  mov     bl, al
0x140002470  mov     ecx, cs:__scrt_current_native_startup_state
0x140002476  cmp     ecx, 1
0x140002479  jz      loc_1400025A1
0x14000247f  test    ecx, ecx
0x140002481  jnz     short loc_1400024CD
0x140002483  mov     cs:__scrt_current_native_startup_state, 1
0x14000248d  lea     rdx, __xi_z; Last
0x140002494  lea     rcx, __xi_a; First
0x14000249b  call    _initterm_e_0
0x1400024a0  test    eax, eax
0x1400024a2  jz      short loc_1400024AE
0x1400024a4  mov     eax, 0FFh
0x1400024a9  jmp     loc_140002586
0x1400024ae  lea     rdx, __xc_z; Last
0x1400024b5  lea     rcx, __xc_a; First
0x1400024bc  call    _initterm_0
0x1400024c1  mov     cs:__scrt_current_native_startup_state, 2
0x1400024cb  jmp     short loc_1400024D5
0x1400024cd  mov     sil, 1
0x1400024d0  mov     [rsp+38h+var_18], sil
0x1400024d5  mov     cl, bl
0x1400024d7  call    __scrt_release_startup_lock
0x1400024dc  call    __scrt_get_dyn_tls_init_callback
0x1400024e1  mov     rbx, rax
0x1400024e4  cmp     qword ptr [rax], 0
0x1400024e8  jz      short loc_140002507
0x1400024ea  mov     rcx, rax
0x1400024ed  call    __scrt_is_nonwritable_in_current_image
0x1400024f2  test    al, al
0x1400024f4  jz      short loc_140002507
0x1400024f6  xor     r8d, r8d
0x1400024f9  lea     edx, [r8+2]
0x1400024fd  xor     ecx, ecx
0x1400024ff  mov     rax, [rbx]
0x140002502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002507  call    __scrt_get_dyn_tls_dtor_callback
0x14000250c  mov     rbx, rax
0x14000250f  cmp     qword ptr [rax], 0
0x140002513  jz      short loc_140002529
0x140002515  mov     rcx, rax
0x140002518  call    __scrt_is_nonwritable_in_current_image
0x14000251d  test    al, al
0x14000251f  jz      short loc_140002529
0x140002521  mov     rcx, [rbx]; Callback
0x140002524  call    _register_thread_local_exe_atexit_callback_0
0x140002529  call    _get_initial_wide_environment
0x14000252e  mov     rdi, rax
0x140002531  call    __p___wargv
0x140002536  mov     rbx, [rax]
0x140002539  call    __p___argc
0x14000253e  mov     r8, rdi
0x140002541  mov     rdx, rbx
0x140002544  mov     ecx, [rax]
0x140002546  call    wmain
0x14000254b  mov     ebx, eax
0x14000254d  call    __scrt_is_managed_app
0x140002552  test    al, al
0x140002554  jz      short loc_1400025AB
0x140002556  test    sil, sil
0x140002559  jnz     short loc_140002560
0x14000255b  call    _o__cexit_0
0x140002560  xor     edx, edx
0x140002562  mov     cl, 1
0x140002564  call    __scrt_uninitialize_crt
0x140002569  mov     eax, ebx
0x14000256b  jmp     short loc_140002586
0x14000256d  mov     ebx, eax
0x14000256f  call    __scrt_is_managed_app
0x140002574  test    al, al
0x140002576  jz      short loc_1400025B3
0x140002578  cmp     [rsp+38h+var_18], 0
0x14000257d  jnz     short loc_140002584
0x14000257f  call    _c_exit_0
0x140002584  mov     eax, ebx
0x140002586  mov     rbx, [rsp+38h+arg_0]
0x14000258b  mov     rsi, [rsp+38h+arg_8]
0x140002590  add     rsp, 30h
0x140002594  pop     rdi
0x140002595  retn
0x140002596  mov     ecx, 7
0x14000259b  call    __scrt_fastfail
0x1400025a1  mov     ecx, 7
0x1400025a6  call    __scrt_fastfail
0x1400025ab  mov     ecx, ebx; Code
0x1400025ad  call    _o_exit_0
0x1400025b3  mov     ecx, ebx
0x1400025b5  call    _o__exit_0
0x1400025ba  nop
0x14001bc1c  push    rbp
0x14001bc1e  sub     rsp, 20h
0x14001bc22  mov     rbp, rdx
0x14001bc25  mov     rdx, rcx; ExceptionPtr
0x14001bc28  mov     rcx, [rcx]
0x14001bc2b  mov     ecx, [rcx]; ExceptionNum
0x14001bc2d  call    _seh_filter_exe
0x14001bc32  nop
0x14001bc33  add     rsp, 20h
0x14001bc37  pop     rbp
0x14001bc38  retn
```
