# dllmain_crt_process_detach

- ea: `0x180001868`
- end: `0x1800018eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001710`

## callees

- `0x180001868`
- `0x180001b74`
- `0x180001bac`
- `0x180001cd4`
- `0x180001d0c`
- `0x180001e9c`
- `0x180001ec8`
- `0x180001f08`
- `0x180001f58`

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

  if ( dword_180028810 <= 0 )
    return 0;
  --dword_180028810;
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
0x180001868  mov     [rsp+arg_0], rbx
0x18000186d  push    rdi
0x18000186e  sub     rsp, 30h
0x180001872  mov     dil, cl
0x180001875  mov     eax, cs:dword_180028810
0x18000187b  test    eax, eax
0x18000187d  jg      short loc_18000188C
0x18000187f  xor     eax, eax
0x180001881  mov     rbx, [rsp+38h+arg_0]
0x180001886  add     rsp, 30h
0x18000188a  pop     rdi
0x18000188b  retn
0x18000188c  dec     eax
0x18000188e  mov     cs:dword_180028810, eax
0x180001894  call    __scrt_acquire_startup_lock
0x180001899  mov     bl, al
0x18000189b  mov     [rsp+38h+var_18], al
0x18000189f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800018a6  jnz     short loc_1800018DE
0x1800018a8  call    __scrt_dllmain_uninitialize_c
0x1800018ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800018b2  call    _RTC_Terminate
0x1800018b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800018c1  mov     cl, bl
0x1800018c3  call    __scrt_release_startup_lock
0x1800018c8  xor     edx, edx
0x1800018ca  mov     cl, dil
0x1800018cd  call    __scrt_uninitialize_crt
0x1800018d2  movzx   ebx, al
0x1800018d5  call    __scrt_dllmain_uninitialize_critical
0x1800018da  mov     eax, ebx
0x1800018dc  jmp     short loc_180001881
0x1800018de  mov     ecx, 7
0x1800018e3  call    __scrt_fastfail
0x18001bef9  push    rbp
0x18001befb  sub     rsp, 20h
0x18001beff  mov     rbp, rdx
0x18001bf02  mov     cl, [rbp+20h]
0x18001bf05  call    __scrt_release_startup_lock
0x18001bf0a  nop
0x18001bf0b  add     rsp, 20h
0x18001bf0f  pop     rbp
0x18001bf10  retn
0x18001bf12  push    rbp
0x18001bf14  sub     rsp, 20h
0x18001bf18  mov     rbp, rdx
0x18001bf1b  add     rsp, 20h
0x18001bf1f  pop     rbp
0x18001bf20  jmp     __scrt_dllmain_uninitialize_critical
```
