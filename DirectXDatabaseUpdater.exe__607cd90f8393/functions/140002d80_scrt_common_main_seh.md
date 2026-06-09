# __scrt_common_main_seh

- ea: `0x140002d80`
- end: `0x140002efb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002f10`

## callees

- `0x140002d80`
- `0x140002fa8`
- `0x140002fe8`
- `0x1400030bc`
- `0x14000315c`
- `0x140003188`
- `0x1400036b8`
- `0x1400036c8`
- `0x1400036d8`
- `0x1400036f0`
- `0x1400038f6`
- `0x140003902`
- `0x14000390e`
- `0x14000391a`
- `0x14000393e`
- `0x14000394a`
- `0x14000399e`
- `0x1400039ce`
- `0x1400039da`
- `0x140003a28`
- `0x140003a58`
- `0x14000f2a4`
- `0x14001a010`

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
  wchar_t **v11; // rbx
  int *v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx

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
  v11 = *_p___wargv();
  v12 = _p___argc();
  v13 = wmain(*v12, (__int64)v11);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
    o_exit_0(v13);
  if ( !v1 )
    o__cexit_0(v15);
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v13;
}

```

## disassembly

```asm
0x140002d80  mov     [rsp+arg_0], rbx
0x140002d85  mov     [rsp+arg_8], rsi
0x140002d8a  push    rdi
0x140002d8b  sub     rsp, 30h
0x140002d8f  mov     ecx, 1
0x140002d94  call    __scrt_initialize_crt
0x140002d99  test    al, al
0x140002d9b  jz      loc_140002ED6
0x140002da1  xor     sil, sil
0x140002da4  mov     [rsp+38h+var_18], sil
0x140002da9  call    __scrt_acquire_startup_lock
0x140002dae  mov     bl, al
0x140002db0  mov     ecx, cs:__scrt_current_native_startup_state
0x140002db6  cmp     ecx, 1
0x140002db9  jz      loc_140002EE1
0x140002dbf  test    ecx, ecx
0x140002dc1  jnz     short loc_140002E0D
0x140002dc3  mov     cs:__scrt_current_native_startup_state, 1
0x140002dcd  lea     rdx, __xi_z; Last
0x140002dd4  lea     rcx, __xi_a; First
0x140002ddb  call    _initterm_e_0
0x140002de0  test    eax, eax
0x140002de2  jz      short loc_140002DEE
0x140002de4  mov     eax, 0FFh
0x140002de9  jmp     loc_140002EC6
0x140002dee  lea     rdx, __xc_z; Last
0x140002df5  lea     rcx, __xc_a; First
0x140002dfc  call    _initterm_0
0x140002e01  mov     cs:__scrt_current_native_startup_state, 2
0x140002e0b  jmp     short loc_140002E15
0x140002e0d  mov     sil, 1
0x140002e10  mov     [rsp+38h+var_18], sil
0x140002e15  mov     cl, bl
0x140002e17  call    __scrt_release_startup_lock
0x140002e1c  call    __scrt_get_dyn_tls_init_callback
0x140002e21  mov     rbx, rax
0x140002e24  cmp     qword ptr [rax], 0
0x140002e28  jz      short loc_140002E47
0x140002e2a  mov     rcx, rax
0x140002e2d  call    __scrt_is_nonwritable_in_current_image
0x140002e32  test    al, al
0x140002e34  jz      short loc_140002E47
0x140002e36  xor     r8d, r8d
0x140002e39  lea     edx, [r8+2]
0x140002e3d  xor     ecx, ecx
0x140002e3f  mov     rax, [rbx]
0x140002e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e47  call    __scrt_get_dyn_tls_dtor_callback
0x140002e4c  mov     rbx, rax
0x140002e4f  cmp     qword ptr [rax], 0
0x140002e53  jz      short loc_140002E69
0x140002e55  mov     rcx, rax
0x140002e58  call    __scrt_is_nonwritable_in_current_image
0x140002e5d  test    al, al
0x140002e5f  jz      short loc_140002E69
0x140002e61  mov     rcx, [rbx]; Callback
0x140002e64  call    _register_thread_local_exe_atexit_callback_0
0x140002e69  call    _get_initial_wide_environment
0x140002e6e  mov     rdi, rax
0x140002e71  call    __p___wargv
0x140002e76  mov     rbx, [rax]
0x140002e79  call    __p___argc
0x140002e7e  mov     r8, rdi
0x140002e81  mov     rdx, rbx
0x140002e84  mov     ecx, [rax]
0x140002e86  call    wmain
0x140002e8b  mov     ebx, eax
0x140002e8d  call    __scrt_is_managed_app
0x140002e92  test    al, al
0x140002e94  jz      short loc_140002EEB
0x140002e96  test    sil, sil
0x140002e99  jnz     short loc_140002EA0
0x140002e9b  call    _o__cexit_0
0x140002ea0  xor     edx, edx
0x140002ea2  mov     cl, 1
0x140002ea4  call    __scrt_uninitialize_crt
0x140002ea9  mov     eax, ebx
0x140002eab  jmp     short loc_140002EC6
0x140002ead  mov     ebx, eax
0x140002eaf  call    __scrt_is_managed_app
0x140002eb4  test    al, al
0x140002eb6  jz      short loc_140002EF3
0x140002eb8  cmp     [rsp+38h+var_18], 0
0x140002ebd  jnz     short loc_140002EC4
0x140002ebf  call    _c_exit_0
0x140002ec4  mov     eax, ebx
0x140002ec6  mov     rbx, [rsp+38h+arg_0]
0x140002ecb  mov     rsi, [rsp+38h+arg_8]
0x140002ed0  add     rsp, 30h
0x140002ed4  pop     rdi
0x140002ed5  retn
0x140002ed6  mov     ecx, 7
0x140002edb  call    __scrt_fastfail
0x140002ee1  mov     ecx, 7
0x140002ee6  call    __scrt_fastfail
0x140002eeb  mov     ecx, ebx; Code
0x140002eed  call    _o_exit_0
0x140002ef3  mov     ecx, ebx
0x140002ef5  call    _o__exit_0
0x140002efa  nop
0x14001852c  push    rbp
0x14001852e  sub     rsp, 20h
0x140018532  mov     rbp, rdx
0x140018535  mov     rdx, rcx; ExceptionPtr
0x140018538  mov     rcx, [rcx]
0x14001853b  mov     ecx, [rcx]; ExceptionNum
0x14001853d  call    _seh_filter_exe
0x140018542  nop
0x140018543  add     rsp, 20h
0x140018547  pop     rbp
0x140018548  retn
```
