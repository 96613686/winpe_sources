# __scrt_common_main_seh(void)

- ea: `0x140007ecc`
- end: `0x140008038`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `364`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140008050`

## callees

- `0x140005b00`
- `0x140007ecc`
- `0x140008218`
- `0x140008254`
- `0x140008380`
- `0x14000841c`
- `0x140008440`
- `0x140008520`
- `0x140008528`
- `0x140008538`
- `0x140008684`
- `0x1400086c0`
- `0x14000880c`
- `0x140008a1d`
- `0x140008a3b`
- `0x140008a41`
- `0x140008a47`
- `0x140008a4d`
- `0x140008a53`
- `0x140008a5f`
- `0x140008a65`
- `0x140008a6b`

## pseudocode

```c
__int64 __fastcall __scrt_common_main_seh()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  char v2; // di
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *v9; // rax
  __int64 v10; // rcx
  _tls_callback_type *v11; // rbx
  int show_window_mode; // ebx
  char *narrow_winmain_command_line; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    _scrt_fastfail(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)dword_1400127D4;
  if ( dword_1400127D4 == 1 )
  {
LABEL_19:
    _scrt_fastfail(7);
    goto LABEL_20;
  }
  if ( dword_1400127D4 )
  {
    v2 = 1;
  }
  else
  {
    dword_1400127D4 = 1;
    if ( initterm_e((_PIFV *)&First, (_PIFV *)&Last) )
      return 255;
    initterm((_PVFV *)&qword_14000A3D0, (_PVFV *)&qword_14000A3E0);
    dword_1400127D4 = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  v6 = (_QWORD *)sub_140008520(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))v6;
  if ( *v6 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v6) )
    (*v8)(0, 2);
  v9 = (_tls_callback_type *)sub_140008528(v7);
  v11 = v9;
  if ( *v9 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v9) )
    register_thread_local_exe_atexit_callback(*v11);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v10);
  narrow_winmain_command_line = get_narrow_winmain_command_line();
  v0 = WinMain(&_ImageBase, 0, narrow_winmain_command_line, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    exit(v0);
  if ( !v2 )
    cexit();
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x140007ecc  mov     [rsp+arg_0], rbx
0x140007ed1  push    rdi
0x140007ed2  sub     rsp, 30h
0x140007ed6  mov     ecx, 1
0x140007edb  call    __scrt_initialize_crt
0x140007ee0  test    al, al
0x140007ee2  jz      loc_14000801C
0x140007ee8  xor     dil, dil
0x140007eeb  mov     [rsp+38h+var_18], dil
0x140007ef0  call    __scrt_acquire_startup_lock
0x140007ef5  mov     bl, al
0x140007ef7  mov     ecx, cs:dword_1400127D4
0x140007efd  cmp     ecx, 1
0x140007f00  jz      loc_140008027
0x140007f06  test    ecx, ecx
0x140007f08  jnz     short loc_140007F54
0x140007f0a  mov     cs:dword_1400127D4, 1
0x140007f14  lea     rdx, Last; Last
0x140007f1b  lea     rcx, First; First
0x140007f22  call    _initterm_e
0x140007f27  test    eax, eax
0x140007f29  jz      short loc_140007F35
0x140007f2b  mov     eax, 0FFh
0x140007f30  jmp     loc_140008011
0x140007f35  lea     rdx, qword_14000A3E0; Last
0x140007f3c  lea     rcx, qword_14000A3D0; First
0x140007f43  call    _initterm
0x140007f48  mov     cs:dword_1400127D4, 2
0x140007f52  jmp     short loc_140007F5C
0x140007f54  mov     dil, 1
0x140007f57  mov     [rsp+38h+var_18], dil
0x140007f5c  mov     cl, bl
0x140007f5e  call    __scrt_release_startup_lock
0x140007f63  call    sub_140008520
0x140007f68  mov     rbx, rax
0x140007f6b  cmp     qword ptr [rax], 0
0x140007f6f  jz      short loc_140007F93
0x140007f71  mov     rcx, rax
0x140007f74  call    __scrt_is_nonwritable_in_current_image
0x140007f79  test    al, al
0x140007f7b  jz      short loc_140007F93
0x140007f7d  mov     rbx, [rbx]
0x140007f80  mov     rcx, rbx
0x140007f83  call    j__guard_check_icall_nop
0x140007f88  xor     r8d, r8d
0x140007f8b  lea     edx, [r8+2]
0x140007f8f  xor     ecx, ecx
0x140007f91  call    rbx
0x140007f93  call    sub_140008528
0x140007f98  mov     rbx, rax
0x140007f9b  cmp     qword ptr [rax], 0
0x140007f9f  jz      short loc_140007FB5
0x140007fa1  mov     rcx, rax
0x140007fa4  call    __scrt_is_nonwritable_in_current_image
0x140007fa9  test    al, al
0x140007fab  jz      short loc_140007FB5
0x140007fad  mov     rcx, [rbx]; Callback
0x140007fb0  call    _register_thread_local_exe_atexit_callback
0x140007fb5  call    __scrt_get_show_window_mode
0x140007fba  movzx   ebx, ax
0x140007fbd  call    _get_narrow_winmain_command_line
0x140007fc2  mov     r8, rax; lpCmdLine
0x140007fc5  mov     r9d, ebx; nShowCmd
0x140007fc8  xor     edx, edx; hPrevInstance
0x140007fca  lea     rcx, __ImageBase; hInstance
0x140007fd1  call    WinMain
0x140007fd6  mov     ebx, eax
0x140007fd8  call    __scrt_is_managed_app
0x140007fdd  test    al, al
0x140007fdf  jz      short loc_140008031
0x140007fe1  test    dil, dil
0x140007fe4  jnz     short loc_140007FEB
0x140007fe6  call    _cexit
0x140007feb  xor     edx, edx
0x140007fed  mov     cl, 1
0x140007fef  call    __scrt_uninitialize_crt
0x140007ff4  mov     eax, ebx
0x140007ff6  jmp     short loc_140008011
0x140007ff8  mov     ebx, eax
0x140007ffa  call    __scrt_is_managed_app
0x140007fff  test    al, al
0x140008001  jz      short loc_140008039
0x140008003  cmp     [rsp+38h+var_18], 0
0x140008008  jnz     short near ptr unk_14000800F
0x14000800a  call    _c_exit
0x140008010  retn
0x140008011  mov     rbx, [rsp+38h+arg_0]
0x140008016  add     rsp, 30h
0x14000801a  pop     rdi
0x14000801b  retn
0x14000801c  mov     ecx, 7
0x140008021  call    __scrt_fastfail
0x140008026  nop
0x140008027  mov     ecx, 7
0x14000802c  call    __scrt_fastfail
0x140008031  mov     ecx, ebx; Code
0x140008033  call    exit
0x140008039  mov     ecx, ebx; Code
0x14000803b  call    _exit
0x1400096eb  push    rbp
0x1400096ed  sub     rsp, 20h
0x1400096f1  mov     rbp, rdx
0x1400096f4  mov     rax, [rcx]
0x1400096f7  mov     rdx, rcx; ExceptionPtr
0x1400096fa  mov     ecx, [rax]; ExceptionNum
0x1400096fc  call    _seh_filter_exe
0x140009701  nop
0x140009702  add     rsp, 20h
0x140009706  pop     rbp
0x140009707  retn
```
