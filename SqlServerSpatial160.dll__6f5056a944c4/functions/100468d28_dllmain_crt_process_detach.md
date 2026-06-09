# dllmain_crt_process_detach

- ea: `0x100468d28`
- end: `0x100468dac`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x100468bb4`
- `0x100468db4`

## callees

- `0x100468d28`
- `0x100468f30`
- `0x10046907c`
- `0x1004690b4`
- `0x100469254`
- `0x100469280`
- `0x100469598`
- `0x100469610`
- `0x1004697a8`

## pseudocode

```c
_BOOL8 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  BOOL v7; // ebx
  __int64 v8; // rcx

  if ( dword_10049A144 <= 0 )
    return 0;
  --dword_10049A144;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x100468DACLL);
  }
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0) != 0;
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x100468d28  mov     [rsp+arg_0], rbx
0x100468d2d  push    rdi
0x100468d2e  sub     rsp, 30h
0x100468d32  mov     dil, cl
0x100468d35  mov     eax, cs:dword_10049A144
0x100468d3b  test    eax, eax
0x100468d3d  jg      short loc_100468D4C
0x100468d3f  xor     eax, eax
0x100468d41  mov     rbx, [rsp+38h+arg_0]
0x100468d46  add     rsp, 30h
0x100468d4a  pop     rdi
0x100468d4b  retn
0x100468d4c  dec     eax
0x100468d4e  mov     cs:dword_10049A144, eax
0x100468d54  call    __scrt_acquire_startup_lock
0x100468d59  mov     bl, al
0x100468d5b  mov     [rsp+38h+var_18], al
0x100468d5f  cmp     cs:__scrt_current_native_startup_state, 2
0x100468d66  jnz     short loc_100468D9F
0x100468d68  call    __scrt_dllmain_uninitialize_c
0x100468d6d  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x100468d72  call    _RTC_Terminate
0x100468d77  and     cs:__scrt_current_native_startup_state, 0
0x100468d7e  mov     cl, bl
0x100468d80  call    __scrt_release_startup_lock
0x100468d85  xor     edx, edx
0x100468d87  mov     cl, dil
0x100468d8a  call    __scrt_uninitialize_crt
0x100468d8f  neg     al
0x100468d91  sbb     ebx, ebx
0x100468d93  and     ebx, 1
0x100468d96  call    __scrt_dllmain_uninitialize_critical
0x100468d9b  mov     eax, ebx
0x100468d9d  jmp     short loc_100468D41
0x100468d9f  mov     ecx, 7
0x100468da4  call    __scrt_fastfail
0x100468da9  nop
0x100468daa  nop
0x100468dab  int     3; Trap to Debugger
0x1004772b8  push    rbp
0x1004772ba  sub     rsp, 20h
0x1004772be  mov     rbp, rdx
0x1004772c1  mov     cl, [rbp+20h]
0x1004772c4  call    __scrt_release_startup_lock
0x1004772c9  nop
0x1004772ca  add     rsp, 20h
0x1004772ce  pop     rbp
0x1004772cf  retn
0x1004772d1  push    rbp
0x1004772d3  sub     rsp, 20h
0x1004772d7  mov     rbp, rdx
0x1004772da  add     rsp, 20h
0x1004772de  pop     rbp
0x1004772df  jmp     __scrt_dllmain_uninitialize_critical
```
