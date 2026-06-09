# dllmain_crt_process_attach

- ea: `0x1800035c8`
- end: `0x1800036c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003570`

## callees

- `0x1800035c8`
- `0x180003984`
- `0x1800039c4`
- `0x180003a00`
- `0x180003b00`
- `0x180003bd4`
- `0x180003c74`
- `0x180004434`
- `0x18000445c`
- `0x180004480`
- `0x180004490`
- `0x18000449c`
- `0x180004566`
- `0x180004572`
- `0x180021010`

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
  ++dword_18002D7D0;
  return 1;
}

```

## disassembly

```asm
0x1800035c8  push    rbx
0x1800035ca  push    rsi
0x1800035cb  push    rdi
0x1800035cc  push    r14
0x1800035ce  sub     rsp, 28h
0x1800035d2  mov     rsi, rdx
0x1800035d5  mov     r14, rcx
0x1800035d8  xor     ecx, ecx
0x1800035da  call    __scrt_initialize_crt
0x1800035df  test    al, al
0x1800035e1  jz      loc_1800036AA
0x1800035e7  call    __scrt_acquire_startup_lock
0x1800035ec  mov     bl, al
0x1800035ee  mov     [rsp+48h+arg_10], al
0x1800035f2  mov     dil, 1
0x1800035f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800035fc  jnz     loc_1800036B6
0x180003602  mov     cs:__scrt_current_native_startup_state, 1
0x18000360c  call    __scrt_dllmain_before_initialize_c
0x180003611  test    al, al
0x180003613  jz      short loc_180003664
0x180003615  call    _RTC_Initialize
0x18000361a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000361f  call    __scrt_initialize_default_local_stdio_options
0x180003624  lea     rdx, __xi_z; Last
0x18000362b  lea     rcx, __xi_a; First
0x180003632  call    _initterm_e_0
0x180003637  test    eax, eax
0x180003639  jnz     short loc_180003664
0x18000363b  call    __scrt_dllmain_after_initialize_c
0x180003640  test    al, al
0x180003642  jz      short loc_180003664
0x180003644  lea     rdx, __xc_z; Last
0x18000364b  lea     rcx, __xc_a; First
0x180003652  call    _initterm_0
0x180003657  mov     cs:__scrt_current_native_startup_state, 2
0x180003661  xor     dil, dil
0x180003664  mov     cl, bl
0x180003666  call    __scrt_release_startup_lock
0x18000366b  test    dil, dil
0x18000366e  jnz     short loc_1800036AA
0x180003670  call    __scrt_get_dyn_tls_init_callback
0x180003675  mov     rbx, rax
0x180003678  cmp     qword ptr [rax], 0
0x18000367c  jz      short loc_18000369D
0x18000367e  mov     rcx, rax
0x180003681  call    __scrt_is_nonwritable_in_current_image
0x180003686  test    al, al
0x180003688  jz      short loc_18000369D
0x18000368a  mov     r8, rsi
0x18000368d  mov     edx, 2
0x180003692  mov     rcx, r14
0x180003695  mov     rax, [rbx]
0x180003698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369d  inc     cs:dword_18002D7D0
0x1800036a3  mov     eax, 1
0x1800036a8  jmp     short loc_1800036AC
0x1800036aa  xor     eax, eax
0x1800036ac  add     rsp, 28h
0x1800036b0  pop     r14
0x1800036b2  pop     rdi
0x1800036b3  pop     rsi
0x1800036b4  pop     rbx
0x1800036b5  retn
0x1800036b6  mov     ecx, 7
0x1800036bb  call    __scrt_fastfail
0x18001f8fc  push    rbp
0x18001f8fe  sub     rsp, 20h
0x18001f902  mov     rbp, rdx
0x18001f905  mov     cl, [rbp+60h]
0x18001f908  add     rsp, 20h
0x18001f90c  pop     rbp
0x18001f90d  jmp     __scrt_release_startup_lock
```
