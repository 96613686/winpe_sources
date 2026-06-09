# dllmain_crt_dispatch

- ea: `0x180002f30`
- end: `0x180002f80`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003114`

## callees

- `0x180002f30`
- `0x180002f88`
- `0x180003088`
- `0x1800033b8`
- `0x1800033e8`

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
0x180002f30  sub     rsp, 28h
0x180002f34  test    edx, edx
0x180002f36  jz      short loc_180002F71
0x180002f38  sub     edx, 1
0x180002f3b  jz      short loc_180002F65
0x180002f3d  sub     edx, 1
0x180002f40  jz      short loc_180002F58
0x180002f42  cmp     edx, 1
0x180002f45  jz      short loc_180002F51
0x180002f47  mov     eax, 1
0x180002f4c  add     rsp, 28h
0x180002f50  retn
0x180002f51  call    __scrt_dllmain_crt_thread_detach
0x180002f56  jmp     short loc_180002F5D
0x180002f58  call    __scrt_dllmain_crt_thread_attach
0x180002f5d  movzx   eax, al
0x180002f60  add     rsp, 28h
0x180002f64  retn
0x180002f65  mov     rdx, r8
0x180002f68  add     rsp, 28h
0x180002f6c  jmp     dllmain_crt_process_attach
0x180002f71  test    r8, r8
0x180002f74  setnz   cl
0x180002f77  add     rsp, 28h
0x180002f7b  jmp     dllmain_crt_process_detach
```
