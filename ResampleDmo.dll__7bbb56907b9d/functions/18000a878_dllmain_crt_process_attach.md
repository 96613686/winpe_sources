# dllmain_crt_process_attach

- ea: `0x18000a878`
- end: `0x18000a972`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000a820`

## callees

- `0x18000a878`
- `0x18000acfc`
- `0x18000ad24`
- `0x18000ad48`
- `0x18000ad88`
- `0x18000adc4`
- `0x18000aec4`
- `0x18000af98`
- `0x18000b038`
- `0x18000b0f4`
- `0x18000b104`
- `0x18000b110`
- `0x18000b626`
- `0x18000b632`
- `0x180085010`

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
  ++dword_1800B4B50;
  return 1;
}

```

## disassembly

```asm
0x18000a878  push    rbx
0x18000a87a  push    rsi
0x18000a87b  push    rdi
0x18000a87c  push    r14
0x18000a87e  sub     rsp, 28h
0x18000a882  mov     rsi, rdx
0x18000a885  mov     r14, rcx
0x18000a888  xor     ecx, ecx
0x18000a88a  call    __scrt_initialize_crt
0x18000a88f  test    al, al
0x18000a891  jz      loc_18000A95A
0x18000a897  call    __scrt_acquire_startup_lock
0x18000a89c  mov     bl, al
0x18000a89e  mov     [rsp+48h+arg_10], al
0x18000a8a2  mov     dil, 1
0x18000a8a5  cmp     cs:__scrt_current_native_startup_state, 0
0x18000a8ac  jnz     loc_18000A966
0x18000a8b2  mov     cs:__scrt_current_native_startup_state, 1
0x18000a8bc  call    __scrt_dllmain_before_initialize_c
0x18000a8c1  test    al, al
0x18000a8c3  jz      short loc_18000A914
0x18000a8c5  call    _RTC_Initialize
0x18000a8ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000a8cf  call    __scrt_initialize_default_local_stdio_options
0x18000a8d4  lea     rdx, __xi_z; Last
0x18000a8db  lea     rcx, __xi_a; First
0x18000a8e2  call    _initterm_e_0
0x18000a8e7  test    eax, eax
0x18000a8e9  jnz     short loc_18000A914
0x18000a8eb  call    __scrt_dllmain_after_initialize_c
0x18000a8f0  test    al, al
0x18000a8f2  jz      short loc_18000A914
0x18000a8f4  lea     rdx, __xc_z; Last
0x18000a8fb  lea     rcx, __xc_a; First
0x18000a902  call    _initterm_0
0x18000a907  mov     cs:__scrt_current_native_startup_state, 2
0x18000a911  xor     dil, dil
0x18000a914  mov     cl, bl
0x18000a916  call    __scrt_release_startup_lock
0x18000a91b  test    dil, dil
0x18000a91e  jnz     short loc_18000A95A
0x18000a920  call    __scrt_get_dyn_tls_init_callback
0x18000a925  mov     rbx, rax
0x18000a928  cmp     qword ptr [rax], 0
0x18000a92c  jz      short loc_18000A94D
0x18000a92e  mov     rcx, rax
0x18000a931  call    __scrt_is_nonwritable_in_current_image
0x18000a936  test    al, al
0x18000a938  jz      short loc_18000A94D
0x18000a93a  mov     r8, rsi
0x18000a93d  mov     edx, 2
0x18000a942  mov     rcx, r14
0x18000a945  mov     rax, [rbx]
0x18000a948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a94d  inc     cs:dword_1800B4B50
0x18000a953  mov     eax, 1
0x18000a958  jmp     short loc_18000A95C
0x18000a95a  xor     eax, eax
0x18000a95c  add     rsp, 28h
0x18000a960  pop     r14
0x18000a962  pop     rdi
0x18000a963  pop     rsi
0x18000a964  pop     rbx
0x18000a965  retn
0x18000a966  mov     ecx, 7
0x18000a96b  call    __scrt_fastfail
0x180084720  push    rbp
0x180084722  sub     rsp, 20h
0x180084726  mov     rbp, rdx
0x180084729  mov     cl, [rbp+60h]
0x18008472c  add     rsp, 20h
0x180084730  pop     rbp
0x180084731  jmp     __scrt_release_startup_lock
```
