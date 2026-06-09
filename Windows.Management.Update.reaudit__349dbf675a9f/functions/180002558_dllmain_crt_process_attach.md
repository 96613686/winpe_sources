# dllmain_crt_process_attach

- ea: `0x180002558`
- end: `0x180002669`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002500`

## callees

- `0x180002558`
- `0x1800028a4`
- `0x1800028e4`
- `0x180002920`
- `0x180002a44`
- `0x180002b18`
- `0x180002bb8`
- `0x180002e8c`
- `0x180002eb4`
- `0x180002ed8`
- `0x180002ef8`
- `0x180003060`
- `0x1800034b6`
- `0x1800034c2`
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
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180002669LL);
  }
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
  ++dword_18003CAD0;
  return 1;
}

```

## disassembly

```asm
0x180002558  mov     [rsp+arg_0], rbx
0x18000255d  mov     [rsp+arg_8], rsi
0x180002562  mov     [rsp+arg_18], rdi
0x180002567  push    r14
0x180002569  sub     rsp, 20h
0x18000256d  mov     rsi, rdx
0x180002570  mov     r14, rcx
0x180002573  xor     ecx, ecx
0x180002575  call    __scrt_initialize_crt
0x18000257a  test    al, al
0x18000257c  jz      loc_180002645
0x180002582  call    __scrt_acquire_startup_lock
0x180002587  mov     bl, al
0x180002589  mov     [rsp+28h+arg_10], al
0x18000258d  mov     dil, 1
0x180002590  cmp     cs:__scrt_current_native_startup_state, 0
0x180002597  jnz     loc_18000265D
0x18000259d  mov     cs:__scrt_current_native_startup_state, 1
0x1800025a7  call    __scrt_dllmain_before_initialize_c
0x1800025ac  test    al, al
0x1800025ae  jz      short loc_1800025FF
0x1800025b0  call    _RTC_Initialize
0x1800025b5  call    ?__scrt_initialize_type_info@@YAXXZ
0x1800025ba  call    __scrt_initialize_default_local_stdio_options
0x1800025bf  lea     rdx, __xi_z; Last
0x1800025c6  lea     rcx, __xi_a; First
0x1800025cd  call    _initterm_e_0
0x1800025d2  test    eax, eax
0x1800025d4  jnz     short loc_1800025FF
0x1800025d6  call    __scrt_dllmain_after_initialize_c
0x1800025db  test    al, al
0x1800025dd  jz      short loc_1800025FF
0x1800025df  lea     rdx, __xc_z; Last
0x1800025e6  lea     rcx, __xc_a; First
0x1800025ed  call    _initterm_0
0x1800025f2  mov     cs:__scrt_current_native_startup_state, 2
0x1800025fc  xor     dil, dil
0x1800025ff  mov     cl, bl
0x180002601  call    __scrt_release_startup_lock
0x180002606  test    dil, dil
0x180002609  jnz     short loc_180002645
0x18000260b  call    __scrt_get_dyn_tls_init_callback
0x180002610  mov     rbx, rax
0x180002613  cmp     qword ptr [rax], 0
0x180002617  jz      short loc_180002638
0x180002619  mov     rcx, rax
0x18000261c  call    __scrt_is_nonwritable_in_current_image
0x180002621  test    al, al
0x180002623  jz      short loc_180002638
0x180002625  mov     r8, rsi
0x180002628  mov     edx, 2
0x18000262d  mov     rcx, r14
0x180002630  mov     rax, [rbx]
0x180002633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002638  inc     cs:dword_18003CAD0
0x18000263e  mov     eax, 1
0x180002643  jmp     short loc_180002647
0x180002645  xor     eax, eax
0x180002647  mov     rbx, [rsp+28h+arg_0]
0x18000264c  mov     rsi, [rsp+28h+arg_8]
0x180002651  mov     rdi, [rsp+28h+arg_18]
0x180002656  add     rsp, 20h
0x18000265a  pop     r14
0x18000265c  retn
0x18000265d  mov     ecx, 7
0x180002662  call    __scrt_fastfail
0x180002667  nop
0x180002668  int     3; Trap to Debugger
0x180028b30  push    rbp
0x180028b32  sub     rsp, 20h
0x180028b36  mov     rbp, rdx
0x180028b39  mov     cl, [rbp+40h]
0x180028b3c  add     rsp, 20h
0x180028b40  pop     rbp
0x180028b41  jmp     __scrt_release_startup_lock
```
