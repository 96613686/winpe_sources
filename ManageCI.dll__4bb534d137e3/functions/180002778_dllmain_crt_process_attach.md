# dllmain_crt_process_attach

- ea: `0x180002778`
- end: `0x180002872`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002720`

## callees

- `0x180002778`
- `0x180002af8`
- `0x180002b38`
- `0x180002b74`
- `0x180002c74`
- `0x180002d48`
- `0x180002de8`
- `0x1800035a0`
- `0x1800035c8`
- `0x1800035ec`
- `0x1800035fc`
- `0x180003608`
- `0x180003746`
- `0x180003752`
- `0x18002c010`

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
  ++dword_1800392D8;
  return 1;
}

```

## disassembly

```asm
0x180002778  push    rbx
0x18000277a  push    rsi
0x18000277b  push    rdi
0x18000277c  push    r14
0x18000277e  sub     rsp, 28h
0x180002782  mov     rsi, rdx
0x180002785  mov     r14, rcx
0x180002788  xor     ecx, ecx
0x18000278a  call    __scrt_initialize_crt
0x18000278f  test    al, al
0x180002791  jz      loc_18000285A
0x180002797  call    __scrt_acquire_startup_lock
0x18000279c  mov     bl, al
0x18000279e  mov     [rsp+48h+arg_10], al
0x1800027a2  mov     dil, 1
0x1800027a5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800027ac  jnz     loc_180002866
0x1800027b2  mov     cs:__scrt_current_native_startup_state, 1
0x1800027bc  call    __scrt_dllmain_before_initialize_c
0x1800027c1  test    al, al
0x1800027c3  jz      short loc_180002814
0x1800027c5  call    _RTC_Initialize
0x1800027ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800027cf  call    __scrt_initialize_default_local_stdio_options
0x1800027d4  lea     rdx, __xi_z; Last
0x1800027db  lea     rcx, __xi_a; First
0x1800027e2  call    _initterm_e_0
0x1800027e7  test    eax, eax
0x1800027e9  jnz     short loc_180002814
0x1800027eb  call    __scrt_dllmain_after_initialize_c
0x1800027f0  test    al, al
0x1800027f2  jz      short loc_180002814
0x1800027f4  lea     rdx, __xc_z; Last
0x1800027fb  lea     rcx, __xc_a; First
0x180002802  call    _initterm_0
0x180002807  mov     cs:__scrt_current_native_startup_state, 2
0x180002811  xor     dil, dil
0x180002814  mov     cl, bl
0x180002816  call    __scrt_release_startup_lock
0x18000281b  test    dil, dil
0x18000281e  jnz     short loc_18000285A
0x180002820  call    __scrt_get_dyn_tls_init_callback
0x180002825  mov     rbx, rax
0x180002828  cmp     qword ptr [rax], 0
0x18000282c  jz      short loc_18000284D
0x18000282e  mov     rcx, rax
0x180002831  call    __scrt_is_nonwritable_in_current_image
0x180002836  test    al, al
0x180002838  jz      short loc_18000284D
0x18000283a  mov     r8, rsi
0x18000283d  mov     edx, 2
0x180002842  mov     rcx, r14
0x180002845  mov     rax, [rbx]
0x180002848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284d  inc     cs:dword_1800392D8
0x180002853  mov     eax, 1
0x180002858  jmp     short loc_18000285C
0x18000285a  xor     eax, eax
0x18000285c  add     rsp, 28h
0x180002860  pop     r14
0x180002862  pop     rdi
0x180002863  pop     rsi
0x180002864  pop     rbx
0x180002865  retn
0x180002866  mov     ecx, 7
0x18000286b  call    __scrt_fastfail
0x18002983c  push    rbp
0x18002983e  sub     rsp, 20h
0x180029842  mov     rbp, rdx
0x180029845  mov     cl, [rbp+60h]
0x180029848  add     rsp, 20h
0x18002984c  pop     rbp
0x18002984d  jmp     __scrt_release_startup_lock
```
