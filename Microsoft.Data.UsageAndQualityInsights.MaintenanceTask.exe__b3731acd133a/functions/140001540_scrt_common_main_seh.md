# __scrt_common_main_seh

- ea: `0x140001540`
- end: `0x1400016b0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400016c0`

## callees

- `0x140001540`
- `0x140001714`
- `0x140001754`
- `0x140001828`
- `0x1400018c8`
- `0x1400018f4`
- `0x140001e4c`
- `0x140001e5c`
- `0x140001e6c`
- `0x140001e78`
- `0x140001ec4`
- `0x140002086`
- `0x140002092`
- `0x14000209e`
- `0x1400020aa`
- `0x14000210a`
- `0x14000213a`
- `0x140002146`
- `0x140002198`
- `0x1400021c8`
- `0x14000b410`
- `0x14000c010`

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
  CHAR *narrow_winmain_command_line_0; // rax
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
  narrow_winmain_command_line_0 = (CHAR *)o__get_narrow_winmain_command_line_0(v13);
  v15 = WinMain((HINSTANCE)0x140000000LL, 0, narrow_winmain_command_line_0, show_window_mode);
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
0x140001540  mov     [rsp+arg_0], rbx
0x140001545  push    rdi
0x140001546  sub     rsp, 30h
0x14000154a  mov     ecx, 1
0x14000154f  call    __scrt_initialize_crt
0x140001554  test    al, al
0x140001556  jz      loc_14000168B
0x14000155c  xor     dil, dil
0x14000155f  mov     [rsp+38h+var_18], dil
0x140001564  call    __scrt_acquire_startup_lock
0x140001569  mov     bl, al
0x14000156b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001571  cmp     ecx, 1
0x140001574  jz      loc_140001696
0x14000157a  test    ecx, ecx
0x14000157c  jnz     short loc_1400015C8
0x14000157e  mov     cs:__scrt_current_native_startup_state, 1
0x140001588  lea     rdx, __xi_z; Last
0x14000158f  lea     rcx, __xi_a; First
0x140001596  call    _initterm_e_0
0x14000159b  test    eax, eax
0x14000159d  jz      short loc_1400015A9
0x14000159f  mov     eax, 0FFh
0x1400015a4  jmp     loc_140001680
0x1400015a9  lea     rdx, __xc_z; Last
0x1400015b0  lea     rcx, __xc_a; First
0x1400015b7  call    _initterm_0
0x1400015bc  mov     cs:__scrt_current_native_startup_state, 2
0x1400015c6  jmp     short loc_1400015D0
0x1400015c8  mov     dil, 1
0x1400015cb  mov     [rsp+38h+var_18], dil
0x1400015d0  mov     cl, bl
0x1400015d2  call    __scrt_release_startup_lock
0x1400015d7  call    __scrt_get_dyn_tls_init_callback
0x1400015dc  mov     rbx, rax
0x1400015df  cmp     qword ptr [rax], 0
0x1400015e3  jz      short loc_140001602
0x1400015e5  mov     rcx, rax
0x1400015e8  call    __scrt_is_nonwritable_in_current_image
0x1400015ed  test    al, al
0x1400015ef  jz      short loc_140001602
0x1400015f1  xor     r8d, r8d
0x1400015f4  lea     edx, [r8+2]
0x1400015f8  xor     ecx, ecx
0x1400015fa  mov     rax, [rbx]
0x1400015fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001602  call    __scrt_get_dyn_tls_dtor_callback
0x140001607  mov     rbx, rax
0x14000160a  cmp     qword ptr [rax], 0
0x14000160e  jz      short loc_140001624
0x140001610  mov     rcx, rax
0x140001613  call    __scrt_is_nonwritable_in_current_image
0x140001618  test    al, al
0x14000161a  jz      short loc_140001624
0x14000161c  mov     rcx, [rbx]; Callback
0x14000161f  call    _register_thread_local_exe_atexit_callback_0
0x140001624  call    __scrt_get_show_window_mode
0x140001629  movzx   ebx, ax
0x14000162c  call    _o__get_narrow_winmain_command_line_0
0x140001631  mov     r9d, ebx; nShowCmd
0x140001634  mov     r8, rax; lpCmdLine
0x140001637  xor     edx, edx; hPrevInstance
0x140001639  lea     rcx, cs:140000000h; hInstance
0x140001640  call    WinMain
0x140001645  mov     ebx, eax
0x140001647  call    __scrt_is_managed_app
0x14000164c  test    al, al
0x14000164e  jz      short loc_1400016A0
0x140001650  test    dil, dil
0x140001653  jnz     short loc_14000165A
0x140001655  call    _o__cexit_0
0x14000165a  xor     edx, edx
0x14000165c  mov     cl, 1
0x14000165e  call    __scrt_uninitialize_crt
0x140001663  mov     eax, ebx
0x140001665  jmp     short loc_140001680
0x140001667  mov     ebx, eax
0x140001669  call    __scrt_is_managed_app
0x14000166e  test    al, al
0x140001670  jz      short loc_1400016A8
0x140001672  cmp     [rsp+38h+var_18], 0
0x140001677  jnz     short loc_14000167E
0x140001679  call    _c_exit_0
0x14000167e  mov     eax, ebx
0x140001680  mov     rbx, [rsp+38h+arg_0]
0x140001685  add     rsp, 30h
0x140001689  pop     rdi
0x14000168a  retn
0x14000168b  mov     ecx, 7
0x140001690  call    __scrt_fastfail
0x140001696  mov     ecx, 7
0x14000169b  call    __scrt_fastfail
0x1400016a0  mov     ecx, ebx; Code
0x1400016a2  call    _o_exit_0
0x1400016a8  mov     ecx, ebx
0x1400016aa  call    _o__exit_0
0x1400016af  nop
0x14000b8fc  push    rbp
0x14000b8fe  sub     rsp, 20h
0x14000b902  mov     rbp, rdx
0x14000b905  mov     rdx, rcx; ExceptionPtr
0x14000b908  mov     rcx, [rcx]
0x14000b90b  mov     ecx, [rcx]; ExceptionNum
0x14000b90d  call    _seh_filter_exe
0x14000b912  nop
0x14000b913  add     rsp, 20h
0x14000b917  pop     rbp
0x14000b918  retn
```
