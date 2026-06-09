# __scrt_common_main_seh

- ea: `0x140001180`
- end: `0x1400012f0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001300`

## callees

- `0x140001180`
- `0x140001384`
- `0x1400013c4`
- `0x140001498`
- `0x140001538`
- `0x140001564`
- `0x140001720`
- `0x140001730`
- `0x140001740`
- `0x14000174c`
- `0x140001798`
- `0x140001e3c`
- `0x140001e48`
- `0x140001e54`
- `0x140001e60`
- `0x140001eb4`
- `0x140001ee4`
- `0x140001ef0`
- `0x140001f20`
- `0x140001f50`
- `0x140002430`
- `0x140003010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  char v0; // di
  char v1; // bl
  __int64 v2; // rcx
  __int64 v4; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v6; // rcx
  void (__fastcall **v7)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  __int64 v9; // rcx
  _tls_callback_type *v10; // rbx
  int show_window_mode; // ebx
  __int64 v12; // rcx
  CHAR *narrow_winmain_command_line_0; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v0 = 0;
  v1 = _scrt_acquire_startup_lock();
  v2 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
    v0 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v2) = v1;
  _scrt_release_startup_lock(v2);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v4);
  v7 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v7)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v6);
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v9);
  narrow_winmain_command_line_0 = (CHAR *)o__get_narrow_winmain_command_line_0(v12);
  v14 = WinMain((HINSTANCE)0x140000000LL, 0, narrow_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    o_exit_0(v14);
  if ( !v0 )
    o__cexit_0(v16);
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x140001180  mov     [rsp+arg_0], rbx
0x140001185  push    rdi
0x140001186  sub     rsp, 30h
0x14000118a  mov     ecx, 1
0x14000118f  call    __scrt_initialize_crt
0x140001194  test    al, al
0x140001196  jz      loc_1400012CB
0x14000119c  xor     dil, dil
0x14000119f  mov     [rsp+38h+var_18], dil
0x1400011a4  call    __scrt_acquire_startup_lock
0x1400011a9  mov     bl, al
0x1400011ab  mov     ecx, cs:__scrt_current_native_startup_state
0x1400011b1  cmp     ecx, 1
0x1400011b4  jz      loc_1400012D6
0x1400011ba  test    ecx, ecx
0x1400011bc  jnz     short loc_140001208
0x1400011be  mov     cs:__scrt_current_native_startup_state, 1
0x1400011c8  lea     rdx, __xi_z; Last
0x1400011cf  lea     rcx, __xi_a; First
0x1400011d6  call    _initterm_e_0
0x1400011db  test    eax, eax
0x1400011dd  jz      short loc_1400011E9
0x1400011df  mov     eax, 0FFh
0x1400011e4  jmp     loc_1400012C0
0x1400011e9  lea     rdx, __xc_z; Last
0x1400011f0  lea     rcx, __xc_a; First
0x1400011f7  call    _initterm_0
0x1400011fc  mov     cs:__scrt_current_native_startup_state, 2
0x140001206  jmp     short loc_140001210
0x140001208  mov     dil, 1
0x14000120b  mov     [rsp+38h+var_18], dil
0x140001210  mov     cl, bl
0x140001212  call    __scrt_release_startup_lock
0x140001217  call    __scrt_get_dyn_tls_init_callback
0x14000121c  mov     rbx, rax
0x14000121f  cmp     qword ptr [rax], 0
0x140001223  jz      short loc_140001242
0x140001225  mov     rcx, rax
0x140001228  call    __scrt_is_nonwritable_in_current_image
0x14000122d  test    al, al
0x14000122f  jz      short loc_140001242
0x140001231  xor     r8d, r8d
0x140001234  lea     edx, [r8+2]
0x140001238  xor     ecx, ecx
0x14000123a  mov     rax, [rbx]
0x14000123d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001242  call    __scrt_get_dyn_tls_dtor_callback
0x140001247  mov     rbx, rax
0x14000124a  cmp     qword ptr [rax], 0
0x14000124e  jz      short loc_140001264
0x140001250  mov     rcx, rax
0x140001253  call    __scrt_is_nonwritable_in_current_image
0x140001258  test    al, al
0x14000125a  jz      short loc_140001264
0x14000125c  mov     rcx, [rbx]; Callback
0x14000125f  call    _register_thread_local_exe_atexit_callback_0
0x140001264  call    __scrt_get_show_window_mode
0x140001269  movzx   ebx, ax
0x14000126c  call    _o__get_narrow_winmain_command_line_0
0x140001271  mov     r9d, ebx; nShowCmd
0x140001274  mov     r8, rax; lpCmdLine
0x140001277  xor     edx, edx; hPrevInstance
0x140001279  lea     rcx, cs:140000000h; hInstance
0x140001280  call    WinMain
0x140001285  mov     ebx, eax
0x140001287  call    __scrt_is_managed_app
0x14000128c  test    al, al
0x14000128e  jz      short loc_1400012E0
0x140001290  test    dil, dil
0x140001293  jnz     short loc_14000129A
0x140001295  call    _o__cexit_0
0x14000129a  xor     edx, edx
0x14000129c  mov     cl, 1
0x14000129e  call    __scrt_uninitialize_crt
0x1400012a3  mov     eax, ebx
0x1400012a5  jmp     short loc_1400012C0
0x1400012a7  mov     ebx, eax
0x1400012a9  call    __scrt_is_managed_app
0x1400012ae  test    al, al
0x1400012b0  jz      short loc_1400012E8
0x1400012b2  cmp     [rsp+38h+var_18], 0
0x1400012b7  jnz     short loc_1400012BE
0x1400012b9  call    _c_exit_0
0x1400012be  mov     eax, ebx
0x1400012c0  mov     rbx, [rsp+38h+arg_0]
0x1400012c5  add     rsp, 30h
0x1400012c9  pop     rdi
0x1400012ca  retn
0x1400012cb  mov     ecx, 7
0x1400012d0  call    __scrt_fastfail
0x1400012d6  mov     ecx, 7
0x1400012db  call    __scrt_fastfail
0x1400012e0  mov     ecx, ebx; Code
0x1400012e2  call    _o_exit_0
0x1400012e8  mov     ecx, ebx
0x1400012ea  call    _o__exit_0
0x1400012ef  nop
0x1400027ec  push    rbp
0x1400027ee  sub     rsp, 20h
0x1400027f2  mov     rbp, rdx
0x1400027f5  mov     rdx, rcx; ExceptionPtr
0x1400027f8  mov     rcx, [rcx]
0x1400027fb  mov     ecx, [rcx]; ExceptionNum
0x1400027fd  call    _seh_filter_exe
0x140002802  nop
0x140002803  add     rsp, 20h
0x140002807  pop     rbp
0x140002808  retn
```
