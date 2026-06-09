# dllmain_crt_process_attach

- ea: `0x180006fc8`
- end: `0x1800070c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180006f70`

## callees

- `0x180006fc8`
- `0x1800073c0`
- `0x1800073e8`
- `0x18000740c`
- `0x18000744c`
- `0x180007488`
- `0x180007588`
- `0x18000765c`
- `0x1800076fc`
- `0x180007758`
- `0x180007768`
- `0x180007774`
- `0x180007ae6`
- `0x180007af2`
- `0x18000c010`

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
  ++dword_1800120D0;
  return 1;
}

```

## disassembly

```asm
0x180006fc8  push    rbx
0x180006fca  push    rsi
0x180006fcb  push    rdi
0x180006fcc  push    r14
0x180006fce  sub     rsp, 28h
0x180006fd2  mov     rsi, rdx
0x180006fd5  mov     r14, rcx
0x180006fd8  xor     ecx, ecx
0x180006fda  call    __scrt_initialize_crt
0x180006fdf  test    al, al
0x180006fe1  jz      loc_1800070AA
0x180006fe7  call    __scrt_acquire_startup_lock
0x180006fec  mov     bl, al
0x180006fee  mov     [rsp+48h+arg_10], al
0x180006ff2  mov     dil, 1
0x180006ff5  cmp     cs:__scrt_current_native_startup_state, 0
0x180006ffc  jnz     loc_1800070B6
0x180007002  mov     cs:__scrt_current_native_startup_state, 1
0x18000700c  call    __scrt_dllmain_before_initialize_c
0x180007011  test    al, al
0x180007013  jz      short loc_180007064
0x180007015  call    _RTC_Initialize
0x18000701a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000701f  call    __scrt_initialize_default_local_stdio_options
0x180007024  lea     rdx, __xi_z; Last
0x18000702b  lea     rcx, __xi_a; First
0x180007032  call    _initterm_e_0
0x180007037  test    eax, eax
0x180007039  jnz     short loc_180007064
0x18000703b  call    __scrt_dllmain_after_initialize_c
0x180007040  test    al, al
0x180007042  jz      short loc_180007064
0x180007044  lea     rdx, __xc_z; Last
0x18000704b  lea     rcx, __xc_a; First
0x180007052  call    _initterm_0
0x180007057  mov     cs:__scrt_current_native_startup_state, 2
0x180007061  xor     dil, dil
0x180007064  mov     cl, bl
0x180007066  call    __scrt_release_startup_lock
0x18000706b  test    dil, dil
0x18000706e  jnz     short loc_1800070AA
0x180007070  call    __scrt_get_dyn_tls_init_callback
0x180007075  mov     rbx, rax
0x180007078  cmp     qword ptr [rax], 0
0x18000707c  jz      short loc_18000709D
0x18000707e  mov     rcx, rax
0x180007081  call    __scrt_is_nonwritable_in_current_image
0x180007086  test    al, al
0x180007088  jz      short loc_18000709D
0x18000708a  mov     r8, rsi
0x18000708d  mov     edx, 2
0x180007092  mov     rcx, r14
0x180007095  mov     rax, [rbx]
0x180007098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709d  inc     cs:dword_1800120D0
0x1800070a3  mov     eax, 1
0x1800070a8  jmp     short loc_1800070AC
0x1800070aa  xor     eax, eax
0x1800070ac  add     rsp, 28h
0x1800070b0  pop     r14
0x1800070b2  pop     rdi
0x1800070b3  pop     rsi
0x1800070b4  pop     rbx
0x1800070b5  retn
0x1800070b6  mov     ecx, 7
0x1800070bb  call    __scrt_fastfail
0x18000be5c  push    rbp
0x18000be5e  sub     rsp, 20h
0x18000be62  mov     rbp, rdx
0x18000be65  mov     cl, [rbp+60h]
0x18000be68  add     rsp, 20h
0x18000be6c  pop     rbp
0x18000be6d  jmp     __scrt_release_startup_lock
```
