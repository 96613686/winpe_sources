# dllmain_crt_process_attach

- ea: `0x180003e58`
- end: `0x180003f52`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003e00`

## callees

- `0x180003e58`
- `0x1800042e4`
- `0x180004324`
- `0x180004360`
- `0x180004460`
- `0x180004534`
- `0x1800045d4`
- `0x180004d98`
- `0x180004dc0`
- `0x180004de4`
- `0x180004df4`
- `0x180004e00`
- `0x180004ec6`
- `0x180004ed2`
- `0x180032010`

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
  ++dword_18005F850;
  return 1;
}

```

## disassembly

```asm
0x180003e58  push    rbx
0x180003e5a  push    rsi
0x180003e5b  push    rdi
0x180003e5c  push    r14
0x180003e5e  sub     rsp, 28h
0x180003e62  mov     rsi, rdx
0x180003e65  mov     r14, rcx
0x180003e68  xor     ecx, ecx
0x180003e6a  call    __scrt_initialize_crt
0x180003e6f  test    al, al
0x180003e71  jz      loc_180003F3A
0x180003e77  call    __scrt_acquire_startup_lock
0x180003e7c  mov     bl, al
0x180003e7e  mov     [rsp+48h+arg_10], al
0x180003e82  mov     dil, 1
0x180003e85  cmp     cs:__scrt_current_native_startup_state, 0
0x180003e8c  jnz     loc_180003F46
0x180003e92  mov     cs:__scrt_current_native_startup_state, 1
0x180003e9c  call    __scrt_dllmain_before_initialize_c
0x180003ea1  test    al, al
0x180003ea3  jz      short loc_180003EF4
0x180003ea5  call    _RTC_Initialize
0x180003eaa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180003eaf  call    __scrt_initialize_default_local_stdio_options
0x180003eb4  lea     rdx, __xi_z; Last
0x180003ebb  lea     rcx, __xi_a; First
0x180003ec2  call    _initterm_e_0
0x180003ec7  test    eax, eax
0x180003ec9  jnz     short loc_180003EF4
0x180003ecb  call    __scrt_dllmain_after_initialize_c
0x180003ed0  test    al, al
0x180003ed2  jz      short loc_180003EF4
0x180003ed4  lea     rdx, __xc_z; Last
0x180003edb  lea     rcx, __xc_a; First
0x180003ee2  call    _initterm_0
0x180003ee7  mov     cs:__scrt_current_native_startup_state, 2
0x180003ef1  xor     dil, dil
0x180003ef4  mov     cl, bl
0x180003ef6  call    __scrt_release_startup_lock
0x180003efb  test    dil, dil
0x180003efe  jnz     short loc_180003F3A
0x180003f00  call    __scrt_get_dyn_tls_init_callback
0x180003f05  mov     rbx, rax
0x180003f08  cmp     qword ptr [rax], 0
0x180003f0c  jz      short loc_180003F2D
0x180003f0e  mov     rcx, rax
0x180003f11  call    __scrt_is_nonwritable_in_current_image
0x180003f16  test    al, al
0x180003f18  jz      short loc_180003F2D
0x180003f1a  mov     r8, rsi
0x180003f1d  mov     edx, 2
0x180003f22  mov     rcx, r14
0x180003f25  mov     rax, [rbx]
0x180003f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2d  inc     cs:dword_18005F850
0x180003f33  mov     eax, 1
0x180003f38  jmp     short loc_180003F3C
0x180003f3a  xor     eax, eax
0x180003f3c  add     rsp, 28h
0x180003f40  pop     r14
0x180003f42  pop     rdi
0x180003f43  pop     rsi
0x180003f44  pop     rbx
0x180003f45  retn
0x180003f46  mov     ecx, 7
0x180003f4b  call    __scrt_fastfail
0x18003019c  push    rbp
0x18003019e  sub     rsp, 20h
0x1800301a2  mov     rbp, rdx
0x1800301a5  mov     cl, [rbp+60h]
0x1800301a8  add     rsp, 20h
0x1800301ac  pop     rbp
0x1800301ad  jmp     __scrt_release_startup_lock
```
