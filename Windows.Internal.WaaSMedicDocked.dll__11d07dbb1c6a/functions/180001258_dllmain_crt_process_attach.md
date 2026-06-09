# dllmain_crt_process_attach

- ea: `0x180001258`
- end: `0x180001352`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001200`

## callees

- `0x180001258`
- `0x180001594`
- `0x1800015d4`
- `0x180001610`
- `0x180001710`
- `0x1800017e4`
- `0x180001884`
- `0x180001acc`
- `0x180001af4`
- `0x180001b18`
- `0x180001b28`
- `0x180001b34`
- `0x180001ed6`
- `0x180001ee2`
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
  ++dword_180013570;
  return 1;
}

```

## disassembly

```asm
0x180001258  push    rbx
0x18000125a  push    rsi
0x18000125b  push    rdi
0x18000125c  push    r14
0x18000125e  sub     rsp, 28h
0x180001262  mov     rsi, rdx
0x180001265  mov     r14, rcx
0x180001268  xor     ecx, ecx
0x18000126a  call    __scrt_initialize_crt
0x18000126f  test    al, al
0x180001271  jz      loc_18000133A
0x180001277  call    __scrt_acquire_startup_lock
0x18000127c  mov     bl, al
0x18000127e  mov     [rsp+48h+arg_10], al
0x180001282  mov     dil, 1
0x180001285  cmp     cs:__scrt_current_native_startup_state, 0
0x18000128c  jnz     loc_180001346
0x180001292  mov     cs:__scrt_current_native_startup_state, 1
0x18000129c  call    __scrt_dllmain_before_initialize_c
0x1800012a1  test    al, al
0x1800012a3  jz      short loc_1800012F4
0x1800012a5  call    _RTC_Initialize
0x1800012aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800012af  call    __scrt_initialize_default_local_stdio_options
0x1800012b4  lea     rdx, __xi_z; Last
0x1800012bb  lea     rcx, __xi_a; First
0x1800012c2  call    _initterm_e_0
0x1800012c7  test    eax, eax
0x1800012c9  jnz     short loc_1800012F4
0x1800012cb  call    __scrt_dllmain_after_initialize_c
0x1800012d0  test    al, al
0x1800012d2  jz      short loc_1800012F4
0x1800012d4  lea     rdx, __xc_z; Last
0x1800012db  lea     rcx, __xc_a; First
0x1800012e2  call    _initterm_0
0x1800012e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800012f1  xor     dil, dil
0x1800012f4  mov     cl, bl
0x1800012f6  call    __scrt_release_startup_lock
0x1800012fb  test    dil, dil
0x1800012fe  jnz     short loc_18000133A
0x180001300  call    __scrt_get_dyn_tls_init_callback
0x180001305  mov     rbx, rax
0x180001308  cmp     qword ptr [rax], 0
0x18000130c  jz      short loc_18000132D
0x18000130e  mov     rcx, rax
0x180001311  call    __scrt_is_nonwritable_in_current_image
0x180001316  test    al, al
0x180001318  jz      short loc_18000132D
0x18000131a  mov     r8, rsi
0x18000131d  mov     edx, 2
0x180001322  mov     rcx, r14
0x180001325  mov     rax, [rbx]
0x180001328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000132d  inc     cs:dword_180013570
0x180001333  mov     eax, 1
0x180001338  jmp     short loc_18000133C
0x18000133a  xor     eax, eax
0x18000133c  add     rsp, 28h
0x180001340  pop     r14
0x180001342  pop     rdi
0x180001343  pop     rsi
0x180001344  pop     rbx
0x180001345  retn
0x180001346  mov     ecx, 7
0x18000134b  call    __scrt_fastfail
0x18000b62c  push    rbp
0x18000b62e  sub     rsp, 20h
0x18000b632  mov     rbp, rdx
0x18000b635  mov     cl, [rbp+60h]
0x18000b638  add     rsp, 20h
0x18000b63c  pop     rbp
0x18000b63d  jmp     __scrt_release_startup_lock
```
