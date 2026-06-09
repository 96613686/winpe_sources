# __scrt_common_main_seh

- ea: `0x140002870`
- end: `0x1400029eb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002a00`

## callees

- `0x140002870`
- `0x140002b68`
- `0x140002ba8`
- `0x140002c7c`
- `0x140002d1c`
- `0x140002d48`
- `0x140002fc8`
- `0x140002fd8`
- `0x140002fe8`
- `0x140003000`
- `0x1400034d6`
- `0x1400034e2`
- `0x1400034ee`
- `0x1400034fa`
- `0x140003512`
- `0x14000351e`
- `0x14000358a`
- `0x1400035ba`
- `0x1400035c6`
- `0x140003618`
- `0x140003648`
- `0x14000a8f0`
- `0x140013010`

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
0x140002870  mov     [rsp+arg_0], rbx
0x140002875  mov     [rsp+arg_8], rsi
0x14000287a  push    rdi
0x14000287b  sub     rsp, 30h
0x14000287f  mov     ecx, 1
0x140002884  call    __scrt_initialize_crt
0x140002889  test    al, al
0x14000288b  jz      loc_1400029C6
0x140002891  xor     sil, sil
0x140002894  mov     [rsp+38h+var_18], sil
0x140002899  call    __scrt_acquire_startup_lock
0x14000289e  mov     bl, al
0x1400028a0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400028a6  cmp     ecx, 1
0x1400028a9  jz      loc_1400029D1
0x1400028af  test    ecx, ecx
0x1400028b1  jnz     short loc_1400028FD
0x1400028b3  mov     cs:__scrt_current_native_startup_state, 1
0x1400028bd  lea     rdx, __xi_z; Last
0x1400028c4  lea     rcx, __xi_a; First
0x1400028cb  call    _initterm_e_0
0x1400028d0  test    eax, eax
0x1400028d2  jz      short loc_1400028DE
0x1400028d4  mov     eax, 0FFh
0x1400028d9  jmp     loc_1400029B6
0x1400028de  lea     rdx, __xc_z; Last
0x1400028e5  lea     rcx, __xc_a; First
0x1400028ec  call    _initterm_0
0x1400028f1  mov     cs:__scrt_current_native_startup_state, 2
0x1400028fb  jmp     short loc_140002905
0x1400028fd  mov     sil, 1
0x140002900  mov     [rsp+38h+var_18], sil
0x140002905  mov     cl, bl
0x140002907  call    __scrt_release_startup_lock
0x14000290c  call    __scrt_get_dyn_tls_init_callback
0x140002911  mov     rbx, rax
0x140002914  cmp     qword ptr [rax], 0
0x140002918  jz      short loc_140002937
0x14000291a  mov     rcx, rax
0x14000291d  call    __scrt_is_nonwritable_in_current_image
0x140002922  test    al, al
0x140002924  jz      short loc_140002937
0x140002926  xor     r8d, r8d
0x140002929  lea     edx, [r8+2]
0x14000292d  xor     ecx, ecx
0x14000292f  mov     rax, [rbx]
0x140002932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002937  call    __scrt_get_dyn_tls_dtor_callback
0x14000293c  mov     rbx, rax
0x14000293f  cmp     qword ptr [rax], 0
0x140002943  jz      short loc_140002959
0x140002945  mov     rcx, rax
0x140002948  call    __scrt_is_nonwritable_in_current_image
0x14000294d  test    al, al
0x14000294f  jz      short loc_140002959
0x140002951  mov     rcx, [rbx]; Callback
0x140002954  call    _register_thread_local_exe_atexit_callback_0
0x140002959  call    _get_initial_wide_environment
0x14000295e  mov     rdi, rax
0x140002961  call    __p___wargv
0x140002966  mov     rbx, [rax]
0x140002969  call    __p___argc
0x14000296e  mov     r8, rdi
0x140002971  mov     rdx, rbx
0x140002974  mov     ecx, [rax]
0x140002976  call    wmain
0x14000297b  mov     ebx, eax
0x14000297d  call    __scrt_is_managed_app
0x140002982  test    al, al
0x140002984  jz      short loc_1400029DB
0x140002986  test    sil, sil
0x140002989  jnz     short loc_140002990
0x14000298b  call    _o__cexit_0
0x140002990  xor     edx, edx
0x140002992  mov     cl, 1
0x140002994  call    __scrt_uninitialize_crt
0x140002999  mov     eax, ebx
0x14000299b  jmp     short loc_1400029B6
0x14000299d  mov     ebx, eax
0x14000299f  call    __scrt_is_managed_app
0x1400029a4  test    al, al
0x1400029a6  jz      short loc_1400029E3
0x1400029a8  cmp     [rsp+38h+var_18], 0
0x1400029ad  jnz     short loc_1400029B4
0x1400029af  call    _c_exit_0
0x1400029b4  mov     eax, ebx
0x1400029b6  mov     rbx, [rsp+38h+arg_0]
0x1400029bb  mov     rsi, [rsp+38h+arg_8]
0x1400029c0  add     rsp, 30h
0x1400029c4  pop     rdi
0x1400029c5  retn
0x1400029c6  mov     ecx, 7
0x1400029cb  call    __scrt_fastfail
0x1400029d1  mov     ecx, 7
0x1400029d6  call    __scrt_fastfail
0x1400029db  mov     ecx, ebx; Code
0x1400029dd  call    _o_exit_0
0x1400029e3  mov     ecx, ebx
0x1400029e5  call    _o__exit_0
0x1400029ea  nop
0x1400120ac  push    rbp
0x1400120ae  sub     rsp, 20h
0x1400120b2  mov     rbp, rdx
0x1400120b5  mov     rdx, rcx; ExceptionPtr
0x1400120b8  mov     rcx, [rcx]
0x1400120bb  mov     ecx, [rcx]; ExceptionNum
0x1400120bd  call    _seh_filter_exe
0x1400120c2  nop
0x1400120c3  add     rsp, 20h
0x1400120c7  pop     rbp
0x1400120c8  retn
```
