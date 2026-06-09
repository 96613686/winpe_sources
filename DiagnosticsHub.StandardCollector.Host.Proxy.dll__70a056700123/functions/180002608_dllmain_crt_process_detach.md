# dllmain_crt_process_detach

- ea: `0x180002608`
- end: `0x18000268b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800024a0`
- `0x18000268c`

## callees

- `0x180002608`
- `0x180002950`
- `0x180002a2c`
- `0x180002b54`
- `0x180002b84`
- `0x180002cf8`
- `0x180002d1c`
- `0x180002dd0`
- `0x180003070`

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

  if ( dword_180077D88 <= 0 )
    return 0;
  --dword_180077D88;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x18000268BLL);
  }
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
0x180002608  mov     [rsp+arg_0], rbx
0x18000260d  push    rdi
0x18000260e  sub     rsp, 30h
0x180002612  mov     dil, cl
0x180002615  mov     eax, cs:dword_180077D88
0x18000261b  test    eax, eax
0x18000261d  jg      short loc_18000262C
0x18000261f  xor     eax, eax
0x180002621  mov     rbx, [rsp+38h+arg_0]
0x180002626  add     rsp, 30h
0x18000262a  pop     rdi
0x18000262b  retn
0x18000262c  dec     eax
0x18000262e  mov     cs:dword_180077D88, eax
0x180002634  call    __scrt_acquire_startup_lock
0x180002639  mov     bl, al
0x18000263b  mov     [rsp+38h+var_18], al
0x18000263f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002646  jnz     short loc_18000267E
0x180002648  call    __scrt_dllmain_uninitialize_c
0x18000264d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002652  call    _RTC_Terminate
0x180002657  mov     cs:__scrt_current_native_startup_state, 0
0x180002661  mov     cl, bl
0x180002663  call    __scrt_release_startup_lock
0x180002668  xor     edx, edx
0x18000266a  mov     cl, dil
0x18000266d  call    __scrt_uninitialize_crt
0x180002672  movzx   ebx, al
0x180002675  call    __scrt_dllmain_uninitialize_critical
0x18000267a  mov     eax, ebx
0x18000267c  jmp     short loc_180002621
0x18000267e  mov     ecx, 7
0x180002683  call    __scrt_fastfail
0x180002688  nop
0x180002689  nop
0x18000268a  int     3; Trap to Debugger
0x180060ea7  push    rbp
0x180060ea9  sub     rsp, 20h
0x180060ead  mov     rbp, rdx
0x180060eb0  mov     cl, [rbp+20h]
0x180060eb3  call    __scrt_release_startup_lock
0x180060eb8  nop
0x180060eb9  add     rsp, 20h
0x180060ebd  pop     rbp
0x180060ebe  retn
0x180060ec0  push    rbp
0x180060ec2  sub     rsp, 20h
0x180060ec6  mov     rbp, rdx
0x180060ec9  add     rsp, 20h
0x180060ecd  pop     rbp
0x180060ece  jmp     __scrt_dllmain_uninitialize_critical
```
