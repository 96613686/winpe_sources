# __scrt_common_main_seh

- ea: `0x140002760`
- end: `0x1400028d0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400028e0`

## callees

- `0x140002760`
- `0x140002934`
- `0x140002974`
- `0x140002a48`
- `0x140002ae8`
- `0x140002b14`
- `0x140002cd4`
- `0x140002ce4`
- `0x140002cf4`
- `0x140002d00`
- `0x140002d4c`
- `0x140003186`
- `0x140003192`
- `0x14000319e`
- `0x1400031aa`
- `0x1400031ce`
- `0x1400031fe`
- `0x14000320a`
- `0x140003258`
- `0x140003288`
- `0x1400074e4`
- `0x140008010`

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
0x140002760  mov     [rsp+arg_0], rbx
0x140002765  push    rdi
0x140002766  sub     rsp, 30h
0x14000276a  mov     ecx, 1
0x14000276f  call    __scrt_initialize_crt
0x140002774  test    al, al
0x140002776  jz      loc_1400028AB
0x14000277c  xor     dil, dil
0x14000277f  mov     [rsp+38h+var_18], dil
0x140002784  call    __scrt_acquire_startup_lock
0x140002789  mov     bl, al
0x14000278b  mov     ecx, cs:__scrt_current_native_startup_state
0x140002791  cmp     ecx, 1
0x140002794  jz      loc_1400028B6
0x14000279a  test    ecx, ecx
0x14000279c  jnz     short loc_1400027E8
0x14000279e  mov     cs:__scrt_current_native_startup_state, 1
0x1400027a8  lea     rdx, __xi_z; Last
0x1400027af  lea     rcx, __xi_a; First
0x1400027b6  call    _initterm_e_0
0x1400027bb  test    eax, eax
0x1400027bd  jz      short loc_1400027C9
0x1400027bf  mov     eax, 0FFh
0x1400027c4  jmp     loc_1400028A0
0x1400027c9  lea     rdx, __xc_z; Last
0x1400027d0  lea     rcx, __xc_a; First
0x1400027d7  call    _initterm_0
0x1400027dc  mov     cs:__scrt_current_native_startup_state, 2
0x1400027e6  jmp     short loc_1400027F0
0x1400027e8  mov     dil, 1
0x1400027eb  mov     [rsp+38h+var_18], dil
0x1400027f0  mov     cl, bl
0x1400027f2  call    __scrt_release_startup_lock
0x1400027f7  call    __scrt_get_dyn_tls_init_callback
0x1400027fc  mov     rbx, rax
0x1400027ff  cmp     qword ptr [rax], 0
0x140002803  jz      short loc_140002822
0x140002805  mov     rcx, rax
0x140002808  call    __scrt_is_nonwritable_in_current_image
0x14000280d  test    al, al
0x14000280f  jz      short loc_140002822
0x140002811  xor     r8d, r8d
0x140002814  lea     edx, [r8+2]
0x140002818  xor     ecx, ecx
0x14000281a  mov     rax, [rbx]
0x14000281d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002822  call    __scrt_get_dyn_tls_dtor_callback
0x140002827  mov     rbx, rax
0x14000282a  cmp     qword ptr [rax], 0
0x14000282e  jz      short loc_140002844
0x140002830  mov     rcx, rax
0x140002833  call    __scrt_is_nonwritable_in_current_image
0x140002838  test    al, al
0x14000283a  jz      short loc_140002844
0x14000283c  mov     rcx, [rbx]; Callback
0x14000283f  call    _register_thread_local_exe_atexit_callback_0
0x140002844  call    __scrt_get_show_window_mode
0x140002849  movzx   ebx, ax
0x14000284c  call    _o__get_wide_winmain_command_line_0
0x140002851  mov     r9d, ebx; nShowCmd
0x140002854  mov     r8, rax; lpCmdLine
0x140002857  xor     edx, edx; hPrevInstance
0x140002859  lea     rcx, __ImageBase; hInstance
0x140002860  call    wWinMain
0x140002865  mov     ebx, eax
0x140002867  call    __scrt_is_managed_app
0x14000286c  test    al, al
0x14000286e  jz      short loc_1400028C0
0x140002870  test    dil, dil
0x140002873  jnz     short loc_14000287A
0x140002875  call    _o__cexit_0
0x14000287a  xor     edx, edx
0x14000287c  mov     cl, 1
0x14000287e  call    __scrt_uninitialize_crt
0x140002883  mov     eax, ebx
0x140002885  jmp     short loc_1400028A0
0x140002887  mov     ebx, eax
0x140002889  call    __scrt_is_managed_app
0x14000288e  test    al, al
0x140002890  jz      short loc_1400028C8
0x140002892  cmp     [rsp+38h+var_18], 0
0x140002897  jnz     short loc_14000289E
0x140002899  call    _c_exit_0
0x14000289e  mov     eax, ebx
0x1400028a0  mov     rbx, [rsp+38h+arg_0]
0x1400028a5  add     rsp, 30h
0x1400028a9  pop     rdi
0x1400028aa  retn
0x1400028ab  mov     ecx, 7
0x1400028b0  call    __scrt_fastfail
0x1400028b6  mov     ecx, 7
0x1400028bb  call    __scrt_fastfail
0x1400028c0  mov     ecx, ebx; Code
0x1400028c2  call    _o_exit_0
0x1400028c8  mov     ecx, ebx
0x1400028ca  call    _o__exit_0
0x1400028cf  nop
0x1400079bc  push    rbp
0x1400079be  sub     rsp, 20h
0x1400079c2  mov     rbp, rdx
0x1400079c5  mov     rdx, rcx; ExceptionPtr
0x1400079c8  mov     rcx, [rcx]
0x1400079cb  mov     ecx, [rcx]; ExceptionNum
0x1400079cd  call    _seh_filter_exe
0x1400079d2  nop
0x1400079d3  add     rsp, 20h
0x1400079d7  pop     rbp
0x1400079d8  retn
```
