# __scrt_common_main_seh

- ea: `0x140001300`
- end: `0x14000147b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001490`

## callees

- `0x140001300`
- `0x1400014e4`
- `0x140001524`
- `0x1400015f8`
- `0x140001698`
- `0x1400016c4`
- `0x1400018bc`
- `0x1400018cc`
- `0x1400018dc`
- `0x1400018f4`
- `0x140001ef6`
- `0x140001f02`
- `0x140001f0e`
- `0x140001f1a`
- `0x140001f3e`
- `0x140001f4a`
- `0x140001f92`
- `0x140001fc2`
- `0x140001fce`
- `0x140002018`
- `0x140002048`
- `0x140007c60`
- `0x140009010`

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
0x140001300  mov     [rsp+arg_0], rbx
0x140001305  mov     [rsp+arg_8], rsi
0x14000130a  push    rdi
0x14000130b  sub     rsp, 30h
0x14000130f  mov     ecx, 1
0x140001314  call    __scrt_initialize_crt
0x140001319  test    al, al
0x14000131b  jz      loc_140001456
0x140001321  xor     sil, sil
0x140001324  mov     [rsp+38h+var_18], sil
0x140001329  call    __scrt_acquire_startup_lock
0x14000132e  mov     bl, al
0x140001330  mov     ecx, cs:__scrt_current_native_startup_state
0x140001336  cmp     ecx, 1
0x140001339  jz      loc_140001461
0x14000133f  test    ecx, ecx
0x140001341  jnz     short loc_14000138D
0x140001343  mov     cs:__scrt_current_native_startup_state, 1
0x14000134d  lea     rdx, __xi_z; Last
0x140001354  lea     rcx, __xi_a; First
0x14000135b  call    _initterm_e_0
0x140001360  test    eax, eax
0x140001362  jz      short loc_14000136E
0x140001364  mov     eax, 0FFh
0x140001369  jmp     loc_140001446
0x14000136e  lea     rdx, __xc_z; Last
0x140001375  lea     rcx, __xc_a; First
0x14000137c  call    _initterm_0
0x140001381  mov     cs:__scrt_current_native_startup_state, 2
0x14000138b  jmp     short loc_140001395
0x14000138d  mov     sil, 1
0x140001390  mov     [rsp+38h+var_18], sil
0x140001395  mov     cl, bl
0x140001397  call    __scrt_release_startup_lock
0x14000139c  call    __scrt_get_dyn_tls_init_callback
0x1400013a1  mov     rbx, rax
0x1400013a4  cmp     qword ptr [rax], 0
0x1400013a8  jz      short loc_1400013C7
0x1400013aa  mov     rcx, rax
0x1400013ad  call    __scrt_is_nonwritable_in_current_image
0x1400013b2  test    al, al
0x1400013b4  jz      short loc_1400013C7
0x1400013b6  xor     r8d, r8d
0x1400013b9  lea     edx, [r8+2]
0x1400013bd  xor     ecx, ecx
0x1400013bf  mov     rax, [rbx]
0x1400013c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400013c7  call    __scrt_get_dyn_tls_dtor_callback
0x1400013cc  mov     rbx, rax
0x1400013cf  cmp     qword ptr [rax], 0
0x1400013d3  jz      short loc_1400013E9
0x1400013d5  mov     rcx, rax
0x1400013d8  call    __scrt_is_nonwritable_in_current_image
0x1400013dd  test    al, al
0x1400013df  jz      short loc_1400013E9
0x1400013e1  mov     rcx, [rbx]; Callback
0x1400013e4  call    _register_thread_local_exe_atexit_callback_0
0x1400013e9  call    _get_initial_wide_environment
0x1400013ee  mov     rdi, rax
0x1400013f1  call    __p___wargv
0x1400013f6  mov     rbx, [rax]
0x1400013f9  call    __p___argc
0x1400013fe  mov     r8, rdi
0x140001401  mov     rdx, rbx
0x140001404  mov     ecx, [rax]
0x140001406  call    wmain
0x14000140b  mov     ebx, eax
0x14000140d  call    __scrt_is_managed_app
0x140001412  test    al, al
0x140001414  jz      short loc_14000146B
0x140001416  test    sil, sil
0x140001419  jnz     short loc_140001420
0x14000141b  call    _o__cexit_0
0x140001420  xor     edx, edx
0x140001422  mov     cl, 1
0x140001424  call    __scrt_uninitialize_crt
0x140001429  mov     eax, ebx
0x14000142b  jmp     short loc_140001446
0x14000142d  mov     ebx, eax
0x14000142f  call    __scrt_is_managed_app
0x140001434  test    al, al
0x140001436  jz      short loc_140001473
0x140001438  cmp     [rsp+38h+var_18], 0
0x14000143d  jnz     short loc_140001444
0x14000143f  call    _c_exit_0
0x140001444  mov     eax, ebx
0x140001446  mov     rbx, [rsp+38h+arg_0]
0x14000144b  mov     rsi, [rsp+38h+arg_8]
0x140001450  add     rsp, 30h
0x140001454  pop     rdi
0x140001455  retn
0x140001456  mov     ecx, 7
0x14000145b  call    __scrt_fastfail
0x140001461  mov     ecx, 7
0x140001466  call    __scrt_fastfail
0x14000146b  mov     ecx, ebx; Code
0x14000146d  call    _o_exit_0
0x140001473  mov     ecx, ebx
0x140001475  call    _o__exit_0
0x14000147a  nop
0x14000883c  push    rbp
0x14000883e  sub     rsp, 20h
0x140008842  mov     rbp, rdx
0x140008845  mov     rdx, rcx; ExceptionPtr
0x140008848  mov     rcx, [rcx]
0x14000884b  mov     ecx, [rcx]; ExceptionNum
0x14000884d  call    _seh_filter_exe
0x140008852  nop
0x140008853  add     rsp, 20h
0x140008857  pop     rbp
0x140008858  retn
```
