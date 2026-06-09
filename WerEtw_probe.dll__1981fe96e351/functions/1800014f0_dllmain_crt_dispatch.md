# dllmain_crt_dispatch

- ea: `0x1800014f0`
- end: `0x180001540`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800016d4`

## callees

- `0x1800014f0`
- `0x180001548`
- `0x180001648`
- `0x180001a4c`
- `0x180001a7c`

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
0x1800014f0  sub     rsp, 28h
0x1800014f4  test    edx, edx
0x1800014f6  jz      short loc_180001531
0x1800014f8  sub     edx, 1
0x1800014fb  jz      short loc_180001525
0x1800014fd  sub     edx, 1
0x180001500  jz      short loc_180001518
0x180001502  cmp     edx, 1
0x180001505  jz      short loc_180001511
0x180001507  mov     eax, 1
0x18000150c  add     rsp, 28h
0x180001510  retn
0x180001511  call    __scrt_dllmain_crt_thread_detach
0x180001516  jmp     short loc_18000151D
0x180001518  call    __scrt_dllmain_crt_thread_attach
0x18000151d  movzx   eax, al
0x180001520  add     rsp, 28h
0x180001524  retn
0x180001525  mov     rdx, r8
0x180001528  add     rsp, 28h
0x18000152c  jmp     dllmain_crt_process_attach
0x180001531  test    r8, r8
0x180001534  setnz   cl
0x180001537  add     rsp, 28h
0x18000153b  jmp     dllmain_crt_process_detach
```
