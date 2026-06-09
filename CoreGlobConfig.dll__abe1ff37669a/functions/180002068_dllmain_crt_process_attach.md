# dllmain_crt_process_attach

- ea: `0x180002068`
- end: `0x180002162`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002010`

## callees

- `0x180002068`
- `0x1800023a4`
- `0x1800023e4`
- `0x180002420`
- `0x180002520`
- `0x1800025f4`
- `0x180002694`
- `0x180003010`
- `0x180003038`
- `0x18000305c`
- `0x18000306c`
- `0x180003078`
- `0x180003196`
- `0x1800031a2`
- `0x180025010`

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
  ++dword_1800329F0;
  return 1;
}

```

## disassembly

```asm
0x180002068  push    rbx
0x18000206a  push    rsi
0x18000206b  push    rdi
0x18000206c  push    r14
0x18000206e  sub     rsp, 28h
0x180002072  mov     rsi, rdx
0x180002075  mov     r14, rcx
0x180002078  xor     ecx, ecx
0x18000207a  call    __scrt_initialize_crt
0x18000207f  test    al, al
0x180002081  jz      loc_18000214A
0x180002087  call    __scrt_acquire_startup_lock
0x18000208c  mov     bl, al
0x18000208e  mov     [rsp+48h+arg_10], al
0x180002092  mov     dil, 1
0x180002095  cmp     cs:__scrt_current_native_startup_state, 0
0x18000209c  jnz     loc_180002156
0x1800020a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800020ac  call    __scrt_dllmain_before_initialize_c
0x1800020b1  test    al, al
0x1800020b3  jz      short loc_180002104
0x1800020b5  call    _RTC_Initialize
0x1800020ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800020bf  call    __scrt_initialize_default_local_stdio_options
0x1800020c4  lea     rdx, __xi_z; Last
0x1800020cb  lea     rcx, __xi_a; First
0x1800020d2  call    _initterm_e_0
0x1800020d7  test    eax, eax
0x1800020d9  jnz     short loc_180002104
0x1800020db  call    __scrt_dllmain_after_initialize_c
0x1800020e0  test    al, al
0x1800020e2  jz      short loc_180002104
0x1800020e4  lea     rdx, __xc_z; Last
0x1800020eb  lea     rcx, __xc_a; First
0x1800020f2  call    _initterm_0
0x1800020f7  mov     cs:__scrt_current_native_startup_state, 2
0x180002101  xor     dil, dil
0x180002104  mov     cl, bl
0x180002106  call    __scrt_release_startup_lock
0x18000210b  test    dil, dil
0x18000210e  jnz     short loc_18000214A
0x180002110  call    __scrt_get_dyn_tls_init_callback
0x180002115  mov     rbx, rax
0x180002118  cmp     qword ptr [rax], 0
0x18000211c  jz      short loc_18000213D
0x18000211e  mov     rcx, rax
0x180002121  call    __scrt_is_nonwritable_in_current_image
0x180002126  test    al, al
0x180002128  jz      short loc_18000213D
0x18000212a  mov     r8, rsi
0x18000212d  mov     edx, 2
0x180002132  mov     rcx, r14
0x180002135  mov     rax, [rbx]
0x180002138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000213d  inc     cs:dword_1800329F0
0x180002143  mov     eax, 1
0x180002148  jmp     short loc_18000214C
0x18000214a  xor     eax, eax
0x18000214c  add     rsp, 28h
0x180002150  pop     r14
0x180002152  pop     rdi
0x180002153  pop     rsi
0x180002154  pop     rbx
0x180002155  retn
0x180002156  mov     ecx, 7
0x18000215b  call    __scrt_fastfail
0x180022870  push    rbp
0x180022872  sub     rsp, 20h
0x180022876  mov     rbp, rdx
0x180022879  mov     cl, [rbp+60h]
0x18002287c  add     rsp, 20h
0x180022880  pop     rbp
0x180022881  jmp     __scrt_release_startup_lock
```
