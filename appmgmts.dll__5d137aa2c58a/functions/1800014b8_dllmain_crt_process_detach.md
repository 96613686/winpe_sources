# dllmain_crt_process_detach

- ea: `0x1800014b8`
- end: `0x18000153b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x1800014b8`
- `0x1800017f0`
- `0x180001828`
- `0x180001950`
- `0x180001988`
- `0x180001b18`
- `0x180001b44`
- `0x180001be4`
- `0x180001c34`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800376D0 <= 0 )
    return 0;
  --dword_1800376D0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x1800014b8  mov     [rsp+arg_0], rbx
0x1800014bd  push    rdi
0x1800014be  sub     rsp, 30h
0x1800014c2  mov     dil, cl
0x1800014c5  mov     eax, cs:dword_1800376D0
0x1800014cb  test    eax, eax
0x1800014cd  jg      short loc_1800014DC
0x1800014cf  xor     eax, eax
0x1800014d1  mov     rbx, [rsp+38h+arg_0]
0x1800014d6  add     rsp, 30h
0x1800014da  pop     rdi
0x1800014db  retn
0x1800014dc  dec     eax
0x1800014de  mov     cs:dword_1800376D0, eax
0x1800014e4  call    __scrt_acquire_startup_lock
0x1800014e9  mov     bl, al
0x1800014eb  mov     [rsp+38h+var_18], al
0x1800014ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800014f6  jnz     short loc_18000152E
0x1800014f8  call    __scrt_dllmain_uninitialize_c
0x1800014fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001502  call    _RTC_Terminate
0x180001507  mov     cs:__scrt_current_native_startup_state, 0
0x180001511  mov     cl, bl
0x180001513  call    __scrt_release_startup_lock
0x180001518  xor     edx, edx
0x18000151a  mov     cl, dil
0x18000151d  call    __scrt_uninitialize_crt
0x180001522  movzx   ebx, al
0x180001525  call    __scrt_dllmain_uninitialize_critical
0x18000152a  mov     eax, ebx
0x18000152c  jmp     short loc_1800014D1
0x18000152e  mov     ecx, 7
0x180001533  call    __scrt_fastfail
0x18002ae49  push    rbp
0x18002ae4b  sub     rsp, 20h
0x18002ae4f  mov     rbp, rdx
0x18002ae52  mov     cl, [rbp+20h]
0x18002ae55  call    __scrt_release_startup_lock
0x18002ae5a  nop
0x18002ae5b  add     rsp, 20h
0x18002ae5f  pop     rbp
0x18002ae60  retn
0x18002ae62  push    rbp
0x18002ae64  sub     rsp, 20h
0x18002ae68  mov     rbp, rdx
0x18002ae6b  add     rsp, 20h
0x18002ae6f  pop     rbp
0x18002ae70  jmp     __scrt_dllmain_uninitialize_critical
```
