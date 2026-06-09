# dllmain_crt_process_attach

- ea: `0x180016728`
- end: `0x180016822`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800166d0`

## callees

- `0x180016728`
- `0x180016abc`
- `0x180016afc`
- `0x180016b38`
- `0x180016c38`
- `0x180016d0c`
- `0x180016dac`
- `0x180016f24`
- `0x180016f4c`
- `0x180016f70`
- `0x180016f80`
- `0x180016f8c`
- `0x1800172e6`
- `0x1800172f2`
- `0x180029010`

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
  ++dword_180099EB0;
  return 1;
}

```

## disassembly

```asm
0x180016728  push    rbx
0x18001672a  push    rsi
0x18001672b  push    rdi
0x18001672c  push    r14
0x18001672e  sub     rsp, 28h
0x180016732  mov     rsi, rdx
0x180016735  mov     r14, rcx
0x180016738  xor     ecx, ecx
0x18001673a  call    __scrt_initialize_crt
0x18001673f  test    al, al
0x180016741  jz      loc_18001680A
0x180016747  call    __scrt_acquire_startup_lock
0x18001674c  mov     bl, al
0x18001674e  mov     [rsp+48h+arg_10], al
0x180016752  mov     dil, 1
0x180016755  cmp     cs:__scrt_current_native_startup_state, 0
0x18001675c  jnz     loc_180016816
0x180016762  mov     cs:__scrt_current_native_startup_state, 1
0x18001676c  call    __scrt_dllmain_before_initialize_c
0x180016771  test    al, al
0x180016773  jz      short loc_1800167C4
0x180016775  call    _RTC_Initialize
0x18001677a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001677f  call    __scrt_initialize_default_local_stdio_options
0x180016784  lea     rdx, __xi_z; Last
0x18001678b  lea     rcx, __xi_a; First
0x180016792  call    _initterm_e_0
0x180016797  test    eax, eax
0x180016799  jnz     short loc_1800167C4
0x18001679b  call    __scrt_dllmain_after_initialize_c
0x1800167a0  test    al, al
0x1800167a2  jz      short loc_1800167C4
0x1800167a4  lea     rdx, __xc_z; Last
0x1800167ab  lea     rcx, __xc_a; First
0x1800167b2  call    _initterm_0
0x1800167b7  mov     cs:__scrt_current_native_startup_state, 2
0x1800167c1  xor     dil, dil
0x1800167c4  mov     cl, bl
0x1800167c6  call    __scrt_release_startup_lock
0x1800167cb  test    dil, dil
0x1800167ce  jnz     short loc_18001680A
0x1800167d0  call    __scrt_get_dyn_tls_init_callback
0x1800167d5  mov     rbx, rax
0x1800167d8  cmp     qword ptr [rax], 0
0x1800167dc  jz      short loc_1800167FD
0x1800167de  mov     rcx, rax
0x1800167e1  call    __scrt_is_nonwritable_in_current_image
0x1800167e6  test    al, al
0x1800167e8  jz      short loc_1800167FD
0x1800167ea  mov     r8, rsi
0x1800167ed  mov     edx, 2
0x1800167f2  mov     rcx, r14
0x1800167f5  mov     rax, [rbx]
0x1800167f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167fd  inc     cs:dword_180099EB0
0x180016803  mov     eax, 1
0x180016808  jmp     short loc_18001680C
0x18001680a  xor     eax, eax
0x18001680c  add     rsp, 28h
0x180016810  pop     r14
0x180016812  pop     rdi
0x180016813  pop     rsi
0x180016814  pop     rbx
0x180016815  retn
0x180016816  mov     ecx, 7
0x18001681b  call    __scrt_fastfail
0x18002807b  push    rbp
0x18002807d  sub     rsp, 20h
0x180028081  mov     rbp, rdx
0x180028084  mov     cl, [rbp+60h]
0x180028087  add     rsp, 20h
0x18002808b  pop     rbp
0x18002808c  jmp     __scrt_release_startup_lock
```
