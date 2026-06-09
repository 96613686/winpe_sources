# dllmain_crt_process_attach

- ea: `0x180008768`
- end: `0x180008862`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180008710`

## callees

- `0x180008768`
- `0x180008aa4`
- `0x180008ae4`
- `0x180008b20`
- `0x180008c20`
- `0x180008cf4`
- `0x180008d94`
- `0x180008f48`
- `0x180008f70`
- `0x180008f94`
- `0x180008fa4`
- `0x180008fb0`
- `0x180009316`
- `0x180009322`
- `0x18000a010`

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
  ++dword_18000F2D0;
  return 1;
}

```

## disassembly

```asm
0x180008768  push    rbx
0x18000876a  push    rsi
0x18000876b  push    rdi
0x18000876c  push    r14
0x18000876e  sub     rsp, 28h
0x180008772  mov     rsi, rdx
0x180008775  mov     r14, rcx
0x180008778  xor     ecx, ecx
0x18000877a  call    __scrt_initialize_crt
0x18000877f  test    al, al
0x180008781  jz      loc_18000884A
0x180008787  call    __scrt_acquire_startup_lock
0x18000878c  mov     bl, al
0x18000878e  mov     [rsp+48h+arg_10], al
0x180008792  mov     dil, 1
0x180008795  cmp     cs:__scrt_current_native_startup_state, 0
0x18000879c  jnz     loc_180008856
0x1800087a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800087ac  call    __scrt_dllmain_before_initialize_c
0x1800087b1  test    al, al
0x1800087b3  jz      short loc_180008804
0x1800087b5  call    _RTC_Initialize
0x1800087ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800087bf  call    __scrt_initialize_default_local_stdio_options
0x1800087c4  lea     rdx, __xi_z; Last
0x1800087cb  lea     rcx, __xi_a; First
0x1800087d2  call    _initterm_e_0
0x1800087d7  test    eax, eax
0x1800087d9  jnz     short loc_180008804
0x1800087db  call    __scrt_dllmain_after_initialize_c
0x1800087e0  test    al, al
0x1800087e2  jz      short loc_180008804
0x1800087e4  lea     rdx, __xc_z; Last
0x1800087eb  lea     rcx, __xc_a; First
0x1800087f2  call    _initterm_0
0x1800087f7  mov     cs:__scrt_current_native_startup_state, 2
0x180008801  xor     dil, dil
0x180008804  mov     cl, bl
0x180008806  call    __scrt_release_startup_lock
0x18000880b  test    dil, dil
0x18000880e  jnz     short loc_18000884A
0x180008810  call    __scrt_get_dyn_tls_init_callback
0x180008815  mov     rbx, rax
0x180008818  cmp     qword ptr [rax], 0
0x18000881c  jz      short loc_18000883D
0x18000881e  mov     rcx, rax
0x180008821  call    __scrt_is_nonwritable_in_current_image
0x180008826  test    al, al
0x180008828  jz      short loc_18000883D
0x18000882a  mov     r8, rsi
0x18000882d  mov     edx, 2
0x180008832  mov     rcx, r14
0x180008835  mov     rax, [rbx]
0x180008838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000883d  inc     cs:dword_18000F2D0
0x180008843  mov     eax, 1
0x180008848  jmp     short loc_18000884C
0x18000884a  xor     eax, eax
0x18000884c  add     rsp, 28h
0x180008850  pop     r14
0x180008852  pop     rdi
0x180008853  pop     rsi
0x180008854  pop     rbx
0x180008855  retn
0x180008856  mov     ecx, 7
0x18000885b  call    __scrt_fastfail
0x180009952  push    rbp
0x180009954  sub     rsp, 20h
0x180009958  mov     rbp, rdx
0x18000995b  mov     cl, [rbp+60h]
0x18000995e  add     rsp, 20h
0x180009962  pop     rbp
0x180009963  jmp     __scrt_release_startup_lock
```
