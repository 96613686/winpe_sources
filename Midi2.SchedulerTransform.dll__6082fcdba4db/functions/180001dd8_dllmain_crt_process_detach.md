# dllmain_crt_process_detach

- ea: `0x180001dd8`
- end: `0x180001e5b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001c80`

## callees

- `0x180001dd8`
- `0x180002094`
- `0x1800021bc`
- `0x1800021f4`
- `0x180002384`
- `0x1800023b0`
- `0x180002570`
- `0x1800025b8`
- `0x180002608`

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

  if ( dword_180015390 <= 0 )
    return 0;
  --dword_180015390;
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
0x180001dd8  mov     [rsp+arg_0], rbx
0x180001ddd  push    rdi
0x180001dde  sub     rsp, 30h
0x180001de2  mov     dil, cl
0x180001de5  mov     eax, cs:dword_180015390
0x180001deb  test    eax, eax
0x180001ded  jg      short loc_180001DFC
0x180001def  xor     eax, eax
0x180001df1  mov     rbx, [rsp+38h+arg_0]
0x180001df6  add     rsp, 30h
0x180001dfa  pop     rdi
0x180001dfb  retn
0x180001dfc  dec     eax
0x180001dfe  mov     cs:dword_180015390, eax
0x180001e04  call    __scrt_acquire_startup_lock
0x180001e09  mov     bl, al
0x180001e0b  mov     [rsp+38h+var_18], al
0x180001e0f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001e16  jnz     short loc_180001E4E
0x180001e18  call    __scrt_dllmain_uninitialize_c
0x180001e1d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001e22  call    _RTC_Terminate
0x180001e27  mov     cs:__scrt_current_native_startup_state, 0
0x180001e31  mov     cl, bl
0x180001e33  call    __scrt_release_startup_lock
0x180001e38  xor     edx, edx
0x180001e3a  mov     cl, dil
0x180001e3d  call    __scrt_uninitialize_crt
0x180001e42  movzx   ebx, al
0x180001e45  call    __scrt_dllmain_uninitialize_critical
0x180001e4a  mov     eax, ebx
0x180001e4c  jmp     short loc_180001DF1
0x180001e4e  mov     ecx, 7
0x180001e53  call    __scrt_fastfail
0x18000cd09  push    rbp
0x18000cd0b  sub     rsp, 20h
0x18000cd0f  mov     rbp, rdx
0x18000cd12  mov     cl, [rbp+20h]
0x18000cd15  call    __scrt_release_startup_lock
0x18000cd1a  nop
0x18000cd1b  add     rsp, 20h
0x18000cd1f  pop     rbp
0x18000cd20  retn
0x18000cd22  push    rbp
0x18000cd24  sub     rsp, 20h
0x18000cd28  mov     rbp, rdx
0x18000cd2b  add     rsp, 20h
0x18000cd2f  pop     rbp
0x18000cd30  jmp     __scrt_dllmain_uninitialize_critical
```
