# __scrt_common_main_seh

- ea: `0x140001380`
- end: `0x1400014f0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001500`

## callees

- `0x140001380`
- `0x140001554`
- `0x140001594`
- `0x140001668`
- `0x140001708`
- `0x140001734`
- `0x140001920`
- `0x140001930`
- `0x140001940`
- `0x14000194c`
- `0x140001998`
- `0x140001dd6`
- `0x140001de2`
- `0x140001dee`
- `0x140001dfa`
- `0x140001e4e`
- `0x140001e7e`
- `0x140001e8a`
- `0x140001ed8`
- `0x140001f08`
- `0x1400085f4`
- `0x140009010`

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
0x140001380  mov     [rsp+arg_0], rbx
0x140001385  push    rdi
0x140001386  sub     rsp, 30h
0x14000138a  mov     ecx, 1
0x14000138f  call    __scrt_initialize_crt
0x140001394  test    al, al
0x140001396  jz      loc_1400014CB
0x14000139c  xor     dil, dil
0x14000139f  mov     [rsp+38h+var_18], dil
0x1400013a4  call    __scrt_acquire_startup_lock
0x1400013a9  mov     bl, al
0x1400013ab  mov     ecx, cs:__scrt_current_native_startup_state
0x1400013b1  cmp     ecx, 1
0x1400013b4  jz      loc_1400014D6
0x1400013ba  test    ecx, ecx
0x1400013bc  jnz     short loc_140001408
0x1400013be  mov     cs:__scrt_current_native_startup_state, 1
0x1400013c8  lea     rdx, __xi_z; Last
0x1400013cf  lea     rcx, __xi_a; First
0x1400013d6  call    _initterm_e_0
0x1400013db  test    eax, eax
0x1400013dd  jz      short loc_1400013E9
0x1400013df  mov     eax, 0FFh
0x1400013e4  jmp     loc_1400014C0
0x1400013e9  lea     rdx, __xc_z; Last
0x1400013f0  lea     rcx, __xc_a; First
0x1400013f7  call    _initterm_0
0x1400013fc  mov     cs:__scrt_current_native_startup_state, 2
0x140001406  jmp     short loc_140001410
0x140001408  mov     dil, 1
0x14000140b  mov     [rsp+38h+var_18], dil
0x140001410  mov     cl, bl
0x140001412  call    __scrt_release_startup_lock
0x140001417  call    __scrt_get_dyn_tls_init_callback
0x14000141c  mov     rbx, rax
0x14000141f  cmp     qword ptr [rax], 0
0x140001423  jz      short loc_140001442
0x140001425  mov     rcx, rax
0x140001428  call    __scrt_is_nonwritable_in_current_image
0x14000142d  test    al, al
0x14000142f  jz      short loc_140001442
0x140001431  xor     r8d, r8d
0x140001434  lea     edx, [r8+2]
0x140001438  xor     ecx, ecx
0x14000143a  mov     rax, [rbx]
0x14000143d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001442  call    __scrt_get_dyn_tls_dtor_callback
0x140001447  mov     rbx, rax
0x14000144a  cmp     qword ptr [rax], 0
0x14000144e  jz      short loc_140001464
0x140001450  mov     rcx, rax
0x140001453  call    __scrt_is_nonwritable_in_current_image
0x140001458  test    al, al
0x14000145a  jz      short loc_140001464
0x14000145c  mov     rcx, [rbx]; Callback
0x14000145f  call    _register_thread_local_exe_atexit_callback_0
0x140001464  call    __scrt_get_show_window_mode
0x140001469  movzx   ebx, ax
0x14000146c  call    _o__get_wide_winmain_command_line_0
0x140001471  mov     r9d, ebx; nShowCmd
0x140001474  mov     r8, rax; lpCmdLine
0x140001477  xor     edx, edx; hPrevInstance
0x140001479  lea     rcx, cs:140000000h; hInstance
0x140001480  call    wWinMain
0x140001485  mov     ebx, eax
0x140001487  call    __scrt_is_managed_app
0x14000148c  test    al, al
0x14000148e  jz      short loc_1400014E0
0x140001490  test    dil, dil
0x140001493  jnz     short loc_14000149A
0x140001495  call    _o__cexit_0
0x14000149a  xor     edx, edx
0x14000149c  mov     cl, 1
0x14000149e  call    __scrt_uninitialize_crt
0x1400014a3  mov     eax, ebx
0x1400014a5  jmp     short loc_1400014C0
0x1400014a7  mov     ebx, eax
0x1400014a9  call    __scrt_is_managed_app
0x1400014ae  test    al, al
0x1400014b0  jz      short loc_1400014E8
0x1400014b2  cmp     [rsp+38h+var_18], 0
0x1400014b7  jnz     short loc_1400014BE
0x1400014b9  call    _c_exit_0
0x1400014be  mov     eax, ebx
0x1400014c0  mov     rbx, [rsp+38h+arg_0]
0x1400014c5  add     rsp, 30h
0x1400014c9  pop     rdi
0x1400014ca  retn
0x1400014cb  mov     ecx, 7
0x1400014d0  call    __scrt_fastfail
0x1400014d6  mov     ecx, 7
0x1400014db  call    __scrt_fastfail
0x1400014e0  mov     ecx, ebx; Code
0x1400014e2  call    _o_exit_0
0x1400014e8  mov     ecx, ebx
0x1400014ea  call    _o__exit_0
0x1400014ef  nop
0x140008a7c  push    rbp
0x140008a7e  sub     rsp, 20h
0x140008a82  mov     rbp, rdx
0x140008a85  mov     rdx, rcx; ExceptionPtr
0x140008a88  mov     rcx, [rcx]
0x140008a8b  mov     ecx, [rcx]; ExceptionNum
0x140008a8d  call    _seh_filter_exe
0x140008a92  nop
0x140008a93  add     rsp, 20h
0x140008a97  pop     rbp
0x140008a98  retn
```
