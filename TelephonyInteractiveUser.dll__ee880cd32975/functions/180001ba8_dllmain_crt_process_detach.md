# dllmain_crt_process_detach

- ea: `0x180001ba8`
- end: `0x180001c2b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180001ba8`
- `0x180001e08`
- `0x180001f30`
- `0x180001f68`
- `0x1800020f8`
- `0x180002124`
- `0x180002318`
- `0x180002360`
- `0x1800023b0`

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

  if ( dword_180025170 <= 0 )
    return 0;
  --dword_180025170;
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
0x180001ba8  mov     [rsp+arg_0], rbx
0x180001bad  push    rdi
0x180001bae  sub     rsp, 30h
0x180001bb2  mov     dil, cl
0x180001bb5  mov     eax, cs:dword_180025170
0x180001bbb  test    eax, eax
0x180001bbd  jg      short loc_180001BCC
0x180001bbf  xor     eax, eax
0x180001bc1  mov     rbx, [rsp+38h+arg_0]
0x180001bc6  add     rsp, 30h
0x180001bca  pop     rdi
0x180001bcb  retn
0x180001bcc  dec     eax
0x180001bce  mov     cs:dword_180025170, eax
0x180001bd4  call    __scrt_acquire_startup_lock
0x180001bd9  mov     bl, al
0x180001bdb  mov     [rsp+38h+var_18], al
0x180001bdf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001be6  jnz     short loc_180001C1E
0x180001be8  call    __scrt_dllmain_uninitialize_c
0x180001bed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001bf2  call    _RTC_Terminate
0x180001bf7  mov     cs:__scrt_current_native_startup_state, 0
0x180001c01  mov     cl, bl
0x180001c03  call    __scrt_release_startup_lock
0x180001c08  xor     edx, edx
0x180001c0a  mov     cl, dil
0x180001c0d  call    __scrt_uninitialize_crt
0x180001c12  movzx   ebx, al
0x180001c15  call    __scrt_dllmain_uninitialize_critical
0x180001c1a  mov     eax, ebx
0x180001c1c  jmp     short loc_180001BC1
0x180001c1e  mov     ecx, 7
0x180001c23  call    __scrt_fastfail
0x1800188d9  push    rbp
0x1800188db  sub     rsp, 20h
0x1800188df  mov     rbp, rdx
0x1800188e2  mov     cl, [rbp+20h]
0x1800188e5  call    __scrt_release_startup_lock
0x1800188ea  nop
0x1800188eb  add     rsp, 20h
0x1800188ef  pop     rbp
0x1800188f0  retn
0x1800188f2  push    rbp
0x1800188f4  sub     rsp, 20h
0x1800188f8  mov     rbp, rdx
0x1800188fb  add     rsp, 20h
0x1800188ff  pop     rbp
0x180018900  jmp     __scrt_dllmain_uninitialize_critical
```
