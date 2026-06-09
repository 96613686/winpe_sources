# dllmain_crt_dispatch

- ea: `0x180001d50`
- end: `0x180001da0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001f34`

## callees

- `0x180001d50`
- `0x180001da8`
- `0x180001ea8`
- `0x180002170`
- `0x1800021a0`

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
0x180001d50  sub     rsp, 28h
0x180001d54  test    edx, edx
0x180001d56  jz      short loc_180001D91
0x180001d58  sub     edx, 1
0x180001d5b  jz      short loc_180001D85
0x180001d5d  sub     edx, 1
0x180001d60  jz      short loc_180001D78
0x180001d62  cmp     edx, 1
0x180001d65  jz      short loc_180001D71
0x180001d67  mov     eax, 1
0x180001d6c  add     rsp, 28h
0x180001d70  retn
0x180001d71  call    __scrt_dllmain_crt_thread_detach
0x180001d76  jmp     short loc_180001D7D
0x180001d78  call    __scrt_dllmain_crt_thread_attach
0x180001d7d  movzx   eax, al
0x180001d80  add     rsp, 28h
0x180001d84  retn
0x180001d85  mov     rdx, r8
0x180001d88  add     rsp, 28h
0x180001d8c  jmp     dllmain_crt_process_attach
0x180001d91  test    r8, r8
0x180001d94  setnz   cl
0x180001d97  add     rsp, 28h
0x180001d9b  jmp     dllmain_crt_process_detach
```
