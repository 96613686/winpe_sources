# dllmain_crt_process_detach

- ea: `0x180002998`
- end: `0x180002a1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002830`
- `0x180002a1c`

## callees

- `0x180002998`
- `0x18000309c`
- `0x180003178`
- `0x1800032a0`
- `0x1800032d0`
- `0x180003444`
- `0x180003468`
- `0x18000351c`
- `0x1800037c0`

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

  if ( dword_18007B2CC <= 0 )
    return 0;
  --dword_18007B2CC;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180002A1BLL);
  }
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
0x180002998  mov     [rsp+arg_0], rbx
0x18000299d  push    rdi
0x18000299e  sub     rsp, 30h
0x1800029a2  mov     dil, cl
0x1800029a5  mov     eax, cs:dword_18007B2CC
0x1800029ab  test    eax, eax
0x1800029ad  jg      short loc_1800029BC
0x1800029af  xor     eax, eax
0x1800029b1  mov     rbx, [rsp+38h+arg_0]
0x1800029b6  add     rsp, 30h
0x1800029ba  pop     rdi
0x1800029bb  retn
0x1800029bc  dec     eax
0x1800029be  mov     cs:dword_18007B2CC, eax
0x1800029c4  call    __scrt_acquire_startup_lock
0x1800029c9  mov     bl, al
0x1800029cb  mov     [rsp+38h+var_18], al
0x1800029cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800029d6  jnz     short loc_180002A0E
0x1800029d8  call    __scrt_dllmain_uninitialize_c
0x1800029dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800029e2  call    _RTC_Terminate
0x1800029e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800029f1  mov     cl, bl
0x1800029f3  call    __scrt_release_startup_lock
0x1800029f8  xor     edx, edx
0x1800029fa  mov     cl, dil
0x1800029fd  call    __scrt_uninitialize_crt
0x180002a02  movzx   ebx, al
0x180002a05  call    __scrt_dllmain_uninitialize_critical
0x180002a0a  mov     eax, ebx
0x180002a0c  jmp     short loc_1800029B1
0x180002a0e  mov     ecx, 7
0x180002a13  call    __scrt_fastfail
0x180002a18  nop
0x180002a19  nop
0x180002a1a  int     3; Trap to Debugger
0x180061187  push    rbp
0x180061189  sub     rsp, 20h
0x18006118d  mov     rbp, rdx
0x180061190  mov     cl, [rbp+20h]
0x180061193  call    __scrt_release_startup_lock
0x180061198  nop
0x180061199  add     rsp, 20h
0x18006119d  pop     rbp
0x18006119e  retn
0x1800611a0  push    rbp
0x1800611a2  sub     rsp, 20h
0x1800611a6  mov     rbp, rdx
0x1800611a9  add     rsp, 20h
0x1800611ad  pop     rbp
0x1800611ae  jmp     __scrt_dllmain_uninitialize_critical
```
