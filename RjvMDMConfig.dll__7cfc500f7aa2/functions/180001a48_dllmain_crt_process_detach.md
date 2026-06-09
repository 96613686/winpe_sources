# dllmain_crt_process_detach

- ea: `0x180001a48`
- end: `0x180001acb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800018f0`

## callees

- `0x180001a48`
- `0x180001e0c`
- `0x180001e44`
- `0x180001f6c`
- `0x180001fa4`
- `0x180002134`
- `0x180002160`
- `0x180002200`
- `0x180002250`

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

  if ( dword_180029810 <= 0 )
    return 0;
  --dword_180029810;
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
0x180001a48  mov     [rsp+arg_0], rbx
0x180001a4d  push    rdi
0x180001a4e  sub     rsp, 30h
0x180001a52  mov     dil, cl
0x180001a55  mov     eax, cs:dword_180029810
0x180001a5b  test    eax, eax
0x180001a5d  jg      short loc_180001A6C
0x180001a5f  xor     eax, eax
0x180001a61  mov     rbx, [rsp+38h+arg_0]
0x180001a66  add     rsp, 30h
0x180001a6a  pop     rdi
0x180001a6b  retn
0x180001a6c  dec     eax
0x180001a6e  mov     cs:dword_180029810, eax
0x180001a74  call    __scrt_acquire_startup_lock
0x180001a79  mov     bl, al
0x180001a7b  mov     [rsp+38h+var_18], al
0x180001a7f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001a86  jnz     short loc_180001ABE
0x180001a88  call    __scrt_dllmain_uninitialize_c
0x180001a8d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001a92  call    _RTC_Terminate
0x180001a97  mov     cs:__scrt_current_native_startup_state, 0
0x180001aa1  mov     cl, bl
0x180001aa3  call    __scrt_release_startup_lock
0x180001aa8  xor     edx, edx
0x180001aaa  mov     cl, dil
0x180001aad  call    __scrt_uninitialize_crt
0x180001ab2  movzx   ebx, al
0x180001ab5  call    __scrt_dllmain_uninitialize_critical
0x180001aba  mov     eax, ebx
0x180001abc  jmp     short loc_180001A61
0x180001abe  mov     ecx, 7
0x180001ac3  call    __scrt_fastfail
0x18001d019  push    rbp
0x18001d01b  sub     rsp, 20h
0x18001d01f  mov     rbp, rdx
0x18001d022  mov     cl, [rbp+20h]
0x18001d025  call    __scrt_release_startup_lock
0x18001d02a  nop
0x18001d02b  add     rsp, 20h
0x18001d02f  pop     rbp
0x18001d030  retn
0x18001d032  push    rbp
0x18001d034  sub     rsp, 20h
0x18001d038  mov     rbp, rdx
0x18001d03b  add     rsp, 20h
0x18001d03f  pop     rbp
0x18001d040  jmp     __scrt_dllmain_uninitialize_critical
```
