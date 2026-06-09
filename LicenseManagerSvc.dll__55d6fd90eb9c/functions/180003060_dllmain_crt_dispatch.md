# dllmain_crt_dispatch

- ea: `0x180003060`
- end: `0x1800030b0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003244`

## callees

- `0x180003060`
- `0x1800030b8`
- `0x1800031b8`
- `0x180003740`
- `0x180003770`

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
0x180003060  sub     rsp, 28h
0x180003064  test    edx, edx
0x180003066  jz      short loc_1800030A1
0x180003068  sub     edx, 1
0x18000306b  jz      short loc_180003095
0x18000306d  sub     edx, 1
0x180003070  jz      short loc_180003088
0x180003072  cmp     edx, 1
0x180003075  jz      short loc_180003081
0x180003077  mov     eax, 1
0x18000307c  add     rsp, 28h
0x180003080  retn
0x180003081  call    __scrt_dllmain_crt_thread_detach
0x180003086  jmp     short loc_18000308D
0x180003088  call    __scrt_dllmain_crt_thread_attach
0x18000308d  movzx   eax, al
0x180003090  add     rsp, 28h
0x180003094  retn
0x180003095  mov     rdx, r8
0x180003098  add     rsp, 28h
0x18000309c  jmp     dllmain_crt_process_attach
0x1800030a1  test    r8, r8
0x1800030a4  setnz   cl
0x1800030a7  add     rsp, 28h
0x1800030ab  jmp     dllmain_crt_process_detach
```
