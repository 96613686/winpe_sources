# dllmain_crt_dispatch

- ea: `0x180001360`
- end: `0x1800013b0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001544`

## callees

- `0x180001360`
- `0x1800013b8`
- `0x1800014b8`
- `0x1800018b4`
- `0x1800018e4`

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
0x180001360  sub     rsp, 28h
0x180001364  test    edx, edx
0x180001366  jz      short loc_1800013A1
0x180001368  sub     edx, 1
0x18000136b  jz      short loc_180001395
0x18000136d  sub     edx, 1
0x180001370  jz      short loc_180001388
0x180001372  cmp     edx, 1
0x180001375  jz      short loc_180001381
0x180001377  mov     eax, 1
0x18000137c  add     rsp, 28h
0x180001380  retn
0x180001381  call    __scrt_dllmain_crt_thread_detach
0x180001386  jmp     short loc_18000138D
0x180001388  call    __scrt_dllmain_crt_thread_attach
0x18000138d  movzx   eax, al
0x180001390  add     rsp, 28h
0x180001394  retn
0x180001395  mov     rdx, r8
0x180001398  add     rsp, 28h
0x18000139c  jmp     dllmain_crt_process_attach
0x1800013a1  test    r8, r8
0x1800013a4  setnz   cl
0x1800013a7  add     rsp, 28h
0x1800013ab  jmp     dllmain_crt_process_detach
```
