# __scrt_common_main_seh

- ea: `0x140001450`
- end: `0x1400015c0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400015d0`

## callees

- `0x140001450`
- `0x140001624`
- `0x140001664`
- `0x140001738`
- `0x1400017d8`
- `0x140001804`
- `0x1400019d0`
- `0x1400019e0`
- `0x1400019f0`
- `0x1400019fc`
- `0x140001a48`
- `0x140001e76`
- `0x140001e82`
- `0x140001e8e`
- `0x140001e9a`
- `0x140001ebe`
- `0x140001eee`
- `0x140001efa`
- `0x140001f36`
- `0x140001f66`
- `0x1400054fc`
- `0x140006010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // di
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  __int64 v10; // rcx
  _tls_callback_type *v11; // rbx
  int show_window_mode; // ebx
  __int64 v13; // rcx
  WCHAR *wide_winmain_command_line_0; // rax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rcx

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
  v11 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v11);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v10);
  wide_winmain_command_line_0 = (WCHAR *)o__get_wide_winmain_command_line_0(v13);
  v15 = wWinMain((HINSTANCE)0x140000000LL, 0, wide_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v16) )
    o_exit_0(v15);
  if ( !v1 )
    o__cexit_0(v17);
  LOBYTE(v17) = 1;
  _scrt_uninitialize_crt(v17, 0);
  return v15;
}

```

## disassembly

```asm
0x140001450  mov     [rsp+arg_0], rbx
0x140001455  push    rdi
0x140001456  sub     rsp, 30h
0x14000145a  mov     ecx, 1
0x14000145f  call    __scrt_initialize_crt
0x140001464  test    al, al
0x140001466  jz      loc_14000159B
0x14000146c  xor     dil, dil
0x14000146f  mov     [rsp+38h+var_18], dil
0x140001474  call    __scrt_acquire_startup_lock
0x140001479  mov     bl, al
0x14000147b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001481  cmp     ecx, 1
0x140001484  jz      loc_1400015A6
0x14000148a  test    ecx, ecx
0x14000148c  jnz     short loc_1400014D8
0x14000148e  mov     cs:__scrt_current_native_startup_state, 1
0x140001498  lea     rdx, __xi_z; Last
0x14000149f  lea     rcx, __xi_a; First
0x1400014a6  call    _initterm_e_0
0x1400014ab  test    eax, eax
0x1400014ad  jz      short loc_1400014B9
0x1400014af  mov     eax, 0FFh
0x1400014b4  jmp     loc_140001590
0x1400014b9  lea     rdx, __xc_z; Last
0x1400014c0  lea     rcx, __xc_a; First
0x1400014c7  call    _initterm_0
0x1400014cc  mov     cs:__scrt_current_native_startup_state, 2
0x1400014d6  jmp     short loc_1400014E0
0x1400014d8  mov     dil, 1
0x1400014db  mov     [rsp+38h+var_18], dil
0x1400014e0  mov     cl, bl
0x1400014e2  call    __scrt_release_startup_lock
0x1400014e7  call    __scrt_get_dyn_tls_init_callback
0x1400014ec  mov     rbx, rax
0x1400014ef  cmp     qword ptr [rax], 0
0x1400014f3  jz      short loc_140001512
0x1400014f5  mov     rcx, rax
0x1400014f8  call    __scrt_is_nonwritable_in_current_image
0x1400014fd  test    al, al
0x1400014ff  jz      short loc_140001512
0x140001501  xor     r8d, r8d
0x140001504  lea     edx, [r8+2]
0x140001508  xor     ecx, ecx
0x14000150a  mov     rax, [rbx]
0x14000150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001512  call    __scrt_get_dyn_tls_dtor_callback
0x140001517  mov     rbx, rax
0x14000151a  cmp     qword ptr [rax], 0
0x14000151e  jz      short loc_140001534
0x140001520  mov     rcx, rax
0x140001523  call    __scrt_is_nonwritable_in_current_image
0x140001528  test    al, al
0x14000152a  jz      short loc_140001534
0x14000152c  mov     rcx, [rbx]; Callback
0x14000152f  call    _register_thread_local_exe_atexit_callback_0
0x140001534  call    __scrt_get_show_window_mode
0x140001539  movzx   ebx, ax
0x14000153c  call    _o__get_wide_winmain_command_line_0
0x140001541  mov     r9d, ebx; nShowCmd
0x140001544  mov     r8, rax; lpCmdLine
0x140001547  xor     edx, edx; hPrevInstance
0x140001549  lea     rcx, cs:140000000h; hInstance
0x140001550  call    wWinMain
0x140001555  mov     ebx, eax
0x140001557  call    __scrt_is_managed_app
0x14000155c  test    al, al
0x14000155e  jz      short loc_1400015B0
0x140001560  test    dil, dil
0x140001563  jnz     short loc_14000156A
0x140001565  call    _o__cexit_0
0x14000156a  xor     edx, edx
0x14000156c  mov     cl, 1
0x14000156e  call    __scrt_uninitialize_crt
0x140001573  mov     eax, ebx
0x140001575  jmp     short loc_140001590
0x140001577  mov     ebx, eax
0x140001579  call    __scrt_is_managed_app
0x14000157e  test    al, al
0x140001580  jz      short loc_1400015B8
0x140001582  cmp     [rsp+38h+var_18], 0
0x140001587  jnz     short loc_14000158E
0x140001589  call    _c_exit_0
0x14000158e  mov     eax, ebx
0x140001590  mov     rbx, [rsp+38h+arg_0]
0x140001595  add     rsp, 30h
0x140001599  pop     rdi
0x14000159a  retn
0x14000159b  mov     ecx, 7
0x1400015a0  call    __scrt_fastfail
0x1400015a6  mov     ecx, 7
0x1400015ab  call    __scrt_fastfail
0x1400015b0  mov     ecx, ebx; Code
0x1400015b2  call    _o_exit_0
0x1400015b8  mov     ecx, ebx
0x1400015ba  call    _o__exit_0
0x1400015bf  nop
0x140005afc  push    rbp
0x140005afe  sub     rsp, 20h
0x140005b02  mov     rbp, rdx
0x140005b05  mov     rdx, rcx; ExceptionPtr
0x140005b08  mov     rcx, [rcx]
0x140005b0b  mov     ecx, [rcx]; ExceptionNum
0x140005b0d  call    _seh_filter_exe
0x140005b12  nop
0x140005b13  add     rsp, 20h
0x140005b17  pop     rbp
0x140005b18  retn
```
