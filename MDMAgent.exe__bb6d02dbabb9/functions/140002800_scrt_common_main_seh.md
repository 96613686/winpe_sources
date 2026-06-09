# __scrt_common_main_seh

- ea: `0x140002800`
- end: `0x14000297b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002990`

## callees

- `0x140002800`
- `0x140002b04`
- `0x140002b44`
- `0x140002c18`
- `0x140002cb8`
- `0x140002ce4`
- `0x140002ef0`
- `0x140002f00`
- `0x140002f10`
- `0x140002f28`
- `0x140003386`
- `0x140003392`
- `0x14000339e`
- `0x1400033aa`
- `0x1400033ce`
- `0x1400033da`
- `0x14000342e`
- `0x14000345e`
- `0x14000346a`
- `0x1400034b8`
- `0x1400034e8`
- `0x14000829c`
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
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx

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
  _p___wargv();
  _p___argc();
  v11 = wmain();
  if ( !(unsigned __int8)_scrt_is_managed_app(v12) )
    o_exit_0(v11);
  if ( !v1 )
    o__cexit_0(v13);
  LOBYTE(v13) = 1;
  _scrt_uninitialize_crt(v13, 0);
  return v11;
}

```

## disassembly

```asm
0x140002800  mov     [rsp+arg_0], rbx
0x140002805  mov     [rsp+arg_8], rsi
0x14000280a  push    rdi
0x14000280b  sub     rsp, 30h
0x14000280f  mov     ecx, 1
0x140002814  call    __scrt_initialize_crt
0x140002819  test    al, al
0x14000281b  jz      loc_140002956
0x140002821  xor     sil, sil
0x140002824  mov     [rsp+38h+var_18], sil
0x140002829  call    __scrt_acquire_startup_lock
0x14000282e  mov     bl, al
0x140002830  mov     ecx, cs:__scrt_current_native_startup_state
0x140002836  cmp     ecx, 1
0x140002839  jz      loc_140002961
0x14000283f  test    ecx, ecx
0x140002841  jnz     short loc_14000288D
0x140002843  mov     cs:__scrt_current_native_startup_state, 1
0x14000284d  lea     rdx, __xi_z; Last
0x140002854  lea     rcx, __xi_a; First
0x14000285b  call    _initterm_e_0
0x140002860  test    eax, eax
0x140002862  jz      short loc_14000286E
0x140002864  mov     eax, 0FFh
0x140002869  jmp     loc_140002946
0x14000286e  lea     rdx, __xc_z; Last
0x140002875  lea     rcx, __xc_a; First
0x14000287c  call    _initterm_0
0x140002881  mov     cs:__scrt_current_native_startup_state, 2
0x14000288b  jmp     short loc_140002895
0x14000288d  mov     sil, 1
0x140002890  mov     [rsp+38h+var_18], sil
0x140002895  mov     cl, bl
0x140002897  call    __scrt_release_startup_lock
0x14000289c  call    __scrt_get_dyn_tls_init_callback
0x1400028a1  mov     rbx, rax
0x1400028a4  cmp     qword ptr [rax], 0
0x1400028a8  jz      short loc_1400028C7
0x1400028aa  mov     rcx, rax
0x1400028ad  call    __scrt_is_nonwritable_in_current_image
0x1400028b2  test    al, al
0x1400028b4  jz      short loc_1400028C7
0x1400028b6  xor     r8d, r8d
0x1400028b9  lea     edx, [r8+2]
0x1400028bd  xor     ecx, ecx
0x1400028bf  mov     rax, [rbx]
0x1400028c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028c7  call    __scrt_get_dyn_tls_dtor_callback
0x1400028cc  mov     rbx, rax
0x1400028cf  cmp     qword ptr [rax], 0
0x1400028d3  jz      short loc_1400028E9
0x1400028d5  mov     rcx, rax
0x1400028d8  call    __scrt_is_nonwritable_in_current_image
0x1400028dd  test    al, al
0x1400028df  jz      short loc_1400028E9
0x1400028e1  mov     rcx, [rbx]; Callback
0x1400028e4  call    _register_thread_local_exe_atexit_callback_0
0x1400028e9  call    _get_initial_wide_environment
0x1400028ee  mov     rdi, rax
0x1400028f1  call    __p___wargv
0x1400028f6  mov     rbx, [rax]
0x1400028f9  call    __p___argc
0x1400028fe  mov     r8, rdi
0x140002901  mov     rdx, rbx
0x140002904  mov     ecx, [rax]
0x140002906  call    wmain
0x14000290b  mov     ebx, eax
0x14000290d  call    __scrt_is_managed_app
0x140002912  test    al, al
0x140002914  jz      short loc_14000296B
0x140002916  test    sil, sil
0x140002919  jnz     short loc_140002920
0x14000291b  call    _o__cexit_0
0x140002920  xor     edx, edx
0x140002922  mov     cl, 1
0x140002924  call    __scrt_uninitialize_crt
0x140002929  mov     eax, ebx
0x14000292b  jmp     short loc_140002946
0x14000292d  mov     ebx, eax
0x14000292f  call    __scrt_is_managed_app
0x140002934  test    al, al
0x140002936  jz      short loc_140002973
0x140002938  cmp     [rsp+38h+var_18], 0
0x14000293d  jnz     short loc_140002944
0x14000293f  call    _c_exit_0
0x140002944  mov     eax, ebx
0x140002946  mov     rbx, [rsp+38h+arg_0]
0x14000294b  mov     rsi, [rsp+38h+arg_8]
0x140002950  add     rsp, 30h
0x140002954  pop     rdi
0x140002955  retn
0x140002956  mov     ecx, 7
0x14000295b  call    __scrt_fastfail
0x140002961  mov     ecx, 7
0x140002966  call    __scrt_fastfail
0x14000296b  mov     ecx, ebx; Code
0x14000296d  call    _o_exit_0
0x140002973  mov     ecx, ebx
0x140002975  call    _o__exit_0
0x14000297a  nop
0x14001942c  push    rbp
0x14001942e  sub     rsp, 20h
0x140019432  mov     rbp, rdx
0x140019435  mov     rdx, rcx; ExceptionPtr
0x140019438  mov     rcx, [rcx]
0x14001943b  mov     ecx, [rcx]; ExceptionNum
0x14001943d  call    _seh_filter_exe
0x140019442  nop
0x140019443  add     rsp, 20h
0x140019447  pop     rbp
0x140019448  retn
```
