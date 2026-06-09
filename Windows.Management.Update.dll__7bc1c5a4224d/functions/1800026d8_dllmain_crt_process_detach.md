# dllmain_crt_process_detach

- ea: `0x1800026d8`
- end: `0x18000275b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002580`

## callees

- `0x1800026d8`
- `0x180002914`
- `0x180002a3c`
- `0x180002a74`
- `0x180002c04`
- `0x180002c30`
- `0x180002ef0`
- `0x180002f38`
- `0x180002f88`

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

  if ( dword_18003AAF0 <= 0 )
    return 0;
  --dword_18003AAF0;
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
0x1800026d8  mov     [rsp+arg_0], rbx
0x1800026dd  push    rdi
0x1800026de  sub     rsp, 30h
0x1800026e2  mov     dil, cl
0x1800026e5  mov     eax, cs:dword_18003AAF0
0x1800026eb  test    eax, eax
0x1800026ed  jg      short loc_1800026FC
0x1800026ef  xor     eax, eax
0x1800026f1  mov     rbx, [rsp+38h+arg_0]
0x1800026f6  add     rsp, 30h
0x1800026fa  pop     rdi
0x1800026fb  retn
0x1800026fc  dec     eax
0x1800026fe  mov     cs:dword_18003AAF0, eax
0x180002704  call    __scrt_acquire_startup_lock
0x180002709  mov     bl, al
0x18000270b  mov     [rsp+38h+var_18], al
0x18000270f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002716  jnz     short loc_18000274E
0x180002718  call    __scrt_dllmain_uninitialize_c
0x18000271d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002722  call    _RTC_Terminate
0x180002727  mov     cs:__scrt_current_native_startup_state, 0
0x180002731  mov     cl, bl
0x180002733  call    __scrt_release_startup_lock
0x180002738  xor     edx, edx
0x18000273a  mov     cl, dil
0x18000273d  call    __scrt_uninitialize_crt
0x180002742  movzx   ebx, al
0x180002745  call    __scrt_dllmain_uninitialize_critical
0x18000274a  mov     eax, ebx
0x18000274c  jmp     short loc_1800026F1
0x18000274e  mov     ecx, 7
0x180002753  call    __scrt_fastfail
0x1800276dd  push    rbp
0x1800276df  sub     rsp, 20h
0x1800276e3  mov     rbp, rdx
0x1800276e6  mov     cl, [rbp+20h]
0x1800276e9  call    __scrt_release_startup_lock
0x1800276ee  nop
0x1800276ef  add     rsp, 20h
0x1800276f3  pop     rbp
0x1800276f4  retn
0x1800276f6  push    rbp
0x1800276f8  sub     rsp, 20h
0x1800276fc  mov     rbp, rdx
0x1800276ff  add     rsp, 20h
0x180027703  pop     rbp
0x180027704  jmp     __scrt_dllmain_uninitialize_critical
```
