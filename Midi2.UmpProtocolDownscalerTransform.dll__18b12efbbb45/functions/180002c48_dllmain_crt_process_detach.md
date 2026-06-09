# dllmain_crt_process_detach

- ea: `0x180002c48`
- end: `0x180002ccb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002af0`

## callees

- `0x180002c48`
- `0x180002fd4`
- `0x1800030fc`
- `0x180003134`
- `0x1800032c4`
- `0x1800032f0`
- `0x1800037cc`
- `0x180003814`
- `0x180003864`

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

  if ( dword_18001B770 <= 0 )
    return 0;
  --dword_18001B770;
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
0x180002c48  mov     [rsp+arg_0], rbx
0x180002c4d  push    rdi
0x180002c4e  sub     rsp, 30h
0x180002c52  mov     dil, cl
0x180002c55  mov     eax, cs:dword_18001B770
0x180002c5b  test    eax, eax
0x180002c5d  jg      short loc_180002C6C
0x180002c5f  xor     eax, eax
0x180002c61  mov     rbx, [rsp+38h+arg_0]
0x180002c66  add     rsp, 30h
0x180002c6a  pop     rdi
0x180002c6b  retn
0x180002c6c  dec     eax
0x180002c6e  mov     cs:dword_18001B770, eax
0x180002c74  call    __scrt_acquire_startup_lock
0x180002c79  mov     bl, al
0x180002c7b  mov     [rsp+38h+var_18], al
0x180002c7f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002c86  jnz     short loc_180002CBE
0x180002c88  call    __scrt_dllmain_uninitialize_c
0x180002c8d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002c92  call    _RTC_Terminate
0x180002c97  mov     cs:__scrt_current_native_startup_state, 0
0x180002ca1  mov     cl, bl
0x180002ca3  call    __scrt_release_startup_lock
0x180002ca8  xor     edx, edx
0x180002caa  mov     cl, dil
0x180002cad  call    __scrt_uninitialize_crt
0x180002cb2  movzx   ebx, al
0x180002cb5  call    __scrt_dllmain_uninitialize_critical
0x180002cba  mov     eax, ebx
0x180002cbc  jmp     short loc_180002C61
0x180002cbe  mov     ecx, 7
0x180002cc3  call    __scrt_fastfail
0x180012169  push    rbp
0x18001216b  sub     rsp, 20h
0x18001216f  mov     rbp, rdx
0x180012172  mov     cl, [rbp+20h]
0x180012175  call    __scrt_release_startup_lock
0x18001217a  nop
0x18001217b  add     rsp, 20h
0x18001217f  pop     rbp
0x180012180  retn
0x180012182  push    rbp
0x180012184  sub     rsp, 20h
0x180012188  mov     rbp, rdx
0x18001218b  add     rsp, 20h
0x18001218f  pop     rbp
0x180012190  jmp     __scrt_dllmain_uninitialize_critical
```
