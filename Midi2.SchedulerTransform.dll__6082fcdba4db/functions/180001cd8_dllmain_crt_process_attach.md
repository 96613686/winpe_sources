# dllmain_crt_process_attach

- ea: `0x180001cd8`
- end: `0x180001dd2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001c80`

## callees

- `0x180001cd8`
- `0x180002094`
- `0x1800020d4`
- `0x180002110`
- `0x180002210`
- `0x1800022e4`
- `0x180002384`
- `0x18000255c`
- `0x180002584`
- `0x1800025a8`
- `0x1800025b8`
- `0x1800025c4`
- `0x180002946`
- `0x180002952`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 v6; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v8)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v5 = 0;
      }
    }
  }
  LOBYTE(v6) = v4;
  _scrt_release_startup_lock(v6);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v8 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v8)(a1, 2, a2);
  }
  ++dword_180015390;
  return 1;
}

```

## disassembly

```asm
0x180001cd8  push    rbx
0x180001cda  push    rsi
0x180001cdb  push    rdi
0x180001cdc  push    r14
0x180001cde  sub     rsp, 28h
0x180001ce2  mov     rsi, rdx
0x180001ce5  mov     r14, rcx
0x180001ce8  xor     ecx, ecx
0x180001cea  call    __scrt_initialize_crt
0x180001cef  test    al, al
0x180001cf1  jz      loc_180001DBA
0x180001cf7  call    __scrt_acquire_startup_lock
0x180001cfc  mov     bl, al
0x180001cfe  mov     [rsp+48h+arg_10], al
0x180001d02  mov     dil, 1
0x180001d05  cmp     cs:__scrt_current_native_startup_state, 0
0x180001d0c  jnz     loc_180001DC6
0x180001d12  mov     cs:__scrt_current_native_startup_state, 1
0x180001d1c  call    __scrt_dllmain_before_initialize_c
0x180001d21  test    al, al
0x180001d23  jz      short loc_180001D74
0x180001d25  call    _RTC_Initialize
0x180001d2a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001d2f  call    __scrt_initialize_default_local_stdio_options
0x180001d34  lea     rdx, __xi_z; Last
0x180001d3b  lea     rcx, __xi_a; First
0x180001d42  call    _initterm_e_0
0x180001d47  test    eax, eax
0x180001d49  jnz     short loc_180001D74
0x180001d4b  call    __scrt_dllmain_after_initialize_c
0x180001d50  test    al, al
0x180001d52  jz      short loc_180001D74
0x180001d54  lea     rdx, __xc_z; Last
0x180001d5b  lea     rcx, __xc_a; First
0x180001d62  call    _initterm_0
0x180001d67  mov     cs:__scrt_current_native_startup_state, 2
0x180001d71  xor     dil, dil
0x180001d74  mov     cl, bl
0x180001d76  call    __scrt_release_startup_lock
0x180001d7b  test    dil, dil
0x180001d7e  jnz     short loc_180001DBA
0x180001d80  call    __scrt_get_dyn_tls_init_callback
0x180001d85  mov     rbx, rax
0x180001d88  cmp     qword ptr [rax], 0
0x180001d8c  jz      short loc_180001DAD
0x180001d8e  mov     rcx, rax
0x180001d91  call    __scrt_is_nonwritable_in_current_image
0x180001d96  test    al, al
0x180001d98  jz      short loc_180001DAD
0x180001d9a  mov     r8, rsi
0x180001d9d  mov     edx, 2
0x180001da2  mov     rcx, r14
0x180001da5  mov     rax, [rbx]
0x180001da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dad  inc     cs:dword_180015390
0x180001db3  mov     eax, 1
0x180001db8  jmp     short loc_180001DBC
0x180001dba  xor     eax, eax
0x180001dbc  add     rsp, 28h
0x180001dc0  pop     r14
0x180001dc2  pop     rdi
0x180001dc3  pop     rsi
0x180001dc4  pop     rbx
0x180001dc5  retn
0x180001dc6  mov     ecx, 7
0x180001dcb  call    __scrt_fastfail
0x18000ccec  push    rbp
0x18000ccee  sub     rsp, 20h
0x18000ccf2  mov     rbp, rdx
0x18000ccf5  mov     cl, [rbp+60h]
0x18000ccf8  add     rsp, 20h
0x18000ccfc  pop     rbp
0x18000ccfd  jmp     __scrt_release_startup_lock
```
