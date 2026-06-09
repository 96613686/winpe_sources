# dllmain_crt_process_detach

- ea: `0x1800019e8`
- end: `0x180001a6b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001890`

## callees

- `0x1800019e8`
- `0x180001c68`
- `0x180001d90`
- `0x180001dc8`
- `0x180001f58`
- `0x180001f84`
- `0x180002130`
- `0x180002178`
- `0x1800021c8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001C270 <= 0 )
    return 0;
  --dword_18001C270;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x1800019e8  mov     [rsp+arg_0], rbx
0x1800019ed  push    rdi
0x1800019ee  sub     rsp, 30h
0x1800019f2  mov     dil, cl
0x1800019f5  mov     eax, cs:dword_18001C270
0x1800019fb  test    eax, eax
0x1800019fd  jg      short loc_180001A0C
0x1800019ff  xor     eax, eax
0x180001a01  mov     rbx, [rsp+38h+arg_0]
0x180001a06  add     rsp, 30h
0x180001a0a  pop     rdi
0x180001a0b  retn
0x180001a0c  dec     eax
0x180001a0e  mov     cs:dword_18001C270, eax
0x180001a14  call    __scrt_acquire_startup_lock
0x180001a19  mov     bl, al
0x180001a1b  mov     [rsp+38h+var_18], al
0x180001a1f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001a26  jnz     short loc_180001A5E
0x180001a28  call    __scrt_dllmain_uninitialize_c
0x180001a2d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001a32  call    _RTC_Terminate
0x180001a37  mov     cs:__scrt_current_native_startup_state, 0
0x180001a41  mov     cl, bl
0x180001a43  call    __scrt_release_startup_lock
0x180001a48  xor     edx, edx
0x180001a4a  mov     cl, dil
0x180001a4d  call    __scrt_uninitialize_crt
0x180001a52  movzx   ebx, al
0x180001a55  call    __scrt_dllmain_uninitialize_critical
0x180001a5a  mov     eax, ebx
0x180001a5c  jmp     short loc_180001A01
0x180001a5e  mov     ecx, 7
0x180001a63  call    __scrt_fastfail
0x180013b59  push    rbp
0x180013b5b  sub     rsp, 20h
0x180013b5f  mov     rbp, rdx
0x180013b62  mov     cl, [rbp+20h]
0x180013b65  call    __scrt_release_startup_lock
0x180013b6a  nop
0x180013b6b  add     rsp, 20h
0x180013b6f  pop     rbp
0x180013b70  retn
0x180013b72  push    rbp
0x180013b74  sub     rsp, 20h
0x180013b78  mov     rbp, rdx
0x180013b7b  add     rsp, 20h
0x180013b7f  pop     rbp
0x180013b80  jmp     __scrt_dllmain_uninitialize_critical
```
