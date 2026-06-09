# dllmain_crt_dispatch

- ea: `0x180002720`
- end: `0x180002770`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002904`

## callees

- `0x180002720`
- `0x180002778`
- `0x180002878`
- `0x180002b84`
- `0x180002bb4`

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
0x180002720  sub     rsp, 28h
0x180002724  test    edx, edx
0x180002726  jz      short loc_180002761
0x180002728  sub     edx, 1
0x18000272b  jz      short loc_180002755
0x18000272d  sub     edx, 1
0x180002730  jz      short loc_180002748
0x180002732  cmp     edx, 1
0x180002735  jz      short loc_180002741
0x180002737  mov     eax, 1
0x18000273c  add     rsp, 28h
0x180002740  retn
0x180002741  call    __scrt_dllmain_crt_thread_detach
0x180002746  jmp     short loc_18000274D
0x180002748  call    __scrt_dllmain_crt_thread_attach
0x18000274d  movzx   eax, al
0x180002750  add     rsp, 28h
0x180002754  retn
0x180002755  mov     rdx, r8
0x180002758  add     rsp, 28h
0x18000275c  jmp     dllmain_crt_process_attach
0x180002761  test    r8, r8
0x180002764  setnz   cl
0x180002767  add     rsp, 28h
0x18000276b  jmp     dllmain_crt_process_detach
```
