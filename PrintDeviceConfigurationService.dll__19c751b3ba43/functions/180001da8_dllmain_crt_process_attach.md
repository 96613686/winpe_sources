# dllmain_crt_process_attach

- ea: `0x180001da8`
- end: `0x180001ea2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001d50`

## callees

- `0x180001da8`
- `0x1800020e4`
- `0x180002124`
- `0x180002160`
- `0x180002260`
- `0x180002334`
- `0x1800023d4`
- `0x1800025cc`
- `0x1800025f4`
- `0x180002618`
- `0x180002628`
- `0x180002634`
- `0x180002a16`
- `0x180002a22`
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
  ++dword_1800242B0;
  return 1;
}

```

## disassembly

```asm
0x180001da8  push    rbx
0x180001daa  push    rsi
0x180001dab  push    rdi
0x180001dac  push    r14
0x180001dae  sub     rsp, 28h
0x180001db2  mov     rsi, rdx
0x180001db5  mov     r14, rcx
0x180001db8  xor     ecx, ecx
0x180001dba  call    __scrt_initialize_crt
0x180001dbf  test    al, al
0x180001dc1  jz      loc_180001E8A
0x180001dc7  call    __scrt_acquire_startup_lock
0x180001dcc  mov     bl, al
0x180001dce  mov     [rsp+48h+arg_10], al
0x180001dd2  mov     dil, 1
0x180001dd5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001ddc  jnz     loc_180001E96
0x180001de2  mov     cs:__scrt_current_native_startup_state, 1
0x180001dec  call    __scrt_dllmain_before_initialize_c
0x180001df1  test    al, al
0x180001df3  jz      short loc_180001E44
0x180001df5  call    _RTC_Initialize
0x180001dfa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001dff  call    __scrt_initialize_default_local_stdio_options
0x180001e04  lea     rdx, __xi_z; Last
0x180001e0b  lea     rcx, __xi_a; First
0x180001e12  call    _initterm_e_0
0x180001e17  test    eax, eax
0x180001e19  jnz     short loc_180001E44
0x180001e1b  call    __scrt_dllmain_after_initialize_c
0x180001e20  test    al, al
0x180001e22  jz      short loc_180001E44
0x180001e24  lea     rdx, __xc_z; Last
0x180001e2b  lea     rcx, __xc_a; First
0x180001e32  call    _initterm_0
0x180001e37  mov     cs:__scrt_current_native_startup_state, 2
0x180001e41  xor     dil, dil
0x180001e44  mov     cl, bl
0x180001e46  call    __scrt_release_startup_lock
0x180001e4b  test    dil, dil
0x180001e4e  jnz     short loc_180001E8A
0x180001e50  call    __scrt_get_dyn_tls_init_callback
0x180001e55  mov     rbx, rax
0x180001e58  cmp     qword ptr [rax], 0
0x180001e5c  jz      short loc_180001E7D
0x180001e5e  mov     rcx, rax
0x180001e61  call    __scrt_is_nonwritable_in_current_image
0x180001e66  test    al, al
0x180001e68  jz      short loc_180001E7D
0x180001e6a  mov     r8, rsi
0x180001e6d  mov     edx, 2
0x180001e72  mov     rcx, r14
0x180001e75  mov     rax, [rbx]
0x180001e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e7d  inc     cs:dword_1800242B0
0x180001e83  mov     eax, 1
0x180001e88  jmp     short loc_180001E8C
0x180001e8a  xor     eax, eax
0x180001e8c  add     rsp, 28h
0x180001e90  pop     r14
0x180001e92  pop     rdi
0x180001e93  pop     rsi
0x180001e94  pop     rbx
0x180001e95  retn
0x180001e96  mov     ecx, 7
0x180001e9b  call    __scrt_fastfail
0x18001657c  push    rbp
0x18001657e  sub     rsp, 20h
0x180016582  mov     rbp, rdx
0x180016585  mov     cl, [rbp+60h]
0x180016588  add     rsp, 20h
0x18001658c  pop     rbp
0x18001658d  jmp     __scrt_release_startup_lock
```
