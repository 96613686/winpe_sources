# dllmain_crt_process_attach

- ea: `0x180003798`
- end: `0x180003892`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003740`

## callees

- `0x180003798`
- `0x180003ad4`
- `0x180003b14`
- `0x180003b50`
- `0x180003c50`
- `0x180003d24`
- `0x180003dc4`
- `0x1800042b8`
- `0x1800042e0`
- `0x180004304`
- `0x180004314`
- `0x180004320`
- `0x1800046b6`
- `0x1800046c2`
- `0x180031010`

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
  ++dword_1800427F0;
  return 1;
}

```

## disassembly

```asm
0x180003798  push    rbx
0x18000379a  push    rsi
0x18000379b  push    rdi
0x18000379c  push    r14
0x18000379e  sub     rsp, 28h
0x1800037a2  mov     rsi, rdx
0x1800037a5  mov     r14, rcx
0x1800037a8  xor     ecx, ecx
0x1800037aa  call    __scrt_initialize_crt
0x1800037af  test    al, al
0x1800037b1  jz      loc_18000387A
0x1800037b7  call    __scrt_acquire_startup_lock
0x1800037bc  mov     bl, al
0x1800037be  mov     [rsp+48h+arg_10], al
0x1800037c2  mov     dil, 1
0x1800037c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800037cc  jnz     loc_180003886
0x1800037d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800037dc  call    __scrt_dllmain_before_initialize_c
0x1800037e1  test    al, al
0x1800037e3  jz      short loc_180003834
0x1800037e5  call    _RTC_Initialize
0x1800037ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800037ef  call    __scrt_initialize_default_local_stdio_options
0x1800037f4  lea     rdx, __xi_z; Last
0x1800037fb  lea     rcx, __xi_a; First
0x180003802  call    _initterm_e_0
0x180003807  test    eax, eax
0x180003809  jnz     short loc_180003834
0x18000380b  call    __scrt_dllmain_after_initialize_c
0x180003810  test    al, al
0x180003812  jz      short loc_180003834
0x180003814  lea     rdx, __xc_z; Last
0x18000381b  lea     rcx, __xc_a; First
0x180003822  call    _initterm_0
0x180003827  mov     cs:__scrt_current_native_startup_state, 2
0x180003831  xor     dil, dil
0x180003834  mov     cl, bl
0x180003836  call    __scrt_release_startup_lock
0x18000383b  test    dil, dil
0x18000383e  jnz     short loc_18000387A
0x180003840  call    __scrt_get_dyn_tls_init_callback
0x180003845  mov     rbx, rax
0x180003848  cmp     qword ptr [rax], 0
0x18000384c  jz      short loc_18000386D
0x18000384e  mov     rcx, rax
0x180003851  call    __scrt_is_nonwritable_in_current_image
0x180003856  test    al, al
0x180003858  jz      short loc_18000386D
0x18000385a  mov     r8, rsi
0x18000385d  mov     edx, 2
0x180003862  mov     rcx, r14
0x180003865  mov     rax, [rbx]
0x180003868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000386d  inc     cs:dword_1800427F0
0x180003873  mov     eax, 1
0x180003878  jmp     short loc_18000387C
0x18000387a  xor     eax, eax
0x18000387c  add     rsp, 28h
0x180003880  pop     r14
0x180003882  pop     rdi
0x180003883  pop     rsi
0x180003884  pop     rbx
0x180003885  retn
0x180003886  mov     ecx, 7
0x18000388b  call    __scrt_fastfail
0x18002f18c  push    rbp
0x18002f18e  sub     rsp, 20h
0x18002f192  mov     rbp, rdx
0x18002f195  mov     cl, [rbp+60h]
0x18002f198  add     rsp, 20h
0x18002f19c  pop     rbp
0x18002f19d  jmp     __scrt_release_startup_lock
```
