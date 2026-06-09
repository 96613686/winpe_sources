# dllmain_crt_process_attach

- ea: `0x180018620`
- end: `0x180018736`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1800185d0`

## callees

- `0x180018240`
- `0x18001827c`
- `0x1800182b0`
- `0x1800183ac`
- `0x180018474`
- `0x18001850c`
- `0x180018620`
- `0x180018f00`
- `0x1800190fc`
- `0x180019120`
- `0x18001913c`
- `0x180019144`
- `0x18001c5c7`
- `0x18001c5cd`
- `0x18001cdf0`

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
    JUMPOUT(0x180018736LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( _scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( _scrt_dllmain_after_initialize_c() )
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
  ++dword_18002DEC8;
  return 1;
}

```

## disassembly

```asm
0x180018620  mov     [rsp+arg_0], rbx
0x180018625  mov     [rsp+arg_8], rsi
0x18001862a  mov     [rsp+arg_18], rdi
0x18001862f  push    r14
0x180018631  sub     rsp, 20h
0x180018635  mov     rsi, rdx
0x180018638  mov     r14, rcx
0x18001863b  xor     ecx, ecx
0x18001863d  call    __scrt_initialize_crt
0x180018642  test    al, al
0x180018644  jz      loc_180018712
0x18001864a  call    __scrt_acquire_startup_lock
0x18001864f  mov     bl, al
0x180018651  mov     [rsp+28h+arg_10], al
0x180018655  mov     dil, 1
0x180018658  cmp     cs:__scrt_current_native_startup_state, 0
0x18001865f  jnz     loc_18001872A
0x180018665  mov     cs:__scrt_current_native_startup_state, 1
0x18001866f  call    __scrt_dllmain_before_initialize_c
0x180018674  test    al, al
0x180018676  jz      short loc_1800186C7
0x180018678  call    _RTC_Initialize
0x18001867d  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180018682  call    __scrt_initialize_default_local_stdio_options
0x180018687  lea     rdx, __xi_z; Last
0x18001868e  lea     rcx, __xi_a; First
0x180018695  call    _initterm_e_0
0x18001869a  test    eax, eax
0x18001869c  jnz     short loc_1800186C7
0x18001869e  call    __scrt_dllmain_after_initialize_c
0x1800186a3  test    al, al
0x1800186a5  jz      short loc_1800186C7
0x1800186a7  lea     rdx, __xc_z; Last
0x1800186ae  lea     rcx, __xc_a; First
0x1800186b5  call    _initterm_0
0x1800186ba  mov     cs:__scrt_current_native_startup_state, 2
0x1800186c4  xor     dil, dil
0x1800186c7  mov     cl, bl
0x1800186c9  call    __scrt_release_startup_lock
0x1800186ce  test    dil, dil
0x1800186d1  jnz     short loc_180018712
0x1800186d3  call    __scrt_get_dyn_tls_init_callback
0x1800186d8  mov     rbx, rax
0x1800186db  cmp     qword ptr [rax], 0
0x1800186df  jz      short loc_180018705
0x1800186e1  mov     rcx, rax
0x1800186e4  call    __scrt_is_nonwritable_in_current_image
0x1800186e9  test    al, al
0x1800186eb  jz      short loc_180018705
0x1800186ed  mov     r8, rsi
0x1800186f0  mov     edx, 2
0x1800186f5  mov     rcx, r14
0x1800186f8  mov     rax, [rbx]
0x1800186fb  mov     r9, cs:__guard_dispatch_icall_fptr
0x180018702  call    r9 ; _guard_dispatch_icall_nop
0x180018705  inc     cs:dword_18002DEC8
0x18001870b  mov     eax, 1
0x180018710  jmp     short loc_180018714
0x180018712  xor     eax, eax
0x180018714  mov     rbx, [rsp+28h+arg_0]
0x180018719  mov     rsi, [rsp+28h+arg_8]
0x18001871e  mov     rdi, [rsp+28h+arg_18]
0x180018723  add     rsp, 20h
0x180018727  pop     r14
0x180018729  retn
0x18001872a  mov     ecx, 7
0x18001872f  call    __scrt_fastfail
0x180018734  nop
0x180018735  int     3; Trap to Debugger
0x18001f548  push    rbp
0x18001f54a  sub     rsp, 20h
0x18001f54e  mov     rbp, rdx
0x18001f551  mov     cl, [rbp+40h]
0x18001f554  add     rsp, 20h
0x18001f558  pop     rbp
0x18001f559  jmp     __scrt_release_startup_lock
```
