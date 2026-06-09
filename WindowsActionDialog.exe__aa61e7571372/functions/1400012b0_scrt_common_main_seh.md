# __scrt_common_main_seh

- ea: `0x1400012b0`
- end: `0x140001420`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001430`

## callees

- `0x1400012b0`
- `0x1400014ec`
- `0x14000152c`
- `0x140001600`
- `0x1400016a0`
- `0x1400016cc`
- `0x1400018c0`
- `0x1400018d0`
- `0x1400018e0`
- `0x1400018ec`
- `0x140001938`
- `0x140001db6`
- `0x140001dc2`
- `0x140001dce`
- `0x140001dda`
- `0x140001e46`
- `0x140001e76`
- `0x140001e82`
- `0x140001ed8`
- `0x140001f08`
- `0x140007a78`
- `0x14000a010`

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
0x1400012b0  mov     [rsp+arg_0], rbx
0x1400012b5  push    rdi
0x1400012b6  sub     rsp, 30h
0x1400012ba  mov     ecx, 1
0x1400012bf  call    __scrt_initialize_crt
0x1400012c4  test    al, al
0x1400012c6  jz      loc_1400013FB
0x1400012cc  xor     dil, dil
0x1400012cf  mov     [rsp+38h+var_18], dil
0x1400012d4  call    __scrt_acquire_startup_lock
0x1400012d9  mov     bl, al
0x1400012db  mov     ecx, cs:__scrt_current_native_startup_state
0x1400012e1  cmp     ecx, 1
0x1400012e4  jz      loc_140001406
0x1400012ea  test    ecx, ecx
0x1400012ec  jnz     short loc_140001338
0x1400012ee  mov     cs:__scrt_current_native_startup_state, 1
0x1400012f8  lea     rdx, __xi_z; Last
0x1400012ff  lea     rcx, __xi_a; First
0x140001306  call    _initterm_e_0
0x14000130b  test    eax, eax
0x14000130d  jz      short loc_140001319
0x14000130f  mov     eax, 0FFh
0x140001314  jmp     loc_1400013F0
0x140001319  lea     rdx, __xc_z; Last
0x140001320  lea     rcx, __xc_a; First
0x140001327  call    _initterm_0
0x14000132c  mov     cs:__scrt_current_native_startup_state, 2
0x140001336  jmp     short loc_140001340
0x140001338  mov     dil, 1
0x14000133b  mov     [rsp+38h+var_18], dil
0x140001340  mov     cl, bl
0x140001342  call    __scrt_release_startup_lock
0x140001347  call    __scrt_get_dyn_tls_init_callback
0x14000134c  mov     rbx, rax
0x14000134f  cmp     qword ptr [rax], 0
0x140001353  jz      short loc_140001372
0x140001355  mov     rcx, rax
0x140001358  call    __scrt_is_nonwritable_in_current_image
0x14000135d  test    al, al
0x14000135f  jz      short loc_140001372
0x140001361  xor     r8d, r8d
0x140001364  lea     edx, [r8+2]
0x140001368  xor     ecx, ecx
0x14000136a  mov     rax, [rbx]
0x14000136d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001372  call    __scrt_get_dyn_tls_dtor_callback
0x140001377  mov     rbx, rax
0x14000137a  cmp     qword ptr [rax], 0
0x14000137e  jz      short loc_140001394
0x140001380  mov     rcx, rax
0x140001383  call    __scrt_is_nonwritable_in_current_image
0x140001388  test    al, al
0x14000138a  jz      short loc_140001394
0x14000138c  mov     rcx, [rbx]; Callback
0x14000138f  call    _register_thread_local_exe_atexit_callback_0
0x140001394  call    __scrt_get_show_window_mode
0x140001399  movzx   ebx, ax
0x14000139c  call    _o__get_wide_winmain_command_line_0
0x1400013a1  mov     r9d, ebx; nShowCmd
0x1400013a4  mov     r8, rax; lpCmdLine
0x1400013a7  xor     edx, edx; hPrevInstance
0x1400013a9  lea     rcx, cs:140000000h; hInstance
0x1400013b0  call    wWinMain
0x1400013b5  mov     ebx, eax
0x1400013b7  call    __scrt_is_managed_app
0x1400013bc  test    al, al
0x1400013be  jz      short loc_140001410
0x1400013c0  test    dil, dil
0x1400013c3  jnz     short loc_1400013CA
0x1400013c5  call    _o__cexit_0
0x1400013ca  xor     edx, edx
0x1400013cc  mov     cl, 1
0x1400013ce  call    __scrt_uninitialize_crt
0x1400013d3  mov     eax, ebx
0x1400013d5  jmp     short loc_1400013F0
0x1400013d7  mov     ebx, eax
0x1400013d9  call    __scrt_is_managed_app
0x1400013de  test    al, al
0x1400013e0  jz      short loc_140001418
0x1400013e2  cmp     [rsp+38h+var_18], 0
0x1400013e7  jnz     short loc_1400013EE
0x1400013e9  call    _c_exit_0
0x1400013ee  mov     eax, ebx
0x1400013f0  mov     rbx, [rsp+38h+arg_0]
0x1400013f5  add     rsp, 30h
0x1400013f9  pop     rdi
0x1400013fa  retn
0x1400013fb  mov     ecx, 7
0x140001400  call    __scrt_fastfail
0x140001406  mov     ecx, 7
0x14000140b  call    __scrt_fastfail
0x140001410  mov     ecx, ebx; Code
0x140001412  call    _o_exit_0
0x140001418  mov     ecx, ebx
0x14000141a  call    _o__exit_0
0x14000141f  nop
0x14000937c  push    rbp
0x14000937e  sub     rsp, 20h
0x140009382  mov     rbp, rdx
0x140009385  mov     rdx, rcx; ExceptionPtr
0x140009388  mov     rcx, [rcx]
0x14000938b  mov     ecx, [rcx]; ExceptionNum
0x14000938d  call    _seh_filter_exe
0x140009392  nop
0x140009393  add     rsp, 20h
0x140009397  pop     rbp
0x140009398  retn
```
