# __scrt_common_main_seh

- ea: `0x140005380`
- end: `0x1400054f0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140005500`

## callees

- `0x14000215c`
- `0x140005380`
- `0x140005554`
- `0x140005594`
- `0x140005668`
- `0x140005708`
- `0x140005734`
- `0x140005938`
- `0x140005948`
- `0x140005958`
- `0x140005964`
- `0x1400059b0`
- `0x14000602c`
- `0x140006038`
- `0x140006044`
- `0x140006050`
- `0x140006098`
- `0x1400060c8`
- `0x1400060d4`
- `0x140006128`
- `0x140006158`
- `0x140010010`

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
  WCHAR *wide_winmain_command_line_0; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx

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
  wide_winmain_command_line_0 = (WCHAR *)o__get_wide_winmain_command_line_0();
  v14 = wWinMain(&_ImageBase, 0, wide_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    o_exit_0(v14);
  if ( !v1 )
    o__cexit_0(v16);
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x140005380  mov     [rsp+arg_0], rbx
0x140005385  push    rdi
0x140005386  sub     rsp, 30h
0x14000538a  mov     ecx, 1
0x14000538f  call    __scrt_initialize_crt
0x140005394  test    al, al
0x140005396  jz      loc_1400054CB
0x14000539c  xor     dil, dil
0x14000539f  mov     [rsp+38h+var_18], dil
0x1400053a4  call    __scrt_acquire_startup_lock
0x1400053a9  mov     bl, al
0x1400053ab  mov     ecx, cs:__scrt_current_native_startup_state
0x1400053b1  cmp     ecx, 1
0x1400053b4  jz      loc_1400054D6
0x1400053ba  test    ecx, ecx
0x1400053bc  jnz     short loc_140005408
0x1400053be  mov     cs:__scrt_current_native_startup_state, 1
0x1400053c8  lea     rdx, __xi_z; Last
0x1400053cf  lea     rcx, __xi_a; First
0x1400053d6  call    _initterm_e_0
0x1400053db  test    eax, eax
0x1400053dd  jz      short loc_1400053E9
0x1400053df  mov     eax, 0FFh
0x1400053e4  jmp     loc_1400054C0
0x1400053e9  lea     rdx, __xc_z; Last
0x1400053f0  lea     rcx, __xc_a; First
0x1400053f7  call    _initterm_0
0x1400053fc  mov     cs:__scrt_current_native_startup_state, 2
0x140005406  jmp     short loc_140005410
0x140005408  mov     dil, 1
0x14000540b  mov     [rsp+38h+var_18], dil
0x140005410  mov     cl, bl
0x140005412  call    __scrt_release_startup_lock
0x140005417  call    __scrt_get_dyn_tls_init_callback
0x14000541c  mov     rbx, rax
0x14000541f  cmp     qword ptr [rax], 0
0x140005423  jz      short loc_140005442
0x140005425  mov     rcx, rax
0x140005428  call    __scrt_is_nonwritable_in_current_image
0x14000542d  test    al, al
0x14000542f  jz      short loc_140005442
0x140005431  xor     r8d, r8d
0x140005434  lea     edx, [r8+2]
0x140005438  xor     ecx, ecx
0x14000543a  mov     rax, [rbx]
0x14000543d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005442  call    __scrt_get_dyn_tls_dtor_callback
0x140005447  mov     rbx, rax
0x14000544a  cmp     qword ptr [rax], 0
0x14000544e  jz      short loc_140005464
0x140005450  mov     rcx, rax
0x140005453  call    __scrt_is_nonwritable_in_current_image
0x140005458  test    al, al
0x14000545a  jz      short loc_140005464
0x14000545c  mov     rcx, [rbx]; Callback
0x14000545f  call    _register_thread_local_exe_atexit_callback_0
0x140005464  call    __scrt_get_show_window_mode
0x140005469  movzx   ebx, ax
0x14000546c  call    _o__get_wide_winmain_command_line_0
0x140005471  mov     r9d, ebx; nShowCmd
0x140005474  mov     r8, rax; lpCmdLine
0x140005477  xor     edx, edx; hPrevInstance
0x140005479  lea     rcx, __ImageBase; hInstance
0x140005480  call    wWinMain
0x140005485  mov     ebx, eax
0x140005487  call    __scrt_is_managed_app
0x14000548c  test    al, al
0x14000548e  jz      short loc_1400054E0
0x140005490  test    dil, dil
0x140005493  jnz     short loc_14000549A
0x140005495  call    _o__cexit_0
0x14000549a  xor     edx, edx
0x14000549c  mov     cl, 1
0x14000549e  call    __scrt_uninitialize_crt
0x1400054a3  mov     eax, ebx
0x1400054a5  jmp     short loc_1400054C0
0x1400054a7  mov     ebx, eax
0x1400054a9  call    __scrt_is_managed_app
0x1400054ae  test    al, al
0x1400054b0  jz      short loc_1400054E8
0x1400054b2  cmp     [rsp+38h+var_18], 0
0x1400054b7  jnz     short loc_1400054BE
0x1400054b9  call    _c_exit_0
0x1400054be  mov     eax, ebx
0x1400054c0  mov     rbx, [rsp+38h+arg_0]
0x1400054c5  add     rsp, 30h
0x1400054c9  pop     rdi
0x1400054ca  retn
0x1400054cb  mov     ecx, 7
0x1400054d0  call    __scrt_fastfail
0x1400054d6  mov     ecx, 7
0x1400054db  call    __scrt_fastfail
0x1400054e0  mov     ecx, ebx; Code
0x1400054e2  call    _o_exit_0
0x1400054e8  mov     ecx, ebx
0x1400054ea  call    _o__exit_0
0x1400054ef  nop
0x14000fcfc  push    rbp
0x14000fcfe  sub     rsp, 20h
0x14000fd02  mov     rbp, rdx
0x14000fd05  mov     rdx, rcx; ExceptionPtr
0x14000fd08  mov     rcx, [rcx]
0x14000fd0b  mov     ecx, [rcx]; ExceptionNum
0x14000fd0d  call    _seh_filter_exe
0x14000fd12  nop
0x14000fd13  add     rsp, 20h
0x14000fd17  pop     rbp
0x14000fd18  retn
```
