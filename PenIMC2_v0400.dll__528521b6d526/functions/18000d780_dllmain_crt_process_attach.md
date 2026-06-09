# dllmain_crt_process_attach

- ea: `0x18000d780`
- end: `0x18000d896`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d730`

## callees

- `0x18000d0b8`
- `0x18000d0f4`
- `0x18000d128`
- `0x18000d224`
- `0x18000d2fc`
- `0x18000d394`
- `0x18000d780`
- `0x18000dc48`
- `0x18000dff0`
- `0x18000e014`
- `0x18000e030`
- `0x18000e038`
- `0x18000e12c`
- `0x18000e132`
- `0x18000e4a0`

## pseudocode

```c
__int64 dllmain_crt_process_attach()
{
  char v0; // bl
  char v1; // di
  __int64 v2; // rcx
  _QWORD *dyn_tls_init_callback; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v0 = _scrt_acquire_startup_lock();
  v1 = 1;
  if ( _scrt_current_native_startup_state )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x18000D896LL);
  }
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
        v1 = 0;
      }
    }
  }
  LOBYTE(v2) = v0;
  _scrt_release_startup_lock(v2);
  if ( v1 )
    return 0;
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback();
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
  }
  ++dword_180018920;
  return 1;
}

```

## disassembly

```asm
0x18000d780  mov     [rsp+arg_0], rbx
0x18000d785  mov     [rsp+arg_8], rsi
0x18000d78a  mov     [rsp+arg_18], rdi
0x18000d78f  push    r14
0x18000d791  sub     rsp, 20h
0x18000d795  mov     rsi, rdx
0x18000d798  mov     r14, rcx
0x18000d79b  xor     ecx, ecx
0x18000d79d  call    __scrt_initialize_crt
0x18000d7a2  test    al, al
0x18000d7a4  jz      loc_18000D872
0x18000d7aa  call    __scrt_acquire_startup_lock
0x18000d7af  mov     bl, al
0x18000d7b1  mov     [rsp+28h+arg_10], al
0x18000d7b5  mov     dil, 1
0x18000d7b8  cmp     cs:__scrt_current_native_startup_state, 0
0x18000d7bf  jnz     loc_18000D88A
0x18000d7c5  mov     cs:__scrt_current_native_startup_state, 1
0x18000d7cf  call    __scrt_dllmain_before_initialize_c
0x18000d7d4  test    al, al
0x18000d7d6  jz      short loc_18000D827
0x18000d7d8  call    _RTC_Initialize
0x18000d7dd  call    ?__scrt_initialize_type_info@@YAXXZ
0x18000d7e2  call    __scrt_initialize_default_local_stdio_options
0x18000d7e7  lea     rdx, __xi_z; Last
0x18000d7ee  lea     rcx, __xi_a; First
0x18000d7f5  call    _initterm_e_0
0x18000d7fa  test    eax, eax
0x18000d7fc  jnz     short loc_18000D827
0x18000d7fe  call    __scrt_dllmain_after_initialize_c
0x18000d803  test    al, al
0x18000d805  jz      short loc_18000D827
0x18000d807  lea     rdx, __xc_z; Last
0x18000d80e  lea     rcx, __xc_a; First
0x18000d815  call    _initterm_0
0x18000d81a  mov     cs:__scrt_current_native_startup_state, 2
0x18000d824  xor     dil, dil
0x18000d827  mov     cl, bl
0x18000d829  call    __scrt_release_startup_lock
0x18000d82e  test    dil, dil
0x18000d831  jnz     short loc_18000D872
0x18000d833  call    __scrt_get_dyn_tls_init_callback
0x18000d838  mov     rbx, rax
0x18000d83b  cmp     qword ptr [rax], 0
0x18000d83f  jz      short loc_18000D865
0x18000d841  mov     rcx, rax
0x18000d844  call    __scrt_is_nonwritable_in_current_image
0x18000d849  test    al, al
0x18000d84b  jz      short loc_18000D865
0x18000d84d  mov     r8, rsi
0x18000d850  mov     edx, 2
0x18000d855  mov     rcx, r14
0x18000d858  mov     rax, [rbx]
0x18000d85b  mov     r9, cs:__guard_dispatch_icall_fptr
0x18000d862  call    r9 ; _guard_dispatch_icall_nop
0x18000d865  inc     cs:dword_180018920
0x18000d86b  mov     eax, 1
0x18000d870  jmp     short loc_18000D874
0x18000d872  xor     eax, eax
0x18000d874  mov     rbx, [rsp+28h+arg_0]
0x18000d879  mov     rsi, [rsp+28h+arg_8]
0x18000d87e  mov     rdi, [rsp+28h+arg_18]
0x18000d883  add     rsp, 20h
0x18000d887  pop     r14
0x18000d889  retn
0x18000d88a  mov     ecx, 7
0x18000d88f  call    __scrt_fastfail
0x18000d894  nop
0x18000d895  int     3; Trap to Debugger
0x18000f22b  push    rbp
0x18000f22d  sub     rsp, 20h
0x18000f231  mov     rbp, rdx
0x18000f234  mov     cl, [rbp+40h]
0x18000f237  add     rsp, 20h
0x18000f23b  pop     rbp
0x18000f23c  jmp     __scrt_release_startup_lock
```
