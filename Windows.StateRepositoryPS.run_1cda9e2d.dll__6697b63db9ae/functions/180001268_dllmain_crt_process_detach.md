# dllmain_crt_process_detach

- ea: `0x180001268`
- end: `0x1800012eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001110`

## callees

- `0x180001268`
- `0x180001574`
- `0x1800015ac`
- `0x1800016d4`
- `0x18000170c`
- `0x18000189c`
- `0x1800018c8`
- `0x180001908`
- `0x180001958`

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

  if ( dword_1800B3350 <= 0 )
    return 0;
  --dword_1800B3350;
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
0x180001268  mov     [rsp+arg_0], rbx
0x18000126d  push    rdi
0x18000126e  sub     rsp, 30h
0x180001272  mov     dil, cl
0x180001275  mov     eax, cs:dword_1800B3350
0x18000127b  test    eax, eax
0x18000127d  jg      short loc_18000128C
0x18000127f  xor     eax, eax
0x180001281  mov     rbx, [rsp+38h+arg_0]
0x180001286  add     rsp, 30h
0x18000128a  pop     rdi
0x18000128b  retn
0x18000128c  dec     eax
0x18000128e  mov     cs:dword_1800B3350, eax
0x180001294  call    __scrt_acquire_startup_lock
0x180001299  mov     bl, al
0x18000129b  mov     [rsp+38h+var_18], al
0x18000129f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800012a6  jnz     short loc_1800012DE
0x1800012a8  call    __scrt_dllmain_uninitialize_c
0x1800012ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800012b2  call    _RTC_Terminate
0x1800012b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800012c1  mov     cl, bl
0x1800012c3  call    __scrt_release_startup_lock
0x1800012c8  xor     edx, edx
0x1800012ca  mov     cl, dil
0x1800012cd  call    __scrt_uninitialize_crt
0x1800012d2  movzx   ebx, al
0x1800012d5  call    __scrt_dllmain_uninitialize_critical
0x1800012da  mov     eax, ebx
0x1800012dc  jmp     short loc_180001281
0x1800012de  mov     ecx, 7
0x1800012e3  call    __scrt_fastfail
0x180001e49  push    rbp
0x180001e4b  sub     rsp, 20h
0x180001e4f  mov     rbp, rdx
0x180001e52  mov     cl, [rbp+20h]
0x180001e55  call    __scrt_release_startup_lock
0x180001e5a  nop
0x180001e5b  add     rsp, 20h
0x180001e5f  pop     rbp
0x180001e60  retn
0x180001e62  push    rbp
0x180001e64  sub     rsp, 20h
0x180001e68  mov     rbp, rdx
0x180001e6b  add     rsp, 20h
0x180001e6f  pop     rbp
0x180001e70  jmp     __scrt_dllmain_uninitialize_critical
```
