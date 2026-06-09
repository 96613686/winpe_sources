# dllmain_crt_process_attach

- ea: `0x18001b8c8`
- end: `0x18001b9c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001b870`

## callees

- `0x18001b8c8`
- `0x18001bc44`
- `0x18001bc84`
- `0x18001bcc0`
- `0x18001bdc0`
- `0x18001be94`
- `0x18001bf34`
- `0x18001c158`
- `0x18001c180`
- `0x18001c1a4`
- `0x18001c1b4`
- `0x18001c1c0`
- `0x18001c566`
- `0x18001c572`
- `0x180031010`

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
  ++dword_1800418D0;
  return 1;
}

```

## disassembly

```asm
0x18001b8c8  push    rbx
0x18001b8ca  push    rsi
0x18001b8cb  push    rdi
0x18001b8cc  push    r14
0x18001b8ce  sub     rsp, 28h
0x18001b8d2  mov     rsi, rdx
0x18001b8d5  mov     r14, rcx
0x18001b8d8  xor     ecx, ecx
0x18001b8da  call    __scrt_initialize_crt
0x18001b8df  test    al, al
0x18001b8e1  jz      loc_18001B9AA
0x18001b8e7  call    __scrt_acquire_startup_lock
0x18001b8ec  mov     bl, al
0x18001b8ee  mov     [rsp+48h+arg_10], al
0x18001b8f2  mov     dil, 1
0x18001b8f5  cmp     cs:__scrt_current_native_startup_state, 0
0x18001b8fc  jnz     loc_18001B9B6
0x18001b902  mov     cs:__scrt_current_native_startup_state, 1
0x18001b90c  call    __scrt_dllmain_before_initialize_c
0x18001b911  test    al, al
0x18001b913  jz      short loc_18001B964
0x18001b915  call    _RTC_Initialize
0x18001b91a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001b91f  call    __scrt_initialize_default_local_stdio_options
0x18001b924  lea     rdx, __xi_z; Last
0x18001b92b  lea     rcx, __xi_a; First
0x18001b932  call    _initterm_e_0
0x18001b937  test    eax, eax
0x18001b939  jnz     short loc_18001B964
0x18001b93b  call    __scrt_dllmain_after_initialize_c
0x18001b940  test    al, al
0x18001b942  jz      short loc_18001B964
0x18001b944  lea     rdx, __xc_z; Last
0x18001b94b  lea     rcx, __xc_a; First
0x18001b952  call    _initterm_0
0x18001b957  mov     cs:__scrt_current_native_startup_state, 2
0x18001b961  xor     dil, dil
0x18001b964  mov     cl, bl
0x18001b966  call    __scrt_release_startup_lock
0x18001b96b  test    dil, dil
0x18001b96e  jnz     short loc_18001B9AA
0x18001b970  call    __scrt_get_dyn_tls_init_callback
0x18001b975  mov     rbx, rax
0x18001b978  cmp     qword ptr [rax], 0
0x18001b97c  jz      short loc_18001B99D
0x18001b97e  mov     rcx, rax
0x18001b981  call    __scrt_is_nonwritable_in_current_image
0x18001b986  test    al, al
0x18001b988  jz      short loc_18001B99D
0x18001b98a  mov     r8, rsi
0x18001b98d  mov     edx, 2
0x18001b992  mov     rcx, r14
0x18001b995  mov     rax, [rbx]
0x18001b998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b99d  inc     cs:dword_1800418D0
0x18001b9a3  mov     eax, 1
0x18001b9a8  jmp     short loc_18001B9AC
0x18001b9aa  xor     eax, eax
0x18001b9ac  add     rsp, 28h
0x18001b9b0  pop     r14
0x18001b9b2  pop     rdi
0x18001b9b3  pop     rsi
0x18001b9b4  pop     rbx
0x18001b9b5  retn
0x18001b9b6  mov     ecx, 7
0x18001b9bb  call    __scrt_fastfail
0x18002ff60  push    rbp
0x18002ff62  sub     rsp, 20h
0x18002ff66  mov     rbp, rdx
0x18002ff69  mov     cl, [rbp+60h]
0x18002ff6c  add     rsp, 20h
0x18002ff70  pop     rbp
0x18002ff71  jmp     __scrt_release_startup_lock
```
