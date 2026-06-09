# dllmain_crt_process_attach

- ea: `0x180004958`
- end: `0x180004a52`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180004900`

## callees

- `0x180004958`
- `0x180004cb8`
- `0x180004cf8`
- `0x180004d34`
- `0x180004e34`
- `0x180004f08`
- `0x180004fa8`
- `0x180005168`
- `0x180005190`
- `0x1800051b4`
- `0x1800051c4`
- `0x1800051d0`
- `0x1800055b6`
- `0x1800055c2`
- `0x180014010`

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
  ++dword_18001C1F0;
  return 1;
}

```

## disassembly

```asm
0x180004958  push    rbx
0x18000495a  push    rsi
0x18000495b  push    rdi
0x18000495c  push    r14
0x18000495e  sub     rsp, 28h
0x180004962  mov     rsi, rdx
0x180004965  mov     r14, rcx
0x180004968  xor     ecx, ecx
0x18000496a  call    __scrt_initialize_crt
0x18000496f  test    al, al
0x180004971  jz      loc_180004A3A
0x180004977  call    __scrt_acquire_startup_lock
0x18000497c  mov     bl, al
0x18000497e  mov     [rsp+48h+arg_10], al
0x180004982  mov     dil, 1
0x180004985  cmp     cs:__scrt_current_native_startup_state, 0
0x18000498c  jnz     loc_180004A46
0x180004992  mov     cs:__scrt_current_native_startup_state, 1
0x18000499c  call    __scrt_dllmain_before_initialize_c
0x1800049a1  test    al, al
0x1800049a3  jz      short loc_1800049F4
0x1800049a5  call    _RTC_Initialize
0x1800049aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800049af  call    __scrt_initialize_default_local_stdio_options
0x1800049b4  lea     rdx, __xi_z; Last
0x1800049bb  lea     rcx, __xi_a; First
0x1800049c2  call    _initterm_e_0
0x1800049c7  test    eax, eax
0x1800049c9  jnz     short loc_1800049F4
0x1800049cb  call    __scrt_dllmain_after_initialize_c
0x1800049d0  test    al, al
0x1800049d2  jz      short loc_1800049F4
0x1800049d4  lea     rdx, __xc_z; Last
0x1800049db  lea     rcx, __xc_a; First
0x1800049e2  call    _initterm_0
0x1800049e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800049f1  xor     dil, dil
0x1800049f4  mov     cl, bl
0x1800049f6  call    __scrt_release_startup_lock
0x1800049fb  test    dil, dil
0x1800049fe  jnz     short loc_180004A3A
0x180004a00  call    __scrt_get_dyn_tls_init_callback
0x180004a05  mov     rbx, rax
0x180004a08  cmp     qword ptr [rax], 0
0x180004a0c  jz      short loc_180004A2D
0x180004a0e  mov     rcx, rax
0x180004a11  call    __scrt_is_nonwritable_in_current_image
0x180004a16  test    al, al
0x180004a18  jz      short loc_180004A2D
0x180004a1a  mov     r8, rsi
0x180004a1d  mov     edx, 2
0x180004a22  mov     rcx, r14
0x180004a25  mov     rax, [rbx]
0x180004a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2d  inc     cs:dword_18001C1F0
0x180004a33  mov     eax, 1
0x180004a38  jmp     short loc_180004A3C
0x180004a3a  xor     eax, eax
0x180004a3c  add     rsp, 28h
0x180004a40  pop     r14
0x180004a42  pop     rdi
0x180004a43  pop     rsi
0x180004a44  pop     rbx
0x180004a45  retn
0x180004a46  mov     ecx, 7
0x180004a4b  call    __scrt_fastfail
0x180013714  push    rbp
0x180013716  sub     rsp, 20h
0x18001371a  mov     rbp, rdx
0x18001371d  mov     cl, [rbp+60h]
0x180013720  add     rsp, 20h
0x180013724  pop     rbp
0x180013725  jmp     __scrt_release_startup_lock
```
