# dllmain_crt_dispatch

- ea: `0x180001200`
- end: `0x180001250`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013e4`

## callees

- `0x180001200`
- `0x180001258`
- `0x180001358`
- `0x180001620`
- `0x180001650`

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
0x180001200  sub     rsp, 28h
0x180001204  test    edx, edx
0x180001206  jz      short loc_180001241
0x180001208  sub     edx, 1
0x18000120b  jz      short loc_180001235
0x18000120d  sub     edx, 1
0x180001210  jz      short loc_180001228
0x180001212  cmp     edx, 1
0x180001215  jz      short loc_180001221
0x180001217  mov     eax, 1
0x18000121c  add     rsp, 28h
0x180001220  retn
0x180001221  call    __scrt_dllmain_crt_thread_detach
0x180001226  jmp     short loc_18000122D
0x180001228  call    __scrt_dllmain_crt_thread_attach
0x18000122d  movzx   eax, al
0x180001230  add     rsp, 28h
0x180001234  retn
0x180001235  mov     rdx, r8
0x180001238  add     rsp, 28h
0x18000123c  jmp     dllmain_crt_process_attach
0x180001241  test    r8, r8
0x180001244  setnz   cl
0x180001247  add     rsp, 28h
0x18000124b  jmp     dllmain_crt_process_detach
```
