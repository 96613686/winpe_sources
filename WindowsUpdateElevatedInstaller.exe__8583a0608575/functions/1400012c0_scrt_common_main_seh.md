# __scrt_common_main_seh

- ea: `0x1400012c0`
- end: `0x14000143b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001450`

## callees

- `0x1400012c0`
- `0x1400014a4`
- `0x1400014e4`
- `0x1400015b8`
- `0x140001658`
- `0x140001684`
- `0x140001880`
- `0x140001890`
- `0x1400018a0`
- `0x1400018b8`
- `0x140001ce6`
- `0x140001cf2`
- `0x140001cfe`
- `0x140001d0a`
- `0x140001d2e`
- `0x140001d3a`
- `0x140001d82`
- `0x140001db2`
- `0x140001dbe`
- `0x140001dfa`
- `0x140001e2a`
- `0x140005df4`
- `0x140008010`

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
0x1400012c0  mov     [rsp+arg_0], rbx
0x1400012c5  mov     [rsp+arg_8], rsi
0x1400012ca  push    rdi
0x1400012cb  sub     rsp, 30h
0x1400012cf  mov     ecx, 1
0x1400012d4  call    __scrt_initialize_crt
0x1400012d9  test    al, al
0x1400012db  jz      loc_140001416
0x1400012e1  xor     sil, sil
0x1400012e4  mov     [rsp+38h+var_18], sil
0x1400012e9  call    __scrt_acquire_startup_lock
0x1400012ee  mov     bl, al
0x1400012f0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400012f6  cmp     ecx, 1
0x1400012f9  jz      loc_140001421
0x1400012ff  test    ecx, ecx
0x140001301  jnz     short loc_14000134D
0x140001303  mov     cs:__scrt_current_native_startup_state, 1
0x14000130d  lea     rdx, __xi_z; Last
0x140001314  lea     rcx, __xi_a; First
0x14000131b  call    _initterm_e_0
0x140001320  test    eax, eax
0x140001322  jz      short loc_14000132E
0x140001324  mov     eax, 0FFh
0x140001329  jmp     loc_140001406
0x14000132e  lea     rdx, __xc_z; Last
0x140001335  lea     rcx, __xc_a; First
0x14000133c  call    _initterm_0
0x140001341  mov     cs:__scrt_current_native_startup_state, 2
0x14000134b  jmp     short loc_140001355
0x14000134d  mov     sil, 1
0x140001350  mov     [rsp+38h+var_18], sil
0x140001355  mov     cl, bl
0x140001357  call    __scrt_release_startup_lock
0x14000135c  call    __scrt_get_dyn_tls_init_callback
0x140001361  mov     rbx, rax
0x140001364  cmp     qword ptr [rax], 0
0x140001368  jz      short loc_140001387
0x14000136a  mov     rcx, rax
0x14000136d  call    __scrt_is_nonwritable_in_current_image
0x140001372  test    al, al
0x140001374  jz      short loc_140001387
0x140001376  xor     r8d, r8d
0x140001379  lea     edx, [r8+2]
0x14000137d  xor     ecx, ecx
0x14000137f  mov     rax, [rbx]
0x140001382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001387  call    __scrt_get_dyn_tls_dtor_callback
0x14000138c  mov     rbx, rax
0x14000138f  cmp     qword ptr [rax], 0
0x140001393  jz      short loc_1400013A9
0x140001395  mov     rcx, rax
0x140001398  call    __scrt_is_nonwritable_in_current_image
0x14000139d  test    al, al
0x14000139f  jz      short loc_1400013A9
0x1400013a1  mov     rcx, [rbx]; Callback
0x1400013a4  call    _register_thread_local_exe_atexit_callback_0
0x1400013a9  call    _get_initial_wide_environment
0x1400013ae  mov     rdi, rax
0x1400013b1  call    __p___wargv
0x1400013b6  mov     rbx, [rax]
0x1400013b9  call    __p___argc
0x1400013be  mov     r8, rdi
0x1400013c1  mov     rdx, rbx
0x1400013c4  mov     ecx, [rax]
0x1400013c6  call    wmain
0x1400013cb  mov     ebx, eax
0x1400013cd  call    __scrt_is_managed_app
0x1400013d2  test    al, al
0x1400013d4  jz      short loc_14000142B
0x1400013d6  test    sil, sil
0x1400013d9  jnz     short loc_1400013E0
0x1400013db  call    _o__cexit_0
0x1400013e0  xor     edx, edx
0x1400013e2  mov     cl, 1
0x1400013e4  call    __scrt_uninitialize_crt
0x1400013e9  mov     eax, ebx
0x1400013eb  jmp     short loc_140001406
0x1400013ed  mov     ebx, eax
0x1400013ef  call    __scrt_is_managed_app
0x1400013f4  test    al, al
0x1400013f6  jz      short loc_140001433
0x1400013f8  cmp     [rsp+38h+var_18], 0
0x1400013fd  jnz     short loc_140001404
0x1400013ff  call    _c_exit_0
0x140001404  mov     eax, ebx
0x140001406  mov     rbx, [rsp+38h+arg_0]
0x14000140b  mov     rsi, [rsp+38h+arg_8]
0x140001410  add     rsp, 30h
0x140001414  pop     rdi
0x140001415  retn
0x140001416  mov     ecx, 7
0x14000141b  call    __scrt_fastfail
0x140001421  mov     ecx, 7
0x140001426  call    __scrt_fastfail
0x14000142b  mov     ecx, ebx; Code
0x14000142d  call    _o_exit_0
0x140001433  mov     ecx, ebx
0x140001435  call    _o__exit_0
0x14000143a  nop
0x14000716c  push    rbp
0x14000716e  sub     rsp, 20h
0x140007172  mov     rbp, rdx
0x140007175  mov     rdx, rcx; ExceptionPtr
0x140007178  mov     rcx, [rcx]
0x14000717b  mov     ecx, [rcx]; ExceptionNum
0x14000717d  call    _seh_filter_exe
0x140007182  nop
0x140007183  add     rsp, 20h
0x140007187  pop     rbp
0x140007188  retn
```
