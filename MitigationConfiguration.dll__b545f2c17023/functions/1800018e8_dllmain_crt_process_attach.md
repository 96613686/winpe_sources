# dllmain_crt_process_attach

- ea: `0x1800018e8`
- end: `0x1800019e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001890`

## callees

- `0x1800018e8`
- `0x180001c68`
- `0x180001ca8`
- `0x180001ce4`
- `0x180001de4`
- `0x180001eb8`
- `0x180001f58`
- `0x18000211c`
- `0x180002144`
- `0x180002168`
- `0x180002178`
- `0x180002184`
- `0x180002536`
- `0x180002542`
- `0x180015010`

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
  ++dword_18001C270;
  return 1;
}

```

## disassembly

```asm
0x1800018e8  push    rbx
0x1800018ea  push    rsi
0x1800018eb  push    rdi
0x1800018ec  push    r14
0x1800018ee  sub     rsp, 28h
0x1800018f2  mov     rsi, rdx
0x1800018f5  mov     r14, rcx
0x1800018f8  xor     ecx, ecx
0x1800018fa  call    __scrt_initialize_crt
0x1800018ff  test    al, al
0x180001901  jz      loc_1800019CA
0x180001907  call    __scrt_acquire_startup_lock
0x18000190c  mov     bl, al
0x18000190e  mov     [rsp+48h+arg_10], al
0x180001912  mov     dil, 1
0x180001915  cmp     cs:__scrt_current_native_startup_state, 0
0x18000191c  jnz     loc_1800019D6
0x180001922  mov     cs:__scrt_current_native_startup_state, 1
0x18000192c  call    __scrt_dllmain_before_initialize_c
0x180001931  test    al, al
0x180001933  jz      short loc_180001984
0x180001935  call    _RTC_Initialize
0x18000193a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000193f  call    __scrt_initialize_default_local_stdio_options
0x180001944  lea     rdx, __xi_z; Last
0x18000194b  lea     rcx, __xi_a; First
0x180001952  call    _initterm_e_0
0x180001957  test    eax, eax
0x180001959  jnz     short loc_180001984
0x18000195b  call    __scrt_dllmain_after_initialize_c
0x180001960  test    al, al
0x180001962  jz      short loc_180001984
0x180001964  lea     rdx, __xc_z; Last
0x18000196b  lea     rcx, __xc_a; First
0x180001972  call    _initterm_0
0x180001977  mov     cs:__scrt_current_native_startup_state, 2
0x180001981  xor     dil, dil
0x180001984  mov     cl, bl
0x180001986  call    __scrt_release_startup_lock
0x18000198b  test    dil, dil
0x18000198e  jnz     short loc_1800019CA
0x180001990  call    __scrt_get_dyn_tls_init_callback
0x180001995  mov     rbx, rax
0x180001998  cmp     qword ptr [rax], 0
0x18000199c  jz      short loc_1800019BD
0x18000199e  mov     rcx, rax
0x1800019a1  call    __scrt_is_nonwritable_in_current_image
0x1800019a6  test    al, al
0x1800019a8  jz      short loc_1800019BD
0x1800019aa  mov     r8, rsi
0x1800019ad  mov     edx, 2
0x1800019b2  mov     rcx, r14
0x1800019b5  mov     rax, [rbx]
0x1800019b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019bd  inc     cs:dword_18001C270
0x1800019c3  mov     eax, 1
0x1800019c8  jmp     short loc_1800019CC
0x1800019ca  xor     eax, eax
0x1800019cc  add     rsp, 28h
0x1800019d0  pop     r14
0x1800019d2  pop     rdi
0x1800019d3  pop     rsi
0x1800019d4  pop     rbx
0x1800019d5  retn
0x1800019d6  mov     ecx, 7
0x1800019db  call    __scrt_fastfail
0x180013b3c  push    rbp
0x180013b3e  sub     rsp, 20h
0x180013b42  mov     rbp, rdx
0x180013b45  mov     cl, [rbp+60h]
0x180013b48  add     rsp, 20h
0x180013b4c  pop     rbp
0x180013b4d  jmp     __scrt_release_startup_lock
```
