# dllmain_crt_process_attach

- ea: `0x180001568`
- end: `0x180001662`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001510`

## callees

- `0x180001568`
- `0x180001960`
- `0x180001988`
- `0x1800019ac`
- `0x1800019ec`
- `0x180001a28`
- `0x180001b28`
- `0x180001bfc`
- `0x180001c9c`
- `0x180001cf8`
- `0x180001d08`
- `0x180001d14`
- `0x180002076`
- `0x180002082`
- `0x180022010`

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
  ++dword_180039610;
  return 1;
}

```

## disassembly

```asm
0x180001568  push    rbx
0x18000156a  push    rsi
0x18000156b  push    rdi
0x18000156c  push    r14
0x18000156e  sub     rsp, 28h
0x180001572  mov     rsi, rdx
0x180001575  mov     r14, rcx
0x180001578  xor     ecx, ecx
0x18000157a  call    __scrt_initialize_crt
0x18000157f  test    al, al
0x180001581  jz      loc_18000164A
0x180001587  call    __scrt_acquire_startup_lock
0x18000158c  mov     bl, al
0x18000158e  mov     [rsp+48h+arg_10], al
0x180001592  mov     dil, 1
0x180001595  cmp     cs:__scrt_current_native_startup_state, 0
0x18000159c  jnz     loc_180001656
0x1800015a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800015ac  call    __scrt_dllmain_before_initialize_c
0x1800015b1  test    al, al
0x1800015b3  jz      short loc_180001604
0x1800015b5  call    _RTC_Initialize
0x1800015ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800015bf  call    __scrt_initialize_default_local_stdio_options
0x1800015c4  lea     rdx, __xi_z; Last
0x1800015cb  lea     rcx, __xi_a; First
0x1800015d2  call    _initterm_e_0
0x1800015d7  test    eax, eax
0x1800015d9  jnz     short loc_180001604
0x1800015db  call    __scrt_dllmain_after_initialize_c
0x1800015e0  test    al, al
0x1800015e2  jz      short loc_180001604
0x1800015e4  lea     rdx, __xc_z; Last
0x1800015eb  lea     rcx, __xc_a; First
0x1800015f2  call    _initterm_0
0x1800015f7  mov     cs:__scrt_current_native_startup_state, 2
0x180001601  xor     dil, dil
0x180001604  mov     cl, bl
0x180001606  call    __scrt_release_startup_lock
0x18000160b  test    dil, dil
0x18000160e  jnz     short loc_18000164A
0x180001610  call    __scrt_get_dyn_tls_init_callback
0x180001615  mov     rbx, rax
0x180001618  cmp     qword ptr [rax], 0
0x18000161c  jz      short loc_18000163D
0x18000161e  mov     rcx, rax
0x180001621  call    __scrt_is_nonwritable_in_current_image
0x180001626  test    al, al
0x180001628  jz      short loc_18000163D
0x18000162a  mov     r8, rsi
0x18000162d  mov     edx, 2
0x180001632  mov     rcx, r14
0x180001635  mov     rax, [rbx]
0x180001638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000163d  inc     cs:dword_180039610
0x180001643  mov     eax, 1
0x180001648  jmp     short loc_18000164C
0x18000164a  xor     eax, eax
0x18000164c  add     rsp, 28h
0x180001650  pop     r14
0x180001652  pop     rdi
0x180001653  pop     rsi
0x180001654  pop     rbx
0x180001655  retn
0x180001656  mov     ecx, 7
0x18000165b  call    __scrt_fastfail
0x180020fbc  push    rbp
0x180020fbe  sub     rsp, 20h
0x180020fc2  mov     rbp, rdx
0x180020fc5  mov     cl, [rbp+60h]
0x180020fc8  add     rsp, 20h
0x180020fcc  pop     rbp
0x180020fcd  jmp     __scrt_release_startup_lock
```
