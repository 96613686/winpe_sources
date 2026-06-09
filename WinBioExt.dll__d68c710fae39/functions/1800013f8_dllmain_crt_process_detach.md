# dllmain_crt_process_detach

- ea: `0x1800013f8`
- end: `0x18000147b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012a0`

## callees

- `0x1800013f8`
- `0x180001634`
- `0x18000175c`
- `0x180001794`
- `0x180001924`
- `0x180001950`
- `0x180001b10`
- `0x180001b58`
- `0x180001ba8`

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

  if ( dword_180010370 <= 0 )
    return 0;
  --dword_180010370;
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
0x1800013f8  mov     [rsp+arg_0], rbx
0x1800013fd  push    rdi
0x1800013fe  sub     rsp, 30h
0x180001402  mov     dil, cl
0x180001405  mov     eax, cs:dword_180010370
0x18000140b  test    eax, eax
0x18000140d  jg      short loc_18000141C
0x18000140f  xor     eax, eax
0x180001411  mov     rbx, [rsp+38h+arg_0]
0x180001416  add     rsp, 30h
0x18000141a  pop     rdi
0x18000141b  retn
0x18000141c  dec     eax
0x18000141e  mov     cs:dword_180010370, eax
0x180001424  call    __scrt_acquire_startup_lock
0x180001429  mov     bl, al
0x18000142b  mov     [rsp+38h+var_18], al
0x18000142f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001436  jnz     short loc_18000146E
0x180001438  call    __scrt_dllmain_uninitialize_c
0x18000143d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001442  call    _RTC_Terminate
0x180001447  mov     cs:__scrt_current_native_startup_state, 0
0x180001451  mov     cl, bl
0x180001453  call    __scrt_release_startup_lock
0x180001458  xor     edx, edx
0x18000145a  mov     cl, dil
0x18000145d  call    __scrt_uninitialize_crt
0x180001462  movzx   ebx, al
0x180001465  call    __scrt_dllmain_uninitialize_critical
0x18000146a  mov     eax, ebx
0x18000146c  jmp     short loc_180001411
0x18000146e  mov     ecx, 7
0x180001473  call    __scrt_fastfail
0x18000a059  push    rbp
0x18000a05b  sub     rsp, 20h
0x18000a05f  mov     rbp, rdx
0x18000a062  mov     cl, [rbp+20h]
0x18000a065  call    __scrt_release_startup_lock
0x18000a06a  nop
0x18000a06b  add     rsp, 20h
0x18000a06f  pop     rbp
0x18000a070  retn
0x18000a072  push    rbp
0x18000a074  sub     rsp, 20h
0x18000a078  mov     rbp, rdx
0x18000a07b  add     rsp, 20h
0x18000a07f  pop     rbp
0x18000a080  jmp     __scrt_dllmain_uninitialize_critical
```
