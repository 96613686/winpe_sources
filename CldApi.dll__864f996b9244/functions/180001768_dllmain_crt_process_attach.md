# dllmain_crt_process_attach

- ea: `0x180001768`
- end: `0x180001862`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001710`

## callees

- `0x180001768`
- `0x180001b60`
- `0x180001b88`
- `0x180001bac`
- `0x180001bec`
- `0x180001c28`
- `0x180001d28`
- `0x180001dfc`
- `0x180001e9c`
- `0x180001ef8`
- `0x180001f08`
- `0x180001f14`
- `0x180002276`
- `0x180002282`
- `0x18001c010`

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
  ++dword_180028810;
  return 1;
}

```

## disassembly

```asm
0x180001768  push    rbx
0x18000176a  push    rsi
0x18000176b  push    rdi
0x18000176c  push    r14
0x18000176e  sub     rsp, 28h
0x180001772  mov     rsi, rdx
0x180001775  mov     r14, rcx
0x180001778  xor     ecx, ecx
0x18000177a  call    __scrt_initialize_crt
0x18000177f  test    al, al
0x180001781  jz      loc_18000184A
0x180001787  call    __scrt_acquire_startup_lock
0x18000178c  mov     bl, al
0x18000178e  mov     [rsp+48h+arg_10], al
0x180001792  mov     dil, 1
0x180001795  cmp     cs:__scrt_current_native_startup_state, 0
0x18000179c  jnz     loc_180001856
0x1800017a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800017ac  call    __scrt_dllmain_before_initialize_c
0x1800017b1  test    al, al
0x1800017b3  jz      short loc_180001804
0x1800017b5  call    _RTC_Initialize
0x1800017ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800017bf  call    __scrt_initialize_default_local_stdio_options
0x1800017c4  lea     rdx, __xi_z; Last
0x1800017cb  lea     rcx, __xi_a; First
0x1800017d2  call    _initterm_e_0
0x1800017d7  test    eax, eax
0x1800017d9  jnz     short loc_180001804
0x1800017db  call    __scrt_dllmain_after_initialize_c
0x1800017e0  test    al, al
0x1800017e2  jz      short loc_180001804
0x1800017e4  lea     rdx, __xc_z; Last
0x1800017eb  lea     rcx, __xc_a; First
0x1800017f2  call    _initterm_0
0x1800017f7  mov     cs:__scrt_current_native_startup_state, 2
0x180001801  xor     dil, dil
0x180001804  mov     cl, bl
0x180001806  call    __scrt_release_startup_lock
0x18000180b  test    dil, dil
0x18000180e  jnz     short loc_18000184A
0x180001810  call    __scrt_get_dyn_tls_init_callback
0x180001815  mov     rbx, rax
0x180001818  cmp     qword ptr [rax], 0
0x18000181c  jz      short loc_18000183D
0x18000181e  mov     rcx, rax
0x180001821  call    __scrt_is_nonwritable_in_current_image
0x180001826  test    al, al
0x180001828  jz      short loc_18000183D
0x18000182a  mov     r8, rsi
0x18000182d  mov     edx, 2
0x180001832  mov     rcx, r14
0x180001835  mov     rax, [rbx]
0x180001838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000183d  inc     cs:dword_180028810
0x180001843  mov     eax, 1
0x180001848  jmp     short loc_18000184C
0x18000184a  xor     eax, eax
0x18000184c  add     rsp, 28h
0x180001850  pop     r14
0x180001852  pop     rdi
0x180001853  pop     rsi
0x180001854  pop     rbx
0x180001855  retn
0x180001856  mov     ecx, 7
0x18000185b  call    __scrt_fastfail
0x18001bedc  push    rbp
0x18001bede  sub     rsp, 20h
0x18001bee2  mov     rbp, rdx
0x18001bee5  mov     cl, [rbp+60h]
0x18001bee8  add     rsp, 20h
0x18001beec  pop     rbp
0x18001beed  jmp     __scrt_release_startup_lock
```
