# dllmain_crt_process_attach

- ea: `0x180001548`
- end: `0x180001642`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800014f0`

## callees

- `0x180001548`
- `0x1800019c0`
- `0x180001a00`
- `0x180001a3c`
- `0x180001b3c`
- `0x180001c10`
- `0x180001cb0`
- `0x180001e54`
- `0x180001e7c`
- `0x180001ea0`
- `0x180001eb0`
- `0x180001ebc`
- `0x1800022b6`
- `0x1800022c2`
- `0x18002a010`

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
  ++dword_180036DD0;
  return 1;
}

```

## disassembly

```asm
0x180001548  push    rbx
0x18000154a  push    rsi
0x18000154b  push    rdi
0x18000154c  push    r14
0x18000154e  sub     rsp, 28h
0x180001552  mov     rsi, rdx
0x180001555  mov     r14, rcx
0x180001558  xor     ecx, ecx
0x18000155a  call    __scrt_initialize_crt
0x18000155f  test    al, al
0x180001561  jz      loc_18000162A
0x180001567  call    __scrt_acquire_startup_lock
0x18000156c  mov     bl, al
0x18000156e  mov     [rsp+48h+arg_10], al
0x180001572  mov     dil, 1
0x180001575  cmp     cs:__scrt_current_native_startup_state, 0
0x18000157c  jnz     loc_180001636
0x180001582  mov     cs:__scrt_current_native_startup_state, 1
0x18000158c  call    __scrt_dllmain_before_initialize_c
0x180001591  test    al, al
0x180001593  jz      short loc_1800015E4
0x180001595  call    _RTC_Initialize
0x18000159a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000159f  call    __scrt_initialize_default_local_stdio_options
0x1800015a4  lea     rdx, __xi_z; Last
0x1800015ab  lea     rcx, __xi_a; First
0x1800015b2  call    _initterm_e_0
0x1800015b7  test    eax, eax
0x1800015b9  jnz     short loc_1800015E4
0x1800015bb  call    __scrt_dllmain_after_initialize_c
0x1800015c0  test    al, al
0x1800015c2  jz      short loc_1800015E4
0x1800015c4  lea     rdx, __xc_z; Last
0x1800015cb  lea     rcx, __xc_a; First
0x1800015d2  call    _initterm_0
0x1800015d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800015e1  xor     dil, dil
0x1800015e4  mov     cl, bl
0x1800015e6  call    __scrt_release_startup_lock
0x1800015eb  test    dil, dil
0x1800015ee  jnz     short loc_18000162A
0x1800015f0  call    __scrt_get_dyn_tls_init_callback
0x1800015f5  mov     rbx, rax
0x1800015f8  cmp     qword ptr [rax], 0
0x1800015fc  jz      short loc_18000161D
0x1800015fe  mov     rcx, rax
0x180001601  call    __scrt_is_nonwritable_in_current_image
0x180001606  test    al, al
0x180001608  jz      short loc_18000161D
0x18000160a  mov     r8, rsi
0x18000160d  mov     edx, 2
0x180001612  mov     rcx, r14
0x180001615  mov     rax, [rbx]
0x180001618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000161d  inc     cs:dword_180036DD0
0x180001623  mov     eax, 1
0x180001628  jmp     short loc_18000162C
0x18000162a  xor     eax, eax
0x18000162c  add     rsp, 28h
0x180001630  pop     r14
0x180001632  pop     rdi
0x180001633  pop     rsi
0x180001634  pop     rbx
0x180001635  retn
0x180001636  mov     ecx, 7
0x18000163b  call    __scrt_fastfail
0x180027c6c  push    rbp
0x180027c6e  sub     rsp, 20h
0x180027c72  mov     rbp, rdx
0x180027c75  mov     cl, [rbp+60h]
0x180027c78  add     rsp, 20h
0x180027c7c  pop     rbp
0x180027c7d  jmp     __scrt_release_startup_lock
```
