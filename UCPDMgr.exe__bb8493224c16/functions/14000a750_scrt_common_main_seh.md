# __scrt_common_main_seh

- ea: `0x14000a750`
- end: `0x14000a8cb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x14000a8e0`

## callees

- `0x14000a263`
- `0x14000a26f`
- `0x14000a2ab`
- `0x14000a2db`
- `0x14000a2f3`
- `0x14000a323`
- `0x14000a35f`
- `0x14000a3b4`
- `0x14000a3f4`
- `0x14000a4c8`
- `0x14000a568`
- `0x14000a594`
- `0x14000a750`
- `0x14000ad84`
- `0x14000af10`
- `0x14000b124`
- `0x14000b134`
- `0x14000e346`
- `0x14000e352`
- `0x14000e35e`
- `0x14000e36a`
- `0x14000e570`
- `0x14000f4d0`

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
  char **initial_narrow_environment; // rdi
  char **v12; // rbx
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
  initial_narrow_environment = get_initial_narrow_environment();
  v12 = *_p___argv();
  v13 = _p___argc();
  v0 = main(*v13, (const char **)v12, (const char **)initial_narrow_environment);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    o_exit_0(v0);
  if ( !v2 )
    o__cexit_0(v15);
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x14000a750  mov     [rsp+arg_0], rbx
0x14000a755  mov     [rsp+arg_8], rsi
0x14000a75a  push    rdi
0x14000a75b  sub     rsp, 30h
0x14000a75f  mov     ecx, 1
0x14000a764  call    __scrt_initialize_crt
0x14000a769  test    al, al
0x14000a76b  jz      loc_14000A8A6
0x14000a771  xor     sil, sil
0x14000a774  mov     [rsp+38h+var_18], sil
0x14000a779  call    __scrt_acquire_startup_lock
0x14000a77e  mov     bl, al
0x14000a780  mov     ecx, cs:__scrt_current_native_startup_state
0x14000a786  cmp     ecx, 1
0x14000a789  jz      loc_14000A8B1
0x14000a78f  test    ecx, ecx
0x14000a791  jnz     short loc_14000A7DD
0x14000a793  mov     cs:__scrt_current_native_startup_state, 1
0x14000a79d  lea     rdx, __xi_z; Last
0x14000a7a4  lea     rcx, __xi_a; First
0x14000a7ab  call    _initterm_e_0
0x14000a7b0  test    eax, eax
0x14000a7b2  jz      short loc_14000A7BE
0x14000a7b4  mov     eax, 0FFh
0x14000a7b9  jmp     loc_14000A896
0x14000a7be  lea     rdx, __xc_z; Last
0x14000a7c5  lea     rcx, __xc_a; First
0x14000a7cc  call    _initterm_0
0x14000a7d1  mov     cs:__scrt_current_native_startup_state, 2
0x14000a7db  jmp     short loc_14000A7E5
0x14000a7dd  mov     sil, 1
0x14000a7e0  mov     [rsp+38h+var_18], sil
0x14000a7e5  mov     cl, bl
0x14000a7e7  call    __scrt_release_startup_lock
0x14000a7ec  call    __scrt_get_dyn_tls_init_callback
0x14000a7f1  mov     rbx, rax
0x14000a7f4  cmp     qword ptr [rax], 0
0x14000a7f8  jz      short loc_14000A817
0x14000a7fa  mov     rcx, rax
0x14000a7fd  call    __scrt_is_nonwritable_in_current_image
0x14000a802  test    al, al
0x14000a804  jz      short loc_14000A817
0x14000a806  xor     r8d, r8d
0x14000a809  lea     edx, [r8+2]
0x14000a80d  xor     ecx, ecx
0x14000a80f  mov     rax, [rbx]
0x14000a812  call    _guard_dispatch_icall
0x14000a817  call    __scrt_get_dyn_tls_dtor_callback
0x14000a81c  mov     rbx, rax
0x14000a81f  cmp     qword ptr [rax], 0
0x14000a823  jz      short loc_14000A839
0x14000a825  mov     rcx, rax
0x14000a828  call    __scrt_is_nonwritable_in_current_image
0x14000a82d  test    al, al
0x14000a82f  jz      short loc_14000A839
0x14000a831  mov     rcx, [rbx]; Callback
0x14000a834  call    _register_thread_local_exe_atexit_callback_0
0x14000a839  call    _get_initial_narrow_environment
0x14000a83e  mov     rdi, rax
0x14000a841  call    __p___argv
0x14000a846  mov     rbx, [rax]
0x14000a849  call    __p___argc
0x14000a84e  mov     r8, rdi; envp
0x14000a851  mov     rdx, rbx; argv
0x14000a854  mov     ecx, [rax]; argc
0x14000a856  call    main
0x14000a85b  mov     ebx, eax
0x14000a85d  call    __scrt_is_managed_app
0x14000a862  test    al, al
0x14000a864  jz      short loc_14000A8BB
0x14000a866  test    sil, sil
0x14000a869  jnz     short loc_14000A870
0x14000a86b  call    _o__cexit_0
0x14000a870  xor     edx, edx
0x14000a872  mov     cl, 1
0x14000a874  call    __scrt_uninitialize_crt
0x14000a879  mov     eax, ebx
0x14000a87b  jmp     short loc_14000A896
0x14000a87d  mov     ebx, eax
0x14000a87f  call    __scrt_is_managed_app
0x14000a884  test    al, al
0x14000a886  jz      short loc_14000A8C3
0x14000a888  cmp     [rsp+38h+var_18], 0
0x14000a88d  jnz     short loc_14000A894
0x14000a88f  call    _c_exit_0
0x14000a894  mov     eax, ebx
0x14000a896  mov     rbx, [rsp+38h+arg_0]
0x14000a89b  mov     rsi, [rsp+38h+arg_8]
0x14000a8a0  add     rsp, 30h
0x14000a8a4  pop     rdi
0x14000a8a5  retn
0x14000a8a6  mov     ecx, 7
0x14000a8ab  call    __scrt_fastfail
0x14000a8b0  nop
0x14000a8b1  mov     ecx, 7
0x14000a8b6  call    __scrt_fastfail
0x14000a8bb  mov     ecx, ebx; Code
0x14000a8bd  call    _o_exit_0
0x14000a8c3  mov     ecx, ebx
0x14000a8c5  call    _o__exit_0
0x14000a8ca  nop
0x14000ffa1  push    rbp
0x14000ffa3  sub     rsp, 20h
0x14000ffa7  mov     rbp, rdx
0x14000ffaa  mov     rdx, rcx; ExceptionPtr
0x14000ffad  mov     rcx, [rcx]
0x14000ffb0  mov     ecx, [rcx]; ExceptionNum
0x14000ffb2  call    _seh_filter_exe
0x14000ffb7  nop
0x14000ffb8  add     rsp, 20h
0x14000ffbc  pop     rbp
0x14000ffbd  retn
```
