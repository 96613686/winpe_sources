# dllmain_crt_process_attach

- ea: `0x180003968`
- end: `0x180003a62`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003910`

## callees

- `0x180003968`
- `0x180003d60`
- `0x180003d88`
- `0x180003dac`
- `0x180003dec`
- `0x180003e28`
- `0x180003f28`
- `0x180003ffc`
- `0x18000409c`
- `0x180004158`
- `0x180004168`
- `0x180004174`
- `0x1800044d6`
- `0x1800044e2`
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
  ++dword_1805E06F0;
  return 1;
}

```

## disassembly

```asm
0x180003968  push    rbx
0x18000396a  push    rsi
0x18000396b  push    rdi
0x18000396c  push    r14
0x18000396e  sub     rsp, 28h
0x180003972  mov     rsi, rdx
0x180003975  mov     r14, rcx
0x180003978  xor     ecx, ecx
0x18000397a  call    __scrt_initialize_crt
0x18000397f  test    al, al
0x180003981  jz      loc_180003A4A
0x180003987  call    __scrt_acquire_startup_lock
0x18000398c  mov     bl, al
0x18000398e  mov     [rsp+48h+arg_10], al
0x180003992  mov     dil, 1
0x180003995  cmp     cs:__scrt_current_native_startup_state, 0
0x18000399c  jnz     loc_180003A56
0x1800039a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800039ac  call    __scrt_dllmain_before_initialize_c
0x1800039b1  test    al, al
0x1800039b3  jz      short loc_180003A04
0x1800039b5  call    _RTC_Initialize
0x1800039ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800039bf  call    __scrt_initialize_default_local_stdio_options
0x1800039c4  lea     rdx, __xi_z; Last
0x1800039cb  lea     rcx, __xi_a; First
0x1800039d2  call    _initterm_e_0
0x1800039d7  test    eax, eax
0x1800039d9  jnz     short loc_180003A04
0x1800039db  call    __scrt_dllmain_after_initialize_c
0x1800039e0  test    al, al
0x1800039e2  jz      short loc_180003A04
0x1800039e4  lea     rdx, __xc_z; Last
0x1800039eb  lea     rcx, __xc_a; First
0x1800039f2  call    _initterm_0
0x1800039f7  mov     cs:__scrt_current_native_startup_state, 2
0x180003a01  xor     dil, dil
0x180003a04  mov     cl, bl
0x180003a06  call    __scrt_release_startup_lock
0x180003a0b  test    dil, dil
0x180003a0e  jnz     short loc_180003A4A
0x180003a10  call    __scrt_get_dyn_tls_init_callback
0x180003a15  mov     rbx, rax
0x180003a18  cmp     qword ptr [rax], 0
0x180003a1c  jz      short loc_180003A3D
0x180003a1e  mov     rcx, rax
0x180003a21  call    __scrt_is_nonwritable_in_current_image
0x180003a26  test    al, al
0x180003a28  jz      short loc_180003A3D
0x180003a2a  mov     r8, rsi
0x180003a2d  mov     edx, 2
0x180003a32  mov     rcx, r14
0x180003a35  mov     rax, [rbx]
0x180003a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3d  inc     cs:dword_1805E06F0
0x180003a43  mov     eax, 1
0x180003a48  jmp     short loc_180003A4C
0x180003a4a  xor     eax, eax
0x180003a4c  add     rsp, 28h
0x180003a50  pop     r14
0x180003a52  pop     rdi
0x180003a53  pop     rsi
0x180003a54  pop     rbx
0x180003a55  retn
0x180003a56  mov     ecx, 7
0x180003a5b  call    __scrt_fastfail
0x18000b357  push    rbp
0x18000b359  sub     rsp, 20h
0x18000b35d  mov     rbp, rdx
0x18000b360  mov     cl, [rbp+60h]
0x18000b363  add     rsp, 20h
0x18000b367  pop     rbp
0x18000b368  jmp     __scrt_release_startup_lock
```
