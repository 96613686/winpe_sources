# dllmain_crt_process_detach

- ea: `0x180002138`
- end: `0x1800021bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001fe0`

## callees

- `0x180002138`
- `0x180002474`
- `0x18000259c`
- `0x1800025d4`
- `0x180002764`
- `0x180002790`
- `0x1800029a4`
- `0x1800029ec`
- `0x180002a3c`

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

  if ( dword_180059B90 <= 0 )
    return 0;
  --dword_180059B90;
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
0x180002138  mov     [rsp+arg_0], rbx
0x18000213d  push    rdi
0x18000213e  sub     rsp, 30h
0x180002142  mov     dil, cl
0x180002145  mov     eax, cs:dword_180059B90
0x18000214b  test    eax, eax
0x18000214d  jg      short loc_18000215C
0x18000214f  xor     eax, eax
0x180002151  mov     rbx, [rsp+38h+arg_0]
0x180002156  add     rsp, 30h
0x18000215a  pop     rdi
0x18000215b  retn
0x18000215c  dec     eax
0x18000215e  mov     cs:dword_180059B90, eax
0x180002164  call    __scrt_acquire_startup_lock
0x180002169  mov     bl, al
0x18000216b  mov     [rsp+38h+var_18], al
0x18000216f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002176  jnz     short loc_1800021AE
0x180002178  call    __scrt_dllmain_uninitialize_c
0x18000217d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002182  call    _RTC_Terminate
0x180002187  mov     cs:__scrt_current_native_startup_state, 0
0x180002191  mov     cl, bl
0x180002193  call    __scrt_release_startup_lock
0x180002198  xor     edx, edx
0x18000219a  mov     cl, dil
0x18000219d  call    __scrt_uninitialize_crt
0x1800021a2  movzx   ebx, al
0x1800021a5  call    __scrt_dllmain_uninitialize_critical
0x1800021aa  mov     eax, ebx
0x1800021ac  jmp     short loc_180002151
0x1800021ae  mov     ecx, 7
0x1800021b3  call    __scrt_fastfail
0x1800292b9  push    rbp
0x1800292bb  sub     rsp, 20h
0x1800292bf  mov     rbp, rdx
0x1800292c2  mov     cl, [rbp+20h]
0x1800292c5  call    __scrt_release_startup_lock
0x1800292ca  nop
0x1800292cb  add     rsp, 20h
0x1800292cf  pop     rbp
0x1800292d0  retn
0x1800292d2  push    rbp
0x1800292d4  sub     rsp, 20h
0x1800292d8  mov     rbp, rdx
0x1800292db  add     rsp, 20h
0x1800292df  pop     rbp
0x1800292e0  jmp     __scrt_dllmain_uninitialize_critical
```
