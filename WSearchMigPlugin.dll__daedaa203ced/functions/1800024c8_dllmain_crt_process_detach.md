# dllmain_crt_process_detach

- ea: `0x1800024c8`
- end: `0x18000254b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002370`

## callees

- `0x1800024c8`
- `0x1800027f0`
- `0x180002918`
- `0x180002950`
- `0x180002ae0`
- `0x180002b0c`
- `0x180002db8`
- `0x180002e00`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180025C10 <= 0 )
    return 0;
  --dword_180025C10;
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
0x1800024c8  mov     [rsp+arg_0], rbx
0x1800024cd  push    rdi
0x1800024ce  sub     rsp, 30h
0x1800024d2  mov     dil, cl
0x1800024d5  mov     eax, cs:dword_180025C10
0x1800024db  test    eax, eax
0x1800024dd  jg      short loc_1800024EC
0x1800024df  xor     eax, eax
0x1800024e1  mov     rbx, [rsp+38h+arg_0]
0x1800024e6  add     rsp, 30h
0x1800024ea  pop     rdi
0x1800024eb  retn
0x1800024ec  dec     eax
0x1800024ee  mov     cs:dword_180025C10, eax
0x1800024f4  call    __scrt_acquire_startup_lock
0x1800024f9  mov     bl, al
0x1800024fb  mov     [rsp+38h+var_18], al
0x1800024ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180002506  jnz     short loc_18000253E
0x180002508  call    __scrt_dllmain_uninitialize_c
0x18000250d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002512  call    _RTC_Terminate
0x180002517  mov     cs:__scrt_current_native_startup_state, 0
0x180002521  mov     cl, bl
0x180002523  call    __scrt_release_startup_lock
0x180002528  xor     edx, edx
0x18000252a  mov     cl, dil
0x18000252d  call    __scrt_uninitialize_crt
0x180002532  movzx   ebx, al
0x180002535  call    __scrt_dllmain_uninitialize_critical
0x18000253a  mov     eax, ebx
0x18000253c  jmp     short loc_1800024E1
0x18000253e  mov     ecx, 7
0x180002543  call    __scrt_fastfail
0x180016e79  push    rbp
0x180016e7b  sub     rsp, 20h
0x180016e7f  mov     rbp, rdx
0x180016e82  mov     cl, [rbp+20h]
0x180016e85  call    __scrt_release_startup_lock
0x180016e8a  nop
0x180016e8b  add     rsp, 20h
0x180016e8f  pop     rbp
0x180016e90  retn
0x180016e92  push    rbp
0x180016e94  sub     rsp, 20h
0x180016e98  mov     rbp, rdx
0x180016e9b  add     rsp, 20h
0x180016e9f  pop     rbp
0x180016ea0  jmp     __scrt_dllmain_uninitialize_critical
```
