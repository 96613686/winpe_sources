# dllmain_crt_process_attach

- ea: `0x180002338`
- end: `0x180002432`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800022e0`

## callees

- `0x180002338`
- `0x180002744`
- `0x180002784`
- `0x1800027c0`
- `0x1800028c0`
- `0x180002994`
- `0x180002a34`
- `0x180002fec`
- `0x180003014`
- `0x180003038`
- `0x180003048`
- `0x180003054`
- `0x180003186`
- `0x180003192`
- `0x18000d010`

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
  ++dword_180014290;
  return 1;
}

```

## disassembly

```asm
0x180002338  push    rbx
0x18000233a  push    rsi
0x18000233b  push    rdi
0x18000233c  push    r14
0x18000233e  sub     rsp, 28h
0x180002342  mov     rsi, rdx
0x180002345  mov     r14, rcx
0x180002348  xor     ecx, ecx
0x18000234a  call    __scrt_initialize_crt
0x18000234f  test    al, al
0x180002351  jz      loc_18000241A
0x180002357  call    __scrt_acquire_startup_lock
0x18000235c  mov     bl, al
0x18000235e  mov     [rsp+48h+arg_10], al
0x180002362  mov     dil, 1
0x180002365  cmp     cs:__scrt_current_native_startup_state, 0
0x18000236c  jnz     loc_180002426
0x180002372  mov     cs:__scrt_current_native_startup_state, 1
0x18000237c  call    __scrt_dllmain_before_initialize_c
0x180002381  test    al, al
0x180002383  jz      short loc_1800023D4
0x180002385  call    _RTC_Initialize
0x18000238a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000238f  call    __scrt_initialize_default_local_stdio_options
0x180002394  lea     rdx, __xi_z; Last
0x18000239b  lea     rcx, __xi_a; First
0x1800023a2  call    _initterm_e_0
0x1800023a7  test    eax, eax
0x1800023a9  jnz     short loc_1800023D4
0x1800023ab  call    __scrt_dllmain_after_initialize_c
0x1800023b0  test    al, al
0x1800023b2  jz      short loc_1800023D4
0x1800023b4  lea     rdx, __xc_z; Last
0x1800023bb  lea     rcx, __xc_a; First
0x1800023c2  call    _initterm_0
0x1800023c7  mov     cs:__scrt_current_native_startup_state, 2
0x1800023d1  xor     dil, dil
0x1800023d4  mov     cl, bl
0x1800023d6  call    __scrt_release_startup_lock
0x1800023db  test    dil, dil
0x1800023de  jnz     short loc_18000241A
0x1800023e0  call    __scrt_get_dyn_tls_init_callback
0x1800023e5  mov     rbx, rax
0x1800023e8  cmp     qword ptr [rax], 0
0x1800023ec  jz      short loc_18000240D
0x1800023ee  mov     rcx, rax
0x1800023f1  call    __scrt_is_nonwritable_in_current_image
0x1800023f6  test    al, al
0x1800023f8  jz      short loc_18000240D
0x1800023fa  mov     r8, rsi
0x1800023fd  mov     edx, 2
0x180002402  mov     rcx, r14
0x180002405  mov     rax, [rbx]
0x180002408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240d  inc     cs:dword_180014290
0x180002413  mov     eax, 1
0x180002418  jmp     short loc_18000241C
0x18000241a  xor     eax, eax
0x18000241c  add     rsp, 28h
0x180002420  pop     r14
0x180002422  pop     rdi
0x180002423  pop     rsi
0x180002424  pop     rbx
0x180002425  retn
0x180002426  mov     ecx, 7
0x18000242b  call    __scrt_fastfail
0x18000bf7c  push    rbp
0x18000bf7e  sub     rsp, 20h
0x18000bf82  mov     rbp, rdx
0x18000bf85  mov     cl, [rbp+60h]
0x18000bf88  add     rsp, 20h
0x18000bf8c  pop     rbp
0x18000bf8d  jmp     __scrt_release_startup_lock
```
