# dllmain_crt_process_detach

- ea: `0x180002670`
- end: `0x1800026f0`
- name: `dllmain_crt_process_detach`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002500`

## callees

- `0x180002670`
- `0x1800028a4`
- `0x1800029f0`
- `0x180002a28`
- `0x180002bb8`
- `0x180002be4`
- `0x180002ea0`
- `0x180002ef8`
- `0x1800030a4`

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

  if ( dword_18003CAD0 <= 0 )
    return 0;
  --dword_18003CAD0;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x1800026F0LL);
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
0x180002670  mov     [rsp+arg_0], rbx
0x180002675  push    rdi
0x180002676  sub     rsp, 30h
0x18000267a  mov     dil, cl
0x18000267d  mov     eax, cs:dword_18003CAD0
0x180002683  test    eax, eax
0x180002685  jg      short loc_180002694
0x180002687  xor     eax, eax
0x180002689  mov     rbx, [rsp+38h+arg_0]
0x18000268e  add     rsp, 30h
0x180002692  pop     rdi
0x180002693  retn
0x180002694  dec     eax
0x180002696  mov     cs:dword_18003CAD0, eax
0x18000269c  call    __scrt_acquire_startup_lock
0x1800026a1  mov     bl, al
0x1800026a3  mov     [rsp+38h+var_18], al
0x1800026a7  cmp     cs:__scrt_current_native_startup_state, 2
0x1800026ae  jnz     short loc_1800026E3
0x1800026b0  call    __scrt_dllmain_uninitialize_c
0x1800026b5  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x1800026ba  call    _RTC_Terminate
0x1800026bf  and     cs:__scrt_current_native_startup_state, 0
0x1800026c6  mov     cl, bl
0x1800026c8  call    __scrt_release_startup_lock
0x1800026cd  xor     edx, edx
0x1800026cf  mov     cl, dil
0x1800026d2  call    __scrt_uninitialize_crt
0x1800026d7  movzx   ebx, al
0x1800026da  call    __scrt_dllmain_uninitialize_critical
0x1800026df  mov     eax, ebx
0x1800026e1  jmp     short loc_180002689
0x1800026e3  mov     ecx, 7
0x1800026e8  call    __scrt_fastfail
0x1800026ed  nop
0x1800026ee  nop
0x1800026ef  int     3; Trap to Debugger
0x180028b4d  push    rbp
0x180028b4f  sub     rsp, 20h
0x180028b53  mov     rbp, rdx
0x180028b56  mov     cl, [rbp+20h]
0x180028b59  call    __scrt_release_startup_lock
0x180028b5e  nop
0x180028b5f  add     rsp, 20h
0x180028b63  pop     rbp
0x180028b64  retn
0x180028b66  push    rbp
0x180028b68  sub     rsp, 20h
0x180028b6c  mov     rbp, rdx
0x180028b6f  add     rsp, 20h
0x180028b73  pop     rbp
0x180028b74  jmp     __scrt_dllmain_uninitialize_critical
```
