# dllmain_crt_process_detach

- ea: `0x1800095b8`
- end: `0x18000963b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180009460`

## callees

- `0x1800095b8`
- `0x1800097f4`
- `0x18000991c`
- `0x180009954`
- `0x180009ae4`
- `0x180009b10`
- `0x180009cd4`
- `0x180009d1c`
- `0x180009d6c`

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

  if ( dword_18001F390 <= 0 )
    return 0;
  --dword_18001F390;
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
0x1800095b8  mov     [rsp+arg_0], rbx
0x1800095bd  push    rdi
0x1800095be  sub     rsp, 30h
0x1800095c2  mov     dil, cl
0x1800095c5  mov     eax, cs:dword_18001F390
0x1800095cb  test    eax, eax
0x1800095cd  jg      short loc_1800095DC
0x1800095cf  xor     eax, eax
0x1800095d1  mov     rbx, [rsp+38h+arg_0]
0x1800095d6  add     rsp, 30h
0x1800095da  pop     rdi
0x1800095db  retn
0x1800095dc  dec     eax
0x1800095de  mov     cs:dword_18001F390, eax
0x1800095e4  call    __scrt_acquire_startup_lock
0x1800095e9  mov     bl, al
0x1800095eb  mov     [rsp+38h+var_18], al
0x1800095ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800095f6  jnz     short loc_18000962E
0x1800095f8  call    __scrt_dllmain_uninitialize_c
0x1800095fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180009602  call    _RTC_Terminate
0x180009607  mov     cs:__scrt_current_native_startup_state, 0
0x180009611  mov     cl, bl
0x180009613  call    __scrt_release_startup_lock
0x180009618  xor     edx, edx
0x18000961a  mov     cl, dil
0x18000961d  call    __scrt_uninitialize_crt
0x180009622  movzx   ebx, al
0x180009625  call    __scrt_dllmain_uninitialize_critical
0x18000962a  mov     eax, ebx
0x18000962c  jmp     short loc_1800095D1
0x18000962e  mov     ecx, 7
0x180009633  call    __scrt_fastfail
0x180015789  push    rbp
0x18001578b  sub     rsp, 20h
0x18001578f  mov     rbp, rdx
0x180015792  mov     cl, [rbp+20h]
0x180015795  call    __scrt_release_startup_lock
0x18001579a  nop
0x18001579b  add     rsp, 20h
0x18001579f  pop     rbp
0x1800157a0  retn
0x1800157a2  push    rbp
0x1800157a4  sub     rsp, 20h
0x1800157a8  mov     rbp, rdx
0x1800157ab  add     rsp, 20h
0x1800157af  pop     rbp
0x1800157b0  jmp     __scrt_dllmain_uninitialize_critical
```
