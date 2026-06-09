# dllmain_crt_process_attach

- ea: `0x180001168`
- end: `0x180001262`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001110`

## callees

- `0x180001168`
- `0x180001560`
- `0x180001588`
- `0x1800015ac`
- `0x1800015ec`
- `0x180001628`
- `0x180001728`
- `0x1800017fc`
- `0x18000189c`
- `0x1800018f8`
- `0x180001908`
- `0x180001914`
- `0x180001c86`
- `0x180001c92`
- `0x180002010`

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
  ++dword_1800B3350;
  return 1;
}

```

## disassembly

```asm
0x180001168  push    rbx
0x18000116a  push    rsi
0x18000116b  push    rdi
0x18000116c  push    r14
0x18000116e  sub     rsp, 28h
0x180001172  mov     rsi, rdx
0x180001175  mov     r14, rcx
0x180001178  xor     ecx, ecx
0x18000117a  call    __scrt_initialize_crt
0x18000117f  test    al, al
0x180001181  jz      loc_18000124A
0x180001187  call    __scrt_acquire_startup_lock
0x18000118c  mov     bl, al
0x18000118e  mov     [rsp+48h+arg_10], al
0x180001192  mov     dil, 1
0x180001195  cmp     cs:__scrt_current_native_startup_state, 0
0x18000119c  jnz     loc_180001256
0x1800011a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800011ac  call    __scrt_dllmain_before_initialize_c
0x1800011b1  test    al, al
0x1800011b3  jz      short loc_180001204
0x1800011b5  call    _RTC_Initialize
0x1800011ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800011bf  call    __scrt_initialize_default_local_stdio_options
0x1800011c4  lea     rdx, __xi_z; Last
0x1800011cb  lea     rcx, __xi_a; First
0x1800011d2  call    _initterm_e_0
0x1800011d7  test    eax, eax
0x1800011d9  jnz     short loc_180001204
0x1800011db  call    __scrt_dllmain_after_initialize_c
0x1800011e0  test    al, al
0x1800011e2  jz      short loc_180001204
0x1800011e4  lea     rdx, __xc_z; Last
0x1800011eb  lea     rcx, __xc_a; First
0x1800011f2  call    _initterm_0
0x1800011f7  mov     cs:__scrt_current_native_startup_state, 2
0x180001201  xor     dil, dil
0x180001204  mov     cl, bl
0x180001206  call    __scrt_release_startup_lock
0x18000120b  test    dil, dil
0x18000120e  jnz     short loc_18000124A
0x180001210  call    __scrt_get_dyn_tls_init_callback
0x180001215  mov     rbx, rax
0x180001218  cmp     qword ptr [rax], 0
0x18000121c  jz      short loc_18000123D
0x18000121e  mov     rcx, rax
0x180001221  call    __scrt_is_nonwritable_in_current_image
0x180001226  test    al, al
0x180001228  jz      short loc_18000123D
0x18000122a  mov     r8, rsi
0x18000122d  mov     edx, 2
0x180001232  mov     rcx, r14
0x180001235  mov     rax, [rbx]
0x180001238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000123d  inc     cs:dword_1800B3350
0x180001243  mov     eax, 1
0x180001248  jmp     short loc_18000124C
0x18000124a  xor     eax, eax
0x18000124c  add     rsp, 28h
0x180001250  pop     r14
0x180001252  pop     rdi
0x180001253  pop     rsi
0x180001254  pop     rbx
0x180001255  retn
0x180001256  mov     ecx, 7
0x18000125b  call    __scrt_fastfail
0x180001e2c  push    rbp
0x180001e2e  sub     rsp, 20h
0x180001e32  mov     rbp, rdx
0x180001e35  mov     cl, [rbp+60h]
0x180001e38  add     rsp, 20h
0x180001e3c  pop     rbp
0x180001e3d  jmp     __scrt_release_startup_lock
```
