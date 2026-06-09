# dllmain_crt_process_attach

- ea: `0x1800013a8`
- end: `0x1800014a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001350`

## callees

- `0x1800013a8`
- `0x1800017c0`
- `0x180001800`
- `0x18000183c`
- `0x18000193c`
- `0x180001a10`
- `0x180001ab0`
- `0x180001c34`
- `0x180001c5c`
- `0x180001c80`
- `0x180001c90`
- `0x180001c9c`
- `0x180002016`
- `0x180002022`
- `0x180012010`

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
  ++dword_18001A210;
  return 1;
}

```

## disassembly

```asm
0x1800013a8  push    rbx
0x1800013aa  push    rsi
0x1800013ab  push    rdi
0x1800013ac  push    r14
0x1800013ae  sub     rsp, 28h
0x1800013b2  mov     rsi, rdx
0x1800013b5  mov     r14, rcx
0x1800013b8  xor     ecx, ecx
0x1800013ba  call    __scrt_initialize_crt
0x1800013bf  test    al, al
0x1800013c1  jz      loc_18000148A
0x1800013c7  call    __scrt_acquire_startup_lock
0x1800013cc  mov     bl, al
0x1800013ce  mov     [rsp+48h+arg_10], al
0x1800013d2  mov     dil, 1
0x1800013d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800013dc  jnz     loc_180001496
0x1800013e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800013ec  call    __scrt_dllmain_before_initialize_c
0x1800013f1  test    al, al
0x1800013f3  jz      short loc_180001444
0x1800013f5  call    _RTC_Initialize
0x1800013fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800013ff  call    __scrt_initialize_default_local_stdio_options
0x180001404  lea     rdx, __xi_z; Last
0x18000140b  lea     rcx, __xi_a; First
0x180001412  call    _initterm_e_0
0x180001417  test    eax, eax
0x180001419  jnz     short loc_180001444
0x18000141b  call    __scrt_dllmain_after_initialize_c
0x180001420  test    al, al
0x180001422  jz      short loc_180001444
0x180001424  lea     rdx, __xc_z; Last
0x18000142b  lea     rcx, __xc_a; First
0x180001432  call    _initterm_0
0x180001437  mov     cs:__scrt_current_native_startup_state, 2
0x180001441  xor     dil, dil
0x180001444  mov     cl, bl
0x180001446  call    __scrt_release_startup_lock
0x18000144b  test    dil, dil
0x18000144e  jnz     short loc_18000148A
0x180001450  call    __scrt_get_dyn_tls_init_callback
0x180001455  mov     rbx, rax
0x180001458  cmp     qword ptr [rax], 0
0x18000145c  jz      short loc_18000147D
0x18000145e  mov     rcx, rax
0x180001461  call    __scrt_is_nonwritable_in_current_image
0x180001466  test    al, al
0x180001468  jz      short loc_18000147D
0x18000146a  mov     r8, rsi
0x18000146d  mov     edx, 2
0x180001472  mov     rcx, r14
0x180001475  mov     rax, [rbx]
0x180001478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000147d  inc     cs:dword_18001A210
0x180001483  mov     eax, 1
0x180001488  jmp     short loc_18000148C
0x18000148a  xor     eax, eax
0x18000148c  add     rsp, 28h
0x180001490  pop     r14
0x180001492  pop     rdi
0x180001493  pop     rsi
0x180001494  pop     rbx
0x180001495  retn
0x180001496  mov     ecx, 7
0x18000149b  call    __scrt_fastfail
0x18001151c  push    rbp
0x18001151e  sub     rsp, 20h
0x180011522  mov     rbp, rdx
0x180011525  mov     cl, [rbp+60h]
0x180011528  add     rsp, 20h
0x18001152c  pop     rbp
0x18001152d  jmp     __scrt_release_startup_lock
```
