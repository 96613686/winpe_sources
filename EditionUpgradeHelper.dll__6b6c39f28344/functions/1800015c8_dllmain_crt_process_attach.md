# dllmain_crt_process_attach

- ea: `0x1800015c8`
- end: `0x1800016c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001570`

## callees

- `0x1800015c8`
- `0x180001904`
- `0x180001944`
- `0x180001980`
- `0x180001a80`
- `0x180001b54`
- `0x180001bf4`
- `0x180001df8`
- `0x180001e20`
- `0x180001e44`
- `0x180001e54`
- `0x180001e60`
- `0x1800023d6`
- `0x1800023e2`
- `0x180027010`

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
    _scrt_fastfail(7u);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
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
  ++dword_18002F5D0;
  return 1;
}

```

## disassembly

```asm
0x1800015c8  push    rbx
0x1800015ca  push    rsi
0x1800015cb  push    rdi
0x1800015cc  push    r14
0x1800015ce  sub     rsp, 28h
0x1800015d2  mov     rsi, rdx
0x1800015d5  mov     r14, rcx
0x1800015d8  xor     ecx, ecx
0x1800015da  call    __scrt_initialize_crt
0x1800015df  test    al, al
0x1800015e1  jz      loc_1800016AA
0x1800015e7  call    __scrt_acquire_startup_lock
0x1800015ec  mov     bl, al
0x1800015ee  mov     [rsp+48h+arg_10], al
0x1800015f2  mov     dil, 1
0x1800015f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800015fc  jnz     loc_1800016B6
0x180001602  mov     cs:__scrt_current_native_startup_state, 1
0x18000160c  call    __scrt_dllmain_before_initialize_c
0x180001611  test    al, al
0x180001613  jz      short loc_180001664
0x180001615  call    _RTC_Initialize
0x18000161a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000161f  call    __scrt_initialize_default_local_stdio_options
0x180001624  lea     rdx, __xi_z; Last
0x18000162b  lea     rcx, __xi_a; First
0x180001632  call    _initterm_e_0
0x180001637  test    eax, eax
0x180001639  jnz     short loc_180001664
0x18000163b  call    __scrt_dllmain_after_initialize_c
0x180001640  test    al, al
0x180001642  jz      short loc_180001664
0x180001644  lea     rdx, __xc_z; Last
0x18000164b  lea     rcx, __xc_a; First
0x180001652  call    _initterm_0
0x180001657  mov     cs:__scrt_current_native_startup_state, 2
0x180001661  xor     dil, dil
0x180001664  mov     cl, bl
0x180001666  call    __scrt_release_startup_lock
0x18000166b  test    dil, dil
0x18000166e  jnz     short loc_1800016AA
0x180001670  call    __scrt_get_dyn_tls_init_callback
0x180001675  mov     rbx, rax
0x180001678  cmp     qword ptr [rax], 0
0x18000167c  jz      short loc_18000169D
0x18000167e  mov     rcx, rax
0x180001681  call    __scrt_is_nonwritable_in_current_image
0x180001686  test    al, al
0x180001688  jz      short loc_18000169D
0x18000168a  mov     r8, rsi
0x18000168d  mov     edx, 2
0x180001692  mov     rcx, r14
0x180001695  mov     rax, [rbx]
0x180001698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000169d  inc     cs:dword_18002F5D0
0x1800016a3  mov     eax, 1
0x1800016a8  jmp     short loc_1800016AC
0x1800016aa  xor     eax, eax
0x1800016ac  add     rsp, 28h
0x1800016b0  pop     r14
0x1800016b2  pop     rdi
0x1800016b3  pop     rsi
0x1800016b4  pop     rbx
0x1800016b5  retn
0x1800016b6  mov     ecx, 7
0x1800016bb  call    __scrt_fastfail
0x1800266cc  push    rbp
0x1800266ce  sub     rsp, 20h
0x1800266d2  mov     rbp, rdx
0x1800266d5  mov     cl, [rbp+60h]
0x1800266d8  add     rsp, 20h
0x1800266dc  pop     rbp
0x1800266dd  jmp     __scrt_release_startup_lock
```
