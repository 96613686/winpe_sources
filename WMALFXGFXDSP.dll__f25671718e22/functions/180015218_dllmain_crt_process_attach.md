# dllmain_crt_process_attach

- ea: `0x180015218`
- end: `0x180015312`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800151c0`

## callees

- `0x180015218`
- `0x1800155ec`
- `0x180015614`
- `0x180015638`
- `0x180015678`
- `0x1800156b4`
- `0x1800157b4`
- `0x180015888`
- `0x180015928`
- `0x1800159e4`
- `0x1800159f4`
- `0x180015a00`
- `0x180015d36`
- `0x180015d42`
- `0x180086010`

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
  ++dword_1801B9510;
  return 1;
}

```

## disassembly

```asm
0x180015218  push    rbx
0x18001521a  push    rsi
0x18001521b  push    rdi
0x18001521c  push    r14
0x18001521e  sub     rsp, 28h
0x180015222  mov     rsi, rdx
0x180015225  mov     r14, rcx
0x180015228  xor     ecx, ecx
0x18001522a  call    __scrt_initialize_crt
0x18001522f  test    al, al
0x180015231  jz      loc_1800152FA
0x180015237  call    __scrt_acquire_startup_lock
0x18001523c  mov     bl, al
0x18001523e  mov     [rsp+48h+arg_10], al
0x180015242  mov     dil, 1
0x180015245  cmp     cs:__scrt_current_native_startup_state, 0
0x18001524c  jnz     loc_180015306
0x180015252  mov     cs:__scrt_current_native_startup_state, 1
0x18001525c  call    __scrt_dllmain_before_initialize_c
0x180015261  test    al, al
0x180015263  jz      short loc_1800152B4
0x180015265  call    _RTC_Initialize
0x18001526a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001526f  call    __scrt_initialize_default_local_stdio_options
0x180015274  lea     rdx, __xi_z; Last
0x18001527b  lea     rcx, __xi_a; First
0x180015282  call    _initterm_e_0
0x180015287  test    eax, eax
0x180015289  jnz     short loc_1800152B4
0x18001528b  call    __scrt_dllmain_after_initialize_c
0x180015290  test    al, al
0x180015292  jz      short loc_1800152B4
0x180015294  lea     rdx, __xc_z; Last
0x18001529b  lea     rcx, __xc_a; First
0x1800152a2  call    _initterm_0
0x1800152a7  mov     cs:__scrt_current_native_startup_state, 2
0x1800152b1  xor     dil, dil
0x1800152b4  mov     cl, bl
0x1800152b6  call    __scrt_release_startup_lock
0x1800152bb  test    dil, dil
0x1800152be  jnz     short loc_1800152FA
0x1800152c0  call    __scrt_get_dyn_tls_init_callback
0x1800152c5  mov     rbx, rax
0x1800152c8  cmp     qword ptr [rax], 0
0x1800152cc  jz      short loc_1800152ED
0x1800152ce  mov     rcx, rax
0x1800152d1  call    __scrt_is_nonwritable_in_current_image
0x1800152d6  test    al, al
0x1800152d8  jz      short loc_1800152ED
0x1800152da  mov     r8, rsi
0x1800152dd  mov     edx, 2
0x1800152e2  mov     rcx, r14
0x1800152e5  mov     rax, [rbx]
0x1800152e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ed  inc     cs:dword_1801B9510
0x1800152f3  mov     eax, 1
0x1800152f8  jmp     short loc_1800152FC
0x1800152fa  xor     eax, eax
0x1800152fc  add     rsp, 28h
0x180015300  pop     r14
0x180015302  pop     rdi
0x180015303  pop     rsi
0x180015304  pop     rbx
0x180015305  retn
0x180015306  mov     ecx, 7
0x18001530b  call    __scrt_fastfail
0x180085abc  push    rbp
0x180085abe  sub     rsp, 20h
0x180085ac2  mov     rbp, rdx
0x180085ac5  mov     cl, [rbp+60h]
0x180085ac8  add     rsp, 20h
0x180085acc  pop     rbp
0x180085acd  jmp     __scrt_release_startup_lock
```
