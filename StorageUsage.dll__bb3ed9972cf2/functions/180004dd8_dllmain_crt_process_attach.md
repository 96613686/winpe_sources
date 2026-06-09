# dllmain_crt_process_attach

- ea: `0x180004dd8`
- end: `0x180004ed2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180004d80`

## callees

- `0x180004dd8`
- `0x18000524c`
- `0x18000528c`
- `0x1800052c8`
- `0x1800053c8`
- `0x18000549c`
- `0x18000553c`
- `0x180005704`
- `0x18000572c`
- `0x180005750`
- `0x180005760`
- `0x18000576c`
- `0x180005b36`
- `0x180005b42`
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
  ++dword_1800404D0;
  return 1;
}

```

## disassembly

```asm
0x180004dd8  push    rbx
0x180004dda  push    rsi
0x180004ddb  push    rdi
0x180004ddc  push    r14
0x180004dde  sub     rsp, 28h
0x180004de2  mov     rsi, rdx
0x180004de5  mov     r14, rcx
0x180004de8  xor     ecx, ecx
0x180004dea  call    __scrt_initialize_crt
0x180004def  test    al, al
0x180004df1  jz      loc_180004EBA
0x180004df7  call    __scrt_acquire_startup_lock
0x180004dfc  mov     bl, al
0x180004dfe  mov     [rsp+48h+arg_10], al
0x180004e02  mov     dil, 1
0x180004e05  cmp     cs:__scrt_current_native_startup_state, 0
0x180004e0c  jnz     loc_180004EC6
0x180004e12  mov     cs:__scrt_current_native_startup_state, 1
0x180004e1c  call    __scrt_dllmain_before_initialize_c
0x180004e21  test    al, al
0x180004e23  jz      short loc_180004E74
0x180004e25  call    _RTC_Initialize
0x180004e2a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180004e2f  call    __scrt_initialize_default_local_stdio_options
0x180004e34  lea     rdx, __xi_z; Last
0x180004e3b  lea     rcx, __xi_a; First
0x180004e42  call    _initterm_e_0
0x180004e47  test    eax, eax
0x180004e49  jnz     short loc_180004E74
0x180004e4b  call    __scrt_dllmain_after_initialize_c
0x180004e50  test    al, al
0x180004e52  jz      short loc_180004E74
0x180004e54  lea     rdx, __xc_z; Last
0x180004e5b  lea     rcx, __xc_a; First
0x180004e62  call    _initterm_0
0x180004e67  mov     cs:__scrt_current_native_startup_state, 2
0x180004e71  xor     dil, dil
0x180004e74  mov     cl, bl
0x180004e76  call    __scrt_release_startup_lock
0x180004e7b  test    dil, dil
0x180004e7e  jnz     short loc_180004EBA
0x180004e80  call    __scrt_get_dyn_tls_init_callback
0x180004e85  mov     rbx, rax
0x180004e88  cmp     qword ptr [rax], 0
0x180004e8c  jz      short loc_180004EAD
0x180004e8e  mov     rcx, rax
0x180004e91  call    __scrt_is_nonwritable_in_current_image
0x180004e96  test    al, al
0x180004e98  jz      short loc_180004EAD
0x180004e9a  mov     r8, rsi
0x180004e9d  mov     edx, 2
0x180004ea2  mov     rcx, r14
0x180004ea5  mov     rax, [rbx]
0x180004ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ead  inc     cs:dword_1800404D0
0x180004eb3  mov     eax, 1
0x180004eb8  jmp     short loc_180004EBC
0x180004eba  xor     eax, eax
0x180004ebc  add     rsp, 28h
0x180004ec0  pop     r14
0x180004ec2  pop     rdi
0x180004ec3  pop     rsi
0x180004ec4  pop     rbx
0x180004ec5  retn
0x180004ec6  mov     ecx, 7
0x180004ecb  call    __scrt_fastfail
0x18002b01c  push    rbp
0x18002b01e  sub     rsp, 20h
0x18002b022  mov     rbp, rdx
0x18002b025  mov     cl, [rbp+60h]
0x18002b028  add     rsp, 20h
0x18002b02c  pop     rbp
0x18002b02d  jmp     __scrt_release_startup_lock
```
