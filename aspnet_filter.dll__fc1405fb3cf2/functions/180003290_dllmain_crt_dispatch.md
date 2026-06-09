# dllmain_crt_dispatch

- ea: `0x180003290`
- end: `0x1800032e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000347c`

## callees

- `0x180003290`
- `0x1800032e0`
- `0x1800033f8`
- `0x180003af0`
- `0x180003b18`

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
    return dllmain_crt_process_attach();
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
0x180003290  sub     rsp, 28h
0x180003294  test    edx, edx
0x180003296  jz      short loc_1800032D1
0x180003298  sub     edx, 1
0x18000329b  jz      short loc_1800032C5
0x18000329d  sub     edx, 1
0x1800032a0  jz      short loc_1800032B8
0x1800032a2  cmp     edx, 1
0x1800032a5  jz      short loc_1800032B1
0x1800032a7  mov     eax, 1
0x1800032ac  add     rsp, 28h
0x1800032b0  retn
0x1800032b1  call    __scrt_dllmain_crt_thread_detach
0x1800032b6  jmp     short loc_1800032BD
0x1800032b8  call    __scrt_dllmain_crt_thread_attach
0x1800032bd  movzx   eax, al
0x1800032c0  add     rsp, 28h
0x1800032c4  retn
0x1800032c5  mov     rdx, r8
0x1800032c8  add     rsp, 28h
0x1800032cc  jmp     dllmain_crt_process_attach
0x1800032d1  test    r8, r8
0x1800032d4  setnz   cl
0x1800032d7  add     rsp, 28h
0x1800032db  jmp     dllmain_crt_process_detach
```
