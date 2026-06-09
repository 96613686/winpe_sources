# dllmain_crt_process_detach

- ea: `0x1800013b8`
- end: `0x18000143b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001260`

## callees

- `0x1800013b8`
- `0x1800015f4`
- `0x18000171c`
- `0x180001754`
- `0x1800018e4`
- `0x180001910`
- `0x180001a80`
- `0x180001ac8`
- `0x180001b18`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  if ( dword_18004A5D0 <= 0 )
    return 0;
  --dword_18004A5D0;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0);
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x1800013b8  mov     [rsp+arg_0], rbx
0x1800013bd  push    rdi
0x1800013be  sub     rsp, 30h
0x1800013c2  mov     dil, cl
0x1800013c5  mov     eax, cs:dword_18004A5D0
0x1800013cb  test    eax, eax
0x1800013cd  jg      short loc_1800013DC
0x1800013cf  xor     eax, eax
0x1800013d1  mov     rbx, [rsp+38h+arg_0]
0x1800013d6  add     rsp, 30h
0x1800013da  pop     rdi
0x1800013db  retn
0x1800013dc  dec     eax
0x1800013de  mov     cs:dword_18004A5D0, eax
0x1800013e4  call    __scrt_acquire_startup_lock
0x1800013e9  mov     bl, al
0x1800013eb  mov     [rsp+38h+var_18], al
0x1800013ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800013f6  jnz     short loc_18000142E
0x1800013f8  call    __scrt_dllmain_uninitialize_c
0x1800013fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001402  call    _RTC_Terminate
0x180001407  mov     cs:__scrt_current_native_startup_state, 0
0x180001411  mov     cl, bl
0x180001413  call    __scrt_release_startup_lock
0x180001418  xor     edx, edx
0x18000141a  mov     cl, dil
0x18000141d  call    __scrt_uninitialize_crt
0x180001422  movzx   ebx, al
0x180001425  call    __scrt_dllmain_uninitialize_critical
0x18000142a  mov     eax, ebx
0x18000142c  jmp     short loc_1800013D1
0x18000142e  mov     ecx, 7
0x180001433  call    __scrt_fastfail
0x18003f349  push    rbp
0x18003f34b  sub     rsp, 20h
0x18003f34f  mov     rbp, rdx
0x18003f352  mov     cl, [rbp+20h]
0x18003f355  call    __scrt_release_startup_lock
0x18003f35a  nop
0x18003f35b  add     rsp, 20h
0x18003f35f  pop     rbp
0x18003f360  retn
0x18003f362  push    rbp
0x18003f364  sub     rsp, 20h
0x18003f368  mov     rbp, rdx
0x18003f36b  add     rsp, 20h
0x18003f36f  pop     rbp
0x18003f370  jmp     __scrt_dllmain_uninitialize_critical
```
