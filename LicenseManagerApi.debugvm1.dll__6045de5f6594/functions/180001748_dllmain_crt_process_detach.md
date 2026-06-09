# dllmain_crt_process_detach

- ea: `0x180001748`
- end: `0x1800017cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800015f0`

## callees

- `0x180001748`
- `0x180001984`
- `0x180001aac`
- `0x180001ae4`
- `0x180001c74`
- `0x180001ca0`
- `0x180001e3c`
- `0x180001e84`
- `0x180001ed4`

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
0x180001748  mov     [rsp+arg_0], rbx
0x18000174d  push    rdi
0x18000174e  sub     rsp, 30h
0x180001752  mov     dil, cl
0x180001755  mov     eax, cs:dword_18001A410
0x18000175b  test    eax, eax
0x18000175d  jg      short loc_18000176C
0x18000175f  xor     eax, eax
0x180001761  mov     rbx, [rsp+38h+arg_0]
0x180001766  add     rsp, 30h
0x18000176a  pop     rdi
0x18000176b  retn
0x18000176c  dec     eax
0x18000176e  mov     cs:dword_18001A410, eax
0x180001774  call    __scrt_acquire_startup_lock
0x180001779  mov     bl, al
0x18000177b  mov     [rsp+38h+var_18], al
0x18000177f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001786  jnz     short loc_1800017BE
0x180001788  call    __scrt_dllmain_uninitialize_c
0x18000178d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001792  call    _RTC_Terminate
0x180001797  mov     cs:__scrt_current_native_startup_state, 0
0x1800017a1  mov     cl, bl
0x1800017a3  call    __scrt_release_startup_lock
0x1800017a8  xor     edx, edx
0x1800017aa  mov     cl, dil
0x1800017ad  call    __scrt_uninitialize_crt
0x1800017b2  movzx   ebx, al
0x1800017b5  call    __scrt_dllmain_uninitialize_critical
0x1800017ba  mov     eax, ebx
0x1800017bc  jmp     short loc_180001761
0x1800017be  mov     ecx, 7
0x1800017c3  call    __scrt_fastfail
0x180011ded  push    rbp
0x180011def  sub     rsp, 20h
0x180011df3  mov     rbp, rdx
0x180011df6  mov     cl, [rbp+20h]
0x180011df9  call    __scrt_release_startup_lock
0x180011dfe  nop
0x180011dff  add     rsp, 20h
0x180011e03  pop     rbp
0x180011e04  retn
0x180011e06  push    rbp
0x180011e08  sub     rsp, 20h
0x180011e0c  mov     rbp, rdx
0x180011e0f  add     rsp, 20h
0x180011e13  pop     rbp
0x180011e14  jmp     __scrt_dllmain_uninitialize_critical
```
