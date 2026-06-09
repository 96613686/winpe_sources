# dllmain_crt_process_detach

- ea: `0x180001fb8`
- end: `0x18000203b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001e60`

## callees

- `0x180001fb8`
- `0x18000222c`
- `0x180002354`
- `0x18000238c`
- `0x18000251c`
- `0x180002548`
- `0x1800026ec`
- `0x180002734`
- `0x180002784`

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

  if ( dword_18002E650 <= 0 )
    return 0;
  --dword_18002E650;
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
0x180001fb8  mov     [rsp+arg_0], rbx
0x180001fbd  push    rdi
0x180001fbe  sub     rsp, 30h
0x180001fc2  mov     dil, cl
0x180001fc5  mov     eax, cs:dword_18002E650
0x180001fcb  test    eax, eax
0x180001fcd  jg      short loc_180001FDC
0x180001fcf  xor     eax, eax
0x180001fd1  mov     rbx, [rsp+38h+arg_0]
0x180001fd6  add     rsp, 30h
0x180001fda  pop     rdi
0x180001fdb  retn
0x180001fdc  dec     eax
0x180001fde  mov     cs:dword_18002E650, eax
0x180001fe4  call    __scrt_acquire_startup_lock
0x180001fe9  mov     bl, al
0x180001feb  mov     [rsp+38h+var_18], al
0x180001fef  cmp     cs:__scrt_current_native_startup_state, 2
0x180001ff6  jnz     short loc_18000202E
0x180001ff8  call    __scrt_dllmain_uninitialize_c
0x180001ffd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002002  call    _RTC_Terminate
0x180002007  mov     cs:__scrt_current_native_startup_state, 0
0x180002011  mov     cl, bl
0x180002013  call    __scrt_release_startup_lock
0x180002018  xor     edx, edx
0x18000201a  mov     cl, dil
0x18000201d  call    __scrt_uninitialize_crt
0x180002022  movzx   ebx, al
0x180002025  call    __scrt_dllmain_uninitialize_critical
0x18000202a  mov     eax, ebx
0x18000202c  jmp     short loc_180001FD1
0x18000202e  mov     ecx, 7
0x180002033  call    __scrt_fastfail
0x180021fe9  push    rbp
0x180021feb  sub     rsp, 20h
0x180021fef  mov     rbp, rdx
0x180021ff2  mov     cl, [rbp+20h]
0x180021ff5  call    __scrt_release_startup_lock
0x180021ffa  nop
0x180021ffb  add     rsp, 20h
0x180021fff  pop     rbp
0x180022000  retn
0x180022002  push    rbp
0x180022004  sub     rsp, 20h
0x180022008  mov     rbp, rdx
0x18002200b  add     rsp, 20h
0x18002200f  pop     rbp
0x180022010  jmp     __scrt_dllmain_uninitialize_critical
```
