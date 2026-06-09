# dllmain_crt_process_attach

- ea: `0x1800025f8`
- end: `0x1800026f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800025a0`

## callees

- `0x1800025f8`
- `0x180002934`
- `0x180002974`
- `0x1800029b0`
- `0x180002ab0`
- `0x180002b84`
- `0x180002c24`
- `0x180002da8`
- `0x180002dd0`
- `0x180002df4`
- `0x180002e04`
- `0x180002e10`
- `0x180003186`
- `0x180003192`
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
  ++dword_1800181F0;
  return 1;
}

```

## disassembly

```asm
0x1800025f8  push    rbx
0x1800025fa  push    rsi
0x1800025fb  push    rdi
0x1800025fc  push    r14
0x1800025fe  sub     rsp, 28h
0x180002602  mov     rsi, rdx
0x180002605  mov     r14, rcx
0x180002608  xor     ecx, ecx
0x18000260a  call    __scrt_initialize_crt
0x18000260f  test    al, al
0x180002611  jz      loc_1800026DA
0x180002617  call    __scrt_acquire_startup_lock
0x18000261c  mov     bl, al
0x18000261e  mov     [rsp+48h+arg_10], al
0x180002622  mov     dil, 1
0x180002625  cmp     cs:__scrt_current_native_startup_state, 0
0x18000262c  jnz     loc_1800026E6
0x180002632  mov     cs:__scrt_current_native_startup_state, 1
0x18000263c  call    __scrt_dllmain_before_initialize_c
0x180002641  test    al, al
0x180002643  jz      short loc_180002694
0x180002645  call    _RTC_Initialize
0x18000264a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000264f  call    __scrt_initialize_default_local_stdio_options
0x180002654  lea     rdx, __xi_z; Last
0x18000265b  lea     rcx, __xi_a; First
0x180002662  call    _initterm_e_0
0x180002667  test    eax, eax
0x180002669  jnz     short loc_180002694
0x18000266b  call    __scrt_dllmain_after_initialize_c
0x180002670  test    al, al
0x180002672  jz      short loc_180002694
0x180002674  lea     rdx, __xc_z; Last
0x18000267b  lea     rcx, __xc_a; First
0x180002682  call    _initterm_0
0x180002687  mov     cs:__scrt_current_native_startup_state, 2
0x180002691  xor     dil, dil
0x180002694  mov     cl, bl
0x180002696  call    __scrt_release_startup_lock
0x18000269b  test    dil, dil
0x18000269e  jnz     short loc_1800026DA
0x1800026a0  call    __scrt_get_dyn_tls_init_callback
0x1800026a5  mov     rbx, rax
0x1800026a8  cmp     qword ptr [rax], 0
0x1800026ac  jz      short loc_1800026CD
0x1800026ae  mov     rcx, rax
0x1800026b1  call    __scrt_is_nonwritable_in_current_image
0x1800026b6  test    al, al
0x1800026b8  jz      short loc_1800026CD
0x1800026ba  mov     r8, rsi
0x1800026bd  mov     edx, 2
0x1800026c2  mov     rcx, r14
0x1800026c5  mov     rax, [rbx]
0x1800026c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026cd  inc     cs:dword_1800181F0
0x1800026d3  mov     eax, 1
0x1800026d8  jmp     short loc_1800026DC
0x1800026da  xor     eax, eax
0x1800026dc  add     rsp, 28h
0x1800026e0  pop     r14
0x1800026e2  pop     rdi
0x1800026e3  pop     rsi
0x1800026e4  pop     rbx
0x1800026e5  retn
0x1800026e6  mov     ecx, 7
0x1800026eb  call    __scrt_fastfail
0x1800105ec  push    rbp
0x1800105ee  sub     rsp, 20h
0x1800105f2  mov     rbp, rdx
0x1800105f5  mov     cl, [rbp+60h]
0x1800105f8  add     rsp, 20h
0x1800105fc  pop     rbp
0x1800105fd  jmp     __scrt_release_startup_lock
```
