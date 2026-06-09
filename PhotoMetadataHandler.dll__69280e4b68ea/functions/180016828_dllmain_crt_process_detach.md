# dllmain_crt_process_detach

- ea: `0x180016828`
- end: `0x1800168ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800166d0`

## callees

- `0x180016828`
- `0x180016abc`
- `0x180016be4`
- `0x180016c1c`
- `0x180016dac`
- `0x180016dd8`
- `0x180016f38`
- `0x180016f80`
- `0x180016fd0`

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

  if ( dword_180099EB0 <= 0 )
    return 0;
  --dword_180099EB0;
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
0x180016828  mov     [rsp+arg_0], rbx
0x18001682d  push    rdi
0x18001682e  sub     rsp, 30h
0x180016832  mov     dil, cl
0x180016835  mov     eax, cs:dword_180099EB0
0x18001683b  test    eax, eax
0x18001683d  jg      short loc_18001684C
0x18001683f  xor     eax, eax
0x180016841  mov     rbx, [rsp+38h+arg_0]
0x180016846  add     rsp, 30h
0x18001684a  pop     rdi
0x18001684b  retn
0x18001684c  dec     eax
0x18001684e  mov     cs:dword_180099EB0, eax
0x180016854  call    __scrt_acquire_startup_lock
0x180016859  mov     bl, al
0x18001685b  mov     [rsp+38h+var_18], al
0x18001685f  cmp     cs:__scrt_current_native_startup_state, 2
0x180016866  jnz     short loc_18001689E
0x180016868  call    __scrt_dllmain_uninitialize_c
0x18001686d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180016872  call    _RTC_Terminate
0x180016877  mov     cs:__scrt_current_native_startup_state, 0
0x180016881  mov     cl, bl
0x180016883  call    __scrt_release_startup_lock
0x180016888  xor     edx, edx
0x18001688a  mov     cl, dil
0x18001688d  call    __scrt_uninitialize_crt
0x180016892  movzx   ebx, al
0x180016895  call    __scrt_dllmain_uninitialize_critical
0x18001689a  mov     eax, ebx
0x18001689c  jmp     short loc_180016841
0x18001689e  mov     ecx, 7
0x1800168a3  call    __scrt_fastfail
0x180028098  push    rbp
0x18002809a  sub     rsp, 20h
0x18002809e  mov     rbp, rdx
0x1800280a1  mov     cl, [rbp+20h]
0x1800280a4  call    __scrt_release_startup_lock
0x1800280a9  nop
0x1800280aa  add     rsp, 20h
0x1800280ae  pop     rbp
0x1800280af  retn
0x1800280b1  push    rbp
0x1800280b3  sub     rsp, 20h
0x1800280b7  mov     rbp, rdx
0x1800280ba  add     rsp, 20h
0x1800280be  pop     rbp
0x1800280bf  jmp     __scrt_dllmain_uninitialize_critical
```
