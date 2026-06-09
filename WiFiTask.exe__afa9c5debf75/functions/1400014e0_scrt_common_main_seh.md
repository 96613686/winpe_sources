# __scrt_common_main_seh

- ea: `0x1400014e0`
- end: `0x14000165b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001670`

## callees

- `0x1400014e0`
- `0x140001738`
- `0x140001778`
- `0x14000184c`
- `0x1400018ec`
- `0x140001918`
- `0x140001b04`
- `0x140001b14`
- `0x140001b24`
- `0x140001b3c`
- `0x140001fb6`
- `0x140001fc2`
- `0x140001fce`
- `0x140001fda`
- `0x140001ffe`
- `0x14000200a`
- `0x140002052`
- `0x140002082`
- `0x14000208e`
- `0x1400020d8`
- `0x140002108`
- `0x14000c7b0`
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
0x1400014e0  mov     [rsp+arg_0], rbx
0x1400014e5  mov     [rsp+arg_8], rsi
0x1400014ea  push    rdi
0x1400014eb  sub     rsp, 30h
0x1400014ef  mov     ecx, 1
0x1400014f4  call    __scrt_initialize_crt
0x1400014f9  test    al, al
0x1400014fb  jz      loc_140001636
0x140001501  xor     sil, sil
0x140001504  mov     [rsp+38h+var_18], sil
0x140001509  call    __scrt_acquire_startup_lock
0x14000150e  mov     bl, al
0x140001510  mov     ecx, cs:__scrt_current_native_startup_state
0x140001516  cmp     ecx, 1
0x140001519  jz      loc_140001641
0x14000151f  test    ecx, ecx
0x140001521  jnz     short loc_14000156D
0x140001523  mov     cs:__scrt_current_native_startup_state, 1
0x14000152d  lea     rdx, __xi_z; Last
0x140001534  lea     rcx, __xi_a; First
0x14000153b  call    _initterm_e_0
0x140001540  test    eax, eax
0x140001542  jz      short loc_14000154E
0x140001544  mov     eax, 0FFh
0x140001549  jmp     loc_140001626
0x14000154e  lea     rdx, __xc_z; Last
0x140001555  lea     rcx, __xc_a; First
0x14000155c  call    _initterm_0
0x140001561  mov     cs:__scrt_current_native_startup_state, 2
0x14000156b  jmp     short loc_140001575
0x14000156d  mov     sil, 1
0x140001570  mov     [rsp+38h+var_18], sil
0x140001575  mov     cl, bl
0x140001577  call    __scrt_release_startup_lock
0x14000157c  call    __scrt_get_dyn_tls_init_callback
0x140001581  mov     rbx, rax
0x140001584  cmp     qword ptr [rax], 0
0x140001588  jz      short loc_1400015A7
0x14000158a  mov     rcx, rax
0x14000158d  call    __scrt_is_nonwritable_in_current_image
0x140001592  test    al, al
0x140001594  jz      short loc_1400015A7
0x140001596  xor     r8d, r8d
0x140001599  lea     edx, [r8+2]
0x14000159d  xor     ecx, ecx
0x14000159f  mov     rax, [rbx]
0x1400015a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400015a7  call    __scrt_get_dyn_tls_dtor_callback
0x1400015ac  mov     rbx, rax
0x1400015af  cmp     qword ptr [rax], 0
0x1400015b3  jz      short loc_1400015C9
0x1400015b5  mov     rcx, rax
0x1400015b8  call    __scrt_is_nonwritable_in_current_image
0x1400015bd  test    al, al
0x1400015bf  jz      short loc_1400015C9
0x1400015c1  mov     rcx, [rbx]; Callback
0x1400015c4  call    _register_thread_local_exe_atexit_callback_0
0x1400015c9  call    _get_initial_wide_environment
0x1400015ce  mov     rdi, rax
0x1400015d1  call    __p___wargv
0x1400015d6  mov     rbx, [rax]
0x1400015d9  call    __p___argc
0x1400015de  mov     r8, rdi
0x1400015e1  mov     rdx, rbx
0x1400015e4  mov     ecx, [rax]
0x1400015e6  call    wmain
0x1400015eb  mov     ebx, eax
0x1400015ed  call    __scrt_is_managed_app
0x1400015f2  test    al, al
0x1400015f4  jz      short loc_14000164B
0x1400015f6  test    sil, sil
0x1400015f9  jnz     short loc_140001600
0x1400015fb  call    _o__cexit_0
0x140001600  xor     edx, edx
0x140001602  mov     cl, 1
0x140001604  call    __scrt_uninitialize_crt
0x140001609  mov     eax, ebx
0x14000160b  jmp     short loc_140001626
0x14000160d  mov     ebx, eax
0x14000160f  call    __scrt_is_managed_app
0x140001614  test    al, al
0x140001616  jz      short loc_140001653
0x140001618  cmp     [rsp+38h+var_18], 0
0x14000161d  jnz     short loc_140001624
0x14000161f  call    _c_exit_0
0x140001624  mov     eax, ebx
0x140001626  mov     rbx, [rsp+38h+arg_0]
0x14000162b  mov     rsi, [rsp+38h+arg_8]
0x140001630  add     rsp, 30h
0x140001634  pop     rdi
0x140001635  retn
0x140001636  mov     ecx, 7
0x14000163b  call    __scrt_fastfail
0x140001641  mov     ecx, 7
0x140001646  call    __scrt_fastfail
0x14000164b  mov     ecx, ebx; Code
0x14000164d  call    _o_exit_0
0x140001653  mov     ecx, ebx
0x140001655  call    _o__exit_0
0x14000165a  nop
0x140010e6c  push    rbp
0x140010e6e  sub     rsp, 20h
0x140010e72  mov     rbp, rdx
0x140010e75  mov     rdx, rcx; ExceptionPtr
0x140010e78  mov     rcx, [rcx]
0x140010e7b  mov     ecx, [rcx]; ExceptionNum
0x140010e7d  call    _seh_filter_exe
0x140010e82  nop
0x140010e83  add     rsp, 20h
0x140010e87  pop     rbp
0x140010e88  retn
```
