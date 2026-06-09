# dllmain_crt_process_attach

- ea: `0x180001948`
- end: `0x180001a42`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800018f0`

## callees

- `0x180001948`
- `0x180001df8`
- `0x180001e20`
- `0x180001e44`
- `0x180001e84`
- `0x180001ec0`
- `0x180001fc0`
- `0x180002094`
- `0x180002134`
- `0x1800021f0`
- `0x180002200`
- `0x18000220c`
- `0x1800025b6`
- `0x1800025c2`
- `0x18001e010`

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
  ++dword_180029810;
  return 1;
}

```

## disassembly

```asm
0x180001948  push    rbx
0x18000194a  push    rsi
0x18000194b  push    rdi
0x18000194c  push    r14
0x18000194e  sub     rsp, 28h
0x180001952  mov     rsi, rdx
0x180001955  mov     r14, rcx
0x180001958  xor     ecx, ecx
0x18000195a  call    __scrt_initialize_crt
0x18000195f  test    al, al
0x180001961  jz      loc_180001A2A
0x180001967  call    __scrt_acquire_startup_lock
0x18000196c  mov     bl, al
0x18000196e  mov     [rsp+48h+arg_10], al
0x180001972  mov     dil, 1
0x180001975  cmp     cs:__scrt_current_native_startup_state, 0
0x18000197c  jnz     loc_180001A36
0x180001982  mov     cs:__scrt_current_native_startup_state, 1
0x18000198c  call    __scrt_dllmain_before_initialize_c
0x180001991  test    al, al
0x180001993  jz      short loc_1800019E4
0x180001995  call    _RTC_Initialize
0x18000199a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000199f  call    __scrt_initialize_default_local_stdio_options
0x1800019a4  lea     rdx, __xi_z; Last
0x1800019ab  lea     rcx, __xi_a; First
0x1800019b2  call    _initterm_e_0
0x1800019b7  test    eax, eax
0x1800019b9  jnz     short loc_1800019E4
0x1800019bb  call    __scrt_dllmain_after_initialize_c
0x1800019c0  test    al, al
0x1800019c2  jz      short loc_1800019E4
0x1800019c4  lea     rdx, __xc_z; Last
0x1800019cb  lea     rcx, __xc_a; First
0x1800019d2  call    _initterm_0
0x1800019d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800019e1  xor     dil, dil
0x1800019e4  mov     cl, bl
0x1800019e6  call    __scrt_release_startup_lock
0x1800019eb  test    dil, dil
0x1800019ee  jnz     short loc_180001A2A
0x1800019f0  call    __scrt_get_dyn_tls_init_callback
0x1800019f5  mov     rbx, rax
0x1800019f8  cmp     qword ptr [rax], 0
0x1800019fc  jz      short loc_180001A1D
0x1800019fe  mov     rcx, rax
0x180001a01  call    __scrt_is_nonwritable_in_current_image
0x180001a06  test    al, al
0x180001a08  jz      short loc_180001A1D
0x180001a0a  mov     r8, rsi
0x180001a0d  mov     edx, 2
0x180001a12  mov     rcx, r14
0x180001a15  mov     rax, [rbx]
0x180001a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1d  inc     cs:dword_180029810
0x180001a23  mov     eax, 1
0x180001a28  jmp     short loc_180001A2C
0x180001a2a  xor     eax, eax
0x180001a2c  add     rsp, 28h
0x180001a30  pop     r14
0x180001a32  pop     rdi
0x180001a33  pop     rsi
0x180001a34  pop     rbx
0x180001a35  retn
0x180001a36  mov     ecx, 7
0x180001a3b  call    __scrt_fastfail
0x18001cffc  push    rbp
0x18001cffe  sub     rsp, 20h
0x18001d002  mov     rbp, rdx
0x18001d005  mov     cl, [rbp+60h]
0x18001d008  add     rsp, 20h
0x18001d00c  pop     rbp
0x18001d00d  jmp     __scrt_release_startup_lock
```
