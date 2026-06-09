# dllmain_crt_process_attach

- ea: `0x1800157d8`
- end: `0x1800158d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180015780`

## callees

- `0x1800157d8`
- `0x180015b9c`
- `0x180015bdc`
- `0x180015c18`
- `0x180015d18`
- `0x180015dec`
- `0x180015e8c`
- `0x18001632c`
- `0x180016354`
- `0x180016378`
- `0x180016388`
- `0x180016394`
- `0x1800164c6`
- `0x1800164d2`
- `0x18001e010`

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
  ++dword_180028870;
  return 1;
}

```

## disassembly

```asm
0x1800157d8  push    rbx
0x1800157da  push    rsi
0x1800157db  push    rdi
0x1800157dc  push    r14
0x1800157de  sub     rsp, 28h
0x1800157e2  mov     rsi, rdx
0x1800157e5  mov     r14, rcx
0x1800157e8  xor     ecx, ecx
0x1800157ea  call    __scrt_initialize_crt
0x1800157ef  test    al, al
0x1800157f1  jz      loc_1800158BA
0x1800157f7  call    __scrt_acquire_startup_lock
0x1800157fc  mov     bl, al
0x1800157fe  mov     [rsp+48h+arg_10], al
0x180015802  mov     dil, 1
0x180015805  cmp     cs:__scrt_current_native_startup_state, 0
0x18001580c  jnz     loc_1800158C6
0x180015812  mov     cs:__scrt_current_native_startup_state, 1
0x18001581c  call    __scrt_dllmain_before_initialize_c
0x180015821  test    al, al
0x180015823  jz      short loc_180015874
0x180015825  call    _RTC_Initialize
0x18001582a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001582f  call    __scrt_initialize_default_local_stdio_options
0x180015834  lea     rdx, __xi_z; Last
0x18001583b  lea     rcx, __xi_a; First
0x180015842  call    _initterm_e_0
0x180015847  test    eax, eax
0x180015849  jnz     short loc_180015874
0x18001584b  call    __scrt_dllmain_after_initialize_c
0x180015850  test    al, al
0x180015852  jz      short loc_180015874
0x180015854  lea     rdx, __xc_z; Last
0x18001585b  lea     rcx, __xc_a; First
0x180015862  call    _initterm_0
0x180015867  mov     cs:__scrt_current_native_startup_state, 2
0x180015871  xor     dil, dil
0x180015874  mov     cl, bl
0x180015876  call    __scrt_release_startup_lock
0x18001587b  test    dil, dil
0x18001587e  jnz     short loc_1800158BA
0x180015880  call    __scrt_get_dyn_tls_init_callback
0x180015885  mov     rbx, rax
0x180015888  cmp     qword ptr [rax], 0
0x18001588c  jz      short loc_1800158AD
0x18001588e  mov     rcx, rax
0x180015891  call    __scrt_is_nonwritable_in_current_image
0x180015896  test    al, al
0x180015898  jz      short loc_1800158AD
0x18001589a  mov     r8, rsi
0x18001589d  mov     edx, 2
0x1800158a2  mov     rcx, r14
0x1800158a5  mov     rax, [rbx]
0x1800158a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ad  inc     cs:dword_180028870
0x1800158b3  mov     eax, 1
0x1800158b8  jmp     short loc_1800158BC
0x1800158ba  xor     eax, eax
0x1800158bc  add     rsp, 28h
0x1800158c0  pop     r14
0x1800158c2  pop     rdi
0x1800158c3  pop     rsi
0x1800158c4  pop     rbx
0x1800158c5  retn
0x1800158c6  mov     ecx, 7
0x1800158cb  call    __scrt_fastfail
0x18001cbde  push    rbp
0x18001cbe0  sub     rsp, 20h
0x18001cbe4  mov     rbp, rdx
0x18001cbe7  mov     cl, [rbp+60h]
0x18001cbea  add     rsp, 20h
0x18001cbee  pop     rbp
0x18001cbef  jmp     __scrt_release_startup_lock
```
