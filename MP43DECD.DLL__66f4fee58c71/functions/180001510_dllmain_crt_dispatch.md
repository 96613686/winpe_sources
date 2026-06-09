# dllmain_crt_dispatch

- ea: `0x180001510`
- end: `0x180001560`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800016f4`

## callees

- `0x180001510`
- `0x180001568`
- `0x180001668`
- `0x180001a38`
- `0x180001a68`

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
0x180001510  sub     rsp, 28h
0x180001514  test    edx, edx
0x180001516  jz      short loc_180001551
0x180001518  sub     edx, 1
0x18000151b  jz      short loc_180001545
0x18000151d  sub     edx, 1
0x180001520  jz      short loc_180001538
0x180001522  cmp     edx, 1
0x180001525  jz      short loc_180001531
0x180001527  mov     eax, 1
0x18000152c  add     rsp, 28h
0x180001530  retn
0x180001531  call    __scrt_dllmain_crt_thread_detach
0x180001536  jmp     short loc_18000153D
0x180001538  call    __scrt_dllmain_crt_thread_attach
0x18000153d  movzx   eax, al
0x180001540  add     rsp, 28h
0x180001544  retn
0x180001545  mov     rdx, r8
0x180001548  add     rsp, 28h
0x18000154c  jmp     dllmain_crt_process_attach
0x180001551  test    r8, r8
0x180001554  setnz   cl
0x180001557  add     rsp, 28h
0x18000155b  jmp     dllmain_crt_process_detach
```
