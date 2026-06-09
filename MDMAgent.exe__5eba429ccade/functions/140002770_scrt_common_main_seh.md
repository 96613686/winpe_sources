# __scrt_common_main_seh

- ea: `0x140002770`
- end: `0x1400028eb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002900`

## callees

- `0x140002770`
- `0x140002a74`
- `0x140002ab4`
- `0x140002b88`
- `0x140002c28`
- `0x140002c54`
- `0x140002e54`
- `0x140002e64`
- `0x140002e74`
- `0x140002e8c`
- `0x1400032e6`
- `0x1400032f2`
- `0x1400032fe`
- `0x14000330a`
- `0x14000332e`
- `0x14000333a`
- `0x14000338e`
- `0x1400033be`
- `0x1400033ca`
- `0x140003418`
- `0x140003448`
- `0x140007f34`
- `0x140019010`

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
0x140002770  mov     [rsp+arg_0], rbx
0x140002775  mov     [rsp+arg_8], rsi
0x14000277a  push    rdi
0x14000277b  sub     rsp, 30h
0x14000277f  mov     ecx, 1
0x140002784  call    __scrt_initialize_crt
0x140002789  test    al, al
0x14000278b  jz      loc_1400028C6
0x140002791  xor     sil, sil
0x140002794  mov     [rsp+38h+var_18], sil
0x140002799  call    __scrt_acquire_startup_lock
0x14000279e  mov     bl, al
0x1400027a0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400027a6  cmp     ecx, 1
0x1400027a9  jz      loc_1400028D1
0x1400027af  test    ecx, ecx
0x1400027b1  jnz     short loc_1400027FD
0x1400027b3  mov     cs:__scrt_current_native_startup_state, 1
0x1400027bd  lea     rdx, __xi_z; Last
0x1400027c4  lea     rcx, __xi_a; First
0x1400027cb  call    _initterm_e_0
0x1400027d0  test    eax, eax
0x1400027d2  jz      short loc_1400027DE
0x1400027d4  mov     eax, 0FFh
0x1400027d9  jmp     loc_1400028B6
0x1400027de  lea     rdx, __xc_z; Last
0x1400027e5  lea     rcx, __xc_a; First
0x1400027ec  call    _initterm_0
0x1400027f1  mov     cs:__scrt_current_native_startup_state, 2
0x1400027fb  jmp     short loc_140002805
0x1400027fd  mov     sil, 1
0x140002800  mov     [rsp+38h+var_18], sil
0x140002805  mov     cl, bl
0x140002807  call    __scrt_release_startup_lock
0x14000280c  call    __scrt_get_dyn_tls_init_callback
0x140002811  mov     rbx, rax
0x140002814  cmp     qword ptr [rax], 0
0x140002818  jz      short loc_140002837
0x14000281a  mov     rcx, rax
0x14000281d  call    __scrt_is_nonwritable_in_current_image
0x140002822  test    al, al
0x140002824  jz      short loc_140002837
0x140002826  xor     r8d, r8d
0x140002829  lea     edx, [r8+2]
0x14000282d  xor     ecx, ecx
0x14000282f  mov     rax, [rbx]
0x140002832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002837  call    __scrt_get_dyn_tls_dtor_callback
0x14000283c  mov     rbx, rax
0x14000283f  cmp     qword ptr [rax], 0
0x140002843  jz      short loc_140002859
0x140002845  mov     rcx, rax
0x140002848  call    __scrt_is_nonwritable_in_current_image
0x14000284d  test    al, al
0x14000284f  jz      short loc_140002859
0x140002851  mov     rcx, [rbx]; Callback
0x140002854  call    _register_thread_local_exe_atexit_callback_0
0x140002859  call    _get_initial_wide_environment
0x14000285e  mov     rdi, rax
0x140002861  call    __p___wargv
0x140002866  mov     rbx, [rax]
0x140002869  call    __p___argc
0x14000286e  mov     r8, rdi
0x140002871  mov     rdx, rbx
0x140002874  mov     ecx, [rax]
0x140002876  call    wmain
0x14000287b  mov     ebx, eax
0x14000287d  call    __scrt_is_managed_app
0x140002882  test    al, al
0x140002884  jz      short loc_1400028DB
0x140002886  test    sil, sil
0x140002889  jnz     short loc_140002890
0x14000288b  call    _o__cexit_0
0x140002890  xor     edx, edx
0x140002892  mov     cl, 1
0x140002894  call    __scrt_uninitialize_crt
0x140002899  mov     eax, ebx
0x14000289b  jmp     short loc_1400028B6
0x14000289d  mov     ebx, eax
0x14000289f  call    __scrt_is_managed_app
0x1400028a4  test    al, al
0x1400028a6  jz      short loc_1400028E3
0x1400028a8  cmp     [rsp+38h+var_18], 0
0x1400028ad  jnz     short loc_1400028B4
0x1400028af  call    _c_exit_0
0x1400028b4  mov     eax, ebx
0x1400028b6  mov     rbx, [rsp+38h+arg_0]
0x1400028bb  mov     rsi, [rsp+38h+arg_8]
0x1400028c0  add     rsp, 30h
0x1400028c4  pop     rdi
0x1400028c5  retn
0x1400028c6  mov     ecx, 7
0x1400028cb  call    __scrt_fastfail
0x1400028d1  mov     ecx, 7
0x1400028d6  call    __scrt_fastfail
0x1400028db  mov     ecx, ebx; Code
0x1400028dd  call    _o_exit_0
0x1400028e3  mov     ecx, ebx
0x1400028e5  call    _o__exit_0
0x1400028ea  nop
0x1400186cc  push    rbp
0x1400186ce  sub     rsp, 20h
0x1400186d2  mov     rbp, rdx
0x1400186d5  mov     rdx, rcx; ExceptionPtr
0x1400186d8  mov     rcx, [rcx]
0x1400186db  mov     ecx, [rcx]; ExceptionNum
0x1400186dd  call    _seh_filter_exe
0x1400186e2  nop
0x1400186e3  add     rsp, 20h
0x1400186e7  pop     rbp
0x1400186e8  retn
```
