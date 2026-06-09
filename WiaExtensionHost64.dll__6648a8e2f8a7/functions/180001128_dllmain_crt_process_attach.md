# dllmain_crt_process_attach

- ea: `0x180001128`
- end: `0x180001222`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800010d0`

## callees

- `0x180001128`
- `0x180001558`
- `0x180001580`
- `0x1800015a4`
- `0x1800015e4`
- `0x180001620`
- `0x180001720`
- `0x1800017f4`
- `0x180001894`
- `0x1800018f0`
- `0x180001900`
- `0x18000190c`
- `0x180001c86`
- `0x180001c92`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 *dyn_tls_init_callback; // rax
  __int64 *v7; // rbx

  if ( !_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7u);
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
  _scrt_release_startup_lock(v4);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = _scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( _scrt_is_nonwritable_in_current_image((__int64)dyn_tls_init_callback) )
      ((void (__fastcall *)(__int64, __int64, __int64))*v7)(a1, 2, a2);
  }
  ++dword_180005090;
  return 1;
}

```

## disassembly

```asm
0x180001128  push    rbx
0x18000112a  push    rsi
0x18000112b  push    rdi
0x18000112c  push    r14
0x18000112e  sub     rsp, 28h
0x180001132  mov     rsi, rdx
0x180001135  mov     r14, rcx
0x180001138  xor     ecx, ecx
0x18000113a  call    __scrt_initialize_crt
0x18000113f  test    al, al
0x180001141  jz      loc_18000120A
0x180001147  call    __scrt_acquire_startup_lock
0x18000114c  mov     bl, al
0x18000114e  mov     [rsp+48h+arg_10], al
0x180001152  mov     dil, 1
0x180001155  cmp     cs:__scrt_current_native_startup_state, 0
0x18000115c  jnz     loc_180001216
0x180001162  mov     cs:__scrt_current_native_startup_state, 1
0x18000116c  call    __scrt_dllmain_before_initialize_c
0x180001171  test    al, al
0x180001173  jz      short loc_1800011C4
0x180001175  call    _RTC_Initialize
0x18000117a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000117f  call    __scrt_initialize_default_local_stdio_options
0x180001184  lea     rdx, __xi_z; Last
0x18000118b  lea     rcx, __xi_a; First
0x180001192  call    _initterm_e_0
0x180001197  test    eax, eax
0x180001199  jnz     short loc_1800011C4
0x18000119b  call    __scrt_dllmain_after_initialize_c
0x1800011a0  test    al, al
0x1800011a2  jz      short loc_1800011C4
0x1800011a4  lea     rdx, __xc_z; Last
0x1800011ab  lea     rcx, __xc_a; First
0x1800011b2  call    _initterm_0
0x1800011b7  mov     cs:__scrt_current_native_startup_state, 2
0x1800011c1  xor     dil, dil
0x1800011c4  mov     cl, bl
0x1800011c6  call    __scrt_release_startup_lock
0x1800011cb  test    dil, dil
0x1800011ce  jnz     short loc_18000120A
0x1800011d0  call    __scrt_get_dyn_tls_init_callback
0x1800011d5  mov     rbx, rax
0x1800011d8  cmp     qword ptr [rax], 0
0x1800011dc  jz      short loc_1800011FD
0x1800011de  mov     rcx, rax
0x1800011e1  call    __scrt_is_nonwritable_in_current_image
0x1800011e6  test    al, al
0x1800011e8  jz      short loc_1800011FD
0x1800011ea  mov     r8, rsi
0x1800011ed  mov     edx, 2
0x1800011f2  mov     rcx, r14
0x1800011f5  mov     rax, [rbx]
0x1800011f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011fd  inc     cs:dword_180005090
0x180001203  mov     eax, 1
0x180001208  jmp     short loc_18000120C
0x18000120a  xor     eax, eax
0x18000120c  add     rsp, 28h
0x180001210  pop     r14
0x180001212  pop     rdi
0x180001213  pop     rsi
0x180001214  pop     rbx
0x180001215  retn
0x180001216  mov     ecx, 7
0x18000121b  call    __scrt_fastfail
0x18000213c  push    rbp
0x18000213e  sub     rsp, 20h
0x180002142  mov     rbp, rdx
0x180002145  mov     cl, [rbp+60h]
0x180002148  add     rsp, 20h
0x18000214c  pop     rbp
0x18000214d  jmp     __scrt_release_startup_lock
```
