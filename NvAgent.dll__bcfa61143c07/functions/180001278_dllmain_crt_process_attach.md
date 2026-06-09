# dllmain_crt_process_attach

- ea: `0x180001278`
- end: `0x180001372`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180001278`
- `0x1800015b4`
- `0x1800015f4`
- `0x180001630`
- `0x180001730`
- `0x180001804`
- `0x1800018a4`
- `0x180001a84`
- `0x180001aac`
- `0x180001ad0`
- `0x180001ae0`
- `0x180001aec`
- `0x180001e66`
- `0x180001e72`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v7)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7u);
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
  _scrt_release_startup_lock(v4);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v7)(a1, 2, a2);
  }
  ++dword_18000B1B0;
  return 1;
}

```

## disassembly

```asm
0x180001278  push    rbx
0x18000127a  push    rsi
0x18000127b  push    rdi
0x18000127c  push    r14
0x18000127e  sub     rsp, 28h
0x180001282  mov     rsi, rdx
0x180001285  mov     r14, rcx
0x180001288  xor     ecx, ecx
0x18000128a  call    __scrt_initialize_crt
0x18000128f  test    al, al
0x180001291  jz      loc_18000135A
0x180001297  call    __scrt_acquire_startup_lock
0x18000129c  mov     bl, al
0x18000129e  mov     [rsp+48h+arg_10], al
0x1800012a2  mov     dil, 1
0x1800012a5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800012ac  jnz     loc_180001366
0x1800012b2  mov     cs:__scrt_current_native_startup_state, 1
0x1800012bc  call    __scrt_dllmain_before_initialize_c
0x1800012c1  test    al, al
0x1800012c3  jz      short loc_180001314
0x1800012c5  call    _RTC_Initialize
0x1800012ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800012cf  call    __scrt_initialize_default_local_stdio_options
0x1800012d4  lea     rdx, __xi_z; Last
0x1800012db  lea     rcx, __xi_a; First
0x1800012e2  call    _initterm_e_0
0x1800012e7  test    eax, eax
0x1800012e9  jnz     short loc_180001314
0x1800012eb  call    __scrt_dllmain_after_initialize_c
0x1800012f0  test    al, al
0x1800012f2  jz      short loc_180001314
0x1800012f4  lea     rdx, __xc_z; Last
0x1800012fb  lea     rcx, __xc_a; First
0x180001302  call    _initterm_0
0x180001307  mov     cs:__scrt_current_native_startup_state, 2
0x180001311  xor     dil, dil
0x180001314  mov     cl, bl
0x180001316  call    __scrt_release_startup_lock
0x18000131b  test    dil, dil
0x18000131e  jnz     short loc_18000135A
0x180001320  call    __scrt_get_dyn_tls_init_callback
0x180001325  mov     rbx, rax
0x180001328  cmp     qword ptr [rax], 0
0x18000132c  jz      short loc_18000134D
0x18000132e  mov     rcx, rax
0x180001331  call    __scrt_is_nonwritable_in_current_image
0x180001336  test    al, al
0x180001338  jz      short loc_18000134D
0x18000133a  mov     r8, rsi
0x18000133d  mov     edx, 2
0x180001342  mov     rcx, r14
0x180001345  mov     rax, [rbx]
0x180001348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000134d  inc     cs:dword_18000B1B0
0x180001353  mov     eax, 1
0x180001358  jmp     short loc_18000135C
0x18000135a  xor     eax, eax
0x18000135c  add     rsp, 28h
0x180001360  pop     r14
0x180001362  pop     rdi
0x180001363  pop     rsi
0x180001364  pop     rbx
0x180001365  retn
0x180001366  mov     ecx, 7
0x18000136b  call    __scrt_fastfail
0x18000624c  push    rbp
0x18000624e  sub     rsp, 20h
0x180006252  mov     rbp, rdx
0x180006255  mov     cl, [rbp+60h]
0x180006258  add     rsp, 20h
0x18000625c  pop     rbp
0x18000625d  jmp     __scrt_release_startup_lock
```
