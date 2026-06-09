# dllmain_crt_process_detach

- ea: `0x1800031a8`
- end: `0x18000322b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003050`

## callees

- `0x1800031a8`
- `0x180003464`
- `0x18000358c`
- `0x1800035c4`
- `0x180003754`
- `0x180003780`
- `0x180003eec`
- `0x180003f34`
- `0x180003f84`

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

  if ( dword_18001A410 <= 0 )
    return 0;
  --dword_18001A410;
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
0x1800031a8  mov     [rsp+arg_0], rbx
0x1800031ad  push    rdi
0x1800031ae  sub     rsp, 30h
0x1800031b2  mov     dil, cl
0x1800031b5  mov     eax, cs:dword_18001A410
0x1800031bb  test    eax, eax
0x1800031bd  jg      short loc_1800031CC
0x1800031bf  xor     eax, eax
0x1800031c1  mov     rbx, [rsp+38h+arg_0]
0x1800031c6  add     rsp, 30h
0x1800031ca  pop     rdi
0x1800031cb  retn
0x1800031cc  dec     eax
0x1800031ce  mov     cs:dword_18001A410, eax
0x1800031d4  call    __scrt_acquire_startup_lock
0x1800031d9  mov     bl, al
0x1800031db  mov     [rsp+38h+var_18], al
0x1800031df  cmp     cs:__scrt_current_native_startup_state, 2
0x1800031e6  jnz     short loc_18000321E
0x1800031e8  call    __scrt_dllmain_uninitialize_c
0x1800031ed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800031f2  call    _RTC_Terminate
0x1800031f7  mov     cs:__scrt_current_native_startup_state, 0
0x180003201  mov     cl, bl
0x180003203  call    __scrt_release_startup_lock
0x180003208  xor     edx, edx
0x18000320a  mov     cl, dil
0x18000320d  call    __scrt_uninitialize_crt
0x180003212  movzx   ebx, al
0x180003215  call    __scrt_dllmain_uninitialize_critical
0x18000321a  mov     eax, ebx
0x18000321c  jmp     short loc_1800031C1
0x18000321e  mov     ecx, 7
0x180003223  call    __scrt_fastfail
0x180012079  push    rbp
0x18001207b  sub     rsp, 20h
0x18001207f  mov     rbp, rdx
0x180012082  mov     cl, [rbp+20h]
0x180012085  call    __scrt_release_startup_lock
0x18001208a  nop
0x18001208b  add     rsp, 20h
0x18001208f  pop     rbp
0x180012090  retn
0x180012092  push    rbp
0x180012094  sub     rsp, 20h
0x180012098  mov     rbp, rdx
0x18001209b  add     rsp, 20h
0x18001209f  pop     rbp
0x1800120a0  jmp     __scrt_dllmain_uninitialize_critical
```
