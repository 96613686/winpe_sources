# __scrt_common_main_seh

- ea: `0x140003000`
- end: `0x140003170`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140003180`

## callees

- `0x140001d60`
- `0x140003000`
- `0x1400031d4`
- `0x140003214`
- `0x1400032e8`
- `0x140003388`
- `0x1400033b4`
- `0x1400035d0`
- `0x1400035e0`
- `0x1400035f0`
- `0x1400035fc`
- `0x140003648`
- `0x140003c46`
- `0x140003c52`
- `0x140003c5e`
- `0x140003c6a`
- `0x140003cca`
- `0x140003cfa`
- `0x140003d06`
- `0x140003d58`
- `0x140003d88`
- `0x14000b010`

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
  v15 = wWinMain(&_ImageBase, 0, wide_winmain_command_line_0, show_window_mode);
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
0x140003000  mov     [rsp+arg_0], rbx
0x140003005  push    rdi
0x140003006  sub     rsp, 30h
0x14000300a  mov     ecx, 1
0x14000300f  call    __scrt_initialize_crt
0x140003014  test    al, al
0x140003016  jz      loc_14000314B
0x14000301c  xor     dil, dil
0x14000301f  mov     [rsp+38h+var_18], dil
0x140003024  call    __scrt_acquire_startup_lock
0x140003029  mov     bl, al
0x14000302b  mov     ecx, cs:__scrt_current_native_startup_state
0x140003031  cmp     ecx, 1
0x140003034  jz      loc_140003156
0x14000303a  test    ecx, ecx
0x14000303c  jnz     short loc_140003088
0x14000303e  mov     cs:__scrt_current_native_startup_state, 1
0x140003048  lea     rdx, __xi_z; Last
0x14000304f  lea     rcx, __xi_a; First
0x140003056  call    _initterm_e_0
0x14000305b  test    eax, eax
0x14000305d  jz      short loc_140003069
0x14000305f  mov     eax, 0FFh
0x140003064  jmp     loc_140003140
0x140003069  lea     rdx, __xc_z; Last
0x140003070  lea     rcx, __xc_a; First
0x140003077  call    _initterm_0
0x14000307c  mov     cs:__scrt_current_native_startup_state, 2
0x140003086  jmp     short loc_140003090
0x140003088  mov     dil, 1
0x14000308b  mov     [rsp+38h+var_18], dil
0x140003090  mov     cl, bl
0x140003092  call    __scrt_release_startup_lock
0x140003097  call    __scrt_get_dyn_tls_init_callback
0x14000309c  mov     rbx, rax
0x14000309f  cmp     qword ptr [rax], 0
0x1400030a3  jz      short loc_1400030C2
0x1400030a5  mov     rcx, rax
0x1400030a8  call    __scrt_is_nonwritable_in_current_image
0x1400030ad  test    al, al
0x1400030af  jz      short loc_1400030C2
0x1400030b1  xor     r8d, r8d
0x1400030b4  lea     edx, [r8+2]
0x1400030b8  xor     ecx, ecx
0x1400030ba  mov     rax, [rbx]
0x1400030bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030c2  call    __scrt_get_dyn_tls_dtor_callback
0x1400030c7  mov     rbx, rax
0x1400030ca  cmp     qword ptr [rax], 0
0x1400030ce  jz      short loc_1400030E4
0x1400030d0  mov     rcx, rax
0x1400030d3  call    __scrt_is_nonwritable_in_current_image
0x1400030d8  test    al, al
0x1400030da  jz      short loc_1400030E4
0x1400030dc  mov     rcx, [rbx]; Callback
0x1400030df  call    _register_thread_local_exe_atexit_callback_0
0x1400030e4  call    __scrt_get_show_window_mode
0x1400030e9  movzx   ebx, ax
0x1400030ec  call    _o__get_wide_winmain_command_line_0
0x1400030f1  mov     r9d, ebx; nShowCmd
0x1400030f4  mov     r8, rax; lpCmdLine
0x1400030f7  xor     edx, edx; hPrevInstance
0x1400030f9  lea     rcx, __ImageBase; hInstance
0x140003100  call    wWinMain
0x140003105  mov     ebx, eax
0x140003107  call    __scrt_is_managed_app
0x14000310c  test    al, al
0x14000310e  jz      short loc_140003160
0x140003110  test    dil, dil
0x140003113  jnz     short loc_14000311A
0x140003115  call    _o__cexit_0
0x14000311a  xor     edx, edx
0x14000311c  mov     cl, 1
0x14000311e  call    __scrt_uninitialize_crt
0x140003123  mov     eax, ebx
0x140003125  jmp     short loc_140003140
0x140003127  mov     ebx, eax
0x140003129  call    __scrt_is_managed_app
0x14000312e  test    al, al
0x140003130  jz      short loc_140003168
0x140003132  cmp     [rsp+38h+var_18], 0
0x140003137  jnz     short loc_14000313E
0x140003139  call    _c_exit_0
0x14000313e  mov     eax, ebx
0x140003140  mov     rbx, [rsp+38h+arg_0]
0x140003145  add     rsp, 30h
0x140003149  pop     rdi
0x14000314a  retn
0x14000314b  mov     ecx, 7
0x140003150  call    __scrt_fastfail
0x140003156  mov     ecx, 7
0x14000315b  call    __scrt_fastfail
0x140003160  mov     ecx, ebx; Code
0x140003162  call    _o_exit_0
0x140003168  mov     ecx, ebx
0x14000316a  call    _o__exit_0
0x14000316f  nop
0x14000a4b2  push    rbp
0x14000a4b4  sub     rsp, 20h
0x14000a4b8  mov     rbp, rdx
0x14000a4bb  mov     rdx, rcx; ExceptionPtr
0x14000a4be  mov     rcx, [rcx]
0x14000a4c1  mov     ecx, [rcx]; ExceptionNum
0x14000a4c3  call    _seh_filter_exe
0x14000a4c8  nop
0x14000a4c9  add     rsp, 20h
0x14000a4cd  pop     rbp
0x14000a4ce  retn
```
