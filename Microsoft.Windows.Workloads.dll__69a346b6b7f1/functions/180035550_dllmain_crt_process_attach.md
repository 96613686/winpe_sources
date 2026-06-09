# dllmain_crt_process_attach

- ea: `0x180035550`
- end: `0x180035666`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180035500`

## callees

- `0x1800350a4`
- `0x1800350e0`
- `0x180035114`
- `0x180035210`
- `0x1800352d8`
- `0x180035370`
- `0x180035550`
- `0x180035e88`
- `0x180036084`
- `0x1800360a0`
- `0x1800360bc`
- `0x1800360c4`
- `0x180039793`
- `0x180039799`
- `0x18003bed0`

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
    JUMPOUT(0x180035666LL);
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
  ++dword_1800595A8;
  return 1;
}

```

## disassembly

```asm
0x180035550  mov     [rsp+arg_0], rbx
0x180035555  mov     [rsp+arg_8], rsi
0x18003555a  mov     [rsp+arg_18], rdi
0x18003555f  push    r14
0x180035561  sub     rsp, 20h
0x180035565  mov     rsi, rdx
0x180035568  mov     r14, rcx
0x18003556b  xor     ecx, ecx
0x18003556d  call    __scrt_initialize_crt
0x180035572  test    al, al
0x180035574  jz      loc_180035642
0x18003557a  call    __scrt_acquire_startup_lock
0x18003557f  mov     bl, al
0x180035581  mov     [rsp+28h+arg_10], al
0x180035585  mov     dil, 1
0x180035588  cmp     cs:__scrt_current_native_startup_state, 0
0x18003558f  jnz     loc_18003565A
0x180035595  mov     cs:__scrt_current_native_startup_state, 1
0x18003559f  call    __scrt_dllmain_before_initialize_c
0x1800355a4  test    al, al
0x1800355a6  jz      short loc_1800355F7
0x1800355a8  call    _RTC_Initialize
0x1800355ad  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800355b2  call    __scrt_initialize_default_local_stdio_options
0x1800355b7  lea     rdx, __xi_z; Last
0x1800355be  lea     rcx, __xi_a; First
0x1800355c5  call    _initterm_e_0
0x1800355ca  test    eax, eax
0x1800355cc  jnz     short loc_1800355F7
0x1800355ce  call    __scrt_dllmain_after_initialize_c
0x1800355d3  test    al, al
0x1800355d5  jz      short loc_1800355F7
0x1800355d7  lea     rdx, __xc_z; Last
0x1800355de  lea     rcx, __xc_a; First
0x1800355e5  call    _initterm_0
0x1800355ea  mov     cs:__scrt_current_native_startup_state, 2
0x1800355f4  xor     dil, dil
0x1800355f7  mov     cl, bl
0x1800355f9  call    __scrt_release_startup_lock
0x1800355fe  test    dil, dil
0x180035601  jnz     short loc_180035642
0x180035603  call    __scrt_get_dyn_tls_init_callback
0x180035608  mov     rbx, rax
0x18003560b  cmp     qword ptr [rax], 0
0x18003560f  jz      short loc_180035635
0x180035611  mov     rcx, rax
0x180035614  call    __scrt_is_nonwritable_in_current_image
0x180035619  test    al, al
0x18003561b  jz      short loc_180035635
0x18003561d  mov     r8, rsi
0x180035620  mov     edx, 2
0x180035625  mov     rcx, r14
0x180035628  mov     rax, [rbx]
0x18003562b  mov     r9, cs:__guard_dispatch_icall_fptr
0x180035632  call    r9 ; _guard_dispatch_icall_nop
0x180035635  inc     cs:dword_1800595A8
0x18003563b  mov     eax, 1
0x180035640  jmp     short loc_180035644
0x180035642  xor     eax, eax
0x180035644  mov     rbx, [rsp+28h+arg_0]
0x180035649  mov     rsi, [rsp+28h+arg_8]
0x18003564e  mov     rdi, [rsp+28h+arg_18]
0x180035653  add     rsp, 20h
0x180035657  pop     r14
0x180035659  retn
0x18003565a  mov     ecx, 7
0x18003565f  call    __scrt_fastfail
0x180035664  nop
0x180035665  int     3; Trap to Debugger
0x180040b77  push    rbp
0x180040b79  sub     rsp, 20h
0x180040b7d  mov     rbp, rdx
0x180040b80  mov     cl, [rbp+40h]
0x180040b83  add     rsp, 20h
0x180040b87  pop     rbp
0x180040b88  jmp     __scrt_release_startup_lock
```
