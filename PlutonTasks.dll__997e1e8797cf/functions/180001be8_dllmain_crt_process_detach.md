# dllmain_crt_process_detach

- ea: `0x180001be8`
- end: `0x180001c6b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001a90`

## callees

- `0x180001be8`
- `0x180001e68`
- `0x180001f90`
- `0x180001fc8`
- `0x180002158`
- `0x180002184`
- `0x18000231c`
- `0x180002364`
- `0x1800023b4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18000F230 <= 0 )
    return 0;
  --dword_18000F230;
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
0x180001be8  mov     [rsp+arg_0], rbx
0x180001bed  push    rdi
0x180001bee  sub     rsp, 30h
0x180001bf2  mov     dil, cl
0x180001bf5  mov     eax, cs:dword_18000F230
0x180001bfb  test    eax, eax
0x180001bfd  jg      short loc_180001C0C
0x180001bff  xor     eax, eax
0x180001c01  mov     rbx, [rsp+38h+arg_0]
0x180001c06  add     rsp, 30h
0x180001c0a  pop     rdi
0x180001c0b  retn
0x180001c0c  dec     eax
0x180001c0e  mov     cs:dword_18000F230, eax
0x180001c14  call    __scrt_acquire_startup_lock
0x180001c19  mov     bl, al
0x180001c1b  mov     [rsp+38h+var_18], al
0x180001c1f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001c26  jnz     short loc_180001C5E
0x180001c28  call    __scrt_dllmain_uninitialize_c
0x180001c2d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001c32  call    _RTC_Terminate
0x180001c37  mov     cs:__scrt_current_native_startup_state, 0
0x180001c41  mov     cl, bl
0x180001c43  call    __scrt_release_startup_lock
0x180001c48  xor     edx, edx
0x180001c4a  mov     cl, dil
0x180001c4d  call    __scrt_uninitialize_crt
0x180001c52  movzx   ebx, al
0x180001c55  call    __scrt_dllmain_uninitialize_critical
0x180001c5a  mov     eax, ebx
0x180001c5c  jmp     short loc_180001C01
0x180001c5e  mov     ecx, 7
0x180001c63  call    __scrt_fastfail
0x1800097e9  push    rbp
0x1800097eb  sub     rsp, 20h
0x1800097ef  mov     rbp, rdx
0x1800097f2  mov     cl, [rbp+20h]
0x1800097f5  call    __scrt_release_startup_lock
0x1800097fa  nop
0x1800097fb  add     rsp, 20h
0x1800097ff  pop     rbp
0x180009800  retn
0x180009802  push    rbp
0x180009804  sub     rsp, 20h
0x180009808  mov     rbp, rdx
0x18000980b  add     rsp, 20h
0x18000980f  pop     rbp
0x180009810  jmp     __scrt_dllmain_uninitialize_critical
```
