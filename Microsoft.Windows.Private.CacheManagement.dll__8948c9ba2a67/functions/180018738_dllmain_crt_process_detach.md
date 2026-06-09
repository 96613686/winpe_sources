# dllmain_crt_process_detach

- ea: `0x180018738`
- end: `0x1800187bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800185d0`
- `0x1800187bc`

## callees

- `0x180018240`
- `0x180018368`
- `0x180018398`
- `0x18001850c`
- `0x180018530`
- `0x180018738`
- `0x180018f00`
- `0x18001910c`
- `0x180019180`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18002DEC8 <= 0 )
    return 0;
  --dword_18002DEC8;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1800187BBLL);
  }
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
0x180018738  mov     [rsp+arg_0], rbx
0x18001873d  push    rdi
0x18001873e  sub     rsp, 30h
0x180018742  mov     dil, cl
0x180018745  mov     eax, cs:dword_18002DEC8
0x18001874b  test    eax, eax
0x18001874d  jg      short loc_18001875C
0x18001874f  xor     eax, eax
0x180018751  mov     rbx, [rsp+38h+arg_0]
0x180018756  add     rsp, 30h
0x18001875a  pop     rdi
0x18001875b  retn
0x18001875c  dec     eax
0x18001875e  mov     cs:dword_18002DEC8, eax
0x180018764  call    __scrt_acquire_startup_lock
0x180018769  mov     bl, al
0x18001876b  mov     [rsp+38h+var_18], al
0x18001876f  cmp     cs:__scrt_current_native_startup_state, 2
0x180018776  jnz     short loc_1800187AE
0x180018778  call    __scrt_dllmain_uninitialize_c
0x18001877d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180018782  call    _RTC_Terminate
0x180018787  mov     cs:__scrt_current_native_startup_state, 0
0x180018791  mov     cl, bl
0x180018793  call    __scrt_release_startup_lock
0x180018798  xor     edx, edx
0x18001879a  mov     cl, dil
0x18001879d  call    __scrt_uninitialize_crt
0x1800187a2  movzx   ebx, al
0x1800187a5  call    __scrt_dllmain_uninitialize_critical
0x1800187aa  mov     eax, ebx
0x1800187ac  jmp     short loc_180018751
0x1800187ae  mov     ecx, 7
0x1800187b3  call    __scrt_fastfail
0x1800187b8  nop
0x1800187b9  nop
0x1800187ba  int     3; Trap to Debugger
0x18001f55f  push    rbp
0x18001f561  sub     rsp, 20h
0x18001f565  mov     rbp, rdx
0x18001f568  mov     cl, [rbp+20h]
0x18001f56b  call    __scrt_release_startup_lock
0x18001f570  nop
0x18001f571  add     rsp, 20h
0x18001f575  pop     rbp
0x18001f576  retn
0x18001f578  push    rbp
0x18001f57a  sub     rsp, 20h
0x18001f57e  mov     rbp, rdx
0x18001f581  add     rsp, 20h
0x18001f585  pop     rbp
0x18001f586  jmp     __scrt_dllmain_uninitialize_critical
```
