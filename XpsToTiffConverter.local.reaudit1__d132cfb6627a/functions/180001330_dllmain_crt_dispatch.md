# dllmain_crt_dispatch

- ea: `0x180001330`
- end: `0x180001380`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001514`

## callees

- `0x180001330`
- `0x180001388`
- `0x180001488`
- `0x180001750`
- `0x180001780`

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
0x180001330  sub     rsp, 28h
0x180001334  test    edx, edx
0x180001336  jz      short loc_180001371
0x180001338  sub     edx, 1
0x18000133b  jz      short loc_180001365
0x18000133d  sub     edx, 1
0x180001340  jz      short loc_180001358
0x180001342  cmp     edx, 1
0x180001345  jz      short loc_180001351
0x180001347  mov     eax, 1
0x18000134c  add     rsp, 28h
0x180001350  retn
0x180001351  call    __scrt_dllmain_crt_thread_detach
0x180001356  jmp     short loc_18000135D
0x180001358  call    __scrt_dllmain_crt_thread_attach
0x18000135d  movzx   eax, al
0x180001360  add     rsp, 28h
0x180001364  retn
0x180001365  mov     rdx, r8
0x180001368  add     rsp, 28h
0x18000136c  jmp     dllmain_crt_process_attach
0x180001371  test    r8, r8
0x180001374  setnz   cl
0x180001377  add     rsp, 28h
0x18000137b  jmp     dllmain_crt_process_detach
```
