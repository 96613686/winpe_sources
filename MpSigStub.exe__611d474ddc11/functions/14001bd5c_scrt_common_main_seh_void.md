# __scrt_common_main_seh(void)

- ea: `0x14001bd5c`
- end: `0x14001becd`
- name: `?__scrt_common_main_seh@@YAHXZ`
- size: `369`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14001bed0`

## callees

- `0x140014398`
- `0x140014cc8`
- `0x140014cd8`
- `0x140014ce8`
- `0x140014cf4`
- `0x140014d34`
- `0x140017e38`
- `0x140017e70`
- `0x14001bd5c`
- `0x14001c570`
- `0x14001c6d4`
- `0x14001c718`
- `0x14001c940`
- `0x14001c97c`
- `0x14001ca54`
- `0x14001caec`
- `0x14001cb10`
- `0x14001cc90`
- `0x14001cc98`
- `0x140022a80`
- `0x1400315f0`
- `0x1400ae030`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v13; // rcx
  CHAR *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    sub_14001C570(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)dword_1400D7808;
  if ( dword_1400D7808 == 1 )
  {
LABEL_19:
    sub_14001C570(7);
    goto LABEL_20;
  }
  if ( dword_1400D7808 )
  {
    v2 = 1;
  }
  else
  {
    dword_1400D7808 = 1;
    if ( initterm_e((_PIFV *)&First, (_PIFV *)&Last) )
      return 255;
    sub_140017E38(&qword_1400B6160, &qword_1400B61A0);
    dword_1400D7808 = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  v6 = (_QWORD *)sub_14001CC90(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))v6;
  if ( *v6 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v6) )
    (*v8)(0, 2);
  v9 = (_tls_callback_type *)sub_14001CC98(v7);
  v11 = v9;
  if ( *v9 && (unsigned __int8)_scrt_is_nonwritable_in_current_image(v9) )
    register_thread_local_exe_atexit_callback(*v11);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v10);
  v14 = (CHAR *)unknown_libname_75(v13);
  v0 = WinMain((HINSTANCE)0x140000000LL, 0, v14, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
LABEL_20:
    exit(v0);
  if ( !v2 )
    cexit();
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v0;
}

```

## disassembly

```asm
0x14001bd5c  mov     [rsp+arg_0], rbx
0x14001bd61  push    rdi
0x14001bd62  sub     rsp, 30h
0x14001bd66  mov     ecx, 1
0x14001bd6b  call    __scrt_initialize_crt
0x14001bd70  test    al, al
0x14001bd72  jz      loc_14001BEA8
0x14001bd78  xor     dil, dil
0x14001bd7b  mov     [rsp+38h+var_18], dil
0x14001bd80  call    __scrt_acquire_startup_lock
0x14001bd85  mov     bl, al
0x14001bd87  mov     ecx, cs:dword_1400D7808
0x14001bd8d  cmp     ecx, 1
0x14001bd90  jz      loc_14001BEB3
0x14001bd96  test    ecx, ecx
0x14001bd98  jnz     short loc_14001BDE4
0x14001bd9a  mov     cs:dword_1400D7808, 1
0x14001bda4  lea     rdx, Last; Last
0x14001bdab  lea     rcx, First; First
0x14001bdb2  call    _initterm_e
0x14001bdb7  test    eax, eax
0x14001bdb9  jz      short loc_14001BDC5
0x14001bdbb  mov     eax, 0FFh
0x14001bdc0  jmp     loc_14001BE9D
0x14001bdc5  lea     rdx, qword_1400B61A0
0x14001bdcc  lea     rcx, qword_1400B6160
0x14001bdd3  call    sub_140017E38
0x14001bdd8  mov     cs:dword_1400D7808, 2
0x14001bde2  jmp     short loc_14001BDEC
0x14001bde4  mov     dil, 1
0x14001bde7  mov     [rsp+38h+var_18], dil
0x14001bdec  mov     cl, bl
0x14001bdee  call    __scrt_release_startup_lock
0x14001bdf3  call    sub_14001CC90
0x14001bdf8  mov     rbx, rax
0x14001bdfb  cmp     qword ptr [rax], 0
0x14001bdff  jz      short loc_14001BE1F
0x14001be01  mov     rcx, rax
0x14001be04  call    __scrt_is_nonwritable_in_current_image
0x14001be09  test    al, al
0x14001be0b  jz      short loc_14001BE1F
0x14001be0d  xor     r8d, r8d
0x14001be10  lea     edx, [r8+2]
0x14001be14  xor     ecx, ecx
0x14001be16  mov     rax, [rbx]
0x14001be19  call    cs:__guard_dispatch_icall_fptr
0x14001be1f  call    sub_14001CC98
0x14001be24  mov     rbx, rax
0x14001be27  cmp     qword ptr [rax], 0
0x14001be2b  jz      short loc_14001BE41
0x14001be2d  mov     rcx, rax
0x14001be30  call    __scrt_is_nonwritable_in_current_image
0x14001be35  test    al, al
0x14001be37  jz      short loc_14001BE41
0x14001be39  mov     rcx, [rbx]; Callback
0x14001be3c  call    _register_thread_local_exe_atexit_callback
0x14001be41  call    __scrt_get_show_window_mode
0x14001be46  movzx   ebx, ax
0x14001be49  call    unknown_libname_75; Microsoft VisualC 64bit universal runtime
0x14001be4e  mov     r9d, ebx; nShowCmd
0x14001be51  mov     r8, rax; lpCmdLine
0x14001be54  xor     edx, edx; hPrevInstance
0x14001be56  lea     rcx, cs:140000000h; hInstance
0x14001be5d  call    WinMain
0x14001be62  mov     ebx, eax
0x14001be64  call    __scrt_is_managed_app
0x14001be69  test    al, al
0x14001be6b  jz      short loc_14001BEBD
0x14001be6d  test    dil, dil
0x14001be70  jnz     short loc_14001BE77
0x14001be72  call    _cexit
0x14001be77  xor     edx, edx
0x14001be79  mov     cl, 1
0x14001be7b  call    __scrt_uninitialize_crt
0x14001be80  mov     eax, ebx
0x14001be82  jmp     short loc_14001BE9D
0x14001be84  mov     ebx, eax
0x14001be86  call    __scrt_is_managed_app
0x14001be8b  test    al, al
0x14001be8d  jz      short loc_14001BEC5
0x14001be8f  cmp     [rsp+38h+var_18], 0
0x14001be94  jnz     short loc_14001BE9B
0x14001be96  call    _c_exit
0x14001be9b  mov     eax, ebx
0x14001be9d  mov     rbx, [rsp+38h+arg_0]
0x14001bea2  add     rsp, 30h
0x14001bea6  pop     rdi
0x14001bea7  retn
0x14001bea8  mov     ecx, 7
0x14001bead  call    sub_14001C570
0x14001beb2  nop
0x14001beb3  mov     ecx, 7
0x14001beb8  call    sub_14001C570
0x14001bebd  mov     ecx, ebx; Code
0x14001bebf  call    exit
0x14001bec5  mov     ecx, ebx; Code
0x14001bec7  call    _exit
0x1400ae3ef  push    rbp
0x1400ae3f1  sub     rsp, 20h
0x1400ae3f5  mov     rbp, rdx
0x1400ae3f8  mov     rax, [rcx]
0x1400ae3fb  mov     rdx, rcx
0x1400ae3fe  mov     ecx, [rax]
0x1400ae400  call    sub_140014398
0x1400ae405  nop
0x1400ae406  add     rsp, 20h
0x1400ae40a  pop     rbp
0x1400ae40b  retn
```
