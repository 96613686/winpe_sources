# dllmain_crt_dispatch

- ea: `0x1800012a0`
- end: `0x1800012f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001484`

## callees

- `0x1800012a0`
- `0x1800012f8`
- `0x1800013f8`
- `0x1800016c0`
- `0x1800016f0`

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
0x1800012a0  sub     rsp, 28h
0x1800012a4  test    edx, edx
0x1800012a6  jz      short loc_1800012E1
0x1800012a8  sub     edx, 1
0x1800012ab  jz      short loc_1800012D5
0x1800012ad  sub     edx, 1
0x1800012b0  jz      short loc_1800012C8
0x1800012b2  cmp     edx, 1
0x1800012b5  jz      short loc_1800012C1
0x1800012b7  mov     eax, 1
0x1800012bc  add     rsp, 28h
0x1800012c0  retn
0x1800012c1  call    __scrt_dllmain_crt_thread_detach
0x1800012c6  jmp     short loc_1800012CD
0x1800012c8  call    __scrt_dllmain_crt_thread_attach
0x1800012cd  movzx   eax, al
0x1800012d0  add     rsp, 28h
0x1800012d4  retn
0x1800012d5  mov     rdx, r8
0x1800012d8  add     rsp, 28h
0x1800012dc  jmp     dllmain_crt_process_attach
0x1800012e1  test    r8, r8
0x1800012e4  setnz   cl
0x1800012e7  add     rsp, 28h
0x1800012eb  jmp     dllmain_crt_process_detach
```
