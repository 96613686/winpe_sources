# dllmain_crt_dispatch

- ea: `0x180003f80`
- end: `0x180003fd0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004180`

## callees

- `0x180003bec`
- `0x180003c14`
- `0x180003f80`
- `0x180003fd0`
- `0x1800040fc`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 1;
    LOBYTE(result) = _scrt_dllmain_crt_thread_detach();
  }
  else
  {
    LOBYTE(result) = _scrt_dllmain_crt_thread_attach();
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x180003f80  sub     rsp, 28h
0x180003f84  test    edx, edx
0x180003f86  jz      short loc_180003FC1
0x180003f88  sub     edx, 1
0x180003f8b  jz      short loc_180003FB5
0x180003f8d  sub     edx, 1
0x180003f90  jz      short loc_180003FA8
0x180003f92  cmp     edx, 1
0x180003f95  jz      short loc_180003FA1
0x180003f97  mov     eax, 1
0x180003f9c  add     rsp, 28h
0x180003fa0  retn
0x180003fa1  call    __scrt_dllmain_crt_thread_detach
0x180003fa6  jmp     short loc_180003FAD
0x180003fa8  call    __scrt_dllmain_crt_thread_attach
0x180003fad  movzx   eax, al
0x180003fb0  add     rsp, 28h
0x180003fb4  retn
0x180003fb5  mov     rdx, r8
0x180003fb8  add     rsp, 28h
0x180003fbc  jmp     dllmain_crt_process_attach
0x180003fc1  test    r8, r8
0x180003fc4  setnz   cl
0x180003fc7  add     rsp, 28h
0x180003fcb  jmp     dllmain_crt_process_detach
```
