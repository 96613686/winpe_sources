# __scrt_common_main_seh

- ea: `0x140002150`
- end: `0x1400022cb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400022e0`

## callees

- `0x140002150`
- `0x140002448`
- `0x140002488`
- `0x14000255c`
- `0x1400025fc`
- `0x140002628`
- `0x140002838`
- `0x140002848`
- `0x140002858`
- `0x140002870`
- `0x140002cf6`
- `0x140002d02`
- `0x140002d0e`
- `0x140002d1a`
- `0x140002d4a`
- `0x140002d56`
- `0x140002dc2`
- `0x140002df2`
- `0x140002dfe`
- `0x140002e48`
- `0x140002e78`
- `0x140014e84`
- `0x140024010`

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
0x140002150  mov     [rsp+arg_0], rbx
0x140002155  mov     [rsp+arg_8], rsi
0x14000215a  push    rdi
0x14000215b  sub     rsp, 30h
0x14000215f  mov     ecx, 1
0x140002164  call    __scrt_initialize_crt
0x140002169  test    al, al
0x14000216b  jz      loc_1400022A6
0x140002171  xor     sil, sil
0x140002174  mov     [rsp+38h+var_18], sil
0x140002179  call    __scrt_acquire_startup_lock
0x14000217e  mov     bl, al
0x140002180  mov     ecx, cs:__scrt_current_native_startup_state
0x140002186  cmp     ecx, 1
0x140002189  jz      loc_1400022B1
0x14000218f  test    ecx, ecx
0x140002191  jnz     short loc_1400021DD
0x140002193  mov     cs:__scrt_current_native_startup_state, 1
0x14000219d  lea     rdx, __xi_z; Last
0x1400021a4  lea     rcx, __xi_a; First
0x1400021ab  call    _initterm_e_0
0x1400021b0  test    eax, eax
0x1400021b2  jz      short loc_1400021BE
0x1400021b4  mov     eax, 0FFh
0x1400021b9  jmp     loc_140002296
0x1400021be  lea     rdx, __xc_z; Last
0x1400021c5  lea     rcx, __xc_a; First
0x1400021cc  call    _initterm_0
0x1400021d1  mov     cs:__scrt_current_native_startup_state, 2
0x1400021db  jmp     short loc_1400021E5
0x1400021dd  mov     sil, 1
0x1400021e0  mov     [rsp+38h+var_18], sil
0x1400021e5  mov     cl, bl
0x1400021e7  call    __scrt_release_startup_lock
0x1400021ec  call    __scrt_get_dyn_tls_init_callback
0x1400021f1  mov     rbx, rax
0x1400021f4  cmp     qword ptr [rax], 0
0x1400021f8  jz      short loc_140002217
0x1400021fa  mov     rcx, rax
0x1400021fd  call    __scrt_is_nonwritable_in_current_image
0x140002202  test    al, al
0x140002204  jz      short loc_140002217
0x140002206  xor     r8d, r8d
0x140002209  lea     edx, [r8+2]
0x14000220d  xor     ecx, ecx
0x14000220f  mov     rax, [rbx]
0x140002212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002217  call    __scrt_get_dyn_tls_dtor_callback
0x14000221c  mov     rbx, rax
0x14000221f  cmp     qword ptr [rax], 0
0x140002223  jz      short loc_140002239
0x140002225  mov     rcx, rax
0x140002228  call    __scrt_is_nonwritable_in_current_image
0x14000222d  test    al, al
0x14000222f  jz      short loc_140002239
0x140002231  mov     rcx, [rbx]; Callback
0x140002234  call    _register_thread_local_exe_atexit_callback_0
0x140002239  call    _get_initial_wide_environment
0x14000223e  mov     rdi, rax
0x140002241  call    __p___wargv
0x140002246  mov     rbx, [rax]
0x140002249  call    __p___argc
0x14000224e  mov     r8, rdi
0x140002251  mov     rdx, rbx
0x140002254  mov     ecx, [rax]
0x140002256  call    wmain
0x14000225b  mov     ebx, eax
0x14000225d  call    __scrt_is_managed_app
0x140002262  test    al, al
0x140002264  jz      short loc_1400022BB
0x140002266  test    sil, sil
0x140002269  jnz     short loc_140002270
0x14000226b  call    _o__cexit_0
0x140002270  xor     edx, edx
0x140002272  mov     cl, 1
0x140002274  call    __scrt_uninitialize_crt
0x140002279  mov     eax, ebx
0x14000227b  jmp     short loc_140002296
0x14000227d  mov     ebx, eax
0x14000227f  call    __scrt_is_managed_app
0x140002284  test    al, al
0x140002286  jz      short loc_1400022C3
0x140002288  cmp     [rsp+38h+var_18], 0
0x14000228d  jnz     short loc_140002294
0x14000228f  call    _c_exit_0
0x140002294  mov     eax, ebx
0x140002296  mov     rbx, [rsp+38h+arg_0]
0x14000229b  mov     rsi, [rsp+38h+arg_8]
0x1400022a0  add     rsp, 30h
0x1400022a4  pop     rdi
0x1400022a5  retn
0x1400022a6  mov     ecx, 7
0x1400022ab  call    __scrt_fastfail
0x1400022b1  mov     ecx, 7
0x1400022b6  call    __scrt_fastfail
0x1400022bb  mov     ecx, ebx; Code
0x1400022bd  call    _o_exit_0
0x1400022c3  mov     ecx, ebx
0x1400022c5  call    _o__exit_0
0x1400022ca  nop
0x14002204c  push    rbp
0x14002204e  sub     rsp, 20h
0x140022052  mov     rbp, rdx
0x140022055  mov     rdx, rcx; ExceptionPtr
0x140022058  mov     rcx, [rcx]
0x14002205b  mov     ecx, [rcx]; ExceptionNum
0x14002205d  call    _seh_filter_exe
0x140022062  nop
0x140022063  add     rsp, 20h
0x140022067  pop     rbp
0x140022068  retn
```
