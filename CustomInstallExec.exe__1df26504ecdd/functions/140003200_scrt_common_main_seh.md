# __scrt_common_main_seh

- ea: `0x140003200`
- end: `0x140003370`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140003380`

## callees

- `0x140003200`
- `0x1400033d4`
- `0x140003414`
- `0x1400034e8`
- `0x140003588`
- `0x1400035b4`
- `0x140003b54`
- `0x140003b64`
- `0x140003b74`
- `0x140003b80`
- `0x140003bcc`
- `0x140003df6`
- `0x140003e02`
- `0x140003e0e`
- `0x140003e1a`
- `0x140003e7a`
- `0x140003eaa`
- `0x140003eb6`
- `0x140003f08`
- `0x140003f38`
- `0x14000d884`
- `0x14000f010`

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
0x140003200  mov     [rsp+arg_0], rbx
0x140003205  push    rdi
0x140003206  sub     rsp, 30h
0x14000320a  mov     ecx, 1
0x14000320f  call    __scrt_initialize_crt
0x140003214  test    al, al
0x140003216  jz      loc_14000334B
0x14000321c  xor     dil, dil
0x14000321f  mov     [rsp+38h+var_18], dil
0x140003224  call    __scrt_acquire_startup_lock
0x140003229  mov     bl, al
0x14000322b  mov     ecx, cs:__scrt_current_native_startup_state
0x140003231  cmp     ecx, 1
0x140003234  jz      loc_140003356
0x14000323a  test    ecx, ecx
0x14000323c  jnz     short loc_140003288
0x14000323e  mov     cs:__scrt_current_native_startup_state, 1
0x140003248  lea     rdx, __xi_z; Last
0x14000324f  lea     rcx, __xi_a; First
0x140003256  call    _initterm_e_0
0x14000325b  test    eax, eax
0x14000325d  jz      short loc_140003269
0x14000325f  mov     eax, 0FFh
0x140003264  jmp     loc_140003340
0x140003269  lea     rdx, __xc_z; Last
0x140003270  lea     rcx, __xc_a; First
0x140003277  call    _initterm_0
0x14000327c  mov     cs:__scrt_current_native_startup_state, 2
0x140003286  jmp     short loc_140003290
0x140003288  mov     dil, 1
0x14000328b  mov     [rsp+38h+var_18], dil
0x140003290  mov     cl, bl
0x140003292  call    __scrt_release_startup_lock
0x140003297  call    __scrt_get_dyn_tls_init_callback
0x14000329c  mov     rbx, rax
0x14000329f  cmp     qword ptr [rax], 0
0x1400032a3  jz      short loc_1400032C2
0x1400032a5  mov     rcx, rax
0x1400032a8  call    __scrt_is_nonwritable_in_current_image
0x1400032ad  test    al, al
0x1400032af  jz      short loc_1400032C2
0x1400032b1  xor     r8d, r8d
0x1400032b4  lea     edx, [r8+2]
0x1400032b8  xor     ecx, ecx
0x1400032ba  mov     rax, [rbx]
0x1400032bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032c2  call    __scrt_get_dyn_tls_dtor_callback
0x1400032c7  mov     rbx, rax
0x1400032ca  cmp     qword ptr [rax], 0
0x1400032ce  jz      short loc_1400032E4
0x1400032d0  mov     rcx, rax
0x1400032d3  call    __scrt_is_nonwritable_in_current_image
0x1400032d8  test    al, al
0x1400032da  jz      short loc_1400032E4
0x1400032dc  mov     rcx, [rbx]; Callback
0x1400032df  call    _register_thread_local_exe_atexit_callback_0
0x1400032e4  call    __scrt_get_show_window_mode
0x1400032e9  movzx   ebx, ax
0x1400032ec  call    _o__get_wide_winmain_command_line_0
0x1400032f1  mov     r9d, ebx; nShowCmd
0x1400032f4  mov     r8, rax; lpCmdLine
0x1400032f7  xor     edx, edx; hPrevInstance
0x1400032f9  lea     rcx, __ImageBase; hInstance
0x140003300  call    wWinMain
0x140003305  mov     ebx, eax
0x140003307  call    __scrt_is_managed_app
0x14000330c  test    al, al
0x14000330e  jz      short loc_140003360
0x140003310  test    dil, dil
0x140003313  jnz     short loc_14000331A
0x140003315  call    _o__cexit_0
0x14000331a  xor     edx, edx
0x14000331c  mov     cl, 1
0x14000331e  call    __scrt_uninitialize_crt
0x140003323  mov     eax, ebx
0x140003325  jmp     short loc_140003340
0x140003327  mov     ebx, eax
0x140003329  call    __scrt_is_managed_app
0x14000332e  test    al, al
0x140003330  jz      short loc_140003368
0x140003332  cmp     [rsp+38h+var_18], 0
0x140003337  jnz     short loc_14000333E
0x140003339  call    _c_exit_0
0x14000333e  mov     eax, ebx
0x140003340  mov     rbx, [rsp+38h+arg_0]
0x140003345  add     rsp, 30h
0x140003349  pop     rdi
0x14000334a  retn
0x14000334b  mov     ecx, 7
0x140003350  call    __scrt_fastfail
0x140003356  mov     ecx, 7
0x14000335b  call    __scrt_fastfail
0x140003360  mov     ecx, ebx; Code
0x140003362  call    _o_exit_0
0x140003368  mov     ecx, ebx
0x14000336a  call    _o__exit_0
0x14000336f  nop
0x14000eb6c  push    rbp
0x14000eb6e  sub     rsp, 20h
0x14000eb72  mov     rbp, rdx
0x14000eb75  mov     rdx, rcx; ExceptionPtr
0x14000eb78  mov     rcx, [rcx]
0x14000eb7b  mov     ecx, [rcx]; ExceptionNum
0x14000eb7d  call    _seh_filter_exe
0x14000eb82  nop
0x14000eb83  add     rsp, 20h
0x14000eb87  pop     rbp
0x14000eb88  retn
```
