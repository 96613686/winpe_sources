# dllmain_crt_process_attach

- ea: `0x180001878`
- end: `0x180001972`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001820`

## callees

- `0x180001878`
- `0x180001cc0`
- `0x180001ce8`
- `0x180001d0c`
- `0x180001d4c`
- `0x180001d88`
- `0x180001e88`
- `0x180001f5c`
- `0x180001ffc`
- `0x1800020b8`
- `0x1800020c8`
- `0x1800020d4`
- `0x1800024e6`
- `0x1800024f2`
- `0x180039010`

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
  ++dword_18004B450;
  return 1;
}

```

## disassembly

```asm
0x180001878  push    rbx
0x18000187a  push    rsi
0x18000187b  push    rdi
0x18000187c  push    r14
0x18000187e  sub     rsp, 28h
0x180001882  mov     rsi, rdx
0x180001885  mov     r14, rcx
0x180001888  xor     ecx, ecx
0x18000188a  call    __scrt_initialize_crt
0x18000188f  test    al, al
0x180001891  jz      loc_18000195A
0x180001897  call    __scrt_acquire_startup_lock
0x18000189c  mov     bl, al
0x18000189e  mov     [rsp+48h+arg_10], al
0x1800018a2  mov     dil, 1
0x1800018a5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800018ac  jnz     loc_180001966
0x1800018b2  mov     cs:__scrt_current_native_startup_state, 1
0x1800018bc  call    __scrt_dllmain_before_initialize_c
0x1800018c1  test    al, al
0x1800018c3  jz      short loc_180001914
0x1800018c5  call    _RTC_Initialize
0x1800018ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800018cf  call    __scrt_initialize_default_local_stdio_options
0x1800018d4  lea     rdx, __xi_z; Last
0x1800018db  lea     rcx, __xi_a; First
0x1800018e2  call    _initterm_e_0
0x1800018e7  test    eax, eax
0x1800018e9  jnz     short loc_180001914
0x1800018eb  call    __scrt_dllmain_after_initialize_c
0x1800018f0  test    al, al
0x1800018f2  jz      short loc_180001914
0x1800018f4  lea     rdx, __xc_z; Last
0x1800018fb  lea     rcx, __xc_a; First
0x180001902  call    _initterm_0
0x180001907  mov     cs:__scrt_current_native_startup_state, 2
0x180001911  xor     dil, dil
0x180001914  mov     cl, bl
0x180001916  call    __scrt_release_startup_lock
0x18000191b  test    dil, dil
0x18000191e  jnz     short loc_18000195A
0x180001920  call    __scrt_get_dyn_tls_init_callback
0x180001925  mov     rbx, rax
0x180001928  cmp     qword ptr [rax], 0
0x18000192c  jz      short loc_18000194D
0x18000192e  mov     rcx, rax
0x180001931  call    __scrt_is_nonwritable_in_current_image
0x180001936  test    al, al
0x180001938  jz      short loc_18000194D
0x18000193a  mov     r8, rsi
0x18000193d  mov     edx, 2
0x180001942  mov     rcx, r14
0x180001945  mov     rax, [rbx]
0x180001948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000194d  inc     cs:dword_18004B450
0x180001953  mov     eax, 1
0x180001958  jmp     short loc_18000195C
0x18000195a  xor     eax, eax
0x18000195c  add     rsp, 28h
0x180001960  pop     r14
0x180001962  pop     rdi
0x180001963  pop     rsi
0x180001964  pop     rbx
0x180001965  retn
0x180001966  mov     ecx, 7
0x18000196b  call    __scrt_fastfail
0x1800370cc  push    rbp
0x1800370ce  sub     rsp, 20h
0x1800370d2  mov     rbp, rdx
0x1800370d5  mov     cl, [rbp+60h]
0x1800370d8  add     rsp, 20h
0x1800370dc  pop     rbp
0x1800370dd  jmp     __scrt_release_startup_lock
```
