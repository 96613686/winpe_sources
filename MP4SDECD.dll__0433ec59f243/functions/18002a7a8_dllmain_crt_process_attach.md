# dllmain_crt_process_attach

- ea: `0x18002a7a8`
- end: `0x18002a8a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18002a750`

## callees

- `0x18002a7a8`
- `0x18002abac`
- `0x18002abd4`
- `0x18002abf8`
- `0x18002ac38`
- `0x18002ac74`
- `0x18002ad74`
- `0x18002ae48`
- `0x18002aee8`
- `0x18002af44`
- `0x18002af54`
- `0x18002af60`
- `0x18002b2b6`
- `0x18002b2c2`
- `0x180046010`

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
  ++dword_180059310;
  return 1;
}

```

## disassembly

```asm
0x18002a7a8  push    rbx
0x18002a7aa  push    rsi
0x18002a7ab  push    rdi
0x18002a7ac  push    r14
0x18002a7ae  sub     rsp, 28h
0x18002a7b2  mov     rsi, rdx
0x18002a7b5  mov     r14, rcx
0x18002a7b8  xor     ecx, ecx
0x18002a7ba  call    __scrt_initialize_crt
0x18002a7bf  test    al, al
0x18002a7c1  jz      loc_18002A88A
0x18002a7c7  call    __scrt_acquire_startup_lock
0x18002a7cc  mov     bl, al
0x18002a7ce  mov     [rsp+48h+arg_10], al
0x18002a7d2  mov     dil, 1
0x18002a7d5  cmp     cs:__scrt_current_native_startup_state, 0
0x18002a7dc  jnz     loc_18002A896
0x18002a7e2  mov     cs:__scrt_current_native_startup_state, 1
0x18002a7ec  call    __scrt_dllmain_before_initialize_c
0x18002a7f1  test    al, al
0x18002a7f3  jz      short loc_18002A844
0x18002a7f5  call    _RTC_Initialize
0x18002a7fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18002a7ff  call    __scrt_initialize_default_local_stdio_options
0x18002a804  lea     rdx, __xi_z; Last
0x18002a80b  lea     rcx, __xi_a; First
0x18002a812  call    _initterm_e_0
0x18002a817  test    eax, eax
0x18002a819  jnz     short loc_18002A844
0x18002a81b  call    __scrt_dllmain_after_initialize_c
0x18002a820  test    al, al
0x18002a822  jz      short loc_18002A844
0x18002a824  lea     rdx, __xc_z; Last
0x18002a82b  lea     rcx, __xc_a; First
0x18002a832  call    _initterm_0
0x18002a837  mov     cs:__scrt_current_native_startup_state, 2
0x18002a841  xor     dil, dil
0x18002a844  mov     cl, bl
0x18002a846  call    __scrt_release_startup_lock
0x18002a84b  test    dil, dil
0x18002a84e  jnz     short loc_18002A88A
0x18002a850  call    __scrt_get_dyn_tls_init_callback
0x18002a855  mov     rbx, rax
0x18002a858  cmp     qword ptr [rax], 0
0x18002a85c  jz      short loc_18002A87D
0x18002a85e  mov     rcx, rax
0x18002a861  call    __scrt_is_nonwritable_in_current_image
0x18002a866  test    al, al
0x18002a868  jz      short loc_18002A87D
0x18002a86a  mov     r8, rsi
0x18002a86d  mov     edx, 2
0x18002a872  mov     rcx, r14
0x18002a875  mov     rax, [rbx]
0x18002a878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a87d  inc     cs:dword_180059310
0x18002a883  mov     eax, 1
0x18002a888  jmp     short loc_18002A88C
0x18002a88a  xor     eax, eax
0x18002a88c  add     rsp, 28h
0x18002a890  pop     r14
0x18002a892  pop     rdi
0x18002a893  pop     rsi
0x18002a894  pop     rbx
0x18002a895  retn
0x18002a896  mov     ecx, 7
0x18002a89b  call    __scrt_fastfail
0x18004587c  push    rbp
0x18004587e  sub     rsp, 20h
0x180045882  mov     rbp, rdx
0x180045885  mov     cl, [rbp+60h]
0x180045888  add     rsp, 20h
0x18004588c  pop     rbp
0x18004588d  jmp     __scrt_release_startup_lock
```
