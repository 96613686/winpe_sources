# dllmain_crt_dispatch

- ea: `0x180001e50`
- end: `0x180001ea0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002034`

## callees

- `0x180001e50`
- `0x180001ea8`
- `0x180001fa8`
- `0x1800022d8`
- `0x180002308`

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
0x180001e50  sub     rsp, 28h
0x180001e54  test    edx, edx
0x180001e56  jz      short loc_180001E91
0x180001e58  sub     edx, 1
0x180001e5b  jz      short loc_180001E85
0x180001e5d  sub     edx, 1
0x180001e60  jz      short loc_180001E78
0x180001e62  cmp     edx, 1
0x180001e65  jz      short loc_180001E71
0x180001e67  mov     eax, 1
0x180001e6c  add     rsp, 28h
0x180001e70  retn
0x180001e71  call    __scrt_dllmain_crt_thread_detach
0x180001e76  jmp     short loc_180001E7D
0x180001e78  call    __scrt_dllmain_crt_thread_attach
0x180001e7d  movzx   eax, al
0x180001e80  add     rsp, 28h
0x180001e84  retn
0x180001e85  mov     rdx, r8
0x180001e88  add     rsp, 28h
0x180001e8c  jmp     dllmain_crt_process_attach
0x180001e91  test    r8, r8
0x180001e94  setnz   cl
0x180001e97  add     rsp, 28h
0x180001e9b  jmp     dllmain_crt_process_detach
```
