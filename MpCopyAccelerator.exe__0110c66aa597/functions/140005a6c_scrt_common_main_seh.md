# __scrt_common_main_seh

- ea: `0x140005a6c`
- end: `0x140005be8`
- name: `__scrt_common_main_seh`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140005bf0`

## callees

- `0x140005a6c`
- `0x140005ddc`
- `0x140005e18`
- `0x140005ee0`
- `0x140005f78`
- `0x140005f9c`
- `0x14000632c`
- `0x140006334`
- `0x140006348`
- `0x14000649c`
- `0x140012100`
- `0x1400129cc`
- `0x140012a24`
- `0x140012a5c`
- `0x140012d10`
- `0x140012d20`
- `0x140012d30`
- `0x140012d3c`
- `0x140012d78`
- `0x140012df8`
- `0x140012e00`
- `0x14001dba4`
- `0x140024c40`

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
  wchar_t **initial_wide_environment; // rdi
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
    if ( initterm_e((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
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
    register_thread_local_exe_atexit_callback(*v10);
  initial_wide_environment = get_initial_wide_environment();
  v12 = *_p___wargv();
  v13 = _p___argc();
  v0 = main(*v13, (const char **)v12, (const char **)initial_wide_environment);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    exit(v0);
  if ( !v2 )
    cexit();
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x140005a6c  mov     [rsp+arg_0], rbx
0x140005a71  mov     [rsp+arg_8], rsi
0x140005a76  push    rdi
0x140005a77  sub     rsp, 30h
0x140005a7b  mov     ecx, 1
0x140005a80  call    __scrt_initialize_crt
0x140005a85  test    al, al
0x140005a87  jz      loc_140005BC3
0x140005a8d  xor     sil, sil
0x140005a90  mov     [rsp+38h+var_18], sil
0x140005a95  call    __scrt_acquire_startup_lock
0x140005a9a  mov     bl, al
0x140005a9c  mov     ecx, cs:__scrt_current_native_startup_state
0x140005aa2  cmp     ecx, 1
0x140005aa5  jz      loc_140005BCE
0x140005aab  test    ecx, ecx
0x140005aad  jnz     short loc_140005AF9
0x140005aaf  mov     cs:__scrt_current_native_startup_state, 1
0x140005ab9  lea     rdx, __xi_z; Last
0x140005ac0  lea     rcx, __xi_a; First
0x140005ac7  call    _initterm_e
0x140005acc  test    eax, eax
0x140005ace  jz      short loc_140005ADA
0x140005ad0  mov     eax, 0FFh
0x140005ad5  jmp     loc_140005BB3
0x140005ada  lea     rdx, __xc_z; Last
0x140005ae1  lea     rcx, __xc_a; First
0x140005ae8  call    _initterm
0x140005aed  mov     cs:__scrt_current_native_startup_state, 2
0x140005af7  jmp     short loc_140005B01
0x140005af9  mov     sil, 1
0x140005afc  mov     [rsp+38h+var_18], sil
0x140005b01  mov     cl, bl
0x140005b03  call    __scrt_release_startup_lock
0x140005b08  call    __scrt_get_dyn_tls_init_callback
0x140005b0d  mov     rbx, rax
0x140005b10  cmp     qword ptr [rax], 0
0x140005b14  jz      short loc_140005B34
0x140005b16  mov     rcx, rax
0x140005b19  call    __scrt_is_nonwritable_in_current_image
0x140005b1e  test    al, al
0x140005b20  jz      short loc_140005B34
0x140005b22  xor     r8d, r8d
0x140005b25  lea     edx, [r8+2]
0x140005b29  xor     ecx, ecx
0x140005b2b  mov     rax, [rbx]
0x140005b2e  call    cs:__guard_dispatch_icall_fptr
0x140005b34  call    __scrt_get_dyn_tls_dtor_callback
0x140005b39  mov     rbx, rax
0x140005b3c  cmp     qword ptr [rax], 0
0x140005b40  jz      short loc_140005B56
0x140005b42  mov     rcx, rax
0x140005b45  call    __scrt_is_nonwritable_in_current_image
0x140005b4a  test    al, al
0x140005b4c  jz      short loc_140005B56
0x140005b4e  mov     rcx, [rbx]; Callback
0x140005b51  call    _register_thread_local_exe_atexit_callback
0x140005b56  call    _get_initial_wide_environment
0x140005b5b  mov     rdi, rax
0x140005b5e  call    __p___wargv
0x140005b63  mov     rbx, [rax]
0x140005b66  call    __p___argc
0x140005b6b  mov     r8, rdi; envp
0x140005b6e  mov     rdx, rbx; argv
0x140005b71  mov     ecx, [rax]; argc
0x140005b73  call    main
0x140005b78  mov     ebx, eax
0x140005b7a  call    __scrt_is_managed_app
0x140005b7f  test    al, al
0x140005b81  jz      short loc_140005BD8
0x140005b83  test    sil, sil
0x140005b86  jnz     short loc_140005B8D
0x140005b88  call    _cexit
0x140005b8d  xor     edx, edx
0x140005b8f  mov     cl, 1
0x140005b91  call    __scrt_uninitialize_crt
0x140005b96  mov     eax, ebx
0x140005b98  jmp     short loc_140005BB3
0x140005b9a  mov     ebx, eax
0x140005b9c  call    __scrt_is_managed_app
0x140005ba1  test    al, al
0x140005ba3  jz      short loc_140005BE0
0x140005ba5  cmp     [rsp+38h+var_18], 0
0x140005baa  jnz     short loc_140005BB1
0x140005bac  call    _c_exit
0x140005bb1  mov     eax, ebx
0x140005bb3  mov     rbx, [rsp+38h+arg_0]
0x140005bb8  mov     rsi, [rsp+38h+arg_8]
0x140005bbd  add     rsp, 30h
0x140005bc1  pop     rdi
0x140005bc2  retn
0x140005bc3  mov     ecx, 7
0x140005bc8  call    __scrt_fastfail
0x140005bcd  nop
0x140005bce  mov     ecx, 7
0x140005bd3  call    __scrt_fastfail
0x140005bd8  mov     ecx, ebx; Code
0x140005bda  call    exit
0x140005be0  mov     ecx, ebx; Code
0x140005be2  call    _exit
0x140025a5b  push    rbp
0x140025a5d  sub     rsp, 20h
0x140025a61  mov     rbp, rdx
0x140025a64  mov     rdx, rcx; ExceptionPtr
0x140025a67  mov     rcx, [rcx]
0x140025a6a  mov     ecx, [rcx]; ExceptionNum
0x140025a6c  call    _seh_filter_exe
0x140025a71  nop
0x140025a72  add     rsp, 20h
0x140025a76  pop     rbp
0x140025a77  retn
```
