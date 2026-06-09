# __scrt_common_main_seh

- ea: `0x140002050`
- end: `0x1400021cb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400021e0`

## callees

- `0x140002050`
- `0x140002294`
- `0x1400022d4`
- `0x1400023a8`
- `0x140002448`
- `0x140002474`
- `0x14000297c`
- `0x14000298c`
- `0x14000299c`
- `0x1400029b4`
- `0x140002b96`
- `0x140002ba2`
- `0x140002bae`
- `0x140002bba`
- `0x140002bea`
- `0x140002bf6`
- `0x140002c4a`
- `0x140002c7a`
- `0x140002c86`
- `0x140002cd8`
- `0x140002d08`
- `0x140008150`
- `0x140012010`

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
  BOOL v13; // ebx
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
  v13 = wmain(*v12, (LPCWCH *)v11);
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
0x140002050  mov     [rsp+arg_0], rbx
0x140002055  mov     [rsp+arg_8], rsi
0x14000205a  push    rdi
0x14000205b  sub     rsp, 30h
0x14000205f  mov     ecx, 1
0x140002064  call    __scrt_initialize_crt
0x140002069  test    al, al
0x14000206b  jz      loc_1400021A6
0x140002071  xor     sil, sil
0x140002074  mov     [rsp+38h+var_18], sil
0x140002079  call    __scrt_acquire_startup_lock
0x14000207e  mov     bl, al
0x140002080  mov     ecx, cs:__scrt_current_native_startup_state
0x140002086  cmp     ecx, 1
0x140002089  jz      loc_1400021B1
0x14000208f  test    ecx, ecx
0x140002091  jnz     short loc_1400020DD
0x140002093  mov     cs:__scrt_current_native_startup_state, 1
0x14000209d  lea     rdx, __xi_z; Last
0x1400020a4  lea     rcx, __xi_a; First
0x1400020ab  call    _initterm_e_0
0x1400020b0  test    eax, eax
0x1400020b2  jz      short loc_1400020BE
0x1400020b4  mov     eax, 0FFh
0x1400020b9  jmp     loc_140002196
0x1400020be  lea     rdx, __xc_z; Last
0x1400020c5  lea     rcx, __xc_a; First
0x1400020cc  call    _initterm_0
0x1400020d1  mov     cs:__scrt_current_native_startup_state, 2
0x1400020db  jmp     short loc_1400020E5
0x1400020dd  mov     sil, 1
0x1400020e0  mov     [rsp+38h+var_18], sil
0x1400020e5  mov     cl, bl
0x1400020e7  call    __scrt_release_startup_lock
0x1400020ec  call    __scrt_get_dyn_tls_init_callback
0x1400020f1  mov     rbx, rax
0x1400020f4  cmp     qword ptr [rax], 0
0x1400020f8  jz      short loc_140002117
0x1400020fa  mov     rcx, rax
0x1400020fd  call    __scrt_is_nonwritable_in_current_image
0x140002102  test    al, al
0x140002104  jz      short loc_140002117
0x140002106  xor     r8d, r8d
0x140002109  lea     edx, [r8+2]
0x14000210d  xor     ecx, ecx
0x14000210f  mov     rax, [rbx]
0x140002112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002117  call    __scrt_get_dyn_tls_dtor_callback
0x14000211c  mov     rbx, rax
0x14000211f  cmp     qword ptr [rax], 0
0x140002123  jz      short loc_140002139
0x140002125  mov     rcx, rax
0x140002128  call    __scrt_is_nonwritable_in_current_image
0x14000212d  test    al, al
0x14000212f  jz      short loc_140002139
0x140002131  mov     rcx, [rbx]; Callback
0x140002134  call    _register_thread_local_exe_atexit_callback_0
0x140002139  call    _get_initial_wide_environment
0x14000213e  mov     rdi, rax
0x140002141  call    __p___wargv
0x140002146  mov     rbx, [rax]
0x140002149  call    __p___argc
0x14000214e  mov     r8, rdi
0x140002151  mov     rdx, rbx
0x140002154  mov     ecx, [rax]
0x140002156  call    wmain
0x14000215b  mov     ebx, eax
0x14000215d  call    __scrt_is_managed_app
0x140002162  test    al, al
0x140002164  jz      short loc_1400021BB
0x140002166  test    sil, sil
0x140002169  jnz     short loc_140002170
0x14000216b  call    _o__cexit_0
0x140002170  xor     edx, edx
0x140002172  mov     cl, 1
0x140002174  call    __scrt_uninitialize_crt
0x140002179  mov     eax, ebx
0x14000217b  jmp     short loc_140002196
0x14000217d  mov     ebx, eax
0x14000217f  call    __scrt_is_managed_app
0x140002184  test    al, al
0x140002186  jz      short loc_1400021C3
0x140002188  cmp     [rsp+38h+var_18], 0
0x14000218d  jnz     short loc_140002194
0x14000218f  call    _c_exit_0
0x140002194  mov     eax, ebx
0x140002196  mov     rbx, [rsp+38h+arg_0]
0x14000219b  mov     rsi, [rsp+38h+arg_8]
0x1400021a0  add     rsp, 30h
0x1400021a4  pop     rdi
0x1400021a5  retn
0x1400021a6  mov     ecx, 7
0x1400021ab  call    __scrt_fastfail
0x1400021b1  mov     ecx, 7
0x1400021b6  call    __scrt_fastfail
0x1400021bb  mov     ecx, ebx; Code
0x1400021bd  call    _o_exit_0
0x1400021c3  mov     ecx, ebx
0x1400021c5  call    _o__exit_0
0x1400021ca  nop
0x140010e9c  push    rbp
0x140010e9e  sub     rsp, 20h
0x140010ea2  mov     rbp, rdx
0x140010ea5  mov     rdx, rcx; ExceptionPtr
0x140010ea8  mov     rcx, [rcx]
0x140010eab  mov     ecx, [rcx]; ExceptionNum
0x140010ead  call    _seh_filter_exe
0x140010eb2  nop
0x140010eb3  add     rsp, 20h
0x140010eb7  pop     rbp
0x140010eb8  retn
```
