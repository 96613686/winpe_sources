# dllmain_crt_process_attach

- ea: `0x1800025d8`
- end: `0x1800026d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002580`

## callees

- `0x1800025d8`
- `0x180002914`
- `0x180002954`
- `0x180002990`
- `0x180002a90`
- `0x180002b64`
- `0x180002c04`
- `0x180002edc`
- `0x180002f04`
- `0x180002f28`
- `0x180002f38`
- `0x180002f44`
- `0x1800032c6`
- `0x1800032d2`
- `0x18002a010`

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
  ++dword_18003AAF0;
  return 1;
}

```

## disassembly

```asm
0x1800025d8  push    rbx
0x1800025da  push    rsi
0x1800025db  push    rdi
0x1800025dc  push    r14
0x1800025de  sub     rsp, 28h
0x1800025e2  mov     rsi, rdx
0x1800025e5  mov     r14, rcx
0x1800025e8  xor     ecx, ecx
0x1800025ea  call    __scrt_initialize_crt
0x1800025ef  test    al, al
0x1800025f1  jz      loc_1800026BA
0x1800025f7  call    __scrt_acquire_startup_lock
0x1800025fc  mov     bl, al
0x1800025fe  mov     [rsp+48h+arg_10], al
0x180002602  mov     dil, 1
0x180002605  cmp     cs:__scrt_current_native_startup_state, 0
0x18000260c  jnz     loc_1800026C6
0x180002612  mov     cs:__scrt_current_native_startup_state, 1
0x18000261c  call    __scrt_dllmain_before_initialize_c
0x180002621  test    al, al
0x180002623  jz      short loc_180002674
0x180002625  call    _RTC_Initialize
0x18000262a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000262f  call    __scrt_initialize_default_local_stdio_options
0x180002634  lea     rdx, __xi_z; Last
0x18000263b  lea     rcx, __xi_a; First
0x180002642  call    _initterm_e_0
0x180002647  test    eax, eax
0x180002649  jnz     short loc_180002674
0x18000264b  call    __scrt_dllmain_after_initialize_c
0x180002650  test    al, al
0x180002652  jz      short loc_180002674
0x180002654  lea     rdx, __xc_z; Last
0x18000265b  lea     rcx, __xc_a; First
0x180002662  call    _initterm_0
0x180002667  mov     cs:__scrt_current_native_startup_state, 2
0x180002671  xor     dil, dil
0x180002674  mov     cl, bl
0x180002676  call    __scrt_release_startup_lock
0x18000267b  test    dil, dil
0x18000267e  jnz     short loc_1800026BA
0x180002680  call    __scrt_get_dyn_tls_init_callback
0x180002685  mov     rbx, rax
0x180002688  cmp     qword ptr [rax], 0
0x18000268c  jz      short loc_1800026AD
0x18000268e  mov     rcx, rax
0x180002691  call    __scrt_is_nonwritable_in_current_image
0x180002696  test    al, al
0x180002698  jz      short loc_1800026AD
0x18000269a  mov     r8, rsi
0x18000269d  mov     edx, 2
0x1800026a2  mov     rcx, r14
0x1800026a5  mov     rax, [rbx]
0x1800026a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ad  inc     cs:dword_18003AAF0
0x1800026b3  mov     eax, 1
0x1800026b8  jmp     short loc_1800026BC
0x1800026ba  xor     eax, eax
0x1800026bc  add     rsp, 28h
0x1800026c0  pop     r14
0x1800026c2  pop     rdi
0x1800026c3  pop     rsi
0x1800026c4  pop     rbx
0x1800026c5  retn
0x1800026c6  mov     ecx, 7
0x1800026cb  call    __scrt_fastfail
0x1800276c0  push    rbp
0x1800276c2  sub     rsp, 20h
0x1800276c6  mov     rbp, rdx
0x1800276c9  mov     cl, [rbp+60h]
0x1800276cc  add     rsp, 20h
0x1800276d0  pop     rbp
0x1800276d1  jmp     __scrt_release_startup_lock
```
