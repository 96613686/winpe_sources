# dllmain_crt_process_detach

- ea: `0x180001228`
- end: `0x1800012ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800010d0`

## callees

- `0x180001228`
- `0x18000156c`
- `0x1800015a4`
- `0x1800016cc`
- `0x180001704`
- `0x180001894`
- `0x1800018c0`
- `0x180001900`
- `0x180001950`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_180005090 <= 0 )
    return 0;
  --dword_180005090;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180001228  mov     [rsp+arg_0], rbx
0x18000122d  push    rdi
0x18000122e  sub     rsp, 30h
0x180001232  mov     dil, cl
0x180001235  mov     eax, cs:dword_180005090
0x18000123b  test    eax, eax
0x18000123d  jg      short loc_18000124C
0x18000123f  xor     eax, eax
0x180001241  mov     rbx, [rsp+38h+arg_0]
0x180001246  add     rsp, 30h
0x18000124a  pop     rdi
0x18000124b  retn
0x18000124c  dec     eax
0x18000124e  mov     cs:dword_180005090, eax
0x180001254  call    __scrt_acquire_startup_lock
0x180001259  mov     bl, al
0x18000125b  mov     [rsp+38h+var_18], al
0x18000125f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001266  jnz     short loc_18000129E
0x180001268  call    __scrt_dllmain_uninitialize_c
0x18000126d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001272  call    _RTC_Terminate
0x180001277  mov     cs:__scrt_current_native_startup_state, 0
0x180001281  mov     cl, bl
0x180001283  call    __scrt_release_startup_lock
0x180001288  xor     edx, edx
0x18000128a  mov     cl, dil
0x18000128d  call    __scrt_uninitialize_crt
0x180001292  movzx   ebx, al
0x180001295  call    __scrt_dllmain_uninitialize_critical
0x18000129a  mov     eax, ebx
0x18000129c  jmp     short loc_180001241
0x18000129e  mov     ecx, 7
0x1800012a3  call    __scrt_fastfail
0x180002159  push    rbp
0x18000215b  sub     rsp, 20h
0x18000215f  mov     rbp, rdx
0x180002162  mov     cl, [rbp+20h]
0x180002165  call    __scrt_release_startup_lock
0x18000216a  nop
0x18000216b  add     rsp, 20h
0x18000216f  pop     rbp
0x180002170  retn
0x180002172  push    rbp
0x180002174  sub     rsp, 20h
0x180002178  mov     rbp, rdx
0x18000217b  add     rsp, 20h
0x18000217f  pop     rbp
0x180002180  jmp     __scrt_dllmain_uninitialize_critical
```
