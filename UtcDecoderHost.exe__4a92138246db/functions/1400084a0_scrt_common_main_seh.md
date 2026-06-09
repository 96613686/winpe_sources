# __scrt_common_main_seh

- ea: `0x1400084a0`
- end: `0x14000861b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140008630`

## callees

- `0x1400084a0`
- `0x140008684`
- `0x1400086c4`
- `0x140008798`
- `0x140008838`
- `0x140008864`
- `0x140008a94`
- `0x140008aa4`
- `0x140008ab4`
- `0x140008acc`
- `0x140008f26`
- `0x140008f32`
- `0x140008f3e`
- `0x140008f4a`
- `0x140008f7a`
- `0x140008f86`
- `0x140008fda`
- `0x14000900a`
- `0x140009016`
- `0x140009068`
- `0x140009098`
- `0x14000d958`
- `0x140018010`

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
  wchar_t **initial_wide_environment; // rdi
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
  initial_wide_environment = get_initial_wide_environment();
  v12 = *_p___wargv();
  v13 = _p___argc();
  v14 = wmain((unsigned int)*v13, v12, initial_wide_environment);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    o_exit_0(v14);
  if ( !v1 )
    o__cexit_0(v16);
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x1400084a0  mov     [rsp+arg_0], rbx
0x1400084a5  mov     [rsp+arg_8], rsi
0x1400084aa  push    rdi
0x1400084ab  sub     rsp, 30h
0x1400084af  mov     ecx, 1
0x1400084b4  call    __scrt_initialize_crt
0x1400084b9  test    al, al
0x1400084bb  jz      loc_1400085F6
0x1400084c1  xor     sil, sil
0x1400084c4  mov     [rsp+38h+var_18], sil
0x1400084c9  call    __scrt_acquire_startup_lock
0x1400084ce  mov     bl, al
0x1400084d0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400084d6  cmp     ecx, 1
0x1400084d9  jz      loc_140008601
0x1400084df  test    ecx, ecx
0x1400084e1  jnz     short loc_14000852D
0x1400084e3  mov     cs:__scrt_current_native_startup_state, 1
0x1400084ed  lea     rdx, __xi_z; Last
0x1400084f4  lea     rcx, __xi_a; First
0x1400084fb  call    _initterm_e_0
0x140008500  test    eax, eax
0x140008502  jz      short loc_14000850E
0x140008504  mov     eax, 0FFh
0x140008509  jmp     loc_1400085E6
0x14000850e  lea     rdx, __xc_z; Last
0x140008515  lea     rcx, __xc_a; First
0x14000851c  call    _initterm_0
0x140008521  mov     cs:__scrt_current_native_startup_state, 2
0x14000852b  jmp     short loc_140008535
0x14000852d  mov     sil, 1
0x140008530  mov     [rsp+38h+var_18], sil
0x140008535  mov     cl, bl
0x140008537  call    __scrt_release_startup_lock
0x14000853c  call    __scrt_get_dyn_tls_init_callback
0x140008541  mov     rbx, rax
0x140008544  cmp     qword ptr [rax], 0
0x140008548  jz      short loc_140008567
0x14000854a  mov     rcx, rax
0x14000854d  call    __scrt_is_nonwritable_in_current_image
0x140008552  test    al, al
0x140008554  jz      short loc_140008567
0x140008556  xor     r8d, r8d
0x140008559  lea     edx, [r8+2]
0x14000855d  xor     ecx, ecx
0x14000855f  mov     rax, [rbx]
0x140008562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008567  call    __scrt_get_dyn_tls_dtor_callback
0x14000856c  mov     rbx, rax
0x14000856f  cmp     qword ptr [rax], 0
0x140008573  jz      short loc_140008589
0x140008575  mov     rcx, rax
0x140008578  call    __scrt_is_nonwritable_in_current_image
0x14000857d  test    al, al
0x14000857f  jz      short loc_140008589
0x140008581  mov     rcx, [rbx]; Callback
0x140008584  call    _register_thread_local_exe_atexit_callback_0
0x140008589  call    _get_initial_wide_environment
0x14000858e  mov     rdi, rax
0x140008591  call    __p___wargv
0x140008596  mov     rbx, [rax]
0x140008599  call    __p___argc
0x14000859e  mov     r8, rdi
0x1400085a1  mov     rdx, rbx
0x1400085a4  mov     ecx, [rax]
0x1400085a6  call    wmain
0x1400085ab  mov     ebx, eax
0x1400085ad  call    __scrt_is_managed_app
0x1400085b2  test    al, al
0x1400085b4  jz      short loc_14000860B
0x1400085b6  test    sil, sil
0x1400085b9  jnz     short loc_1400085C0
0x1400085bb  call    _o__cexit_0
0x1400085c0  xor     edx, edx
0x1400085c2  mov     cl, 1
0x1400085c4  call    __scrt_uninitialize_crt
0x1400085c9  mov     eax, ebx
0x1400085cb  jmp     short loc_1400085E6
0x1400085cd  mov     ebx, eax
0x1400085cf  call    __scrt_is_managed_app
0x1400085d4  test    al, al
0x1400085d6  jz      short loc_140008613
0x1400085d8  cmp     [rsp+38h+var_18], 0
0x1400085dd  jnz     short loc_1400085E4
0x1400085df  call    _c_exit_0
0x1400085e4  mov     eax, ebx
0x1400085e6  mov     rbx, [rsp+38h+arg_0]
0x1400085eb  mov     rsi, [rsp+38h+arg_8]
0x1400085f0  add     rsp, 30h
0x1400085f4  pop     rdi
0x1400085f5  retn
0x1400085f6  mov     ecx, 7
0x1400085fb  call    __scrt_fastfail
0x140008601  mov     ecx, 7
0x140008606  call    __scrt_fastfail
0x14000860b  mov     ecx, ebx; Code
0x14000860d  call    _o_exit_0
0x140008613  mov     ecx, ebx
0x140008615  call    _o__exit_0
0x14000861a  nop
0x14001685c  push    rbp
0x14001685e  sub     rsp, 20h
0x140016862  mov     rbp, rdx
0x140016865  mov     rdx, rcx; ExceptionPtr
0x140016868  mov     rcx, [rcx]
0x14001686b  mov     ecx, [rcx]; ExceptionNum
0x14001686d  call    _seh_filter_exe
0x140016872  nop
0x140016873  add     rsp, 20h
0x140016877  pop     rbp
0x140016878  retn
```
