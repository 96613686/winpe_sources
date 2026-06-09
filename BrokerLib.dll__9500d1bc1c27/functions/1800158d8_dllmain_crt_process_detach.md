# dllmain_crt_process_detach

- ea: `0x1800158d8`
- end: `0x18001595b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180015780`

## callees

- `0x1800158d8`
- `0x180015b9c`
- `0x180015cc4`
- `0x180015cfc`
- `0x180015e8c`
- `0x180015eb8`
- `0x180016340`
- `0x180016388`
- `0x1800163d8`

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

  if ( dword_180028870 <= 0 )
    return 0;
  --dword_180028870;
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
0x1800158d8  mov     [rsp+arg_0], rbx
0x1800158dd  push    rdi
0x1800158de  sub     rsp, 30h
0x1800158e2  mov     dil, cl
0x1800158e5  mov     eax, cs:dword_180028870
0x1800158eb  test    eax, eax
0x1800158ed  jg      short loc_1800158FC
0x1800158ef  xor     eax, eax
0x1800158f1  mov     rbx, [rsp+38h+arg_0]
0x1800158f6  add     rsp, 30h
0x1800158fa  pop     rdi
0x1800158fb  retn
0x1800158fc  dec     eax
0x1800158fe  mov     cs:dword_180028870, eax
0x180015904  call    __scrt_acquire_startup_lock
0x180015909  mov     bl, al
0x18001590b  mov     [rsp+38h+var_18], al
0x18001590f  cmp     cs:__scrt_current_native_startup_state, 2
0x180015916  jnz     short loc_18001594E
0x180015918  call    __scrt_dllmain_uninitialize_c
0x18001591d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180015922  call    _RTC_Terminate
0x180015927  mov     cs:__scrt_current_native_startup_state, 0
0x180015931  mov     cl, bl
0x180015933  call    __scrt_release_startup_lock
0x180015938  xor     edx, edx
0x18001593a  mov     cl, dil
0x18001593d  call    __scrt_uninitialize_crt
0x180015942  movzx   ebx, al
0x180015945  call    __scrt_dllmain_uninitialize_critical
0x18001594a  mov     eax, ebx
0x18001594c  jmp     short loc_1800158F1
0x18001594e  mov     ecx, 7
0x180015953  call    __scrt_fastfail
0x18001cbfb  push    rbp
0x18001cbfd  sub     rsp, 20h
0x18001cc01  mov     rbp, rdx
0x18001cc04  mov     cl, [rbp+20h]
0x18001cc07  call    __scrt_release_startup_lock
0x18001cc0c  nop
0x18001cc0d  add     rsp, 20h
0x18001cc11  pop     rbp
0x18001cc12  retn
0x18001cc14  push    rbp
0x18001cc16  sub     rsp, 20h
0x18001cc1a  mov     rbp, rdx
0x18001cc1d  add     rsp, 20h
0x18001cc21  pop     rbp
0x18001cc22  jmp     __scrt_dllmain_uninitialize_critical
```
