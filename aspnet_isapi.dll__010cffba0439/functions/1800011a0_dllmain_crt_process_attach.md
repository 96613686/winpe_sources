# dllmain_crt_process_attach

- ea: `0x1800011a0`
- end: `0x1800012b6`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180001150`

## callees

- `0x1800011a0`
- `0x18000160c`
- `0x180001638`
- `0x180001654`
- `0x180001690`
- `0x1800016c4`
- `0x1800017c0`
- `0x180001898`
- `0x180001930`
- `0x180001980`
- `0x180001990`
- `0x180001adc`
- `0x180001eb2`
- `0x180001eb8`
- `0x180001f00`

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
    JUMPOUT(0x1800012B6LL);
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
  ++dword_180003048;
  return 1;
}

```

## disassembly

```asm
0x1800011a0  mov     [rsp+arg_0], rbx
0x1800011a5  mov     [rsp+arg_8], rsi
0x1800011aa  mov     [rsp+arg_18], rdi
0x1800011af  push    r14
0x1800011b1  sub     rsp, 20h
0x1800011b5  mov     rsi, rdx
0x1800011b8  mov     r14, rcx
0x1800011bb  xor     ecx, ecx
0x1800011bd  call    __scrt_initialize_crt
0x1800011c2  test    al, al
0x1800011c4  jz      loc_180001292
0x1800011ca  call    __scrt_acquire_startup_lock
0x1800011cf  mov     bl, al
0x1800011d1  mov     [rsp+28h+arg_10], al
0x1800011d5  mov     dil, 1
0x1800011d8  cmp     cs:__scrt_current_native_startup_state, 0
0x1800011df  jnz     loc_1800012AA
0x1800011e5  mov     cs:__scrt_current_native_startup_state, 1
0x1800011ef  call    __scrt_dllmain_before_initialize_c
0x1800011f4  test    al, al
0x1800011f6  jz      short loc_180001247
0x1800011f8  call    _RTC_Initialize
0x1800011fd  call    ?__scrt_initialize_type_info@@YAXXZ
0x180001202  call    __scrt_initialize_default_local_stdio_options
0x180001207  lea     rdx, __xi_z; Last
0x18000120e  lea     rcx, __xi_a; First
0x180001215  call    _initterm_e_0
0x18000121a  test    eax, eax
0x18000121c  jnz     short loc_180001247
0x18000121e  call    __scrt_dllmain_after_initialize_c
0x180001223  test    al, al
0x180001225  jz      short loc_180001247
0x180001227  lea     rdx, __xc_z; Last
0x18000122e  lea     rcx, __xc_a; First
0x180001235  call    _initterm_0
0x18000123a  mov     cs:__scrt_current_native_startup_state, 2
0x180001244  xor     dil, dil
0x180001247  mov     cl, bl
0x180001249  call    __scrt_release_startup_lock
0x18000124e  test    dil, dil
0x180001251  jnz     short loc_180001292
0x180001253  call    __scrt_get_dyn_tls_init_callback
0x180001258  mov     rbx, rax
0x18000125b  cmp     qword ptr [rax], 0
0x18000125f  jz      short loc_180001285
0x180001261  mov     rcx, rax
0x180001264  call    __scrt_is_nonwritable_in_current_image
0x180001269  test    al, al
0x18000126b  jz      short loc_180001285
0x18000126d  mov     r8, rsi
0x180001270  mov     edx, 2
0x180001275  mov     rcx, r14
0x180001278  mov     rax, [rbx]
0x18000127b  mov     r9, cs:__guard_dispatch_icall_fptr
0x180001282  call    r9 ; _guard_dispatch_icall_nop
0x180001285  inc     cs:dword_180003048
0x18000128b  mov     eax, 1
0x180001290  jmp     short loc_180001294
0x180001292  xor     eax, eax
0x180001294  mov     rbx, [rsp+28h+arg_0]
0x180001299  mov     rsi, [rsp+28h+arg_8]
0x18000129e  mov     rdi, [rsp+28h+arg_18]
0x1800012a3  add     rsp, 20h
0x1800012a7  pop     r14
0x1800012a9  retn
0x1800012aa  mov     ecx, 7
0x1800012af  call    __scrt_fastfail
0x1800012b4  nop
0x1800012b5  int     3; Trap to Debugger
0x180001f26  push    rbp
0x180001f28  sub     rsp, 20h
0x180001f2c  mov     rbp, rdx
0x180001f2f  mov     cl, [rbp+40h]
0x180001f32  add     rsp, 20h
0x180001f36  pop     rbp
0x180001f37  jmp     __scrt_release_startup_lock
```
