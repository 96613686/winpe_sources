# dllmain_crt_process_detach

- ea: `0x180001948`
- end: `0x1800019cb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800017f0`

## callees

- `0x180001948`
- `0x180001ca4`
- `0x180001cdc`
- `0x180001e04`
- `0x180001e3c`
- `0x180001fcc`
- `0x180001ff8`
- `0x180002098`
- `0x1800020e8`

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

  if ( dword_180049450 <= 0 )
    return 0;
  --dword_180049450;
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
0x180001948  mov     [rsp+arg_0], rbx
0x18000194d  push    rdi
0x18000194e  sub     rsp, 30h
0x180001952  mov     dil, cl
0x180001955  mov     eax, cs:dword_180049450
0x18000195b  test    eax, eax
0x18000195d  jg      short loc_18000196C
0x18000195f  xor     eax, eax
0x180001961  mov     rbx, [rsp+38h+arg_0]
0x180001966  add     rsp, 30h
0x18000196a  pop     rdi
0x18000196b  retn
0x18000196c  dec     eax
0x18000196e  mov     cs:dword_180049450, eax
0x180001974  call    __scrt_acquire_startup_lock
0x180001979  mov     bl, al
0x18000197b  mov     [rsp+38h+var_18], al
0x18000197f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001986  jnz     short loc_1800019BE
0x180001988  call    __scrt_dllmain_uninitialize_c
0x18000198d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001992  call    _RTC_Terminate
0x180001997  mov     cs:__scrt_current_native_startup_state, 0
0x1800019a1  mov     cl, bl
0x1800019a3  call    __scrt_release_startup_lock
0x1800019a8  xor     edx, edx
0x1800019aa  mov     cl, dil
0x1800019ad  call    __scrt_uninitialize_crt
0x1800019b2  movzx   ebx, al
0x1800019b5  call    __scrt_dllmain_uninitialize_critical
0x1800019ba  mov     eax, ebx
0x1800019bc  jmp     short loc_180001961
0x1800019be  mov     ecx, 7
0x1800019c3  call    __scrt_fastfail
0x180035939  push    rbp
0x18003593b  sub     rsp, 20h
0x18003593f  mov     rbp, rdx
0x180035942  mov     cl, [rbp+20h]
0x180035945  call    __scrt_release_startup_lock
0x18003594a  nop
0x18003594b  add     rsp, 20h
0x18003594f  pop     rbp
0x180035950  retn
0x180035952  push    rbp
0x180035954  sub     rsp, 20h
0x180035958  mov     rbp, rdx
0x18003595b  add     rsp, 20h
0x18003595f  pop     rbp
0x180035960  jmp     __scrt_dllmain_uninitialize_critical
```
