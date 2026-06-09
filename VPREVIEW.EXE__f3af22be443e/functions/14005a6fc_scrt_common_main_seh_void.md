# __scrt_common_main_seh(void)

- ea: `0x14005a6fc`
- end: `0x14005a871`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `373`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14005a880`

## callees

- `0x140003bf0`
- `0x14005a6fc`
- `0x14005a9d4`
- `0x14005aa10`
- `0x14005aad8`
- `0x14005ab70`
- `0x14005ab94`
- `0x14005b528`
- `0x14005b530`
- `0x14005b544`
- `0x14005b690`
- `0x14005b6d4`
- `0x14005bb48`
- `0x14005bb66`
- `0x14005bb6c`
- `0x14005bb72`
- `0x14005bb78`
- `0x14005bb7e`
- `0x14005bb8a`
- `0x14005bb90`
- `0x14005bb96`
- `0x14005c580`

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
    sub_14005B544(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)dword_1400775C0;
  if ( dword_1400775C0 == 1 )
  {
LABEL_19:
    sub_14005B544(7);
    goto LABEL_20;
  }
  if ( dword_1400775C0 )
  {
    v2 = 1;
  }
  else
  {
    dword_1400775C0 = 1;
    if ( initterm_e((_PIFV *)&First, (_PIFV *)&Last) )
      return 255;
    initterm((_PVFV *)&qword_14005E950, (_PVFV *)&qword_14005EA78);
    dword_1400775C0 = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  v6 = (_QWORD *)sub_14005B528(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))v6;
  if ( *v6 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v6) )
    (*v8)(0, 2);
  v9 = (_tls_callback_type *)sub_14005B530(v7);
  v11 = v9;
  if ( *v9 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v9) )
    register_thread_local_exe_atexit_callback(*v11);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v10);
  narrow_winmain_command_line = get_narrow_winmain_command_line();
  v0 = WinMain(&_ImageBase, 0, narrow_winmain_command_line, show_window_mode);
  if ( !(unsigned __int8)sub_14005B6D4(v14) )
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
0x14005a6fc  mov     [rsp+arg_0], rbx
0x14005a701  push    rdi
0x14005a702  sub     rsp, 30h
0x14005a706  mov     ecx, 1
0x14005a70b  call    __scrt_initialize_crt
0x14005a710  test    al, al
0x14005a712  jz      loc_14005A848
0x14005a718  xor     dil, dil
0x14005a71b  mov     [rsp+38h+var_18], dil
0x14005a720  call    __scrt_acquire_startup_lock
0x14005a725  mov     bl, al
0x14005a727  mov     ecx, cs:dword_1400775C0
0x14005a72d  cmp     ecx, 1
0x14005a730  jz      loc_14005A857
0x14005a736  test    ecx, ecx
0x14005a738  jnz     short loc_14005A784
0x14005a73a  mov     cs:dword_1400775C0, 1
0x14005a744  lea     rdx, Last; Last
0x14005a74b  lea     rcx, First; First
0x14005a752  call    _initterm_e
0x14005a757  test    eax, eax
0x14005a759  jz      short loc_14005A765
0x14005a75b  mov     eax, 0FFh
0x14005a760  jmp     loc_14005A83D
0x14005a765  lea     rdx, qword_14005EA78; Last
0x14005a76c  lea     rcx, qword_14005E950; First
0x14005a773  call    _initterm
0x14005a778  mov     cs:dword_1400775C0, 2
0x14005a782  jmp     short loc_14005A78C
0x14005a784  mov     dil, 1
0x14005a787  mov     [rsp+38h+var_18], dil
0x14005a78c  mov     cl, bl
0x14005a78e  call    __scrt_release_startup_lock
0x14005a793  call    sub_14005B528
0x14005a798  mov     rbx, rax
0x14005a79b  cmp     qword ptr [rax], 0
0x14005a79f  jz      short loc_14005A7BF
0x14005a7a1  mov     rcx, rax
0x14005a7a4  call    __scrt_is_nonwritable_in_current_image
0x14005a7a9  test    al, al
0x14005a7ab  jz      short loc_14005A7BF
0x14005a7ad  xor     r8d, r8d
0x14005a7b0  lea     edx, [r8+2]
0x14005a7b4  xor     ecx, ecx
0x14005a7b6  mov     rax, [rbx]
0x14005a7b9  call    cs:__guard_dispatch_icall_fptr
0x14005a7bf  call    sub_14005B530
0x14005a7c4  mov     rbx, rax
0x14005a7c7  cmp     qword ptr [rax], 0
0x14005a7cb  jz      short loc_14005A7E1
0x14005a7cd  mov     rcx, rax
0x14005a7d0  call    __scrt_is_nonwritable_in_current_image
0x14005a7d5  test    al, al
0x14005a7d7  jz      short loc_14005A7E1
0x14005a7d9  mov     rcx, [rbx]; Callback
0x14005a7dc  call    _register_thread_local_exe_atexit_callback
0x14005a7e1  call    __scrt_get_show_window_mode
0x14005a7e6  movzx   ebx, ax
0x14005a7e9  call    _get_narrow_winmain_command_line
0x14005a7ee  mov     r9d, ebx; nShowCmd
0x14005a7f1  mov     r8, rax; lpCmdLine
0x14005a7f4  xor     edx, edx; hPrevInstance
0x14005a7f6  lea     rcx, __ImageBase; hInstance
0x14005a7fd  call    WinMain
0x14005a802  mov     ebx, eax
0x14005a804  call    sub_14005B6D4
0x14005a809  test    al, al
0x14005a80b  jz      short loc_14005A861
0x14005a80d  test    dil, dil
0x14005a810  jnz     short loc_14005A817
0x14005a812  call    _cexit
0x14005a817  xor     edx, edx
0x14005a819  mov     cl, 1
0x14005a81b  call    __scrt_uninitialize_crt
0x14005a820  mov     eax, ebx
0x14005a822  jmp     short loc_14005A83D
0x14005a824  mov     ebx, eax
0x14005a826  call    sub_14005B6D4
0x14005a82b  test    al, al
0x14005a82d  jz      short loc_14005A869
0x14005a82f  cmp     [rsp+38h+var_18], 0
0x14005a834  jnz     short loc_14005A83B
0x14005a836  call    _c_exit
0x14005a83b  mov     eax, ebx
0x14005a83d  mov     rbx, [rsp+38h+arg_0]
0x14005a842  add     rsp, 30h
0x14005a846  pop     rdi
0x14005a847  retn
0x14005a848  mov     ecx, 7
0x14005a84d  call    sub_14005B544
0x14005a852  nop
0x14005a853  jmp     short loc_14005A856
0x14005a856  nop
0x14005a857  mov     ecx, 7
0x14005a85c  call    sub_14005B544
0x14005a861  mov     ecx, ebx; Code
0x14005a863  call    exit
0x14005a869  mov     ecx, ebx; Code
0x14005a86b  call    _exit
0x14005cbce  push    rbp
0x14005cbd0  sub     rsp, 20h
0x14005cbd4  mov     rbp, rdx
0x14005cbd7  mov     rdx, rcx; ExceptionPtr
0x14005cbda  mov     rcx, [rcx]
0x14005cbdd  mov     ecx, [rcx]; ExceptionNum
0x14005cbdf  call    _seh_filter_exe
0x14005cbe4  nop
0x14005cbe5  add     rsp, 20h
0x14005cbe9  pop     rbp
0x14005cbea  retn
```
