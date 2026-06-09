# dllmain_crt_process_attach

- ea: `0x180001308`
- end: `0x180001402`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x180001308`
- `0x180001644`
- `0x180001684`
- `0x1800016c0`
- `0x1800017c0`
- `0x180001894`
- `0x180001934`
- `0x180001ae8`
- `0x180001b10`
- `0x180001b34`
- `0x180001b44`
- `0x180001b50`
- `0x180001ea6`
- `0x180001eb2`
- `0x180010010`

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
  ++dword_180016270;
  return 1;
}

```

## disassembly

```asm
0x180001308  push    rbx
0x18000130a  push    rsi
0x18000130b  push    rdi
0x18000130c  push    r14
0x18000130e  sub     rsp, 28h
0x180001312  mov     rsi, rdx
0x180001315  mov     r14, rcx
0x180001318  xor     ecx, ecx
0x18000131a  call    __scrt_initialize_crt
0x18000131f  test    al, al
0x180001321  jz      loc_1800013EA
0x180001327  call    __scrt_acquire_startup_lock
0x18000132c  mov     bl, al
0x18000132e  mov     [rsp+48h+arg_10], al
0x180001332  mov     dil, 1
0x180001335  cmp     cs:__scrt_current_native_startup_state, 0
0x18000133c  jnz     loc_1800013F6
0x180001342  mov     cs:__scrt_current_native_startup_state, 1
0x18000134c  call    __scrt_dllmain_before_initialize_c
0x180001351  test    al, al
0x180001353  jz      short loc_1800013A4
0x180001355  call    _RTC_Initialize
0x18000135a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000135f  call    __scrt_initialize_default_local_stdio_options
0x180001364  lea     rdx, __xi_z; Last
0x18000136b  lea     rcx, __xi_a; First
0x180001372  call    _initterm_e_0
0x180001377  test    eax, eax
0x180001379  jnz     short loc_1800013A4
0x18000137b  call    __scrt_dllmain_after_initialize_c
0x180001380  test    al, al
0x180001382  jz      short loc_1800013A4
0x180001384  lea     rdx, __xc_z; Last
0x18000138b  lea     rcx, __xc_a; First
0x180001392  call    _initterm_0
0x180001397  mov     cs:__scrt_current_native_startup_state, 2
0x1800013a1  xor     dil, dil
0x1800013a4  mov     cl, bl
0x1800013a6  call    __scrt_release_startup_lock
0x1800013ab  test    dil, dil
0x1800013ae  jnz     short loc_1800013EA
0x1800013b0  call    __scrt_get_dyn_tls_init_callback
0x1800013b5  mov     rbx, rax
0x1800013b8  cmp     qword ptr [rax], 0
0x1800013bc  jz      short loc_1800013DD
0x1800013be  mov     rcx, rax
0x1800013c1  call    __scrt_is_nonwritable_in_current_image
0x1800013c6  test    al, al
0x1800013c8  jz      short loc_1800013DD
0x1800013ca  mov     r8, rsi
0x1800013cd  mov     edx, 2
0x1800013d2  mov     rcx, r14
0x1800013d5  mov     rax, [rbx]
0x1800013d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013dd  inc     cs:dword_180016270
0x1800013e3  mov     eax, 1
0x1800013e8  jmp     short loc_1800013EC
0x1800013ea  xor     eax, eax
0x1800013ec  add     rsp, 28h
0x1800013f0  pop     r14
0x1800013f2  pop     rdi
0x1800013f3  pop     rsi
0x1800013f4  pop     rbx
0x1800013f5  retn
0x1800013f6  mov     ecx, 7
0x1800013fb  call    __scrt_fastfail
0x18000ef4c  push    rbp
0x18000ef4e  sub     rsp, 20h
0x18000ef52  mov     rbp, rdx
0x18000ef55  mov     cl, [rbp+60h]
0x18000ef58  add     rsp, 20h
0x18000ef5c  pop     rbp
0x18000ef5d  jmp     __scrt_release_startup_lock
```
