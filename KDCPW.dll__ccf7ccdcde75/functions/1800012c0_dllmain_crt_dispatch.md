# dllmain_crt_dispatch

- ea: `0x1800012c0`
- end: `0x180001310`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014a4`

## callees

- `0x1800012c0`
- `0x180001318`
- `0x180001418`
- `0x1800016e0`
- `0x180001710`

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
0x1800012c0  sub     rsp, 28h
0x1800012c4  test    edx, edx
0x1800012c6  jz      short loc_180001301
0x1800012c8  sub     edx, 1
0x1800012cb  jz      short loc_1800012F5
0x1800012cd  sub     edx, 1
0x1800012d0  jz      short loc_1800012E8
0x1800012d2  cmp     edx, 1
0x1800012d5  jz      short loc_1800012E1
0x1800012d7  mov     eax, 1
0x1800012dc  add     rsp, 28h
0x1800012e0  retn
0x1800012e1  call    __scrt_dllmain_crt_thread_detach
0x1800012e6  jmp     short loc_1800012ED
0x1800012e8  call    __scrt_dllmain_crt_thread_attach
0x1800012ed  movzx   eax, al
0x1800012f0  add     rsp, 28h
0x1800012f4  retn
0x1800012f5  mov     rdx, r8
0x1800012f8  add     rsp, 28h
0x1800012fc  jmp     dllmain_crt_process_attach
0x180001301  test    r8, r8
0x180001304  setnz   cl
0x180001307  add     rsp, 28h
0x18000130b  jmp     dllmain_crt_process_detach
```
