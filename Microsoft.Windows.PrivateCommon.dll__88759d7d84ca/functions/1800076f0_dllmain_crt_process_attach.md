# dllmain_crt_process_attach

- ea: `0x1800076f0`
- end: `0x180007806`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1800076a0`

## callees

- `0x1800072f0`
- `0x18000732c`
- `0x180007360`
- `0x18000745c`
- `0x180007524`
- `0x1800075bc`
- `0x1800076f0`
- `0x180007ee0`
- `0x1800080ec`
- `0x180008110`
- `0x18000812c`
- `0x180008134`
- `0x18000b5f2`
- `0x18000b5f8`
- `0x18000b930`

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
    _scrt_fastfail(7u);
    __debugbreak();
    JUMPOUT(0x180007806LL);
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
  ++dword_180015BB8;
  return 1;
}

```

## disassembly

```asm
0x1800076f0  mov     [rsp+arg_0], rbx
0x1800076f5  mov     [rsp+arg_8], rsi
0x1800076fa  mov     [rsp+arg_18], rdi
0x1800076ff  push    r14
0x180007701  sub     rsp, 20h
0x180007705  mov     rsi, rdx
0x180007708  mov     r14, rcx
0x18000770b  xor     ecx, ecx
0x18000770d  call    __scrt_initialize_crt
0x180007712  test    al, al
0x180007714  jz      loc_1800077E2
0x18000771a  call    __scrt_acquire_startup_lock
0x18000771f  mov     bl, al
0x180007721  mov     [rsp+28h+arg_10], al
0x180007725  mov     dil, 1
0x180007728  cmp     cs:__scrt_current_native_startup_state, 0
0x18000772f  jnz     loc_1800077FA
0x180007735  mov     cs:__scrt_current_native_startup_state, 1
0x18000773f  call    __scrt_dllmain_before_initialize_c
0x180007744  test    al, al
0x180007746  jz      short loc_180007797
0x180007748  call    _RTC_Initialize
0x18000774d  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180007752  call    __scrt_initialize_default_local_stdio_options
0x180007757  lea     rdx, __xi_z; Last
0x18000775e  lea     rcx, __xi_a; First
0x180007765  call    _initterm_e_0
0x18000776a  test    eax, eax
0x18000776c  jnz     short loc_180007797
0x18000776e  call    __scrt_dllmain_after_initialize_c
0x180007773  test    al, al
0x180007775  jz      short loc_180007797
0x180007777  lea     rdx, __xc_z; Last
0x18000777e  lea     rcx, __xc_a; First
0x180007785  call    _initterm_0
0x18000778a  mov     cs:__scrt_current_native_startup_state, 2
0x180007794  xor     dil, dil
0x180007797  mov     cl, bl
0x180007799  call    __scrt_release_startup_lock
0x18000779e  test    dil, dil
0x1800077a1  jnz     short loc_1800077E2
0x1800077a3  call    __scrt_get_dyn_tls_init_callback
0x1800077a8  mov     rbx, rax
0x1800077ab  cmp     qword ptr [rax], 0
0x1800077af  jz      short loc_1800077D5
0x1800077b1  mov     rcx, rax
0x1800077b4  call    __scrt_is_nonwritable_in_current_image
0x1800077b9  test    al, al
0x1800077bb  jz      short loc_1800077D5
0x1800077bd  mov     r8, rsi
0x1800077c0  mov     edx, 2
0x1800077c5  mov     rcx, r14
0x1800077c8  mov     rax, [rbx]
0x1800077cb  mov     r9, cs:__guard_dispatch_icall_fptr
0x1800077d2  call    r9 ; _guard_dispatch_icall_nop
0x1800077d5  inc     cs:dword_180015BB8
0x1800077db  mov     eax, 1
0x1800077e0  jmp     short loc_1800077E4
0x1800077e2  xor     eax, eax
0x1800077e4  mov     rbx, [rsp+28h+arg_0]
0x1800077e9  mov     rsi, [rsp+28h+arg_8]
0x1800077ee  mov     rdi, [rsp+28h+arg_18]
0x1800077f3  add     rsp, 20h
0x1800077f7  pop     r14
0x1800077f9  retn
0x1800077fa  mov     ecx, 7
0x1800077ff  call    __scrt_fastfail
0x180007804  nop
0x180007805  int     3; Trap to Debugger
0x18000c9b2  push    rbp
0x18000c9b4  sub     rsp, 20h
0x18000c9b8  mov     rbp, rdx
0x18000c9bb  mov     cl, [rbp+40h]
0x18000c9be  add     rsp, 20h
0x18000c9c2  pop     rbp
0x18000c9c3  jmp     __scrt_release_startup_lock
```
