# dllmain_crt_dispatch

- ea: `0x180003e00`
- end: `0x180003e50`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003fe4`

## callees

- `0x180003e00`
- `0x180003e58`
- `0x180003f58`
- `0x180004370`
- `0x1800043a0`

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
0x180003e00  sub     rsp, 28h
0x180003e04  test    edx, edx
0x180003e06  jz      short loc_180003E41
0x180003e08  sub     edx, 1
0x180003e0b  jz      short loc_180003E35
0x180003e0d  sub     edx, 1
0x180003e10  jz      short loc_180003E28
0x180003e12  cmp     edx, 1
0x180003e15  jz      short loc_180003E21
0x180003e17  mov     eax, 1
0x180003e1c  add     rsp, 28h
0x180003e20  retn
0x180003e21  call    __scrt_dllmain_crt_thread_detach
0x180003e26  jmp     short loc_180003E2D
0x180003e28  call    __scrt_dllmain_crt_thread_attach
0x180003e2d  movzx   eax, al
0x180003e30  add     rsp, 28h
0x180003e34  retn
0x180003e35  mov     rdx, r8
0x180003e38  add     rsp, 28h
0x180003e3c  jmp     dllmain_crt_process_attach
0x180003e41  test    r8, r8
0x180003e44  setnz   cl
0x180003e47  add     rsp, 28h
0x180003e4b  jmp     dllmain_crt_process_detach
```
