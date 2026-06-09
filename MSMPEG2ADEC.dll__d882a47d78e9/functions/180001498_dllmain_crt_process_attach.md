# dllmain_crt_process_attach

- ea: `0x180001498`
- end: `0x180001592`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180001498`
- `0x1800017d4`
- `0x180001814`
- `0x180001850`
- `0x180001950`
- `0x180001a24`
- `0x180001ac4`
- `0x180001c78`
- `0x180001ca0`
- `0x180001cc4`
- `0x180001cd4`
- `0x180001ce0`
- `0x180002062`
- `0x18000206e`
- `0x180089010`

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
  ++dword_1800AD5D0;
  return 1;
}

```

## disassembly

```asm
0x180001498  push    rbx
0x18000149a  push    rsi
0x18000149b  push    rdi
0x18000149c  push    r14
0x18000149e  sub     rsp, 28h
0x1800014a2  mov     rsi, rdx
0x1800014a5  mov     r14, rcx
0x1800014a8  xor     ecx, ecx
0x1800014aa  call    __scrt_initialize_crt
0x1800014af  test    al, al
0x1800014b1  jz      loc_18000157A
0x1800014b7  call    __scrt_acquire_startup_lock
0x1800014bc  mov     bl, al
0x1800014be  mov     [rsp+48h+arg_10], al
0x1800014c2  mov     dil, 1
0x1800014c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800014cc  jnz     loc_180001586
0x1800014d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800014dc  call    __scrt_dllmain_before_initialize_c
0x1800014e1  test    al, al
0x1800014e3  jz      short loc_180001534
0x1800014e5  call    _RTC_Initialize
0x1800014ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800014ef  call    __scrt_initialize_default_local_stdio_options
0x1800014f4  lea     rdx, __xi_z; Last
0x1800014fb  lea     rcx, __xi_a; First
0x180001502  call    _initterm_e_0
0x180001507  test    eax, eax
0x180001509  jnz     short loc_180001534
0x18000150b  call    __scrt_dllmain_after_initialize_c
0x180001510  test    al, al
0x180001512  jz      short loc_180001534
0x180001514  lea     rdx, __xc_z; Last
0x18000151b  lea     rcx, __xc_a; First
0x180001522  call    _initterm_0
0x180001527  mov     cs:__scrt_current_native_startup_state, 2
0x180001531  xor     dil, dil
0x180001534  mov     cl, bl
0x180001536  call    __scrt_release_startup_lock
0x18000153b  test    dil, dil
0x18000153e  jnz     short loc_18000157A
0x180001540  call    __scrt_get_dyn_tls_init_callback
0x180001545  mov     rbx, rax
0x180001548  cmp     qword ptr [rax], 0
0x18000154c  jz      short loc_18000156D
0x18000154e  mov     rcx, rax
0x180001551  call    __scrt_is_nonwritable_in_current_image
0x180001556  test    al, al
0x180001558  jz      short loc_18000156D
0x18000155a  mov     r8, rsi
0x18000155d  mov     edx, 2
0x180001562  mov     rcx, r14
0x180001565  mov     rax, [rbx]
0x180001568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156d  inc     cs:dword_1800AD5D0
0x180001573  mov     eax, 1
0x180001578  jmp     short loc_18000157C
0x18000157a  xor     eax, eax
0x18000157c  add     rsp, 28h
0x180001580  pop     r14
0x180001582  pop     rdi
0x180001583  pop     rsi
0x180001584  pop     rbx
0x180001585  retn
0x180001586  mov     ecx, 7
0x18000158b  call    __scrt_fastfail
0x180088780  push    rbp
0x180088782  sub     rsp, 20h
0x180088786  mov     rbp, rdx
0x180088789  mov     cl, [rbp+60h]
0x18008878c  add     rsp, 20h
0x180088790  pop     rbp
0x180088791  jmp     __scrt_release_startup_lock
```
