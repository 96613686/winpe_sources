# dllmain_crt_dispatch

- ea: `0x180001e60`
- end: `0x180001eb0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002044`

## callees

- `0x180001e60`
- `0x180001eb8`
- `0x180001fb8`
- `0x1800022b8`
- `0x1800022e8`

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
0x180001e60  sub     rsp, 28h
0x180001e64  test    edx, edx
0x180001e66  jz      short loc_180001EA1
0x180001e68  sub     edx, 1
0x180001e6b  jz      short loc_180001E95
0x180001e6d  sub     edx, 1
0x180001e70  jz      short loc_180001E88
0x180001e72  cmp     edx, 1
0x180001e75  jz      short loc_180001E81
0x180001e77  mov     eax, 1
0x180001e7c  add     rsp, 28h
0x180001e80  retn
0x180001e81  call    __scrt_dllmain_crt_thread_detach
0x180001e86  jmp     short loc_180001E8D
0x180001e88  call    __scrt_dllmain_crt_thread_attach
0x180001e8d  movzx   eax, al
0x180001e90  add     rsp, 28h
0x180001e94  retn
0x180001e95  mov     rdx, r8
0x180001e98  add     rsp, 28h
0x180001e9c  jmp     dllmain_crt_process_attach
0x180001ea1  test    r8, r8
0x180001ea4  setnz   cl
0x180001ea7  add     rsp, 28h
0x180001eab  jmp     dllmain_crt_process_detach
```
