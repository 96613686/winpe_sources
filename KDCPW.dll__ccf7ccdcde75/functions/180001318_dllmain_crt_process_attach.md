# dllmain_crt_process_attach

- ea: `0x180001318`
- end: `0x180001412`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800012c0`

## callees

- `0x180001318`
- `0x180001654`
- `0x180001694`
- `0x1800016d0`
- `0x1800017d0`
- `0x1800018a4`
- `0x180001944`
- `0x180001ac8`
- `0x180001af0`
- `0x180001b14`
- `0x180001b24`
- `0x180001b30`
- `0x180001e96`
- `0x180001ea2`
- `0x18000d010`

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
  ++dword_1800123F0;
  return 1;
}

```

## disassembly

```asm
0x180001318  push    rbx
0x18000131a  push    rsi
0x18000131b  push    rdi
0x18000131c  push    r14
0x18000131e  sub     rsp, 28h
0x180001322  mov     rsi, rdx
0x180001325  mov     r14, rcx
0x180001328  xor     ecx, ecx
0x18000132a  call    __scrt_initialize_crt
0x18000132f  test    al, al
0x180001331  jz      loc_1800013FA
0x180001337  call    __scrt_acquire_startup_lock
0x18000133c  mov     bl, al
0x18000133e  mov     [rsp+48h+arg_10], al
0x180001342  mov     dil, 1
0x180001345  cmp     cs:__scrt_current_native_startup_state, 0
0x18000134c  jnz     loc_180001406
0x180001352  mov     cs:__scrt_current_native_startup_state, 1
0x18000135c  call    __scrt_dllmain_before_initialize_c
0x180001361  test    al, al
0x180001363  jz      short loc_1800013B4
0x180001365  call    _RTC_Initialize
0x18000136a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000136f  call    __scrt_initialize_default_local_stdio_options
0x180001374  lea     rdx, __xi_z; Last
0x18000137b  lea     rcx, __xi_a; First
0x180001382  call    _initterm_e_0
0x180001387  test    eax, eax
0x180001389  jnz     short loc_1800013B4
0x18000138b  call    __scrt_dllmain_after_initialize_c
0x180001390  test    al, al
0x180001392  jz      short loc_1800013B4
0x180001394  lea     rdx, __xc_z; Last
0x18000139b  lea     rcx, __xc_a; First
0x1800013a2  call    _initterm_0
0x1800013a7  mov     cs:__scrt_current_native_startup_state, 2
0x1800013b1  xor     dil, dil
0x1800013b4  mov     cl, bl
0x1800013b6  call    __scrt_release_startup_lock
0x1800013bb  test    dil, dil
0x1800013be  jnz     short loc_1800013FA
0x1800013c0  call    __scrt_get_dyn_tls_init_callback
0x1800013c5  mov     rbx, rax
0x1800013c8  cmp     qword ptr [rax], 0
0x1800013cc  jz      short loc_1800013ED
0x1800013ce  mov     rcx, rax
0x1800013d1  call    __scrt_is_nonwritable_in_current_image
0x1800013d6  test    al, al
0x1800013d8  jz      short loc_1800013ED
0x1800013da  mov     r8, rsi
0x1800013dd  mov     edx, 2
0x1800013e2  mov     rcx, r14
0x1800013e5  mov     rax, [rbx]
0x1800013e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ed  inc     cs:dword_1800123F0
0x1800013f3  mov     eax, 1
0x1800013f8  jmp     short loc_1800013FC
0x1800013fa  xor     eax, eax
0x1800013fc  add     rsp, 28h
0x180001400  pop     r14
0x180001402  pop     rdi
0x180001403  pop     rsi
0x180001404  pop     rbx
0x180001405  retn
0x180001406  mov     ecx, 7
0x18000140b  call    __scrt_fastfail
0x18000cb7c  push    rbp
0x18000cb7e  sub     rsp, 20h
0x18000cb82  mov     rbp, rdx
0x18000cb85  mov     cl, [rbp+60h]
0x18000cb88  add     rsp, 20h
0x18000cb8c  pop     rbp
0x18000cb8d  jmp     __scrt_release_startup_lock
```
