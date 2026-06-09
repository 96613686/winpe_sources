# dllmain_crt_process_attach

- ea: `0x18001baf8`
- end: `0x18001bbf2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001baa0`

## callees

- `0x18001baf8`
- `0x18001be50`
- `0x18001be90`
- `0x18001becc`
- `0x18001bfcc`
- `0x18001c0a0`
- `0x18001c140`
- `0x18001c2e8`
- `0x18001c310`
- `0x18001c334`
- `0x18001c344`
- `0x18001c350`
- `0x18001c686`
- `0x18001c692`
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
  ++dword_1800452D0;
  return 1;
}

```

## disassembly

```asm
0x18001baf8  push    rbx
0x18001bafa  push    rsi
0x18001bafb  push    rdi
0x18001bafc  push    r14
0x18001bafe  sub     rsp, 28h
0x18001bb02  mov     rsi, rdx
0x18001bb05  mov     r14, rcx
0x18001bb08  xor     ecx, ecx
0x18001bb0a  call    __scrt_initialize_crt
0x18001bb0f  test    al, al
0x18001bb11  jz      loc_18001BBDA
0x18001bb17  call    __scrt_acquire_startup_lock
0x18001bb1c  mov     bl, al
0x18001bb1e  mov     [rsp+48h+arg_10], al
0x18001bb22  mov     dil, 1
0x18001bb25  cmp     cs:__scrt_current_native_startup_state, 0
0x18001bb2c  jnz     loc_18001BBE6
0x18001bb32  mov     cs:__scrt_current_native_startup_state, 1
0x18001bb3c  call    __scrt_dllmain_before_initialize_c
0x18001bb41  test    al, al
0x18001bb43  jz      short loc_18001BB94
0x18001bb45  call    _RTC_Initialize
0x18001bb4a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001bb4f  call    __scrt_initialize_default_local_stdio_options
0x18001bb54  lea     rdx, __xi_z; Last
0x18001bb5b  lea     rcx, __xi_a; First
0x18001bb62  call    _initterm_e_0
0x18001bb67  test    eax, eax
0x18001bb69  jnz     short loc_18001BB94
0x18001bb6b  call    __scrt_dllmain_after_initialize_c
0x18001bb70  test    al, al
0x18001bb72  jz      short loc_18001BB94
0x18001bb74  lea     rdx, __xc_z; Last
0x18001bb7b  lea     rcx, __xc_a; First
0x18001bb82  call    _initterm_0
0x18001bb87  mov     cs:__scrt_current_native_startup_state, 2
0x18001bb91  xor     dil, dil
0x18001bb94  mov     cl, bl
0x18001bb96  call    __scrt_release_startup_lock
0x18001bb9b  test    dil, dil
0x18001bb9e  jnz     short loc_18001BBDA
0x18001bba0  call    __scrt_get_dyn_tls_init_callback
0x18001bba5  mov     rbx, rax
0x18001bba8  cmp     qword ptr [rax], 0
0x18001bbac  jz      short loc_18001BBCD
0x18001bbae  mov     rcx, rax
0x18001bbb1  call    __scrt_is_nonwritable_in_current_image
0x18001bbb6  test    al, al
0x18001bbb8  jz      short loc_18001BBCD
0x18001bbba  mov     r8, rsi
0x18001bbbd  mov     edx, 2
0x18001bbc2  mov     rcx, r14
0x18001bbc5  mov     rax, [rbx]
0x18001bbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbcd  inc     cs:dword_1800452D0
0x18001bbd3  mov     eax, 1
0x18001bbd8  jmp     short loc_18001BBDC
0x18001bbda  xor     eax, eax
0x18001bbdc  add     rsp, 28h
0x18001bbe0  pop     r14
0x18001bbe2  pop     rdi
0x18001bbe3  pop     rsi
0x18001bbe4  pop     rbx
0x18001bbe5  retn
0x18001bbe6  mov     ecx, 7
0x18001bbeb  call    __scrt_fastfail
0x1800319c9  push    rbp
0x1800319cb  sub     rsp, 20h
0x1800319cf  mov     rbp, rdx
0x1800319d2  mov     cl, [rbp+60h]
0x1800319d5  add     rsp, 20h
0x1800319d9  pop     rbp
0x1800319da  jmp     __scrt_release_startup_lock
```
