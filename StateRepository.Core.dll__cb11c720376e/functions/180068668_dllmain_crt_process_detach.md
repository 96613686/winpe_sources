# dllmain_crt_process_detach

- ea: `0x180068668`
- end: `0x1800686eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180068510`

## callees

- `0x180068668`
- `0x1800689cc`
- `0x180068a04`
- `0x180068b2c`
- `0x180068b64`
- `0x180068cf4`
- `0x180068d20`
- `0x180068d60`
- `0x180068db0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800B5A50 <= 0 )
    return 0;
  --dword_1800B5A50;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
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
0x180068668  mov     [rsp+arg_0], rbx
0x18006866d  push    rdi
0x18006866e  sub     rsp, 30h
0x180068672  mov     dil, cl
0x180068675  mov     eax, cs:dword_1800B5A50
0x18006867b  test    eax, eax
0x18006867d  jg      short loc_18006868C
0x18006867f  xor     eax, eax
0x180068681  mov     rbx, [rsp+38h+arg_0]
0x180068686  add     rsp, 30h
0x18006868a  pop     rdi
0x18006868b  retn
0x18006868c  dec     eax
0x18006868e  mov     cs:dword_1800B5A50, eax
0x180068694  call    __scrt_acquire_startup_lock
0x180068699  mov     bl, al
0x18006869b  mov     [rsp+38h+var_18], al
0x18006869f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800686a6  jnz     short loc_1800686DE
0x1800686a8  call    __scrt_dllmain_uninitialize_c
0x1800686ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800686b2  call    _RTC_Terminate
0x1800686b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800686c1  mov     cl, bl
0x1800686c3  call    __scrt_release_startup_lock
0x1800686c8  xor     edx, edx
0x1800686ca  mov     cl, dil
0x1800686cd  call    __scrt_uninitialize_crt
0x1800686d2  movzx   ebx, al
0x1800686d5  call    __scrt_dllmain_uninitialize_critical
0x1800686da  mov     eax, ebx
0x1800686dc  jmp     short loc_180068681
0x1800686de  mov     ecx, 7
0x1800686e3  call    __scrt_fastfail
0x1800999ac  push    rbp
0x1800999ae  sub     rsp, 20h
0x1800999b2  mov     rbp, rdx
0x1800999b5  mov     cl, [rbp+20h]
0x1800999b8  call    __scrt_release_startup_lock
0x1800999bd  nop
0x1800999be  add     rsp, 20h
0x1800999c2  pop     rbp
0x1800999c3  retn
0x1800999c5  push    rbp
0x1800999c7  sub     rsp, 20h
0x1800999cb  mov     rbp, rdx
0x1800999ce  add     rsp, 20h
0x1800999d2  pop     rbp
0x1800999d3  jmp     __scrt_dllmain_uninitialize_critical
```
