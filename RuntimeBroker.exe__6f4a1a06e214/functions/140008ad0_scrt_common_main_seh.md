# __scrt_common_main_seh

- ea: `0x140008ad0`
- end: `0x140008c40`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140008c50`

## callees

- `0x140005770`
- `0x140008ad0`
- `0x140008cc8`
- `0x140008d08`
- `0x140008ddc`
- `0x140008e7c`
- `0x140008ea8`
- `0x140009050`
- `0x140009060`
- `0x140009070`
- `0x14000907c`
- `0x1400090c8`
- `0x1400094f6`
- `0x140009502`
- `0x14000950e`
- `0x14000951a`
- `0x14000953e`
- `0x14000956e`
- `0x14000957a`
- `0x1400095c8`
- `0x1400095f8`
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
0x140008ad0  mov     [rsp+arg_0], rbx
0x140008ad5  push    rdi
0x140008ad6  sub     rsp, 30h
0x140008ada  mov     ecx, 1
0x140008adf  call    __scrt_initialize_crt
0x140008ae4  test    al, al
0x140008ae6  jz      loc_140008C1B
0x140008aec  xor     dil, dil
0x140008aef  mov     [rsp+38h+var_18], dil
0x140008af4  call    __scrt_acquire_startup_lock
0x140008af9  mov     bl, al
0x140008afb  mov     ecx, cs:__scrt_current_native_startup_state
0x140008b01  cmp     ecx, 1
0x140008b04  jz      loc_140008C26
0x140008b0a  test    ecx, ecx
0x140008b0c  jnz     short loc_140008B58
0x140008b0e  mov     cs:__scrt_current_native_startup_state, 1
0x140008b18  lea     rdx, __xi_z; Last
0x140008b1f  lea     rcx, __xi_a; First
0x140008b26  call    _initterm_e_0
0x140008b2b  test    eax, eax
0x140008b2d  jz      short loc_140008B39
0x140008b2f  mov     eax, 0FFh
0x140008b34  jmp     loc_140008C10
0x140008b39  lea     rdx, __xc_z; Last
0x140008b40  lea     rcx, __xc_a; First
0x140008b47  call    _initterm_0
0x140008b4c  mov     cs:__scrt_current_native_startup_state, 2
0x140008b56  jmp     short loc_140008B60
0x140008b58  mov     dil, 1
0x140008b5b  mov     [rsp+38h+var_18], dil
0x140008b60  mov     cl, bl
0x140008b62  call    __scrt_release_startup_lock
0x140008b67  call    __scrt_get_dyn_tls_init_callback
0x140008b6c  mov     rbx, rax
0x140008b6f  cmp     qword ptr [rax], 0
0x140008b73  jz      short loc_140008B92
0x140008b75  mov     rcx, rax
0x140008b78  call    __scrt_is_nonwritable_in_current_image
0x140008b7d  test    al, al
0x140008b7f  jz      short loc_140008B92
0x140008b81  xor     r8d, r8d
0x140008b84  lea     edx, [r8+2]
0x140008b88  xor     ecx, ecx
0x140008b8a  mov     rax, [rbx]
0x140008b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b92  call    __scrt_get_dyn_tls_dtor_callback
0x140008b97  mov     rbx, rax
0x140008b9a  cmp     qword ptr [rax], 0
0x140008b9e  jz      short loc_140008BB4
0x140008ba0  mov     rcx, rax
0x140008ba3  call    __scrt_is_nonwritable_in_current_image
0x140008ba8  test    al, al
0x140008baa  jz      short loc_140008BB4
0x140008bac  mov     rcx, [rbx]; Callback
0x140008baf  call    _register_thread_local_exe_atexit_callback_0
0x140008bb4  call    __scrt_get_show_window_mode
0x140008bb9  movzx   ebx, ax
0x140008bbc  call    _o__get_wide_winmain_command_line_0
0x140008bc1  mov     r9d, ebx; nShowCmd
0x140008bc4  mov     r8, rax; lpCmdLine
0x140008bc7  xor     edx, edx; hPrevInstance
0x140008bc9  lea     rcx, __ImageBase; hInstance
0x140008bd0  call    wWinMain
0x140008bd5  mov     ebx, eax
0x140008bd7  call    __scrt_is_managed_app
0x140008bdc  test    al, al
0x140008bde  jz      short loc_140008C30
0x140008be0  test    dil, dil
0x140008be3  jnz     short loc_140008BEA
0x140008be5  call    _o__cexit_0
0x140008bea  xor     edx, edx
0x140008bec  mov     cl, 1
0x140008bee  call    __scrt_uninitialize_crt
0x140008bf3  mov     eax, ebx
0x140008bf5  jmp     short loc_140008C10
0x140008bf7  mov     ebx, eax
0x140008bf9  call    __scrt_is_managed_app
0x140008bfe  test    al, al
0x140008c00  jz      short loc_140008C38
0x140008c02  cmp     [rsp+38h+var_18], 0
0x140008c07  jnz     short loc_140008C0E
0x140008c09  call    _c_exit_0
0x140008c0e  mov     eax, ebx
0x140008c10  mov     rbx, [rsp+38h+arg_0]
0x140008c15  add     rsp, 30h
0x140008c19  pop     rdi
0x140008c1a  retn
0x140008c1b  mov     ecx, 7
0x140008c20  call    __scrt_fastfail
0x140008c26  mov     ecx, 7
0x140008c2b  call    __scrt_fastfail
0x140008c30  mov     ecx, ebx; Code
0x140008c32  call    _o_exit_0
0x140008c38  mov     ecx, ebx
0x140008c3a  call    _o__exit_0
0x140008c3f  nop
0x14000f34c  push    rbp
0x14000f34e  sub     rsp, 20h
0x14000f352  mov     rbp, rdx
0x14000f355  mov     rdx, rcx; ExceptionPtr
0x14000f358  mov     rcx, [rcx]
0x14000f35b  mov     ecx, [rcx]; ExceptionNum
0x14000f35d  call    _seh_filter_exe
0x14000f362  nop
0x14000f363  add     rsp, 20h
0x14000f367  pop     rbp
0x14000f368  retn
```
