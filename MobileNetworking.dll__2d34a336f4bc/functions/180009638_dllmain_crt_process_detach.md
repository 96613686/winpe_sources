# dllmain_crt_process_detach

- ea: `0x180009638`
- end: `0x1800096bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800094e0`

## callees

- `0x180009638`
- `0x180009944`
- `0x18000997c`
- `0x180009aa4`
- `0x180009adc`
- `0x180009c6c`
- `0x180009c98`
- `0x180009d38`
- `0x180009d88`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001B230 <= 0 )
    return 0;
  --dword_18001B230;
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
0x180009638  mov     [rsp+arg_0], rbx
0x18000963d  push    rdi
0x18000963e  sub     rsp, 30h
0x180009642  mov     dil, cl
0x180009645  mov     eax, cs:dword_18001B230
0x18000964b  test    eax, eax
0x18000964d  jg      short loc_18000965C
0x18000964f  xor     eax, eax
0x180009651  mov     rbx, [rsp+38h+arg_0]
0x180009656  add     rsp, 30h
0x18000965a  pop     rdi
0x18000965b  retn
0x18000965c  dec     eax
0x18000965e  mov     cs:dword_18001B230, eax
0x180009664  call    __scrt_acquire_startup_lock
0x180009669  mov     bl, al
0x18000966b  mov     [rsp+38h+var_18], al
0x18000966f  cmp     cs:__scrt_current_native_startup_state, 2
0x180009676  jnz     short loc_1800096AE
0x180009678  call    __scrt_dllmain_uninitialize_c
0x18000967d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180009682  call    _RTC_Terminate
0x180009687  mov     cs:__scrt_current_native_startup_state, 0
0x180009691  mov     cl, bl
0x180009693  call    __scrt_release_startup_lock
0x180009698  xor     edx, edx
0x18000969a  mov     cl, dil
0x18000969d  call    __scrt_uninitialize_crt
0x1800096a2  movzx   ebx, al
0x1800096a5  call    __scrt_dllmain_uninitialize_critical
0x1800096aa  mov     eax, ebx
0x1800096ac  jmp     short loc_180009651
0x1800096ae  mov     ecx, 7
0x1800096b3  call    __scrt_fastfail
0x1800119b2  push    rbp
0x1800119b4  sub     rsp, 20h
0x1800119b8  mov     rbp, rdx
0x1800119bb  mov     cl, [rbp+20h]
0x1800119be  call    __scrt_release_startup_lock
0x1800119c3  nop
0x1800119c4  add     rsp, 20h
0x1800119c8  pop     rbp
0x1800119c9  retn
0x1800119cb  push    rbp
0x1800119cd  sub     rsp, 20h
0x1800119d1  mov     rbp, rdx
0x1800119d4  add     rsp, 20h
0x1800119d8  pop     rbp
0x1800119d9  jmp     __scrt_dllmain_uninitialize_critical
```
