# __scrt_common_main_seh

- ea: `0x140003470`
- end: `0x1400035e0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400035f0`

## callees

- `0x140003470`
- `0x140003668`
- `0x1400036a8`
- `0x14000377c`
- `0x14000381c`
- `0x140003848`
- `0x140003a14`
- `0x140003a24`
- `0x140003a34`
- `0x140003a40`
- `0x140003a8c`
- `0x14000412c`
- `0x140004138`
- `0x140004144`
- `0x140004150`
- `0x140004198`
- `0x1400041c8`
- `0x1400041d4`
- `0x140004228`
- `0x140004258`
- `0x14001c3d4`
- `0x14001f010`

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
0x140003470  mov     [rsp+arg_0], rbx
0x140003475  push    rdi
0x140003476  sub     rsp, 30h
0x14000347a  mov     ecx, 1
0x14000347f  call    __scrt_initialize_crt
0x140003484  test    al, al
0x140003486  jz      loc_1400035BB
0x14000348c  xor     dil, dil
0x14000348f  mov     [rsp+38h+var_18], dil
0x140003494  call    __scrt_acquire_startup_lock
0x140003499  mov     bl, al
0x14000349b  mov     ecx, cs:__scrt_current_native_startup_state
0x1400034a1  cmp     ecx, 1
0x1400034a4  jz      loc_1400035C6
0x1400034aa  test    ecx, ecx
0x1400034ac  jnz     short loc_1400034F8
0x1400034ae  mov     cs:__scrt_current_native_startup_state, 1
0x1400034b8  lea     rdx, __xi_z; Last
0x1400034bf  lea     rcx, __xi_a; First
0x1400034c6  call    _initterm_e_0
0x1400034cb  test    eax, eax
0x1400034cd  jz      short loc_1400034D9
0x1400034cf  mov     eax, 0FFh
0x1400034d4  jmp     loc_1400035B0
0x1400034d9  lea     rdx, __xc_z; Last
0x1400034e0  lea     rcx, __xc_a; First
0x1400034e7  call    _initterm_0
0x1400034ec  mov     cs:__scrt_current_native_startup_state, 2
0x1400034f6  jmp     short loc_140003500
0x1400034f8  mov     dil, 1
0x1400034fb  mov     [rsp+38h+var_18], dil
0x140003500  mov     cl, bl
0x140003502  call    __scrt_release_startup_lock
0x140003507  call    __scrt_get_dyn_tls_init_callback
0x14000350c  mov     rbx, rax
0x14000350f  cmp     qword ptr [rax], 0
0x140003513  jz      short loc_140003532
0x140003515  mov     rcx, rax
0x140003518  call    __scrt_is_nonwritable_in_current_image
0x14000351d  test    al, al
0x14000351f  jz      short loc_140003532
0x140003521  xor     r8d, r8d
0x140003524  lea     edx, [r8+2]
0x140003528  xor     ecx, ecx
0x14000352a  mov     rax, [rbx]
0x14000352d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003532  call    __scrt_get_dyn_tls_dtor_callback
0x140003537  mov     rbx, rax
0x14000353a  cmp     qword ptr [rax], 0
0x14000353e  jz      short loc_140003554
0x140003540  mov     rcx, rax
0x140003543  call    __scrt_is_nonwritable_in_current_image
0x140003548  test    al, al
0x14000354a  jz      short loc_140003554
0x14000354c  mov     rcx, [rbx]; Callback
0x14000354f  call    _register_thread_local_exe_atexit_callback_0
0x140003554  call    __scrt_get_show_window_mode
0x140003559  movzx   ebx, ax
0x14000355c  call    _o__get_wide_winmain_command_line_0
0x140003561  mov     r9d, ebx; nShowCmd
0x140003564  mov     r8, rax; lpCmdLine
0x140003567  xor     edx, edx; hPrevInstance
0x140003569  lea     rcx, __ImageBase; hInstance
0x140003570  call    wWinMain
0x140003575  mov     ebx, eax
0x140003577  call    __scrt_is_managed_app
0x14000357c  test    al, al
0x14000357e  jz      short loc_1400035D0
0x140003580  test    dil, dil
0x140003583  jnz     short loc_14000358A
0x140003585  call    _o__cexit_0
0x14000358a  xor     edx, edx
0x14000358c  mov     cl, 1
0x14000358e  call    __scrt_uninitialize_crt
0x140003593  mov     eax, ebx
0x140003595  jmp     short loc_1400035B0
0x140003597  mov     ebx, eax
0x140003599  call    __scrt_is_managed_app
0x14000359e  test    al, al
0x1400035a0  jz      short loc_1400035D8
0x1400035a2  cmp     [rsp+38h+var_18], 0
0x1400035a7  jnz     short loc_1400035AE
0x1400035a9  call    _c_exit_0
0x1400035ae  mov     eax, ebx
0x1400035b0  mov     rbx, [rsp+38h+arg_0]
0x1400035b5  add     rsp, 30h
0x1400035b9  pop     rdi
0x1400035ba  retn
0x1400035bb  mov     ecx, 7
0x1400035c0  call    __scrt_fastfail
0x1400035c6  mov     ecx, 7
0x1400035cb  call    __scrt_fastfail
0x1400035d0  mov     ecx, ebx; Code
0x1400035d2  call    _o_exit_0
0x1400035d8  mov     ecx, ebx
0x1400035da  call    _o__exit_0
0x1400035df  nop
0x14001e0ec  push    rbp
0x14001e0ee  sub     rsp, 20h
0x14001e0f2  mov     rbp, rdx
0x14001e0f5  mov     rdx, rcx; ExceptionPtr
0x14001e0f8  mov     rcx, [rcx]
0x14001e0fb  mov     ecx, [rcx]; ExceptionNum
0x14001e0fd  call    _seh_filter_exe
0x14001e102  nop
0x14001e103  add     rsp, 20h
0x14001e107  pop     rbp
0x14001e108  retn
```
