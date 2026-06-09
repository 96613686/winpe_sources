# dllmain_crt_process_attach

- ea: `0x1800017a8`
- end: `0x1800018a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001750`

## callees

- `0x1800017a8`
- `0x180001ae4`
- `0x180001b24`
- `0x180001b60`
- `0x180001c60`
- `0x180001d34`
- `0x180001dd4`
- `0x180001fd8`
- `0x180002000`
- `0x180002024`
- `0x180002034`
- `0x180002040`
- `0x1800025b6`
- `0x1800025c2`
- `0x180023010`

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
  ++dword_18002F7D0;
  return 1;
}

```

## disassembly

```asm
0x1800017a8  push    rbx
0x1800017aa  push    rsi
0x1800017ab  push    rdi
0x1800017ac  push    r14
0x1800017ae  sub     rsp, 28h
0x1800017b2  mov     rsi, rdx
0x1800017b5  mov     r14, rcx
0x1800017b8  xor     ecx, ecx
0x1800017ba  call    __scrt_initialize_crt
0x1800017bf  test    al, al
0x1800017c1  jz      loc_18000188A
0x1800017c7  call    __scrt_acquire_startup_lock
0x1800017cc  mov     bl, al
0x1800017ce  mov     [rsp+48h+arg_10], al
0x1800017d2  mov     dil, 1
0x1800017d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800017dc  jnz     loc_180001896
0x1800017e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800017ec  call    __scrt_dllmain_before_initialize_c
0x1800017f1  test    al, al
0x1800017f3  jz      short loc_180001844
0x1800017f5  call    _RTC_Initialize
0x1800017fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800017ff  call    __scrt_initialize_default_local_stdio_options
0x180001804  lea     rdx, __xi_z; Last
0x18000180b  lea     rcx, __xi_a; First
0x180001812  call    _initterm_e_0
0x180001817  test    eax, eax
0x180001819  jnz     short loc_180001844
0x18000181b  call    __scrt_dllmain_after_initialize_c
0x180001820  test    al, al
0x180001822  jz      short loc_180001844
0x180001824  lea     rdx, __xc_z; Last
0x18000182b  lea     rcx, __xc_a; First
0x180001832  call    _initterm_0
0x180001837  mov     cs:__scrt_current_native_startup_state, 2
0x180001841  xor     dil, dil
0x180001844  mov     cl, bl
0x180001846  call    __scrt_release_startup_lock
0x18000184b  test    dil, dil
0x18000184e  jnz     short loc_18000188A
0x180001850  call    __scrt_get_dyn_tls_init_callback
0x180001855  mov     rbx, rax
0x180001858  cmp     qword ptr [rax], 0
0x18000185c  jz      short loc_18000187D
0x18000185e  mov     rcx, rax
0x180001861  call    __scrt_is_nonwritable_in_current_image
0x180001866  test    al, al
0x180001868  jz      short loc_18000187D
0x18000186a  mov     r8, rsi
0x18000186d  mov     edx, 2
0x180001872  mov     rcx, r14
0x180001875  mov     rax, [rbx]
0x180001878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000187d  inc     cs:dword_18002F7D0
0x180001883  mov     eax, 1
0x180001888  jmp     short loc_18000188C
0x18000188a  xor     eax, eax
0x18000188c  add     rsp, 28h
0x180001890  pop     r14
0x180001892  pop     rdi
0x180001893  pop     rsi
0x180001894  pop     rbx
0x180001895  retn
0x180001896  mov     ecx, 7
0x18000189b  call    __scrt_fastfail
0x1800229dc  push    rbp
0x1800229de  sub     rsp, 20h
0x1800229e2  mov     rbp, rdx
0x1800229e5  mov     cl, [rbp+60h]
0x1800229e8  add     rsp, 20h
0x1800229ec  pop     rbp
0x1800229ed  jmp     __scrt_release_startup_lock
```
