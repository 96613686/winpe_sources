# dllmain_crt_dispatch

- ea: `0x1800024a0`
- end: `0x1800024f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000268c`
- `0x1800027d0`

## callees

- `0x1800024a0`
- `0x1800024f0`
- `0x180002608`
- `0x180002ab4`
- `0x180002adc`

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
0x1800024a0  sub     rsp, 28h
0x1800024a4  test    edx, edx
0x1800024a6  jz      short loc_1800024E1
0x1800024a8  sub     edx, 1
0x1800024ab  jz      short loc_1800024D5
0x1800024ad  sub     edx, 1
0x1800024b0  jz      short loc_1800024C8
0x1800024b2  cmp     edx, 1
0x1800024b5  jz      short loc_1800024C1
0x1800024b7  mov     eax, 1
0x1800024bc  add     rsp, 28h
0x1800024c0  retn
0x1800024c1  call    __scrt_dllmain_crt_thread_detach
0x1800024c6  jmp     short loc_1800024CD
0x1800024c8  call    __scrt_dllmain_crt_thread_attach
0x1800024cd  movzx   eax, al
0x1800024d0  add     rsp, 28h
0x1800024d4  retn
0x1800024d5  mov     rdx, r8
0x1800024d8  add     rsp, 28h
0x1800024dc  jmp     dllmain_crt_process_attach
0x1800024e1  test    r8, r8
0x1800024e4  setnz   cl
0x1800024e7  add     rsp, 28h
0x1800024eb  jmp     dllmain_crt_process_detach
```
