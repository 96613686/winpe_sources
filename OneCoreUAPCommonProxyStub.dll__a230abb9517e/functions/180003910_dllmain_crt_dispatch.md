# dllmain_crt_dispatch

- ea: `0x180003910`
- end: `0x180003960`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003af4`

## callees

- `0x180003910`
- `0x180003968`
- `0x180003a68`
- `0x180003e38`
- `0x180003e68`

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
0x180003910  sub     rsp, 28h
0x180003914  test    edx, edx
0x180003916  jz      short loc_180003951
0x180003918  sub     edx, 1
0x18000391b  jz      short loc_180003945
0x18000391d  sub     edx, 1
0x180003920  jz      short loc_180003938
0x180003922  cmp     edx, 1
0x180003925  jz      short loc_180003931
0x180003927  mov     eax, 1
0x18000392c  add     rsp, 28h
0x180003930  retn
0x180003931  call    __scrt_dllmain_crt_thread_detach
0x180003936  jmp     short loc_18000393D
0x180003938  call    __scrt_dllmain_crt_thread_attach
0x18000393d  movzx   eax, al
0x180003940  add     rsp, 28h
0x180003944  retn
0x180003945  mov     rdx, r8
0x180003948  add     rsp, 28h
0x18000394c  jmp     dllmain_crt_process_attach
0x180003951  test    r8, r8
0x180003954  setnz   cl
0x180003957  add     rsp, 28h
0x18000395b  jmp     dllmain_crt_process_detach
```
