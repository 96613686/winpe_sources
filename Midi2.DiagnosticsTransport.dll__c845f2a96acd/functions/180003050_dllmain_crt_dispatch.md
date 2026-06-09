# dllmain_crt_dispatch

- ea: `0x180003050`
- end: `0x1800030a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003234`

## callees

- `0x180003050`
- `0x1800030a8`
- `0x1800031a8`
- `0x1800034f0`
- `0x180003520`

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
0x180003050  sub     rsp, 28h
0x180003054  test    edx, edx
0x180003056  jz      short loc_180003091
0x180003058  sub     edx, 1
0x18000305b  jz      short loc_180003085
0x18000305d  sub     edx, 1
0x180003060  jz      short loc_180003078
0x180003062  cmp     edx, 1
0x180003065  jz      short loc_180003071
0x180003067  mov     eax, 1
0x18000306c  add     rsp, 28h
0x180003070  retn
0x180003071  call    __scrt_dllmain_crt_thread_detach
0x180003076  jmp     short loc_18000307D
0x180003078  call    __scrt_dllmain_crt_thread_attach
0x18000307d  movzx   eax, al
0x180003080  add     rsp, 28h
0x180003084  retn
0x180003085  mov     rdx, r8
0x180003088  add     rsp, 28h
0x18000308c  jmp     dllmain_crt_process_attach
0x180003091  test    r8, r8
0x180003094  setnz   cl
0x180003097  add     rsp, 28h
0x18000309b  jmp     dllmain_crt_process_detach
```
