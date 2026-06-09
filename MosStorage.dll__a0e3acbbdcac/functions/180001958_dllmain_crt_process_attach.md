# dllmain_crt_process_attach

- ea: `0x180001958`
- end: `0x180001a52`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x180001958`
- `0x180001ca4`
- `0x180001ce4`
- `0x180001d20`
- `0x180001e20`
- `0x180001ef4`
- `0x180001f94`
- `0x1800022e4`
- `0x18000230c`
- `0x180002330`
- `0x180002340`
- `0x18000234c`
- `0x1800026d6`
- `0x1800026e2`
- `0x180010010`

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
  ++dword_180018250;
  return 1;
}

```

## disassembly

```asm
0x180001958  push    rbx
0x18000195a  push    rsi
0x18000195b  push    rdi
0x18000195c  push    r14
0x18000195e  sub     rsp, 28h
0x180001962  mov     rsi, rdx
0x180001965  mov     r14, rcx
0x180001968  xor     ecx, ecx
0x18000196a  call    __scrt_initialize_crt
0x18000196f  test    al, al
0x180001971  jz      loc_180001A3A
0x180001977  call    __scrt_acquire_startup_lock
0x18000197c  mov     bl, al
0x18000197e  mov     [rsp+48h+arg_10], al
0x180001982  mov     dil, 1
0x180001985  cmp     cs:__scrt_current_native_startup_state, 0
0x18000198c  jnz     loc_180001A46
0x180001992  mov     cs:__scrt_current_native_startup_state, 1
0x18000199c  call    __scrt_dllmain_before_initialize_c
0x1800019a1  test    al, al
0x1800019a3  jz      short loc_1800019F4
0x1800019a5  call    _RTC_Initialize
0x1800019aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800019af  call    __scrt_initialize_default_local_stdio_options
0x1800019b4  lea     rdx, __xi_z; Last
0x1800019bb  lea     rcx, __xi_a; First
0x1800019c2  call    _initterm_e_0
0x1800019c7  test    eax, eax
0x1800019c9  jnz     short loc_1800019F4
0x1800019cb  call    __scrt_dllmain_after_initialize_c
0x1800019d0  test    al, al
0x1800019d2  jz      short loc_1800019F4
0x1800019d4  lea     rdx, __xc_z; Last
0x1800019db  lea     rcx, __xc_a; First
0x1800019e2  call    _initterm_0
0x1800019e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800019f1  xor     dil, dil
0x1800019f4  mov     cl, bl
0x1800019f6  call    __scrt_release_startup_lock
0x1800019fb  test    dil, dil
0x1800019fe  jnz     short loc_180001A3A
0x180001a00  call    __scrt_get_dyn_tls_init_callback
0x180001a05  mov     rbx, rax
0x180001a08  cmp     qword ptr [rax], 0
0x180001a0c  jz      short loc_180001A2D
0x180001a0e  mov     rcx, rax
0x180001a11  call    __scrt_is_nonwritable_in_current_image
0x180001a16  test    al, al
0x180001a18  jz      short loc_180001A2D
0x180001a1a  mov     r8, rsi
0x180001a1d  mov     edx, 2
0x180001a22  mov     rcx, r14
0x180001a25  mov     rax, [rbx]
0x180001a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a2d  inc     cs:dword_180018250
0x180001a33  mov     eax, 1
0x180001a38  jmp     short loc_180001A3C
0x180001a3a  xor     eax, eax
0x180001a3c  add     rsp, 28h
0x180001a40  pop     r14
0x180001a42  pop     rdi
0x180001a43  pop     rsi
0x180001a44  pop     rbx
0x180001a45  retn
0x180001a46  mov     ecx, 7
0x180001a4b  call    __scrt_fastfail
0x18000e86c  push    rbp
0x18000e86e  sub     rsp, 20h
0x18000e872  mov     rbp, rdx
0x18000e875  mov     cl, [rbp+60h]
0x18000e878  add     rsp, 20h
0x18000e87c  pop     rbp
0x18000e87d  jmp     __scrt_release_startup_lock
```
