# dllmain_crt_dispatch

- ea: `0x180001bb0`
- end: `0x180001c00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d94`

## callees

- `0x180001bb0`
- `0x180001c08`
- `0x180001d08`
- `0x180002008`
- `0x180002038`

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
0x180001bb0  sub     rsp, 28h
0x180001bb4  test    edx, edx
0x180001bb6  jz      short loc_180001BF1
0x180001bb8  sub     edx, 1
0x180001bbb  jz      short loc_180001BE5
0x180001bbd  sub     edx, 1
0x180001bc0  jz      short loc_180001BD8
0x180001bc2  cmp     edx, 1
0x180001bc5  jz      short loc_180001BD1
0x180001bc7  mov     eax, 1
0x180001bcc  add     rsp, 28h
0x180001bd0  retn
0x180001bd1  call    __scrt_dllmain_crt_thread_detach
0x180001bd6  jmp     short loc_180001BDD
0x180001bd8  call    __scrt_dllmain_crt_thread_attach
0x180001bdd  movzx   eax, al
0x180001be0  add     rsp, 28h
0x180001be4  retn
0x180001be5  mov     rdx, r8
0x180001be8  add     rsp, 28h
0x180001bec  jmp     dllmain_crt_process_attach
0x180001bf1  test    r8, r8
0x180001bf4  setnz   cl
0x180001bf7  add     rsp, 28h
0x180001bfb  jmp     dllmain_crt_process_detach
```
