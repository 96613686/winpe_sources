# dllmain_crt_dispatch

- ea: `0x1800020f0`
- end: `0x180002140`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800022d4`

## callees

- `0x1800020f0`
- `0x180002148`
- `0x180002248`
- `0x180002590`
- `0x1800025c0`

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
0x1800020f0  sub     rsp, 28h
0x1800020f4  test    edx, edx
0x1800020f6  jz      short loc_180002131
0x1800020f8  sub     edx, 1
0x1800020fb  jz      short loc_180002125
0x1800020fd  sub     edx, 1
0x180002100  jz      short loc_180002118
0x180002102  cmp     edx, 1
0x180002105  jz      short loc_180002111
0x180002107  mov     eax, 1
0x18000210c  add     rsp, 28h
0x180002110  retn
0x180002111  call    __scrt_dllmain_crt_thread_detach
0x180002116  jmp     short loc_18000211D
0x180002118  call    __scrt_dllmain_crt_thread_attach
0x18000211d  movzx   eax, al
0x180002120  add     rsp, 28h
0x180002124  retn
0x180002125  mov     rdx, r8
0x180002128  add     rsp, 28h
0x18000212c  jmp     dllmain_crt_process_attach
0x180002131  test    r8, r8
0x180002134  setnz   cl
0x180002137  add     rsp, 28h
0x18000213b  jmp     dllmain_crt_process_detach
```
