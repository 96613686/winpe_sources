# dllmain_crt_process_attach

- ea: `0x1800094b8`
- end: `0x1800095b2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180009460`

## callees

- `0x1800094b8`
- `0x1800097f4`
- `0x180009834`
- `0x180009870`
- `0x180009970`
- `0x180009a44`
- `0x180009ae4`
- `0x180009cc0`
- `0x180009ce8`
- `0x180009d0c`
- `0x180009d1c`
- `0x180009d28`
- `0x18000a066`
- `0x18000a072`
- `0x180016010`

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
  ++dword_18001F390;
  return 1;
}

```

## disassembly

```asm
0x1800094b8  push    rbx
0x1800094ba  push    rsi
0x1800094bb  push    rdi
0x1800094bc  push    r14
0x1800094be  sub     rsp, 28h
0x1800094c2  mov     rsi, rdx
0x1800094c5  mov     r14, rcx
0x1800094c8  xor     ecx, ecx
0x1800094ca  call    __scrt_initialize_crt
0x1800094cf  test    al, al
0x1800094d1  jz      loc_18000959A
0x1800094d7  call    __scrt_acquire_startup_lock
0x1800094dc  mov     bl, al
0x1800094de  mov     [rsp+48h+arg_10], al
0x1800094e2  mov     dil, 1
0x1800094e5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800094ec  jnz     loc_1800095A6
0x1800094f2  mov     cs:__scrt_current_native_startup_state, 1
0x1800094fc  call    __scrt_dllmain_before_initialize_c
0x180009501  test    al, al
0x180009503  jz      short loc_180009554
0x180009505  call    _RTC_Initialize
0x18000950a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000950f  call    __scrt_initialize_default_local_stdio_options
0x180009514  lea     rdx, __xi_z; Last
0x18000951b  lea     rcx, __xi_a; First
0x180009522  call    _initterm_e_0
0x180009527  test    eax, eax
0x180009529  jnz     short loc_180009554
0x18000952b  call    __scrt_dllmain_after_initialize_c
0x180009530  test    al, al
0x180009532  jz      short loc_180009554
0x180009534  lea     rdx, __xc_z; Last
0x18000953b  lea     rcx, __xc_a; First
0x180009542  call    _initterm_0
0x180009547  mov     cs:__scrt_current_native_startup_state, 2
0x180009551  xor     dil, dil
0x180009554  mov     cl, bl
0x180009556  call    __scrt_release_startup_lock
0x18000955b  test    dil, dil
0x18000955e  jnz     short loc_18000959A
0x180009560  call    __scrt_get_dyn_tls_init_callback
0x180009565  mov     rbx, rax
0x180009568  cmp     qword ptr [rax], 0
0x18000956c  jz      short loc_18000958D
0x18000956e  mov     rcx, rax
0x180009571  call    __scrt_is_nonwritable_in_current_image
0x180009576  test    al, al
0x180009578  jz      short loc_18000958D
0x18000957a  mov     r8, rsi
0x18000957d  mov     edx, 2
0x180009582  mov     rcx, r14
0x180009585  mov     rax, [rbx]
0x180009588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958d  inc     cs:dword_18001F390
0x180009593  mov     eax, 1
0x180009598  jmp     short loc_18000959C
0x18000959a  xor     eax, eax
0x18000959c  add     rsp, 28h
0x1800095a0  pop     r14
0x1800095a2  pop     rdi
0x1800095a3  pop     rsi
0x1800095a4  pop     rbx
0x1800095a5  retn
0x1800095a6  mov     ecx, 7
0x1800095ab  call    __scrt_fastfail
0x18001576c  push    rbp
0x18001576e  sub     rsp, 20h
0x180015772  mov     rbp, rdx
0x180015775  mov     cl, [rbp+60h]
0x180015778  add     rsp, 20h
0x18001577c  pop     rbp
0x18001577d  jmp     __scrt_release_startup_lock
```
