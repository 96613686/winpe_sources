# dllmain_crt_process_attach

- ea: `0x1800030a8`
- end: `0x1800031a2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003050`

## callees

- `0x1800030a8`
- `0x180003464`
- `0x1800034a4`
- `0x1800034e0`
- `0x1800035e0`
- `0x1800036b4`
- `0x180003754`
- `0x180003ed8`
- `0x180003f00`
- `0x180003f24`
- `0x180003f34`
- `0x180003f40`
- `0x180004036`
- `0x180004042`
- `0x180013010`

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
  ++dword_18001A410;
  return 1;
}

```

## disassembly

```asm
0x1800030a8  push    rbx
0x1800030aa  push    rsi
0x1800030ab  push    rdi
0x1800030ac  push    r14
0x1800030ae  sub     rsp, 28h
0x1800030b2  mov     rsi, rdx
0x1800030b5  mov     r14, rcx
0x1800030b8  xor     ecx, ecx
0x1800030ba  call    __scrt_initialize_crt
0x1800030bf  test    al, al
0x1800030c1  jz      loc_18000318A
0x1800030c7  call    __scrt_acquire_startup_lock
0x1800030cc  mov     bl, al
0x1800030ce  mov     [rsp+48h+arg_10], al
0x1800030d2  mov     dil, 1
0x1800030d5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800030dc  jnz     loc_180003196
0x1800030e2  mov     cs:__scrt_current_native_startup_state, 1
0x1800030ec  call    __scrt_dllmain_before_initialize_c
0x1800030f1  test    al, al
0x1800030f3  jz      short loc_180003144
0x1800030f5  call    _RTC_Initialize
0x1800030fa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800030ff  call    __scrt_initialize_default_local_stdio_options
0x180003104  lea     rdx, __xi_z; Last
0x18000310b  lea     rcx, __xi_a; First
0x180003112  call    _initterm_e_0
0x180003117  test    eax, eax
0x180003119  jnz     short loc_180003144
0x18000311b  call    __scrt_dllmain_after_initialize_c
0x180003120  test    al, al
0x180003122  jz      short loc_180003144
0x180003124  lea     rdx, __xc_z; Last
0x18000312b  lea     rcx, __xc_a; First
0x180003132  call    _initterm_0
0x180003137  mov     cs:__scrt_current_native_startup_state, 2
0x180003141  xor     dil, dil
0x180003144  mov     cl, bl
0x180003146  call    __scrt_release_startup_lock
0x18000314b  test    dil, dil
0x18000314e  jnz     short loc_18000318A
0x180003150  call    __scrt_get_dyn_tls_init_callback
0x180003155  mov     rbx, rax
0x180003158  cmp     qword ptr [rax], 0
0x18000315c  jz      short loc_18000317D
0x18000315e  mov     rcx, rax
0x180003161  call    __scrt_is_nonwritable_in_current_image
0x180003166  test    al, al
0x180003168  jz      short loc_18000317D
0x18000316a  mov     r8, rsi
0x18000316d  mov     edx, 2
0x180003172  mov     rcx, r14
0x180003175  mov     rax, [rbx]
0x180003178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317d  inc     cs:dword_18001A410
0x180003183  mov     eax, 1
0x180003188  jmp     short loc_18000318C
0x18000318a  xor     eax, eax
0x18000318c  add     rsp, 28h
0x180003190  pop     r14
0x180003192  pop     rdi
0x180003193  pop     rsi
0x180003194  pop     rbx
0x180003195  retn
0x180003196  mov     ecx, 7
0x18000319b  call    __scrt_fastfail
0x18001205c  push    rbp
0x18001205e  sub     rsp, 20h
0x180012062  mov     rbp, rdx
0x180012065  mov     cl, [rbp+60h]
0x180012068  add     rsp, 20h
0x18001206c  pop     rbp
0x18001206d  jmp     __scrt_release_startup_lock
```
