# __scrt_common_main_seh

- ea: `0x140002220`
- end: `0x14000239b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400023b0`

## callees

- `0x140002220`
- `0x140002404`
- `0x140002444`
- `0x140002518`
- `0x1400025b8`
- `0x1400025e4`
- `0x140002798`
- `0x1400027a8`
- `0x1400027b8`
- `0x1400027d0`
- `0x140002c06`
- `0x140002c12`
- `0x140002c1e`
- `0x140002c2a`
- `0x140002c36`
- `0x140002c42`
- `0x140002c96`
- `0x140002cd2`
- `0x140002cea`
- `0x140002d48`
- `0x140002d84`
- `0x14000b79c`
- `0x14002b010`

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
  v13 = wmain(*v12, v11);
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
0x140002220  mov     [rsp+arg_0], rbx
0x140002225  mov     [rsp+arg_8], rsi
0x14000222a  push    rdi
0x14000222b  sub     rsp, 30h
0x14000222f  mov     ecx, 1
0x140002234  call    __scrt_initialize_crt
0x140002239  test    al, al
0x14000223b  jz      loc_140002376
0x140002241  xor     sil, sil
0x140002244  mov     [rsp+38h+var_18], sil
0x140002249  call    __scrt_acquire_startup_lock
0x14000224e  mov     bl, al
0x140002250  mov     ecx, cs:__scrt_current_native_startup_state
0x140002256  cmp     ecx, 1
0x140002259  jz      loc_140002381
0x14000225f  test    ecx, ecx
0x140002261  jnz     short loc_1400022AD
0x140002263  mov     cs:__scrt_current_native_startup_state, 1
0x14000226d  lea     rdx, __xi_z; Last
0x140002274  lea     rcx, __xi_a; First
0x14000227b  call    _initterm_e_0
0x140002280  test    eax, eax
0x140002282  jz      short loc_14000228E
0x140002284  mov     eax, 0FFh
0x140002289  jmp     loc_140002366
0x14000228e  lea     rdx, __xc_z; Last
0x140002295  lea     rcx, __xc_a; First
0x14000229c  call    _initterm_0
0x1400022a1  mov     cs:__scrt_current_native_startup_state, 2
0x1400022ab  jmp     short loc_1400022B5
0x1400022ad  mov     sil, 1
0x1400022b0  mov     [rsp+38h+var_18], sil
0x1400022b5  mov     cl, bl
0x1400022b7  call    __scrt_release_startup_lock
0x1400022bc  call    __scrt_get_dyn_tls_init_callback
0x1400022c1  mov     rbx, rax
0x1400022c4  cmp     qword ptr [rax], 0
0x1400022c8  jz      short loc_1400022E7
0x1400022ca  mov     rcx, rax
0x1400022cd  call    __scrt_is_nonwritable_in_current_image
0x1400022d2  test    al, al
0x1400022d4  jz      short loc_1400022E7
0x1400022d6  xor     r8d, r8d
0x1400022d9  lea     edx, [r8+2]
0x1400022dd  xor     ecx, ecx
0x1400022df  mov     rax, [rbx]
0x1400022e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022e7  call    __scrt_get_dyn_tls_dtor_callback
0x1400022ec  mov     rbx, rax
0x1400022ef  cmp     qword ptr [rax], 0
0x1400022f3  jz      short loc_140002309
0x1400022f5  mov     rcx, rax
0x1400022f8  call    __scrt_is_nonwritable_in_current_image
0x1400022fd  test    al, al
0x1400022ff  jz      short loc_140002309
0x140002301  mov     rcx, [rbx]; Callback
0x140002304  call    _register_thread_local_exe_atexit_callback_0
0x140002309  call    _get_initial_wide_environment
0x14000230e  mov     rdi, rax
0x140002311  call    __p___wargv
0x140002316  mov     rbx, [rax]
0x140002319  call    __p___argc
0x14000231e  mov     r8, rdi
0x140002321  mov     rdx, rbx; wchar_t **
0x140002324  mov     ecx, [rax]; unsigned int
0x140002326  call    wmain
0x14000232b  mov     ebx, eax
0x14000232d  call    __scrt_is_managed_app
0x140002332  test    al, al
0x140002334  jz      short loc_14000238B
0x140002336  test    sil, sil
0x140002339  jnz     short loc_140002340
0x14000233b  call    _o__cexit_0
0x140002340  xor     edx, edx
0x140002342  mov     cl, 1
0x140002344  call    __scrt_uninitialize_crt
0x140002349  mov     eax, ebx
0x14000234b  jmp     short loc_140002366
0x14000234d  mov     ebx, eax
0x14000234f  call    __scrt_is_managed_app
0x140002354  test    al, al
0x140002356  jz      short loc_140002393
0x140002358  cmp     [rsp+38h+var_18], 0
0x14000235d  jnz     short loc_140002364
0x14000235f  call    _c_exit_0
0x140002364  mov     eax, ebx
0x140002366  mov     rbx, [rsp+38h+arg_0]
0x14000236b  mov     rsi, [rsp+38h+arg_8]
0x140002370  add     rsp, 30h
0x140002374  pop     rdi
0x140002375  retn
0x140002376  mov     ecx, 7
0x14000237b  call    __scrt_fastfail
0x140002381  mov     ecx, 7
0x140002386  call    __scrt_fastfail
0x14000238b  mov     ecx, ebx; Code
0x14000238d  call    _o_exit_0
0x140002393  mov     ecx, ebx
0x140002395  call    _o__exit_0
0x14000239a  nop
0x14002a9dc  push    rbp
0x14002a9de  sub     rsp, 20h
0x14002a9e2  mov     rbp, rdx
0x14002a9e5  mov     rdx, rcx; ExceptionPtr
0x14002a9e8  mov     rcx, [rcx]
0x14002a9eb  mov     ecx, [rcx]; ExceptionNum
0x14002a9ed  call    _seh_filter_exe
0x14002a9f2  nop
0x14002a9f3  add     rsp, 20h
0x14002a9f7  pop     rbp
0x14002a9f8  retn
```
