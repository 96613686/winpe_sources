# dllmain_crt_dispatch

- ea: `0x180001b70`
- end: `0x180001bc0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d54`

## callees

- `0x180001b70`
- `0x180001bc8`
- `0x180001cc8`
- `0x180001fc8`
- `0x180001ff8`

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
0x180001b70  sub     rsp, 28h
0x180001b74  test    edx, edx
0x180001b76  jz      short loc_180001BB1
0x180001b78  sub     edx, 1
0x180001b7b  jz      short loc_180001BA5
0x180001b7d  sub     edx, 1
0x180001b80  jz      short loc_180001B98
0x180001b82  cmp     edx, 1
0x180001b85  jz      short loc_180001B91
0x180001b87  mov     eax, 1
0x180001b8c  add     rsp, 28h
0x180001b90  retn
0x180001b91  call    __scrt_dllmain_crt_thread_detach
0x180001b96  jmp     short loc_180001B9D
0x180001b98  call    __scrt_dllmain_crt_thread_attach
0x180001b9d  movzx   eax, al
0x180001ba0  add     rsp, 28h
0x180001ba4  retn
0x180001ba5  mov     rdx, r8
0x180001ba8  add     rsp, 28h
0x180001bac  jmp     dllmain_crt_process_attach
0x180001bb1  test    r8, r8
0x180001bb4  setnz   cl
0x180001bb7  add     rsp, 28h
0x180001bbb  jmp     dllmain_crt_process_detach
```
