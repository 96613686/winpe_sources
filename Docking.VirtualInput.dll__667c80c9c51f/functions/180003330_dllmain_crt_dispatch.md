# dllmain_crt_dispatch

- ea: `0x180003330`
- end: `0x180003380`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003514`

## callees

- `0x180003330`
- `0x180003388`
- `0x180003488`
- `0x180003750`
- `0x180003780`

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
0x180003330  sub     rsp, 28h
0x180003334  test    edx, edx
0x180003336  jz      short loc_180003371
0x180003338  sub     edx, 1
0x18000333b  jz      short loc_180003365
0x18000333d  sub     edx, 1
0x180003340  jz      short loc_180003358
0x180003342  cmp     edx, 1
0x180003345  jz      short loc_180003351
0x180003347  mov     eax, 1
0x18000334c  add     rsp, 28h
0x180003350  retn
0x180003351  call    __scrt_dllmain_crt_thread_detach
0x180003356  jmp     short loc_18000335D
0x180003358  call    __scrt_dllmain_crt_thread_attach
0x18000335d  movzx   eax, al
0x180003360  add     rsp, 28h
0x180003364  retn
0x180003365  mov     rdx, r8
0x180003368  add     rsp, 28h
0x18000336c  jmp     dllmain_crt_process_attach
0x180003371  test    r8, r8
0x180003374  setnz   cl
0x180003377  add     rsp, 28h
0x18000337b  jmp     dllmain_crt_process_detach
```
