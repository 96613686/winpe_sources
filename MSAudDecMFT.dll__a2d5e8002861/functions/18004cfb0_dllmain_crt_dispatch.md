# dllmain_crt_dispatch

- ea: `0x18004cfb0`
- end: `0x18004d000`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18004d194`

## callees

- `0x18004cfb0`
- `0x18004d008`
- `0x18004d108`
- `0x18004d4d8`
- `0x18004d508`

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
0x18004cfb0  sub     rsp, 28h
0x18004cfb4  test    edx, edx
0x18004cfb6  jz      short loc_18004CFF1
0x18004cfb8  sub     edx, 1
0x18004cfbb  jz      short loc_18004CFE5
0x18004cfbd  sub     edx, 1
0x18004cfc0  jz      short loc_18004CFD8
0x18004cfc2  cmp     edx, 1
0x18004cfc5  jz      short loc_18004CFD1
0x18004cfc7  mov     eax, 1
0x18004cfcc  add     rsp, 28h
0x18004cfd0  retn
0x18004cfd1  call    __scrt_dllmain_crt_thread_detach
0x18004cfd6  jmp     short loc_18004CFDD
0x18004cfd8  call    __scrt_dllmain_crt_thread_attach
0x18004cfdd  movzx   eax, al
0x18004cfe0  add     rsp, 28h
0x18004cfe4  retn
0x18004cfe5  mov     rdx, r8
0x18004cfe8  add     rsp, 28h
0x18004cfec  jmp     dllmain_crt_process_attach
0x18004cff1  test    r8, r8
0x18004cff4  setnz   cl
0x18004cff7  add     rsp, 28h
0x18004cffb  jmp     dllmain_crt_process_detach
```
