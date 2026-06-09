# dllmain_crt_dispatch

- ea: `0x180004d80`
- end: `0x180004dd0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004f64`

## callees

- `0x180004d80`
- `0x180004dd8`
- `0x180004ed8`
- `0x1800052d8`
- `0x180005308`

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
0x180004d80  sub     rsp, 28h
0x180004d84  test    edx, edx
0x180004d86  jz      short loc_180004DC1
0x180004d88  sub     edx, 1
0x180004d8b  jz      short loc_180004DB5
0x180004d8d  sub     edx, 1
0x180004d90  jz      short loc_180004DA8
0x180004d92  cmp     edx, 1
0x180004d95  jz      short loc_180004DA1
0x180004d97  mov     eax, 1
0x180004d9c  add     rsp, 28h
0x180004da0  retn
0x180004da1  call    __scrt_dllmain_crt_thread_detach
0x180004da6  jmp     short loc_180004DAD
0x180004da8  call    __scrt_dllmain_crt_thread_attach
0x180004dad  movzx   eax, al
0x180004db0  add     rsp, 28h
0x180004db4  retn
0x180004db5  mov     rdx, r8
0x180004db8  add     rsp, 28h
0x180004dbc  jmp     dllmain_crt_process_attach
0x180004dc1  test    r8, r8
0x180004dc4  setnz   cl
0x180004dc7  add     rsp, 28h
0x180004dcb  jmp     dllmain_crt_process_detach
```
