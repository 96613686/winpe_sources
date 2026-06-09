# dllmain_crt_process_attach

- ea: `0x180001998`
- end: `0x180001a92`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001940`

## callees

- `0x180001998`
- `0x180001de4`
- `0x180001e0c`
- `0x180001e30`
- `0x180001e70`
- `0x180001eac`
- `0x180001fac`
- `0x180002080`
- `0x180002120`
- `0x1800021dc`
- `0x1800021ec`
- `0x1800021f8`
- `0x1800027dc`
- `0x1800027e8`
- `0x180009010`

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
  ++dword_180013290;
  return 1;
}

```

## disassembly

```asm
0x180001998  push    rbx
0x18000199a  push    rsi
0x18000199b  push    rdi
0x18000199c  push    r14
0x18000199e  sub     rsp, 28h
0x1800019a2  mov     rsi, rdx
0x1800019a5  mov     r14, rcx
0x1800019a8  xor     ecx, ecx
0x1800019aa  call    __scrt_initialize_crt
0x1800019af  test    al, al
0x1800019b1  jz      loc_180001A7A
0x1800019b7  call    __scrt_acquire_startup_lock
0x1800019bc  mov     bl, al
0x1800019be  mov     [rsp+48h+arg_10], al
0x1800019c2  mov     dil, 1
0x1800019c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800019cc  jnz     loc_180001A86
0x1800019d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800019dc  call    __scrt_dllmain_before_initialize_c
0x1800019e1  test    al, al
0x1800019e3  jz      short loc_180001A34
0x1800019e5  call    _RTC_Initialize
0x1800019ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800019ef  call    __scrt_initialize_default_local_stdio_options
0x1800019f4  lea     rdx, __xi_z; Last
0x1800019fb  lea     rcx, __xi_a; First
0x180001a02  call    _initterm_e_0
0x180001a07  test    eax, eax
0x180001a09  jnz     short loc_180001A34
0x180001a0b  call    __scrt_dllmain_after_initialize_c
0x180001a10  test    al, al
0x180001a12  jz      short loc_180001A34
0x180001a14  lea     rdx, __xc_z; Last
0x180001a1b  lea     rcx, __xc_a; First
0x180001a22  call    _initterm_0
0x180001a27  mov     cs:__scrt_current_native_startup_state, 2
0x180001a31  xor     dil, dil
0x180001a34  mov     cl, bl
0x180001a36  call    __scrt_release_startup_lock
0x180001a3b  test    dil, dil
0x180001a3e  jnz     short loc_180001A7A
0x180001a40  call    __scrt_get_dyn_tls_init_callback
0x180001a45  mov     rbx, rax
0x180001a48  cmp     qword ptr [rax], 0
0x180001a4c  jz      short loc_180001A6D
0x180001a4e  mov     rcx, rax
0x180001a51  call    __scrt_is_nonwritable_in_current_image
0x180001a56  test    al, al
0x180001a58  jz      short loc_180001A6D
0x180001a5a  mov     r8, rsi
0x180001a5d  mov     edx, 2
0x180001a62  mov     rcx, r14
0x180001a65  mov     rax, [rbx]
0x180001a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a6d  inc     cs:dword_180013290
0x180001a73  mov     eax, 1
0x180001a78  jmp     short loc_180001A7C
0x180001a7a  xor     eax, eax
0x180001a7c  add     rsp, 28h
0x180001a80  pop     r14
0x180001a82  pop     rdi
0x180001a83  pop     rsi
0x180001a84  pop     rbx
0x180001a85  retn
0x180001a86  mov     ecx, 7
0x180001a8b  call    __scrt_fastfail
0x180008c3c  push    rbp
0x180008c3e  sub     rsp, 20h
0x180008c42  mov     rbp, rdx
0x180008c45  mov     cl, [rbp+60h]
0x180008c48  add     rsp, 20h
0x180008c4c  pop     rbp
0x180008c4d  jmp     __scrt_release_startup_lock
```
