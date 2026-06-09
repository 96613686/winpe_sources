# dllmain_crt_process_detach

- ea: `0x1800025a8`
- end: `0x18000262b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002450`

## callees

- `0x1800025a8`
- `0x1800027e4`
- `0x18000290c`
- `0x180002944`
- `0x180002ad4`
- `0x180002b00`
- `0x180002ffc`
- `0x180003044`
- `0x180003094`

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

  if ( dword_180049410 <= 0 )
    return 0;
  --dword_180049410;
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
0x1800025a8  mov     [rsp+arg_0], rbx
0x1800025ad  push    rdi
0x1800025ae  sub     rsp, 30h
0x1800025b2  mov     dil, cl
0x1800025b5  mov     eax, cs:dword_180049410
0x1800025bb  test    eax, eax
0x1800025bd  jg      short loc_1800025CC
0x1800025bf  xor     eax, eax
0x1800025c1  mov     rbx, [rsp+38h+arg_0]
0x1800025c6  add     rsp, 30h
0x1800025ca  pop     rdi
0x1800025cb  retn
0x1800025cc  dec     eax
0x1800025ce  mov     cs:dword_180049410, eax
0x1800025d4  call    __scrt_acquire_startup_lock
0x1800025d9  mov     bl, al
0x1800025db  mov     [rsp+38h+var_18], al
0x1800025df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800025e6  jnz     short loc_18000261E
0x1800025e8  call    __scrt_dllmain_uninitialize_c
0x1800025ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800025f2  call    _RTC_Terminate
0x1800025f7  mov     cs:__scrt_current_native_startup_state, 0
0x180002601  mov     cl, bl
0x180002603  call    __scrt_release_startup_lock
0x180002608  xor     edx, edx
0x18000260a  mov     cl, dil
0x18000260d  call    __scrt_uninitialize_crt
0x180002612  movzx   ebx, al
0x180002615  call    __scrt_dllmain_uninitialize_critical
0x18000261a  mov     eax, ebx
0x18000261c  jmp     short loc_1800025C1
0x18000261e  mov     ecx, 7
0x180002623  call    __scrt_fastfail
0x18002e369  push    rbp
0x18002e36b  sub     rsp, 20h
0x18002e36f  mov     rbp, rdx
0x18002e372  mov     cl, [rbp+20h]
0x18002e375  call    __scrt_release_startup_lock
0x18002e37a  nop
0x18002e37b  add     rsp, 20h
0x18002e37f  pop     rbp
0x18002e380  retn
0x18002e382  push    rbp
0x18002e384  sub     rsp, 20h
0x18002e388  mov     rbp, rdx
0x18002e38b  add     rsp, 20h
0x18002e38f  pop     rbp
0x18002e390  jmp     __scrt_dllmain_uninitialize_critical
```
