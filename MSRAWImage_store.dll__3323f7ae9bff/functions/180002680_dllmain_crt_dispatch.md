# dllmain_crt_dispatch

- ea: `0x180002680`
- end: `0x1800026d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000287c`

## callees

- `0x180002680`
- `0x1800026d8`
- `0x1800027f0`
- `0x180002ae0`
- `0x180002b10`

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
0x180002680  sub     rsp, 28h
0x180002684  test    edx, edx
0x180002686  jz      short loc_1800026C1
0x180002688  sub     edx, 1
0x18000268b  jz      short loc_1800026B5
0x18000268d  sub     edx, 1
0x180002690  jz      short loc_1800026A8
0x180002692  cmp     edx, 1
0x180002695  jz      short loc_1800026A1
0x180002697  mov     eax, 1
0x18000269c  add     rsp, 28h
0x1800026a0  retn
0x1800026a1  call    __scrt_dllmain_crt_thread_detach
0x1800026a6  jmp     short loc_1800026AD
0x1800026a8  call    __scrt_dllmain_crt_thread_attach
0x1800026ad  movzx   eax, al
0x1800026b0  add     rsp, 28h
0x1800026b4  retn
0x1800026b5  mov     rdx, r8
0x1800026b8  add     rsp, 28h
0x1800026bc  jmp     dllmain_crt_process_attach
0x1800026c1  test    r8, r8
0x1800026c4  setnz   cl
0x1800026c7  add     rsp, 28h
0x1800026cb  jmp     dllmain_crt_process_detach
```
