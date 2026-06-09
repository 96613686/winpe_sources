# __scrt_common_main_seh

- ea: `0x140001b20`
- end: `0x140001c90`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001ca0`

## callees

- `0x140001b20`
- `0x140001cf4`
- `0x140001d34`
- `0x140001e08`
- `0x140001ea8`
- `0x140001ed4`
- `0x140002088`
- `0x140002098`
- `0x1400020a8`
- `0x1400020b4`
- `0x140002100`
- `0x140002526`
- `0x140002532`
- `0x14000253e`
- `0x14000254a`
- `0x140002586`
- `0x1400025b6`
- `0x1400025c2`
- `0x140002618`
- `0x140002648`
- `0x140006694`
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
  v14 = wWinMain((HINSTANCE)0x140000000LL, 0, wide_winmain_command_line_0, show_window_mode);
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
0x140001b20  mov     [rsp+arg_0], rbx
0x140001b25  push    rdi
0x140001b26  sub     rsp, 30h
0x140001b2a  mov     ecx, 1
0x140001b2f  call    __scrt_initialize_crt
0x140001b34  test    al, al
0x140001b36  jz      loc_140001C6B
0x140001b3c  xor     dil, dil
0x140001b3f  mov     [rsp+38h+var_18], dil
0x140001b44  call    __scrt_acquire_startup_lock
0x140001b49  mov     bl, al
0x140001b4b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001b51  cmp     ecx, 1
0x140001b54  jz      loc_140001C76
0x140001b5a  test    ecx, ecx
0x140001b5c  jnz     short loc_140001BA8
0x140001b5e  mov     cs:__scrt_current_native_startup_state, 1
0x140001b68  lea     rdx, __xi_z; Last
0x140001b6f  lea     rcx, __xi_a; First
0x140001b76  call    _initterm_e_0
0x140001b7b  test    eax, eax
0x140001b7d  jz      short loc_140001B89
0x140001b7f  mov     eax, 0FFh
0x140001b84  jmp     loc_140001C60
0x140001b89  lea     rdx, __xc_z; Last
0x140001b90  lea     rcx, __xc_a; First
0x140001b97  call    _initterm_0
0x140001b9c  mov     cs:__scrt_current_native_startup_state, 2
0x140001ba6  jmp     short loc_140001BB0
0x140001ba8  mov     dil, 1
0x140001bab  mov     [rsp+38h+var_18], dil
0x140001bb0  mov     cl, bl
0x140001bb2  call    __scrt_release_startup_lock
0x140001bb7  call    __scrt_get_dyn_tls_init_callback
0x140001bbc  mov     rbx, rax
0x140001bbf  cmp     qword ptr [rax], 0
0x140001bc3  jz      short loc_140001BE2
0x140001bc5  mov     rcx, rax
0x140001bc8  call    __scrt_is_nonwritable_in_current_image
0x140001bcd  test    al, al
0x140001bcf  jz      short loc_140001BE2
0x140001bd1  xor     r8d, r8d
0x140001bd4  lea     edx, [r8+2]
0x140001bd8  xor     ecx, ecx
0x140001bda  mov     rax, [rbx]
0x140001bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001be2  call    __scrt_get_dyn_tls_dtor_callback
0x140001be7  mov     rbx, rax
0x140001bea  cmp     qword ptr [rax], 0
0x140001bee  jz      short loc_140001C04
0x140001bf0  mov     rcx, rax
0x140001bf3  call    __scrt_is_nonwritable_in_current_image
0x140001bf8  test    al, al
0x140001bfa  jz      short loc_140001C04
0x140001bfc  mov     rcx, [rbx]; Callback
0x140001bff  call    _register_thread_local_exe_atexit_callback_0
0x140001c04  call    __scrt_get_show_window_mode
0x140001c09  movzx   ebx, ax
0x140001c0c  call    _o__get_wide_winmain_command_line_0
0x140001c11  mov     r9d, ebx; nShowCmd
0x140001c14  mov     r8, rax; lpCmdLine
0x140001c17  xor     edx, edx; hPrevInstance
0x140001c19  lea     rcx, cs:140000000h; hInstance
0x140001c20  call    wWinMain
0x140001c25  mov     ebx, eax
0x140001c27  call    __scrt_is_managed_app
0x140001c2c  test    al, al
0x140001c2e  jz      short loc_140001C80
0x140001c30  test    dil, dil
0x140001c33  jnz     short loc_140001C3A
0x140001c35  call    _o__cexit_0
0x140001c3a  xor     edx, edx
0x140001c3c  mov     cl, 1
0x140001c3e  call    __scrt_uninitialize_crt
0x140001c43  mov     eax, ebx
0x140001c45  jmp     short loc_140001C60
0x140001c47  mov     ebx, eax
0x140001c49  call    __scrt_is_managed_app
0x140001c4e  test    al, al
0x140001c50  jz      short loc_140001C88
0x140001c52  cmp     [rsp+38h+var_18], 0
0x140001c57  jnz     short loc_140001C5E
0x140001c59  call    _c_exit_0
0x140001c5e  mov     eax, ebx
0x140001c60  mov     rbx, [rsp+38h+arg_0]
0x140001c65  add     rsp, 30h
0x140001c69  pop     rdi
0x140001c6a  retn
0x140001c6b  mov     ecx, 7
0x140001c70  call    __scrt_fastfail
0x140001c76  mov     ecx, 7
0x140001c7b  call    __scrt_fastfail
0x140001c80  mov     ecx, ebx; Code
0x140001c82  call    _o_exit_0
0x140001c88  mov     ecx, ebx
0x140001c8a  call    _o__exit_0
0x140001c8f  nop
0x1400077dc  push    rbp
0x1400077de  sub     rsp, 20h
0x1400077e2  mov     rbp, rdx
0x1400077e5  mov     rdx, rcx; ExceptionPtr
0x1400077e8  mov     rcx, [rcx]
0x1400077eb  mov     ecx, [rcx]; ExceptionNum
0x1400077ed  call    _seh_filter_exe
0x1400077f2  nop
0x1400077f3  add     rsp, 20h
0x1400077f7  pop     rbp
0x1400077f8  retn
```
