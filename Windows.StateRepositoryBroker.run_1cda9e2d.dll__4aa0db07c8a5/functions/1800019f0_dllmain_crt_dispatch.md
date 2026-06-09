# dllmain_crt_dispatch

- ea: `0x1800019f0`
- end: `0x180001a40`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001bd4`

## callees

- `0x1800019f0`
- `0x180001a48`
- `0x180001b48`
- `0x180001e34`
- `0x180001e64`

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
0x1800019f0  sub     rsp, 28h
0x1800019f4  test    edx, edx
0x1800019f6  jz      short loc_180001A31
0x1800019f8  sub     edx, 1
0x1800019fb  jz      short loc_180001A25
0x1800019fd  sub     edx, 1
0x180001a00  jz      short loc_180001A18
0x180001a02  cmp     edx, 1
0x180001a05  jz      short loc_180001A11
0x180001a07  mov     eax, 1
0x180001a0c  add     rsp, 28h
0x180001a10  retn
0x180001a11  call    __scrt_dllmain_crt_thread_detach
0x180001a16  jmp     short loc_180001A1D
0x180001a18  call    __scrt_dllmain_crt_thread_attach
0x180001a1d  movzx   eax, al
0x180001a20  add     rsp, 28h
0x180001a24  retn
0x180001a25  mov     rdx, r8
0x180001a28  add     rsp, 28h
0x180001a2c  jmp     dllmain_crt_process_attach
0x180001a31  test    r8, r8
0x180001a34  setnz   cl
0x180001a37  add     rsp, 28h
0x180001a3b  jmp     dllmain_crt_process_detach
```
