# __scrt_common_main_seh

- ea: `0x140001430`
- end: `0x1400015ab`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400015c0`

## callees

- `0x140001430`
- `0x140001690`
- `0x1400016d0`
- `0x1400017a4`
- `0x140001844`
- `0x140001870`
- `0x140001f64`
- `0x140001f74`
- `0x140001f84`
- `0x140001f9c`
- `0x140002166`
- `0x140002196`
- `0x1400021a2`
- `0x1400021ae`
- `0x1400021ba`
- `0x1400021c6`
- `0x1400021de`
- `0x1400021ea`
- `0x1400021f6`
- `0x140002202`
- `0x14000220e`
- `0x140003188`
- `0x140011010`

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
  wchar_t **initial_wide_environment_0; // rdi
  wchar_t **v12; // rbx
  int *v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx

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
  initial_wide_environment_0 = get_initial_wide_environment_0();
  v12 = *_p___wargv_0();
  v13 = _p___argc_0();
  v14 = wmain((unsigned int)*v13, v12, initial_wide_environment_0);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    exit_0(v14);
  if ( !v1 )
    cexit_0();
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x140001430  mov     [rsp+arg_0], rbx
0x140001435  mov     [rsp+arg_8], rsi
0x14000143a  push    rdi
0x14000143b  sub     rsp, 30h
0x14000143f  mov     ecx, 1
0x140001444  call    __scrt_initialize_crt
0x140001449  test    al, al
0x14000144b  jz      loc_140001586
0x140001451  xor     sil, sil
0x140001454  mov     [rsp+38h+var_18], sil
0x140001459  call    __scrt_acquire_startup_lock
0x14000145e  mov     bl, al
0x140001460  mov     ecx, cs:__scrt_current_native_startup_state
0x140001466  cmp     ecx, 1
0x140001469  jz      loc_140001591
0x14000146f  test    ecx, ecx
0x140001471  jnz     short loc_1400014BD
0x140001473  mov     cs:__scrt_current_native_startup_state, 1
0x14000147d  lea     rdx, __xi_z; Last
0x140001484  lea     rcx, __xi_a; First
0x14000148b  call    _initterm_e_0
0x140001490  test    eax, eax
0x140001492  jz      short loc_14000149E
0x140001494  mov     eax, 0FFh
0x140001499  jmp     loc_140001576
0x14000149e  lea     rdx, __xc_z; Last
0x1400014a5  lea     rcx, __xc_a; First
0x1400014ac  call    _initterm_0
0x1400014b1  mov     cs:__scrt_current_native_startup_state, 2
0x1400014bb  jmp     short loc_1400014C5
0x1400014bd  mov     sil, 1
0x1400014c0  mov     [rsp+38h+var_18], sil
0x1400014c5  mov     cl, bl
0x1400014c7  call    __scrt_release_startup_lock
0x1400014cc  call    __scrt_get_dyn_tls_init_callback
0x1400014d1  mov     rbx, rax
0x1400014d4  cmp     qword ptr [rax], 0
0x1400014d8  jz      short loc_1400014F7
0x1400014da  mov     rcx, rax
0x1400014dd  call    __scrt_is_nonwritable_in_current_image
0x1400014e2  test    al, al
0x1400014e4  jz      short loc_1400014F7
0x1400014e6  xor     r8d, r8d
0x1400014e9  lea     edx, [r8+2]
0x1400014ed  xor     ecx, ecx
0x1400014ef  mov     rax, [rbx]
0x1400014f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400014f7  call    __scrt_get_dyn_tls_dtor_callback
0x1400014fc  mov     rbx, rax
0x1400014ff  cmp     qword ptr [rax], 0
0x140001503  jz      short loc_140001519
0x140001505  mov     rcx, rax
0x140001508  call    __scrt_is_nonwritable_in_current_image
0x14000150d  test    al, al
0x14000150f  jz      short loc_140001519
0x140001511  mov     rcx, [rbx]; Callback
0x140001514  call    _register_thread_local_exe_atexit_callback_0
0x140001519  call    _get_initial_wide_environment_0
0x14000151e  mov     rdi, rax
0x140001521  call    __p___wargv_0
0x140001526  mov     rbx, [rax]
0x140001529  call    __p___argc_0
0x14000152e  mov     r8, rdi
0x140001531  mov     rdx, rbx
0x140001534  mov     ecx, [rax]
0x140001536  call    wmain
0x14000153b  mov     ebx, eax
0x14000153d  call    __scrt_is_managed_app
0x140001542  test    al, al
0x140001544  jz      short loc_14000159B
0x140001546  test    sil, sil
0x140001549  jnz     short loc_140001550
0x14000154b  call    _cexit_0
0x140001550  xor     edx, edx
0x140001552  mov     cl, 1
0x140001554  call    __scrt_uninitialize_crt
0x140001559  mov     eax, ebx
0x14000155b  jmp     short loc_140001576
0x14000155d  mov     ebx, eax
0x14000155f  call    __scrt_is_managed_app
0x140001564  test    al, al
0x140001566  jz      short loc_1400015A3
0x140001568  cmp     [rsp+38h+var_18], 0
0x14000156d  jnz     short loc_140001574
0x14000156f  call    _c_exit_0
0x140001574  mov     eax, ebx
0x140001576  mov     rbx, [rsp+38h+arg_0]
0x14000157b  mov     rsi, [rsp+38h+arg_8]
0x140001580  add     rsp, 30h
0x140001584  pop     rdi
0x140001585  retn
0x140001586  mov     ecx, 7
0x14000158b  call    __scrt_fastfail
0x140001591  mov     ecx, 7
0x140001596  call    __scrt_fastfail
0x14000159b  mov     ecx, ebx; Code
0x14000159d  call    exit_0
0x1400015a3  mov     ecx, ebx; Code
0x1400015a5  call    _exit_0
0x14000fb0c  push    rbp
0x14000fb0e  sub     rsp, 20h
0x14000fb12  mov     rbp, rdx
0x14000fb15  mov     rdx, rcx; ExceptionPtr
0x14000fb18  mov     rcx, [rcx]
0x14000fb1b  mov     ecx, [rcx]; ExceptionNum
0x14000fb1d  call    _seh_filter_exe_0
0x14000fb22  nop
0x14000fb23  add     rsp, 20h
0x14000fb27  pop     rbp
0x14000fb28  retn
```
