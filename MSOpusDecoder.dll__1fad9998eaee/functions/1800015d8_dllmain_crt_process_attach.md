# dllmain_crt_process_attach

- ea: `0x1800015d8`
- end: `0x1800016d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x1800015d8`
- `0x180001940`
- `0x180001980`
- `0x1800019bc`
- `0x180001abc`
- `0x180001b90`
- `0x180001c30`
- `0x180001dd8`
- `0x180001e00`
- `0x180001e24`
- `0x180001e34`
- `0x180001e40`
- `0x180002166`
- `0x180002172`
- `0x180024010`

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
  ++dword_1800352F8;
  return 1;
}

```

## disassembly

```asm
0x1800015d8  push    rbx
0x1800015da  push    rsi
0x1800015db  push    rdi
0x1800015dc  push    r14
0x1800015de  sub     rsp, 28h
0x1800015e2  mov     rsi, rdx
0x1800015e5  mov     r14, rcx
0x1800015e8  xor     ecx, ecx
0x1800015ea  call    __scrt_initialize_crt
0x1800015ef  test    al, al
0x1800015f1  jz      loc_1800016BA
0x1800015f7  call    __scrt_acquire_startup_lock
0x1800015fc  mov     bl, al
0x1800015fe  mov     [rsp+48h+arg_10], al
0x180001602  mov     dil, 1
0x180001605  cmp     cs:__scrt_current_native_startup_state, 0
0x18000160c  jnz     loc_1800016C6
0x180001612  mov     cs:__scrt_current_native_startup_state, 1
0x18000161c  call    __scrt_dllmain_before_initialize_c
0x180001621  test    al, al
0x180001623  jz      short loc_180001674
0x180001625  call    _RTC_Initialize
0x18000162a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000162f  call    __scrt_initialize_default_local_stdio_options
0x180001634  lea     rdx, __xi_z; Last
0x18000163b  lea     rcx, __xi_a; First
0x180001642  call    _initterm_e_0
0x180001647  test    eax, eax
0x180001649  jnz     short loc_180001674
0x18000164b  call    __scrt_dllmain_after_initialize_c
0x180001650  test    al, al
0x180001652  jz      short loc_180001674
0x180001654  lea     rdx, __xc_z; Last
0x18000165b  lea     rcx, __xc_a; First
0x180001662  call    _initterm_0
0x180001667  mov     cs:__scrt_current_native_startup_state, 2
0x180001671  xor     dil, dil
0x180001674  mov     cl, bl
0x180001676  call    __scrt_release_startup_lock
0x18000167b  test    dil, dil
0x18000167e  jnz     short loc_1800016BA
0x180001680  call    __scrt_get_dyn_tls_init_callback
0x180001685  mov     rbx, rax
0x180001688  cmp     qword ptr [rax], 0
0x18000168c  jz      short loc_1800016AD
0x18000168e  mov     rcx, rax
0x180001691  call    __scrt_is_nonwritable_in_current_image
0x180001696  test    al, al
0x180001698  jz      short loc_1800016AD
0x18000169a  mov     r8, rsi
0x18000169d  mov     edx, 2
0x1800016a2  mov     rcx, r14
0x1800016a5  mov     rax, [rbx]
0x1800016a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ad  inc     cs:dword_1800352F8
0x1800016b3  mov     eax, 1
0x1800016b8  jmp     short loc_1800016BC
0x1800016ba  xor     eax, eax
0x1800016bc  add     rsp, 28h
0x1800016c0  pop     r14
0x1800016c2  pop     rdi
0x1800016c3  pop     rsi
0x1800016c4  pop     rbx
0x1800016c5  retn
0x1800016c6  mov     ecx, 7
0x1800016cb  call    __scrt_fastfail
0x180022ecc  push    rbp
0x180022ece  sub     rsp, 20h
0x180022ed2  mov     rbp, rdx
0x180022ed5  mov     cl, [rbp+60h]
0x180022ed8  add     rsp, 20h
0x180022edc  pop     rbp
0x180022edd  jmp     __scrt_release_startup_lock
```
