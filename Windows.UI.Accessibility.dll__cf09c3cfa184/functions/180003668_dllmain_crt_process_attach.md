# dllmain_crt_process_attach

- ea: `0x180003668`
- end: `0x180003762`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003610`

## callees

- `0x180003668`
- `0x180003a98`
- `0x180003ac0`
- `0x180003ae4`
- `0x180003b24`
- `0x180003b60`
- `0x180003c60`
- `0x180003d34`
- `0x180003dd4`
- `0x180003e90`
- `0x180003ea0`
- `0x180003eac`
- `0x180004206`
- `0x180004212`
- `0x180035010`

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
  ++dword_180046850;
  return 1;
}

```

## disassembly

```asm
0x180003668  push    rbx
0x18000366a  push    rsi
0x18000366b  push    rdi
0x18000366c  push    r14
0x18000366e  sub     rsp, 28h
0x180003672  mov     rsi, rdx
0x180003675  mov     r14, rcx
0x180003678  xor     ecx, ecx
0x18000367a  call    __scrt_initialize_crt
0x18000367f  test    al, al
0x180003681  jz      loc_18000374A
0x180003687  call    __scrt_acquire_startup_lock
0x18000368c  mov     bl, al
0x18000368e  mov     [rsp+48h+arg_10], al
0x180003692  mov     dil, 1
0x180003695  cmp     cs:__scrt_current_native_startup_state, 0
0x18000369c  jnz     loc_180003756
0x1800036a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800036ac  call    __scrt_dllmain_before_initialize_c
0x1800036b1  test    al, al
0x1800036b3  jz      short loc_180003704
0x1800036b5  call    _RTC_Initialize
0x1800036ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800036bf  call    __scrt_initialize_default_local_stdio_options
0x1800036c4  lea     rdx, __xi_z; Last
0x1800036cb  lea     rcx, __xi_a; First
0x1800036d2  call    _initterm_e_0
0x1800036d7  test    eax, eax
0x1800036d9  jnz     short loc_180003704
0x1800036db  call    __scrt_dllmain_after_initialize_c
0x1800036e0  test    al, al
0x1800036e2  jz      short loc_180003704
0x1800036e4  lea     rdx, __xc_z; Last
0x1800036eb  lea     rcx, __xc_a; First
0x1800036f2  call    _initterm_0
0x1800036f7  mov     cs:__scrt_current_native_startup_state, 2
0x180003701  xor     dil, dil
0x180003704  mov     cl, bl
0x180003706  call    __scrt_release_startup_lock
0x18000370b  test    dil, dil
0x18000370e  jnz     short loc_18000374A
0x180003710  call    __scrt_get_dyn_tls_init_callback
0x180003715  mov     rbx, rax
0x180003718  cmp     qword ptr [rax], 0
0x18000371c  jz      short loc_18000373D
0x18000371e  mov     rcx, rax
0x180003721  call    __scrt_is_nonwritable_in_current_image
0x180003726  test    al, al
0x180003728  jz      short loc_18000373D
0x18000372a  mov     r8, rsi
0x18000372d  mov     edx, 2
0x180003732  mov     rcx, r14
0x180003735  mov     rax, [rbx]
0x180003738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373d  inc     cs:dword_180046850
0x180003743  mov     eax, 1
0x180003748  jmp     short loc_18000374C
0x18000374a  xor     eax, eax
0x18000374c  add     rsp, 28h
0x180003750  pop     r14
0x180003752  pop     rdi
0x180003753  pop     rsi
0x180003754  pop     rbx
0x180003755  retn
0x180003756  mov     ecx, 7
0x18000375b  call    __scrt_fastfail
0x180031ddc  push    rbp
0x180031dde  sub     rsp, 20h
0x180031de2  mov     rbp, rdx
0x180031de5  mov     cl, [rbp+60h]
0x180031de8  add     rsp, 20h
0x180031dec  pop     rbp
0x180031ded  jmp     __scrt_release_startup_lock
```
