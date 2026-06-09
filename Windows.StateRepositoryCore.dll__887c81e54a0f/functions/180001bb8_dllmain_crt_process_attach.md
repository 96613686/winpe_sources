# dllmain_crt_process_attach

- ea: `0x180001bb8`
- end: `0x180001cb2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001b60`

## callees

- `0x180001bb8`
- `0x180001ef4`
- `0x180001f34`
- `0x180001f70`
- `0x180002070`
- `0x180002144`
- `0x1800021e4`
- `0x180002398`
- `0x1800023c0`
- `0x1800023e4`
- `0x1800023f4`
- `0x180002400`
- `0x180002766`
- `0x180002772`
- `0x180011010`

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
  ++dword_1800182B0;
  return 1;
}

```

## disassembly

```asm
0x180001bb8  push    rbx
0x180001bba  push    rsi
0x180001bbb  push    rdi
0x180001bbc  push    r14
0x180001bbe  sub     rsp, 28h
0x180001bc2  mov     rsi, rdx
0x180001bc5  mov     r14, rcx
0x180001bc8  xor     ecx, ecx
0x180001bca  call    __scrt_initialize_crt
0x180001bcf  test    al, al
0x180001bd1  jz      loc_180001C9A
0x180001bd7  call    __scrt_acquire_startup_lock
0x180001bdc  mov     bl, al
0x180001bde  mov     [rsp+48h+arg_10], al
0x180001be2  mov     dil, 1
0x180001be5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001bec  jnz     loc_180001CA6
0x180001bf2  mov     cs:__scrt_current_native_startup_state, 1
0x180001bfc  call    __scrt_dllmain_before_initialize_c
0x180001c01  test    al, al
0x180001c03  jz      short loc_180001C54
0x180001c05  call    _RTC_Initialize
0x180001c0a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001c0f  call    __scrt_initialize_default_local_stdio_options
0x180001c14  lea     rdx, __xi_z; Last
0x180001c1b  lea     rcx, __xi_a; First
0x180001c22  call    _initterm_e_0
0x180001c27  test    eax, eax
0x180001c29  jnz     short loc_180001C54
0x180001c2b  call    __scrt_dllmain_after_initialize_c
0x180001c30  test    al, al
0x180001c32  jz      short loc_180001C54
0x180001c34  lea     rdx, __xc_z; Last
0x180001c3b  lea     rcx, __xc_a; First
0x180001c42  call    _initterm_0
0x180001c47  mov     cs:__scrt_current_native_startup_state, 2
0x180001c51  xor     dil, dil
0x180001c54  mov     cl, bl
0x180001c56  call    __scrt_release_startup_lock
0x180001c5b  test    dil, dil
0x180001c5e  jnz     short loc_180001C9A
0x180001c60  call    __scrt_get_dyn_tls_init_callback
0x180001c65  mov     rbx, rax
0x180001c68  cmp     qword ptr [rax], 0
0x180001c6c  jz      short loc_180001C8D
0x180001c6e  mov     rcx, rax
0x180001c71  call    __scrt_is_nonwritable_in_current_image
0x180001c76  test    al, al
0x180001c78  jz      short loc_180001C8D
0x180001c7a  mov     r8, rsi
0x180001c7d  mov     edx, 2
0x180001c82  mov     rcx, r14
0x180001c85  mov     rax, [rbx]
0x180001c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c8d  inc     cs:dword_1800182B0
0x180001c93  mov     eax, 1
0x180001c98  jmp     short loc_180001C9C
0x180001c9a  xor     eax, eax
0x180001c9c  add     rsp, 28h
0x180001ca0  pop     r14
0x180001ca2  pop     rdi
0x180001ca3  pop     rsi
0x180001ca4  pop     rbx
0x180001ca5  retn
0x180001ca6  mov     ecx, 7
0x180001cab  call    __scrt_fastfail
0x1800100fc  push    rbp
0x1800100fe  sub     rsp, 20h
0x180010102  mov     rbp, rdx
0x180010105  mov     cl, [rbp+60h]
0x180010108  add     rsp, 20h
0x18001010c  pop     rbp
0x18001010d  jmp     __scrt_release_startup_lock
```
