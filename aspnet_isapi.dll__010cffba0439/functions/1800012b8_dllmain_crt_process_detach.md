# dllmain_crt_process_detach

- ea: `0x1800012b8`
- end: `0x18000133c`
- name: `dllmain_crt_process_detach`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180001150`
- `0x18000133c`

## callees

- `0x1800012b8`
- `0x18000161c`
- `0x180001654`
- `0x18000177c`
- `0x1800017ac`
- `0x180001930`
- `0x180001954`
- `0x180001990`
- `0x180001b18`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  BOOL v7; // ebx
  __int64 v8; // rcx
  DWORD v9; // edx
  HINSTANCE v10; // rcx
  LPVOID v11; // r8

  if ( dword_180003048 <= 0 )
    return 0;
  --dword_180003048;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state == 2 )
  {
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
  else
  {
    _scrt_fastfail(7);
    __debugbreak();
    return dllmain_dispatch(v10, v9, v11);
  }
}

```

## disassembly

```asm
0x1800012b8  mov     [rsp+arg_0], rbx
0x1800012bd  push    rdi
0x1800012be  sub     rsp, 30h
0x1800012c2  mov     dil, cl
0x1800012c5  mov     eax, cs:dword_180003048
0x1800012cb  test    eax, eax
0x1800012cd  jg      short loc_1800012DC
0x1800012cf  xor     eax, eax
0x1800012d1  mov     rbx, [rsp+38h+arg_0]
0x1800012d6  add     rsp, 30h
0x1800012da  pop     rdi
0x1800012db  retn
0x1800012dc  dec     eax
0x1800012de  mov     cs:dword_180003048, eax
0x1800012e4  call    __scrt_acquire_startup_lock
0x1800012e9  mov     bl, al
0x1800012eb  mov     [rsp+38h+var_18], al
0x1800012ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800012f6  jnz     short loc_18000132F
0x1800012f8  call    __scrt_dllmain_uninitialize_c
0x1800012fd  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x180001302  call    _RTC_Terminate
0x180001307  and     cs:__scrt_current_native_startup_state, 0
0x18000130e  mov     cl, bl
0x180001310  call    __scrt_release_startup_lock
0x180001315  xor     edx, edx
0x180001317  mov     cl, dil
0x18000131a  call    __scrt_uninitialize_crt
0x18000131f  neg     al
0x180001321  sbb     ebx, ebx
0x180001323  and     ebx, 1
0x180001326  call    __scrt_dllmain_uninitialize_critical
0x18000132b  mov     eax, ebx
0x18000132d  jmp     short loc_1800012D1
0x18000132f  mov     ecx, 7
0x180001334  call    __scrt_fastfail
0x180001339  nop
0x18000133a  nop
0x18000133b  int     3; Trap to Debugger
0x180001f3d  push    rbp
0x180001f3f  sub     rsp, 20h
0x180001f43  mov     rbp, rdx
0x180001f46  mov     cl, [rbp+20h]
0x180001f49  call    __scrt_release_startup_lock
0x180001f4e  nop
0x180001f4f  add     rsp, 20h
0x180001f53  pop     rbp
0x180001f54  retn
0x180001f56  push    rbp
0x180001f58  sub     rsp, 20h
0x180001f5c  mov     rbp, rdx
0x180001f5f  add     rsp, 20h
0x180001f63  pop     rbp
0x180001f64  jmp     __scrt_dllmain_uninitialize_critical
```
