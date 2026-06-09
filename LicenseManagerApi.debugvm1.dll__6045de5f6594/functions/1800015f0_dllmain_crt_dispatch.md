# dllmain_crt_dispatch

- ea: `0x1800015f0`
- end: `0x180001640`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800017d4`

## callees

- `0x1800015f0`
- `0x180001648`
- `0x180001748`
- `0x180001a10`
- `0x180001a40`

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
0x1800015f0  sub     rsp, 28h
0x1800015f4  test    edx, edx
0x1800015f6  jz      short loc_180001631
0x1800015f8  sub     edx, 1
0x1800015fb  jz      short loc_180001625
0x1800015fd  sub     edx, 1
0x180001600  jz      short loc_180001618
0x180001602  cmp     edx, 1
0x180001605  jz      short loc_180001611
0x180001607  mov     eax, 1
0x18000160c  add     rsp, 28h
0x180001610  retn
0x180001611  call    __scrt_dllmain_crt_thread_detach
0x180001616  jmp     short loc_18000161D
0x180001618  call    __scrt_dllmain_crt_thread_attach
0x18000161d  movzx   eax, al
0x180001620  add     rsp, 28h
0x180001624  retn
0x180001625  mov     rdx, r8
0x180001628  add     rsp, 28h
0x18000162c  jmp     dllmain_crt_process_attach
0x180001631  test    r8, r8
0x180001634  setnz   cl
0x180001637  add     rsp, 28h
0x18000163b  jmp     dllmain_crt_process_detach
```
