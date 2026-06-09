# dllmain_crt_process_attach

- ea: `0x180002f88`
- end: `0x180003082`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002f30`

## callees

- `0x180002f88`
- `0x18000332c`
- `0x18000336c`
- `0x1800033a8`
- `0x1800034a8`
- `0x18000357c`
- `0x18000361c`
- `0x1800037d8`
- `0x180003800`
- `0x180003824`
- `0x180003834`
- `0x180003840`
- `0x180003be6`
- `0x180003bf2`
- `0x18002c010`

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
  ++dword_18004A3F0;
  return 1;
}

```

## disassembly

```asm
0x180002f88  push    rbx
0x180002f8a  push    rsi
0x180002f8b  push    rdi
0x180002f8c  push    r14
0x180002f8e  sub     rsp, 28h
0x180002f92  mov     rsi, rdx
0x180002f95  mov     r14, rcx
0x180002f98  xor     ecx, ecx
0x180002f9a  call    __scrt_initialize_crt
0x180002f9f  test    al, al
0x180002fa1  jz      loc_18000306A
0x180002fa7  call    __scrt_acquire_startup_lock
0x180002fac  mov     bl, al
0x180002fae  mov     [rsp+48h+arg_10], al
0x180002fb2  mov     dil, 1
0x180002fb5  cmp     cs:__scrt_current_native_startup_state, 0
0x180002fbc  jnz     loc_180003076
0x180002fc2  mov     cs:__scrt_current_native_startup_state, 1
0x180002fcc  call    __scrt_dllmain_before_initialize_c
0x180002fd1  test    al, al
0x180002fd3  jz      short loc_180003024
0x180002fd5  call    _RTC_Initialize
0x180002fda  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180002fdf  call    __scrt_initialize_default_local_stdio_options
0x180002fe4  lea     rdx, __xi_z; Last
0x180002feb  lea     rcx, __xi_a; First
0x180002ff2  call    _initterm_e_0
0x180002ff7  test    eax, eax
0x180002ff9  jnz     short loc_180003024
0x180002ffb  call    __scrt_dllmain_after_initialize_c
0x180003000  test    al, al
0x180003002  jz      short loc_180003024
0x180003004  lea     rdx, __xc_z; Last
0x18000300b  lea     rcx, __xc_a; First
0x180003012  call    _initterm_0
0x180003017  mov     cs:__scrt_current_native_startup_state, 2
0x180003021  xor     dil, dil
0x180003024  mov     cl, bl
0x180003026  call    __scrt_release_startup_lock
0x18000302b  test    dil, dil
0x18000302e  jnz     short loc_18000306A
0x180003030  call    __scrt_get_dyn_tls_init_callback
0x180003035  mov     rbx, rax
0x180003038  cmp     qword ptr [rax], 0
0x18000303c  jz      short loc_18000305D
0x18000303e  mov     rcx, rax
0x180003041  call    __scrt_is_nonwritable_in_current_image
0x180003046  test    al, al
0x180003048  jz      short loc_18000305D
0x18000304a  mov     r8, rsi
0x18000304d  mov     edx, 2
0x180003052  mov     rcx, r14
0x180003055  mov     rax, [rbx]
0x180003058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305d  inc     cs:dword_18004A3F0
0x180003063  mov     eax, 1
0x180003068  jmp     short loc_18000306C
0x18000306a  xor     eax, eax
0x18000306c  add     rsp, 28h
0x180003070  pop     r14
0x180003072  pop     rdi
0x180003073  pop     rsi
0x180003074  pop     rbx
0x180003075  retn
0x180003076  mov     ecx, 7
0x18000307b  call    __scrt_fastfail
0x18002909c  push    rbp
0x18002909e  sub     rsp, 20h
0x1800290a2  mov     rbp, rdx
0x1800290a5  mov     cl, [rbp+60h]
0x1800290a8  add     rsp, 20h
0x1800290ac  pop     rbp
0x1800290ad  jmp     __scrt_release_startup_lock
```
