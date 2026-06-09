# dllmain_crt_dispatch

- ea: `0x180001cb0`
- end: `0x180001d00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e94`

## callees

- `0x180001cb0`
- `0x180001d08`
- `0x180001e08`
- `0x180002114`
- `0x180002144`

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
0x180001cb0  sub     rsp, 28h
0x180001cb4  test    edx, edx
0x180001cb6  jz      short loc_180001CF1
0x180001cb8  sub     edx, 1
0x180001cbb  jz      short loc_180001CE5
0x180001cbd  sub     edx, 1
0x180001cc0  jz      short loc_180001CD8
0x180001cc2  cmp     edx, 1
0x180001cc5  jz      short loc_180001CD1
0x180001cc7  mov     eax, 1
0x180001ccc  add     rsp, 28h
0x180001cd0  retn
0x180001cd1  call    __scrt_dllmain_crt_thread_detach
0x180001cd6  jmp     short loc_180001CDD
0x180001cd8  call    __scrt_dllmain_crt_thread_attach
0x180001cdd  movzx   eax, al
0x180001ce0  add     rsp, 28h
0x180001ce4  retn
0x180001ce5  mov     rdx, r8
0x180001ce8  add     rsp, 28h
0x180001cec  jmp     dllmain_crt_process_attach
0x180001cf1  test    r8, r8
0x180001cf4  setnz   cl
0x180001cf7  add     rsp, 28h
0x180001cfb  jmp     dllmain_crt_process_detach
```
