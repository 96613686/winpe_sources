# dllmain_crt_dispatch

- ea: `0x1800019c0`
- end: `0x180001a10`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ba4`

## callees

- `0x1800019c0`
- `0x180001a18`
- `0x180001b18`
- `0x180001de0`
- `0x180001e10`

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
0x1800019c0  sub     rsp, 28h
0x1800019c4  test    edx, edx
0x1800019c6  jz      short loc_180001A01
0x1800019c8  sub     edx, 1
0x1800019cb  jz      short loc_1800019F5
0x1800019cd  sub     edx, 1
0x1800019d0  jz      short loc_1800019E8
0x1800019d2  cmp     edx, 1
0x1800019d5  jz      short loc_1800019E1
0x1800019d7  mov     eax, 1
0x1800019dc  add     rsp, 28h
0x1800019e0  retn
0x1800019e1  call    __scrt_dllmain_crt_thread_detach
0x1800019e6  jmp     short loc_1800019ED
0x1800019e8  call    __scrt_dllmain_crt_thread_attach
0x1800019ed  movzx   eax, al
0x1800019f0  add     rsp, 28h
0x1800019f4  retn
0x1800019f5  mov     rdx, r8
0x1800019f8  add     rsp, 28h
0x1800019fc  jmp     dllmain_crt_process_attach
0x180001a01  test    r8, r8
0x180001a04  setnz   cl
0x180001a07  add     rsp, 28h
0x180001a0b  jmp     dllmain_crt_process_detach
```
