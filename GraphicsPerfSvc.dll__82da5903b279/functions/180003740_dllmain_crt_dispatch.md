# dllmain_crt_dispatch

- ea: `0x180003740`
- end: `0x180003790`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003924`

## callees

- `0x180003740`
- `0x180003798`
- `0x180003898`
- `0x180003b60`
- `0x180003b90`

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
0x180003740  sub     rsp, 28h
0x180003744  test    edx, edx
0x180003746  jz      short loc_180003781
0x180003748  sub     edx, 1
0x18000374b  jz      short loc_180003775
0x18000374d  sub     edx, 1
0x180003750  jz      short loc_180003768
0x180003752  cmp     edx, 1
0x180003755  jz      short loc_180003761
0x180003757  mov     eax, 1
0x18000375c  add     rsp, 28h
0x180003760  retn
0x180003761  call    __scrt_dllmain_crt_thread_detach
0x180003766  jmp     short loc_18000376D
0x180003768  call    __scrt_dllmain_crt_thread_attach
0x18000376d  movzx   eax, al
0x180003770  add     rsp, 28h
0x180003774  retn
0x180003775  mov     rdx, r8
0x180003778  add     rsp, 28h
0x18000377c  jmp     dllmain_crt_process_attach
0x180003781  test    r8, r8
0x180003784  setnz   cl
0x180003787  add     rsp, 28h
0x18000378b  jmp     dllmain_crt_process_detach
```
