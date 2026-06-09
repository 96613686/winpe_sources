# dllmain_crt_dispatch

- ea: `0x1800018f0`
- end: `0x180001940`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ad4`

## callees

- `0x1800018f0`
- `0x180001948`
- `0x180001a48`
- `0x180001ed0`
- `0x180001f00`

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
0x1800018f0  sub     rsp, 28h
0x1800018f4  test    edx, edx
0x1800018f6  jz      short loc_180001931
0x1800018f8  sub     edx, 1
0x1800018fb  jz      short loc_180001925
0x1800018fd  sub     edx, 1
0x180001900  jz      short loc_180001918
0x180001902  cmp     edx, 1
0x180001905  jz      short loc_180001911
0x180001907  mov     eax, 1
0x18000190c  add     rsp, 28h
0x180001910  retn
0x180001911  call    __scrt_dllmain_crt_thread_detach
0x180001916  jmp     short loc_18000191D
0x180001918  call    __scrt_dllmain_crt_thread_attach
0x18000191d  movzx   eax, al
0x180001920  add     rsp, 28h
0x180001924  retn
0x180001925  mov     rdx, r8
0x180001928  add     rsp, 28h
0x18000192c  jmp     dllmain_crt_process_attach
0x180001931  test    r8, r8
0x180001934  setnz   cl
0x180001937  add     rsp, 28h
0x18000193b  jmp     dllmain_crt_process_detach
```
