# __scrt_common_main_seh(void)

- ea: `0x1400018dc`
- end: `0x140001a51`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `373`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001a60`

## callees

- `0x140001020`
- `0x1400011a0`
- `0x1400018dc`
- `0x140001a80`
- `0x140001abc`
- `0x140001b84`
- `0x140001c1c`
- `0x140001c40`
- `0x14000218c`
- `0x140002194`
- `0x1400021a8`
- `0x1400022f4`
- `0x140002338`
- `0x140002787`
- `0x1400027a5`
- `0x1400027ab`
- `0x1400027b1`
- `0x1400027b7`
- `0x1400027bd`
- `0x1400027c9`
- `0x1400027cf`
- `0x1400027d5`

## pseudocode

```c
__int64 __fastcall __scrt_common_main_seh()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  char v2; // di
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  __int64 v10; // rcx
  _tls_callback_type *v11; // rbx
  int show_window_mode; // ebx
  char *narrow_winmain_command_line_0; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    _scrt_fastfail(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
  {
LABEL_19:
    _scrt_fastfail(7);
    goto LABEL_20;
  }
  if ( _scrt_current_native_startup_state )
  {
    v2 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xc_z, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&Last);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v0;
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
  narrow_winmain_command_line_0 = get_narrow_winmain_command_line_0();
  v0 = WinMain(&_NULL_IMPORT_DESCRIPTOR, 0, narrow_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    exit_0(v0);
  if ( !v2 )
    cexit_0();
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x1400018dc  mov     [rsp+arg_0], rbx
0x1400018e1  push    rdi
0x1400018e2  sub     rsp, 30h
0x1400018e6  mov     ecx, 1
0x1400018eb  call    __scrt_initialize_crt
0x1400018f0  test    al, al
0x1400018f2  jz      loc_140001A28
0x1400018f8  xor     dil, dil
0x1400018fb  mov     [rsp+38h+var_18], dil
0x140001900  call    __scrt_acquire_startup_lock
0x140001905  mov     bl, al
0x140001907  mov     ecx, cs:__scrt_current_native_startup_state
0x14000190d  cmp     ecx, 1
0x140001910  jz      loc_140001A37
0x140001916  test    ecx, ecx
0x140001918  jnz     short loc_140001964
0x14000191a  mov     cs:__scrt_current_native_startup_state, 1
0x140001924  lea     rdx, __xi_z; Last
0x14000192b  lea     rcx, __xc_z; First
0x140001932  call    _initterm_e_0
0x140001937  test    eax, eax
0x140001939  jz      short loc_140001945
0x14000193b  mov     eax, 0FFh
0x140001940  jmp     loc_140001A1D
0x140001945  lea     rdx, Last; Last
0x14000194c  lea     rcx, __xc_a; First
0x140001953  call    _initterm_0
0x140001958  mov     cs:__scrt_current_native_startup_state, 2
0x140001962  jmp     short loc_14000196C
0x140001964  mov     dil, 1
0x140001967  mov     [rsp+38h+var_18], dil
0x14000196c  mov     cl, bl
0x14000196e  call    __scrt_release_startup_lock
0x140001973  call    __scrt_get_dyn_tls_init_callback
0x140001978  mov     rbx, rax
0x14000197b  cmp     qword ptr [rax], 0
0x14000197f  jz      short loc_14000199F
0x140001981  mov     rcx, rax
0x140001984  call    __scrt_is_nonwritable_in_current_image
0x140001989  test    al, al
0x14000198b  jz      short loc_14000199F
0x14000198d  xor     r8d, r8d
0x140001990  lea     edx, [r8+2]
0x140001994  xor     ecx, ecx
0x140001996  mov     rax, [rbx]
0x140001999  call    cs:__guard_dispatch_icall_fptr
0x14000199f  call    __scrt_get_dyn_tls_dtor_callback
0x1400019a4  mov     rbx, rax
0x1400019a7  cmp     qword ptr [rax], 0
0x1400019ab  jz      short loc_1400019C1
0x1400019ad  mov     rcx, rax
0x1400019b0  call    __scrt_is_nonwritable_in_current_image
0x1400019b5  test    al, al
0x1400019b7  jz      short loc_1400019C1
0x1400019b9  mov     rcx, [rbx]; Callback
0x1400019bc  call    _register_thread_local_exe_atexit_callback_0
0x1400019c1  call    __scrt_get_show_window_mode
0x1400019c6  movzx   ebx, ax
0x1400019c9  call    _get_narrow_winmain_command_line_0
0x1400019ce  mov     r9d, ebx; nShowCmd
0x1400019d1  mov     r8, rax; lpCmdLine
0x1400019d4  xor     edx, edx; hPrevInstance
0x1400019d6  lea     rcx, __NULL_IMPORT_DESCRIPTOR; hInstance
0x1400019dd  call    WinMain
0x1400019e2  mov     ebx, eax
0x1400019e4  call    __scrt_is_managed_app
0x1400019e9  test    al, al
0x1400019eb  jz      short loc_140001A41
0x1400019ed  test    dil, dil
0x1400019f0  jnz     short loc_1400019F7
0x1400019f2  call    _cexit_0
0x1400019f7  xor     edx, edx
0x1400019f9  mov     cl, 1
0x1400019fb  call    __scrt_uninitialize_crt
0x140001a00  mov     eax, ebx
0x140001a02  jmp     short loc_140001A1D
0x140001a04  mov     ebx, eax
0x140001a06  call    __scrt_is_managed_app
0x140001a0b  test    al, al
0x140001a0d  jz      short loc_140001A49
0x140001a0f  cmp     [rsp+38h+var_18], 0
0x140001a14  jnz     short loc_140001A1B
0x140001a16  call    _c_exit_0
0x140001a1b  mov     eax, ebx
0x140001a1d  mov     rbx, [rsp+38h+arg_0]
0x140001a22  add     rsp, 30h
0x140001a26  pop     rdi
0x140001a27  retn
0x140001a28  mov     ecx, 7
0x140001a2d  call    __scrt_fastfail
0x140001a32  nop
0x140001a33  jmp     short loc_140001A36
0x140001a36  nop
0x140001a37  mov     ecx, 7
0x140001a3c  call    __scrt_fastfail
0x140001a41  mov     ecx, ebx; Code
0x140001a43  call    exit_0
0x140001a49  mov     ecx, ebx; Code
0x140001a4b  call    _exit_0
0x140003157  push    rbp
0x140003159  sub     rsp, 20h
0x14000315d  mov     rbp, rdx
0x140003160  mov     rdx, rcx; ExceptionPtr
0x140003163  mov     rcx, [rcx]
0x140003166  mov     ecx, [rcx]; ExceptionNum
0x140003168  call    _seh_filter_exe_0
0x14000316d  nop
0x14000316e  add     rsp, 20h
0x140003172  pop     rbp
0x140003173  retn
```
