# __scrt_common_main_seh

- ea: `0x1400058fc`
- end: `0x140005a78`
- name: `__scrt_common_main_seh`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140005a80`

## callees

- `0x140002a78`
- `0x1400058fc`
- `0x140005b40`
- `0x140005b7c`
- `0x140005c54`
- `0x140005cec`
- `0x140005d10`
- `0x140005e98`
- `0x140005ea0`
- `0x140005eb0`
- `0x140006004`
- `0x1400064c2`
- `0x1400064e0`
- `0x1400064e6`
- `0x1400064ec`
- `0x1400064f2`
- `0x1400064f8`
- `0x140006504`
- `0x14000650a`
- `0x140006510`
- `0x140006516`
- `0x14000651c`
- `0x140006590`

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
0x1400058fc  mov     [rsp+arg_0], rbx
0x140005901  mov     [rsp+arg_8], rsi
0x140005906  push    rdi
0x140005907  sub     rsp, 30h
0x14000590b  mov     ecx, 1
0x140005910  call    __scrt_initialize_crt
0x140005915  test    al, al
0x140005917  jz      loc_140005A53
0x14000591d  xor     sil, sil
0x140005920  mov     [rsp+38h+var_18], sil
0x140005925  call    __scrt_acquire_startup_lock
0x14000592a  mov     bl, al
0x14000592c  mov     ecx, cs:__scrt_current_native_startup_state
0x140005932  cmp     ecx, 1
0x140005935  jz      loc_140005A5E
0x14000593b  test    ecx, ecx
0x14000593d  jnz     short loc_140005989
0x14000593f  mov     cs:__scrt_current_native_startup_state, 1
0x140005949  lea     rdx, __xi_z; Last
0x140005950  lea     rcx, __xi_a; First
0x140005957  call    _initterm_e_0
0x14000595c  test    eax, eax
0x14000595e  jz      short loc_14000596A
0x140005960  mov     eax, 0FFh
0x140005965  jmp     loc_140005A43
0x14000596a  lea     rdx, __xc_z; Last
0x140005971  lea     rcx, __xc_a; First
0x140005978  call    _initterm_0
0x14000597d  mov     cs:__scrt_current_native_startup_state, 2
0x140005987  jmp     short loc_140005991
0x140005989  mov     sil, 1
0x14000598c  mov     [rsp+38h+var_18], sil
0x140005991  mov     cl, bl
0x140005993  call    __scrt_release_startup_lock
0x140005998  call    __scrt_get_dyn_tls_init_callback
0x14000599d  mov     rbx, rax
0x1400059a0  cmp     qword ptr [rax], 0
0x1400059a4  jz      short loc_1400059C4
0x1400059a6  mov     rcx, rax
0x1400059a9  call    __scrt_is_nonwritable_in_current_image
0x1400059ae  test    al, al
0x1400059b0  jz      short loc_1400059C4
0x1400059b2  xor     r8d, r8d
0x1400059b5  lea     edx, [r8+2]
0x1400059b9  xor     ecx, ecx
0x1400059bb  mov     rax, [rbx]
0x1400059be  call    cs:__guard_dispatch_icall_fptr
0x1400059c4  call    __scrt_get_dyn_tls_dtor_callback
0x1400059c9  mov     rbx, rax
0x1400059cc  cmp     qword ptr [rax], 0
0x1400059d0  jz      short loc_1400059E6
0x1400059d2  mov     rcx, rax
0x1400059d5  call    __scrt_is_nonwritable_in_current_image
0x1400059da  test    al, al
0x1400059dc  jz      short loc_1400059E6
0x1400059de  mov     rcx, [rbx]; Callback
0x1400059e1  call    _register_thread_local_exe_atexit_callback_0
0x1400059e6  call    _get_initial_wide_environment_0
0x1400059eb  mov     rdi, rax
0x1400059ee  call    __p___wargv_0
0x1400059f3  mov     rbx, [rax]
0x1400059f6  call    __p___argc_0
0x1400059fb  mov     r8, rdi; envp
0x1400059fe  mov     rdx, rbx; argv
0x140005a01  mov     ecx, [rax]; argc
0x140005a03  call    main
0x140005a08  mov     ebx, eax
0x140005a0a  call    __scrt_is_managed_app
0x140005a0f  test    al, al
0x140005a11  jz      short loc_140005A68
0x140005a13  test    sil, sil
0x140005a16  jnz     short loc_140005A1D
0x140005a18  call    _cexit_0
0x140005a1d  xor     edx, edx
0x140005a1f  mov     cl, 1
0x140005a21  call    __scrt_uninitialize_crt
0x140005a26  mov     eax, ebx
0x140005a28  jmp     short loc_140005A43
0x140005a2a  mov     ebx, eax
0x140005a2c  call    __scrt_is_managed_app
0x140005a31  test    al, al
0x140005a33  jz      short loc_140005A70
0x140005a35  cmp     [rsp+38h+var_18], 0
0x140005a3a  jnz     short loc_140005A41
0x140005a3c  call    _c_exit_0
0x140005a41  mov     eax, ebx
0x140005a43  mov     rbx, [rsp+38h+arg_0]
0x140005a48  mov     rsi, [rsp+38h+arg_8]
0x140005a4d  add     rsp, 30h
0x140005a51  pop     rdi
0x140005a52  retn
0x140005a53  mov     ecx, 7
0x140005a58  call    __scrt_fastfail
0x140005a5d  nop
0x140005a5e  mov     ecx, 7
0x140005a63  call    __scrt_fastfail
0x140005a68  mov     ecx, ebx; Code
0x140005a6a  call    exit_0
0x140005a70  mov     ecx, ebx; Code
0x140005a72  call    _exit_0
0x140006644  push    rbp
0x140006646  sub     rsp, 20h
0x14000664a  mov     rbp, rdx
0x14000664d  mov     rax, [rcx]
0x140006650  mov     rdx, rcx; ExceptionPtr
0x140006653  mov     ecx, [rax]; ExceptionNum
0x140006655  call    _seh_filter_exe_0
0x14000665a  nop
0x14000665b  add     rsp, 20h
0x14000665f  pop     rbp
0x140006660  retn
```
