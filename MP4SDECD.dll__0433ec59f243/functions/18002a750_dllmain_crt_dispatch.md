# dllmain_crt_dispatch

- ea: `0x18002a750`
- end: `0x18002a7a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a934`

## callees

- `0x18002a750`
- `0x18002a7a8`
- `0x18002a8a8`
- `0x18002ac84`
- `0x18002acb4`

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
0x18002a750  sub     rsp, 28h
0x18002a754  test    edx, edx
0x18002a756  jz      short loc_18002A791
0x18002a758  sub     edx, 1
0x18002a75b  jz      short loc_18002A785
0x18002a75d  sub     edx, 1
0x18002a760  jz      short loc_18002A778
0x18002a762  cmp     edx, 1
0x18002a765  jz      short loc_18002A771
0x18002a767  mov     eax, 1
0x18002a76c  add     rsp, 28h
0x18002a770  retn
0x18002a771  call    __scrt_dllmain_crt_thread_detach
0x18002a776  jmp     short loc_18002A77D
0x18002a778  call    __scrt_dllmain_crt_thread_attach
0x18002a77d  movzx   eax, al
0x18002a780  add     rsp, 28h
0x18002a784  retn
0x18002a785  mov     rdx, r8
0x18002a788  add     rsp, 28h
0x18002a78c  jmp     dllmain_crt_process_attach
0x18002a791  test    r8, r8
0x18002a794  setnz   cl
0x18002a797  add     rsp, 28h
0x18002a79b  jmp     dllmain_crt_process_detach
```
