# dllmain_crt_process_attach

- ea: `0x100468c0c`
- end: `0x100468d22`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x100468bb4`

## callees

- `0x100468c0c`
- `0x100468f30`
- `0x100468f70`
- `0x100468fac`
- `0x1004690d0`
- `0x1004691b4`
- `0x100469254`
- `0x100469584`
- `0x1004695cc`
- `0x1004695f0`
- `0x100469610`
- `0x100469764`
- `0x100469876`
- `0x100469882`
- `0x100469b20`

## pseudocode

```c
__int64 dllmain_crt_process_attach()
{
  char v0; // bl
  char v1; // di
  __int64 v2; // rcx
  _QWORD *dyn_tls_init_callback; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v0 = _scrt_acquire_startup_lock();
  v1 = 1;
  if ( _scrt_current_native_startup_state )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x100468D22LL);
  }
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
        v1 = 0;
      }
    }
  }
  LOBYTE(v2) = v0;
  _scrt_release_startup_lock(v2);
  if ( v1 )
    return 0;
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback();
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
  }
  ++dword_10049A144;
  return 1;
}

```

## disassembly

```asm
0x100468c0c  mov     [rsp+arg_0], rbx
0x100468c11  mov     [rsp+arg_8], rsi
0x100468c16  mov     [rsp+arg_18], rdi
0x100468c1b  push    r14
0x100468c1d  sub     rsp, 20h
0x100468c21  mov     rsi, rdx
0x100468c24  mov     r14, rcx
0x100468c27  xor     ecx, ecx
0x100468c29  call    __scrt_initialize_crt
0x100468c2e  test    al, al
0x100468c30  jz      loc_100468CFE
0x100468c36  call    __scrt_acquire_startup_lock
0x100468c3b  mov     bl, al
0x100468c3d  mov     [rsp+28h+arg_10], al
0x100468c41  mov     dil, 1
0x100468c44  cmp     cs:__scrt_current_native_startup_state, 0
0x100468c4b  jnz     loc_100468D16
0x100468c51  mov     cs:__scrt_current_native_startup_state, 1
0x100468c5b  call    __scrt_dllmain_before_initialize_c
0x100468c60  test    al, al
0x100468c62  jz      short loc_100468CB3
0x100468c64  call    _RTC_Initialize
0x100468c69  call    ?__scrt_initialize_type_info@@YAXXZ
0x100468c6e  call    __scrt_initialize_default_local_stdio_options
0x100468c73  lea     rdx, __xi_z; Last
0x100468c7a  lea     rcx, __xi_a; First
0x100468c81  call    _initterm_e_0
0x100468c86  test    eax, eax
0x100468c88  jnz     short loc_100468CB3
0x100468c8a  call    __scrt_dllmain_after_initialize_c
0x100468c8f  test    al, al
0x100468c91  jz      short loc_100468CB3
0x100468c93  lea     rdx, __xc_z; Last
0x100468c9a  lea     rcx, __xc_a; First
0x100468ca1  call    _initterm_0
0x100468ca6  mov     cs:__scrt_current_native_startup_state, 2
0x100468cb0  xor     dil, dil
0x100468cb3  mov     cl, bl
0x100468cb5  call    __scrt_release_startup_lock
0x100468cba  test    dil, dil
0x100468cbd  jnz     short loc_100468CFE
0x100468cbf  call    __scrt_get_dyn_tls_init_callback
0x100468cc4  mov     rbx, rax
0x100468cc7  cmp     qword ptr [rax], 0
0x100468ccb  jz      short loc_100468CF1
0x100468ccd  mov     rcx, rax
0x100468cd0  call    __scrt_is_nonwritable_in_current_image
0x100468cd5  test    al, al
0x100468cd7  jz      short loc_100468CF1
0x100468cd9  mov     r8, rsi
0x100468cdc  mov     edx, 2
0x100468ce1  mov     rcx, r14
0x100468ce4  mov     rax, [rbx]
0x100468ce7  mov     r9, cs:__guard_dispatch_icall_fptr
0x100468cee  call    r9 ; _guard_dispatch_icall_nop
0x100468cf1  inc     cs:dword_10049A144
0x100468cf7  mov     eax, 1
0x100468cfc  jmp     short loc_100468D00
0x100468cfe  xor     eax, eax
0x100468d00  mov     rbx, [rsp+28h+arg_0]
0x100468d05  mov     rsi, [rsp+28h+arg_8]
0x100468d0a  mov     rdi, [rsp+28h+arg_18]
0x100468d0f  add     rsp, 20h
0x100468d13  pop     r14
0x100468d15  retn
0x100468d16  mov     ecx, 7
0x100468d1b  call    __scrt_fastfail
0x100468d20  nop
0x100468d21  int     3; Trap to Debugger
0x10047729b  push    rbp
0x10047729d  sub     rsp, 20h
0x1004772a1  mov     rbp, rdx
0x1004772a4  mov     cl, [rbp+40h]
0x1004772a7  add     rsp, 20h
0x1004772ab  pop     rbp
0x1004772ac  jmp     __scrt_release_startup_lock
```
