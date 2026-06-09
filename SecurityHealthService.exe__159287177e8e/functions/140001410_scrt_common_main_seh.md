# __scrt_common_main_seh

- ea: `0x140001410`
- end: `0x14000158b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400015a0`

## callees

- `0x140001410`
- `0x140001650`
- `0x140001690`
- `0x140001764`
- `0x140001804`
- `0x140001830`
- `0x1400019d8`
- `0x1400019e8`
- `0x1400019f8`
- `0x140001a10`
- `0x140001ea6`
- `0x140001ed6`
- `0x140001ee2`
- `0x140001eee`
- `0x140001efa`
- `0x140001f06`
- `0x140001f1e`
- `0x140001f2a`
- `0x140001f36`
- `0x140001f42`
- `0x140001f4e`
- `0x140005508`
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
  get_initial_wide_environment_0();
  _p___wargv_0();
  _p___argc_0();
  v11 = wmain();
  if ( !(unsigned __int8)_scrt_is_managed_app(v12) )
    exit_0(v11);
  if ( !v1 )
    cexit_0();
  LOBYTE(v13) = 1;
  _scrt_uninitialize_crt(v13, 0);
  return v11;
}

```

## disassembly

```asm
0x140001410  mov     [rsp+arg_0], rbx
0x140001415  mov     [rsp+arg_8], rsi
0x14000141a  push    rdi
0x14000141b  sub     rsp, 30h
0x14000141f  mov     ecx, 1
0x140001424  call    __scrt_initialize_crt
0x140001429  test    al, al
0x14000142b  jz      loc_140001566
0x140001431  xor     sil, sil
0x140001434  mov     [rsp+38h+var_18], sil
0x140001439  call    __scrt_acquire_startup_lock
0x14000143e  mov     bl, al
0x140001440  mov     ecx, cs:__scrt_current_native_startup_state
0x140001446  cmp     ecx, 1
0x140001449  jz      loc_140001571
0x14000144f  test    ecx, ecx
0x140001451  jnz     short loc_14000149D
0x140001453  mov     cs:__scrt_current_native_startup_state, 1
0x14000145d  lea     rdx, __xi_z; Last
0x140001464  lea     rcx, __xi_a; First
0x14000146b  call    _initterm_e_0
0x140001470  test    eax, eax
0x140001472  jz      short loc_14000147E
0x140001474  mov     eax, 0FFh
0x140001479  jmp     loc_140001556
0x14000147e  lea     rdx, __xc_z; Last
0x140001485  lea     rcx, __xc_a; First
0x14000148c  call    _initterm_0
0x140001491  mov     cs:__scrt_current_native_startup_state, 2
0x14000149b  jmp     short loc_1400014A5
0x14000149d  mov     sil, 1
0x1400014a0  mov     [rsp+38h+var_18], sil
0x1400014a5  mov     cl, bl
0x1400014a7  call    __scrt_release_startup_lock
0x1400014ac  call    __scrt_get_dyn_tls_init_callback
0x1400014b1  mov     rbx, rax
0x1400014b4  cmp     qword ptr [rax], 0
0x1400014b8  jz      short loc_1400014D7
0x1400014ba  mov     rcx, rax
0x1400014bd  call    __scrt_is_nonwritable_in_current_image
0x1400014c2  test    al, al
0x1400014c4  jz      short loc_1400014D7
0x1400014c6  xor     r8d, r8d
0x1400014c9  lea     edx, [r8+2]
0x1400014cd  xor     ecx, ecx
0x1400014cf  mov     rax, [rbx]
0x1400014d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400014d7  call    __scrt_get_dyn_tls_dtor_callback
0x1400014dc  mov     rbx, rax
0x1400014df  cmp     qword ptr [rax], 0
0x1400014e3  jz      short loc_1400014F9
0x1400014e5  mov     rcx, rax
0x1400014e8  call    __scrt_is_nonwritable_in_current_image
0x1400014ed  test    al, al
0x1400014ef  jz      short loc_1400014F9
0x1400014f1  mov     rcx, [rbx]; Callback
0x1400014f4  call    _register_thread_local_exe_atexit_callback_0
0x1400014f9  call    _get_initial_wide_environment_0
0x1400014fe  mov     rdi, rax
0x140001501  call    __p___wargv_0
0x140001506  mov     rbx, [rax]
0x140001509  call    __p___argc_0
0x14000150e  mov     r8, rdi
0x140001511  mov     rdx, rbx
0x140001514  mov     ecx, [rax]
0x140001516  call    wmain
0x14000151b  mov     ebx, eax
0x14000151d  call    __scrt_is_managed_app
0x140001522  test    al, al
0x140001524  jz      short loc_14000157B
0x140001526  test    sil, sil
0x140001529  jnz     short loc_140001530
0x14000152b  call    _cexit_0
0x140001530  xor     edx, edx
0x140001532  mov     cl, 1
0x140001534  call    __scrt_uninitialize_crt
0x140001539  mov     eax, ebx
0x14000153b  jmp     short loc_140001556
0x14000153d  mov     ebx, eax
0x14000153f  call    __scrt_is_managed_app
0x140001544  test    al, al
0x140001546  jz      short loc_140001583
0x140001548  cmp     [rsp+38h+var_18], 0
0x14000154d  jnz     short loc_140001554
0x14000154f  call    _c_exit_0
0x140001554  mov     eax, ebx
0x140001556  mov     rbx, [rsp+38h+arg_0]
0x14000155b  mov     rsi, [rsp+38h+arg_8]
0x140001560  add     rsp, 30h
0x140001564  pop     rdi
0x140001565  retn
0x140001566  mov     ecx, 7
0x14000156b  call    __scrt_fastfail
0x140001571  mov     ecx, 7
0x140001576  call    __scrt_fastfail
0x14000157b  mov     ecx, ebx; Code
0x14000157d  call    exit_0
0x140001583  mov     ecx, ebx; Code
0x140001585  call    _exit_0
0x14001226c  push    rbp
0x14001226e  sub     rsp, 20h
0x140012272  mov     rbp, rdx
0x140012275  mov     rdx, rcx; ExceptionPtr
0x140012278  mov     rcx, [rcx]
0x14001227b  mov     ecx, [rcx]; ExceptionNum
0x14001227d  call    _seh_filter_exe_0
0x140012282  nop
0x140012283  add     rsp, 20h
0x140012287  pop     rbp
0x140012288  retn
```
