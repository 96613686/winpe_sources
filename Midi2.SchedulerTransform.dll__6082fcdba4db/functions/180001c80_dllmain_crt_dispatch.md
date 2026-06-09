# dllmain_crt_dispatch

- ea: `0x180001c80`
- end: `0x180001cd0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e64`

## callees

- `0x180001c80`
- `0x180001cd8`
- `0x180001dd8`
- `0x180002120`
- `0x180002150`

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
0x180001c80  sub     rsp, 28h
0x180001c84  test    edx, edx
0x180001c86  jz      short loc_180001CC1
0x180001c88  sub     edx, 1
0x180001c8b  jz      short loc_180001CB5
0x180001c8d  sub     edx, 1
0x180001c90  jz      short loc_180001CA8
0x180001c92  cmp     edx, 1
0x180001c95  jz      short loc_180001CA1
0x180001c97  mov     eax, 1
0x180001c9c  add     rsp, 28h
0x180001ca0  retn
0x180001ca1  call    __scrt_dllmain_crt_thread_detach
0x180001ca6  jmp     short loc_180001CAD
0x180001ca8  call    __scrt_dllmain_crt_thread_attach
0x180001cad  movzx   eax, al
0x180001cb0  add     rsp, 28h
0x180001cb4  retn
0x180001cb5  mov     rdx, r8
0x180001cb8  add     rsp, 28h
0x180001cbc  jmp     dllmain_crt_process_attach
0x180001cc1  test    r8, r8
0x180001cc4  setnz   cl
0x180001cc7  add     rsp, 28h
0x180001ccb  jmp     dllmain_crt_process_detach
```
