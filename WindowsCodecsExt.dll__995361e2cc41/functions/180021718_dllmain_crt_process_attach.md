# dllmain_crt_process_attach

- ea: `0x180021718`
- end: `0x180021812`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800216c0`

## callees

- `0x180021718`
- `0x180021b1c`
- `0x180021b44`
- `0x180021b68`
- `0x180021ba8`
- `0x180021be4`
- `0x180021ce4`
- `0x180021db8`
- `0x180021e58`
- `0x180021f14`
- `0x180021f24`
- `0x180021f30`
- `0x180022276`
- `0x180022282`
- `0x180033010`

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
  ++dword_1800401B0;
  return 1;
}

```

## disassembly

```asm
0x180021718  push    rbx
0x18002171a  push    rsi
0x18002171b  push    rdi
0x18002171c  push    r14
0x18002171e  sub     rsp, 28h
0x180021722  mov     rsi, rdx
0x180021725  mov     r14, rcx
0x180021728  xor     ecx, ecx
0x18002172a  call    __scrt_initialize_crt
0x18002172f  test    al, al
0x180021731  jz      loc_1800217FA
0x180021737  call    __scrt_acquire_startup_lock
0x18002173c  mov     bl, al
0x18002173e  mov     [rsp+48h+arg_10], al
0x180021742  mov     dil, 1
0x180021745  cmp     cs:__scrt_current_native_startup_state, 0
0x18002174c  jnz     loc_180021806
0x180021752  mov     cs:__scrt_current_native_startup_state, 1
0x18002175c  call    __scrt_dllmain_before_initialize_c
0x180021761  test    al, al
0x180021763  jz      short loc_1800217B4
0x180021765  call    _RTC_Initialize
0x18002176a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18002176f  call    __scrt_initialize_default_local_stdio_options
0x180021774  lea     rdx, __xi_z; Last
0x18002177b  lea     rcx, __xi_a; First
0x180021782  call    _initterm_e_0
0x180021787  test    eax, eax
0x180021789  jnz     short loc_1800217B4
0x18002178b  call    __scrt_dllmain_after_initialize_c
0x180021790  test    al, al
0x180021792  jz      short loc_1800217B4
0x180021794  lea     rdx, __xc_z; Last
0x18002179b  lea     rcx, __xc_a; First
0x1800217a2  call    _initterm_0
0x1800217a7  mov     cs:__scrt_current_native_startup_state, 2
0x1800217b1  xor     dil, dil
0x1800217b4  mov     cl, bl
0x1800217b6  call    __scrt_release_startup_lock
0x1800217bb  test    dil, dil
0x1800217be  jnz     short loc_1800217FA
0x1800217c0  call    __scrt_get_dyn_tls_init_callback
0x1800217c5  mov     rbx, rax
0x1800217c8  cmp     qword ptr [rax], 0
0x1800217cc  jz      short loc_1800217ED
0x1800217ce  mov     rcx, rax
0x1800217d1  call    __scrt_is_nonwritable_in_current_image
0x1800217d6  test    al, al
0x1800217d8  jz      short loc_1800217ED
0x1800217da  mov     r8, rsi
0x1800217dd  mov     edx, 2
0x1800217e2  mov     rcx, r14
0x1800217e5  mov     rax, [rbx]
0x1800217e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217ed  inc     cs:dword_1800401B0
0x1800217f3  mov     eax, 1
0x1800217f8  jmp     short loc_1800217FC
0x1800217fa  xor     eax, eax
0x1800217fc  add     rsp, 28h
0x180021800  pop     r14
0x180021802  pop     rdi
0x180021803  pop     rsi
0x180021804  pop     rbx
0x180021805  retn
0x180021806  mov     ecx, 7
0x18002180b  call    __scrt_fastfail
0x180032e4c  push    rbp
0x180032e4e  sub     rsp, 20h
0x180032e52  mov     rbp, rdx
0x180032e55  mov     cl, [rbp+60h]
0x180032e58  add     rsp, 20h
0x180032e5c  pop     rbp
0x180032e5d  jmp     __scrt_release_startup_lock
```
