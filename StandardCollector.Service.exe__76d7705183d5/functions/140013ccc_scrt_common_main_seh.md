# __scrt_common_main_seh

- ea: `0x140013ccc`
- end: `0x140013e48`
- name: `__scrt_common_main_seh`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140013e50`

## callees

- `0x140001388`
- `0x140013994`
- `0x1400139d0`
- `0x140013a98`
- `0x140013b30`
- `0x140013b54`
- `0x140013ccc`
- `0x140014364`
- `0x1400144b8`
- `0x140014680`
- `0x140014688`
- `0x140014b3e`
- `0x140014b44`
- `0x140014b62`
- `0x140014b68`
- `0x140014b6e`
- `0x140014b74`
- `0x140014b7a`
- `0x140014b86`
- `0x140014b8c`
- `0x140014b92`
- `0x140014b98`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall _scrt_common_main_seh()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  char v2; // si
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
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    _scrt_fastfail(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
  {
LABEL_19:
    _scrt_fastfail(7);
    goto LABEL_20;
  }
  if ( _scrt_current_native_startup_state )
  {
    v2 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v0;
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
  v0 = main(*v13, (const char **)v12, (const char **)initial_wide_environment_0);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    exit_0(v0);
  if ( !v2 )
    cexit_0();
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x140013ccc  mov     [rsp+arg_0], rbx
0x140013cd1  mov     [rsp+arg_8], rsi
0x140013cd6  push    rdi
0x140013cd7  sub     rsp, 30h
0x140013cdb  mov     ecx, 1
0x140013ce0  call    __scrt_initialize_crt
0x140013ce5  test    al, al
0x140013ce7  jz      loc_140013E23
0x140013ced  xor     sil, sil
0x140013cf0  mov     [rsp+38h+var_18], sil
0x140013cf5  call    __scrt_acquire_startup_lock
0x140013cfa  mov     bl, al
0x140013cfc  mov     ecx, cs:__scrt_current_native_startup_state
0x140013d02  cmp     ecx, 1
0x140013d05  jz      loc_140013E2E
0x140013d0b  test    ecx, ecx
0x140013d0d  jnz     short loc_140013D59
0x140013d0f  mov     cs:__scrt_current_native_startup_state, 1
0x140013d19  lea     rdx, __xi_z; Last
0x140013d20  lea     rcx, __xi_a; First
0x140013d27  call    _initterm_e_0
0x140013d2c  test    eax, eax
0x140013d2e  jz      short loc_140013D3A
0x140013d30  mov     eax, 0FFh
0x140013d35  jmp     loc_140013E13
0x140013d3a  lea     rdx, __xc_z; Last
0x140013d41  lea     rcx, __xc_a; First
0x140013d48  call    _initterm_0
0x140013d4d  mov     cs:__scrt_current_native_startup_state, 2
0x140013d57  jmp     short loc_140013D61
0x140013d59  mov     sil, 1
0x140013d5c  mov     [rsp+38h+var_18], sil
0x140013d61  mov     cl, bl
0x140013d63  call    __scrt_release_startup_lock
0x140013d68  call    __scrt_get_dyn_tls_init_callback
0x140013d6d  mov     rbx, rax
0x140013d70  cmp     qword ptr [rax], 0
0x140013d74  jz      short loc_140013D94
0x140013d76  mov     rcx, rax
0x140013d79  call    __scrt_is_nonwritable_in_current_image
0x140013d7e  test    al, al
0x140013d80  jz      short loc_140013D94
0x140013d82  xor     r8d, r8d
0x140013d85  lea     edx, [r8+2]
0x140013d89  xor     ecx, ecx
0x140013d8b  mov     rax, [rbx]
0x140013d8e  call    cs:__guard_dispatch_icall_fptr
0x140013d94  call    __scrt_get_dyn_tls_dtor_callback
0x140013d99  mov     rbx, rax
0x140013d9c  cmp     qword ptr [rax], 0
0x140013da0  jz      short loc_140013DB6
0x140013da2  mov     rcx, rax
0x140013da5  call    __scrt_is_nonwritable_in_current_image
0x140013daa  test    al, al
0x140013dac  jz      short loc_140013DB6
0x140013dae  mov     rcx, [rbx]; Callback
0x140013db1  call    _register_thread_local_exe_atexit_callback_0
0x140013db6  call    _get_initial_wide_environment_0
0x140013dbb  mov     rdi, rax
0x140013dbe  call    __p___wargv_0
0x140013dc3  mov     rbx, [rax]
0x140013dc6  call    __p___argc_0
0x140013dcb  mov     r8, rdi; envp
0x140013dce  mov     rdx, rbx; argv
0x140013dd1  mov     ecx, [rax]; argc
0x140013dd3  call    main
0x140013dd8  mov     ebx, eax
0x140013dda  call    __scrt_is_managed_app
0x140013ddf  test    al, al
0x140013de1  jz      short loc_140013E38
0x140013de3  test    sil, sil
0x140013de6  jnz     short loc_140013DED
0x140013de8  call    _cexit_0
0x140013ded  xor     edx, edx
0x140013def  mov     cl, 1
0x140013df1  call    __scrt_uninitialize_crt
0x140013df6  mov     eax, ebx
0x140013df8  jmp     short loc_140013E13
0x140013dfa  mov     ebx, eax
0x140013dfc  call    __scrt_is_managed_app
0x140013e01  test    al, al
0x140013e03  jz      short loc_140013E40
0x140013e05  cmp     [rsp+38h+var_18], 0
0x140013e0a  jnz     short loc_140013E11
0x140013e0c  call    _c_exit_0
0x140013e11  mov     eax, ebx
0x140013e13  mov     rbx, [rsp+38h+arg_0]
0x140013e18  mov     rsi, [rsp+38h+arg_8]
0x140013e1d  add     rsp, 30h
0x140013e21  pop     rdi
0x140013e22  retn
0x140013e23  mov     ecx, 7
0x140013e28  call    __scrt_fastfail
0x140013e2d  nop
0x140013e2e  mov     ecx, 7
0x140013e33  call    __scrt_fastfail
0x140013e38  mov     ecx, ebx; Code
0x140013e3a  call    exit_0
0x140013e40  mov     ecx, ebx; Code
0x140013e42  call    _exit_0
0x140015b59  push    rbp
0x140015b5b  sub     rsp, 20h
0x140015b5f  mov     rbp, rdx
0x140015b62  mov     rdx, rcx; ExceptionPtr
0x140015b65  mov     rcx, [rcx]
0x140015b68  mov     ecx, [rcx]; ExceptionNum
0x140015b6a  call    _seh_filter_exe_0
0x140015b6f  nop
0x140015b70  add     rsp, 20h
0x140015b74  pop     rbp
0x140015b75  retn
```
