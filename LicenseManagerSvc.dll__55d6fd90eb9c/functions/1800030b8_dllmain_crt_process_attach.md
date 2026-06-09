# dllmain_crt_process_attach

- ea: `0x1800030b8`
- end: `0x1800031b2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003060`

## callees

- `0x1800030b8`
- `0x1800036b4`
- `0x1800036f4`
- `0x180003730`
- `0x180003830`
- `0x180003904`
- `0x1800039a4`
- `0x180003b68`
- `0x180003b90`
- `0x180003bb4`
- `0x180003bc4`
- `0x180003bd0`
- `0x180004066`
- `0x180004072`
- `0x180018010`

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
  ++dword_180021610;
  return 1;
}

```

## disassembly

```asm
0x1800030b8  push    rbx
0x1800030ba  push    rsi
0x1800030bb  push    rdi
0x1800030bc  push    r14
0x1800030be  sub     rsp, 28h
0x1800030c2  mov     rsi, rdx
0x1800030c5  mov     r14, rcx
0x1800030c8  xor     ecx, ecx
0x1800030ca  call    __scrt_initialize_crt
0x1800030cf  test    al, al
0x1800030d1  jz      loc_18000319A
0x1800030d7  call    __scrt_acquire_startup_lock
0x1800030dc  mov     bl, al
0x1800030de  mov     [rsp+48h+arg_10], al
0x1800030e2  mov     dil, 1
0x1800030e5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800030ec  jnz     loc_1800031A6
0x1800030f2  mov     cs:__scrt_current_native_startup_state, 1
0x1800030fc  call    __scrt_dllmain_before_initialize_c
0x180003101  test    al, al
0x180003103  jz      short loc_180003154
0x180003105  call    _RTC_Initialize
0x18000310a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000310f  call    __scrt_initialize_default_local_stdio_options
0x180003114  lea     rdx, __xi_z; Last
0x18000311b  lea     rcx, __xi_a; First
0x180003122  call    _initterm_e_0
0x180003127  test    eax, eax
0x180003129  jnz     short loc_180003154
0x18000312b  call    __scrt_dllmain_after_initialize_c
0x180003130  test    al, al
0x180003132  jz      short loc_180003154
0x180003134  lea     rdx, __xc_z; Last
0x18000313b  lea     rcx, __xc_a; First
0x180003142  call    _initterm_0
0x180003147  mov     cs:__scrt_current_native_startup_state, 2
0x180003151  xor     dil, dil
0x180003154  mov     cl, bl
0x180003156  call    __scrt_release_startup_lock
0x18000315b  test    dil, dil
0x18000315e  jnz     short loc_18000319A
0x180003160  call    __scrt_get_dyn_tls_init_callback
0x180003165  mov     rbx, rax
0x180003168  cmp     qword ptr [rax], 0
0x18000316c  jz      short loc_18000318D
0x18000316e  mov     rcx, rax
0x180003171  call    __scrt_is_nonwritable_in_current_image
0x180003176  test    al, al
0x180003178  jz      short loc_18000318D
0x18000317a  mov     r8, rsi
0x18000317d  mov     edx, 2
0x180003182  mov     rcx, r14
0x180003185  mov     rax, [rbx]
0x180003188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318d  inc     cs:dword_180021610
0x180003193  mov     eax, 1
0x180003198  jmp     short loc_18000319C
0x18000319a  xor     eax, eax
0x18000319c  add     rsp, 28h
0x1800031a0  pop     r14
0x1800031a2  pop     rdi
0x1800031a3  pop     rsi
0x1800031a4  pop     rbx
0x1800031a5  retn
0x1800031a6  mov     ecx, 7
0x1800031ab  call    __scrt_fastfail
0x18001750e  push    rbp
0x180017510  sub     rsp, 20h
0x180017514  mov     rbp, rdx
0x180017517  mov     cl, [rbp+60h]
0x18001751a  add     rsp, 20h
0x18001751e  pop     rbp
0x18001751f  jmp     __scrt_release_startup_lock
```
