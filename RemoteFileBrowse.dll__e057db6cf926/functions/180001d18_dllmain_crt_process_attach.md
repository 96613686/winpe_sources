# dllmain_crt_process_attach

- ea: `0x180001d18`
- end: `0x180001e12`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001cc0`

## callees

- `0x180001d18`
- `0x180002100`
- `0x180002140`
- `0x18000217c`
- `0x18000227c`
- `0x180002350`
- `0x1800023f0`
- `0x180002b18`
- `0x180002b40`
- `0x180002b64`
- `0x180002b74`
- `0x180002b80`
- `0x180002c96`
- `0x180002ca2`
- `0x180019010`

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
  ++dword_180023470;
  return 1;
}

```

## disassembly

```asm
0x180001d18  push    rbx
0x180001d1a  push    rsi
0x180001d1b  push    rdi
0x180001d1c  push    r14
0x180001d1e  sub     rsp, 28h
0x180001d22  mov     rsi, rdx
0x180001d25  mov     r14, rcx
0x180001d28  xor     ecx, ecx
0x180001d2a  call    __scrt_initialize_crt
0x180001d2f  test    al, al
0x180001d31  jz      loc_180001DFA
0x180001d37  call    __scrt_acquire_startup_lock
0x180001d3c  mov     bl, al
0x180001d3e  mov     [rsp+48h+arg_10], al
0x180001d42  mov     dil, 1
0x180001d45  cmp     cs:__scrt_current_native_startup_state, 0
0x180001d4c  jnz     loc_180001E06
0x180001d52  mov     cs:__scrt_current_native_startup_state, 1
0x180001d5c  call    __scrt_dllmain_before_initialize_c
0x180001d61  test    al, al
0x180001d63  jz      short loc_180001DB4
0x180001d65  call    _RTC_Initialize
0x180001d6a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001d6f  call    __scrt_initialize_default_local_stdio_options
0x180001d74  lea     rdx, __xi_z; Last
0x180001d7b  lea     rcx, __xi_a; First
0x180001d82  call    _initterm_e_0
0x180001d87  test    eax, eax
0x180001d89  jnz     short loc_180001DB4
0x180001d8b  call    __scrt_dllmain_after_initialize_c
0x180001d90  test    al, al
0x180001d92  jz      short loc_180001DB4
0x180001d94  lea     rdx, __xc_z; Last
0x180001d9b  lea     rcx, __xc_a; First
0x180001da2  call    _initterm_0
0x180001da7  mov     cs:__scrt_current_native_startup_state, 2
0x180001db1  xor     dil, dil
0x180001db4  mov     cl, bl
0x180001db6  call    __scrt_release_startup_lock
0x180001dbb  test    dil, dil
0x180001dbe  jnz     short loc_180001DFA
0x180001dc0  call    __scrt_get_dyn_tls_init_callback
0x180001dc5  mov     rbx, rax
0x180001dc8  cmp     qword ptr [rax], 0
0x180001dcc  jz      short loc_180001DED
0x180001dce  mov     rcx, rax
0x180001dd1  call    __scrt_is_nonwritable_in_current_image
0x180001dd6  test    al, al
0x180001dd8  jz      short loc_180001DED
0x180001dda  mov     r8, rsi
0x180001ddd  mov     edx, 2
0x180001de2  mov     rcx, r14
0x180001de5  mov     rax, [rbx]
0x180001de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ded  inc     cs:dword_180023470
0x180001df3  mov     eax, 1
0x180001df8  jmp     short loc_180001DFC
0x180001dfa  xor     eax, eax
0x180001dfc  add     rsp, 28h
0x180001e00  pop     r14
0x180001e02  pop     rdi
0x180001e03  pop     rsi
0x180001e04  pop     rbx
0x180001e05  retn
0x180001e06  mov     ecx, 7
0x180001e0b  call    __scrt_fastfail
0x1800174ac  push    rbp
0x1800174ae  sub     rsp, 20h
0x1800174b2  mov     rbp, rdx
0x1800174b5  mov     cl, [rbp+60h]
0x1800174b8  add     rsp, 20h
0x1800174bc  pop     rbp
0x1800174bd  jmp     __scrt_release_startup_lock
```
