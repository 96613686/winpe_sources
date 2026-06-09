# dllmain_crt_process_attach

- ea: `0x180001388`
- end: `0x180001482`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001330`

## callees

- `0x180001388`
- `0x1800017c0`
- `0x1800017e8`
- `0x18000180c`
- `0x18000184c`
- `0x180001888`
- `0x180001988`
- `0x180001a5c`
- `0x180001afc`
- `0x180001bb8`
- `0x180001bc8`
- `0x180001bd4`
- `0x18000201c`
- `0x180002028`
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
  ++dword_180013390;
  return 1;
}

```

## disassembly

```asm
0x180001388  push    rbx
0x18000138a  push    rsi
0x18000138b  push    rdi
0x18000138c  push    r14
0x18000138e  sub     rsp, 28h
0x180001392  mov     rsi, rdx
0x180001395  mov     r14, rcx
0x180001398  xor     ecx, ecx
0x18000139a  call    __scrt_initialize_crt
0x18000139f  test    al, al
0x1800013a1  jz      loc_18000146A
0x1800013a7  call    __scrt_acquire_startup_lock
0x1800013ac  mov     bl, al
0x1800013ae  mov     [rsp+48h+arg_10], al
0x1800013b2  mov     dil, 1
0x1800013b5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800013bc  jnz     loc_180001476
0x1800013c2  mov     cs:__scrt_current_native_startup_state, 1
0x1800013cc  call    __scrt_dllmain_before_initialize_c
0x1800013d1  test    al, al
0x1800013d3  jz      short loc_180001424
0x1800013d5  call    _RTC_Initialize
0x1800013da  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800013df  call    __scrt_initialize_default_local_stdio_options
0x1800013e4  lea     rdx, __xi_z; Last
0x1800013eb  lea     rcx, __xi_a; First
0x1800013f2  call    _initterm_e_0
0x1800013f7  test    eax, eax
0x1800013f9  jnz     short loc_180001424
0x1800013fb  call    __scrt_dllmain_after_initialize_c
0x180001400  test    al, al
0x180001402  jz      short loc_180001424
0x180001404  lea     rdx, __xc_z; Last
0x18000140b  lea     rcx, __xc_a; First
0x180001412  call    _initterm_0
0x180001417  mov     cs:__scrt_current_native_startup_state, 2
0x180001421  xor     dil, dil
0x180001424  mov     cl, bl
0x180001426  call    __scrt_release_startup_lock
0x18000142b  test    dil, dil
0x18000142e  jnz     short loc_18000146A
0x180001430  call    __scrt_get_dyn_tls_init_callback
0x180001435  mov     rbx, rax
0x180001438  cmp     qword ptr [rax], 0
0x18000143c  jz      short loc_18000145D
0x18000143e  mov     rcx, rax
0x180001441  call    __scrt_is_nonwritable_in_current_image
0x180001446  test    al, al
0x180001448  jz      short loc_18000145D
0x18000144a  mov     r8, rsi
0x18000144d  mov     edx, 2
0x180001452  mov     rcx, r14
0x180001455  mov     rax, [rbx]
0x180001458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000145d  inc     cs:dword_180013390
0x180001463  mov     eax, 1
0x180001468  jmp     short loc_18000146C
0x18000146a  xor     eax, eax
0x18000146c  add     rsp, 28h
0x180001470  pop     r14
0x180001472  pop     rdi
0x180001473  pop     rsi
0x180001474  pop     rbx
0x180001475  retn
0x180001476  mov     ecx, 7
0x18000147b  call    __scrt_fastfail
0x18000bc8c  push    rbp
0x18000bc8e  sub     rsp, 20h
0x18000bc92  mov     rbp, rdx
0x18000bc95  mov     cl, [rbp+60h]
0x18000bc98  add     rsp, 20h
0x18000bc9c  pop     rbp
0x18000bc9d  jmp     __scrt_release_startup_lock
```
