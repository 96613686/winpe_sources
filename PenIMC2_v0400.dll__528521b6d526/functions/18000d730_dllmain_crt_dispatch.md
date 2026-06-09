# dllmain_crt_dispatch

- ea: `0x18000d730`
- end: `0x18000d780`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d91c`

## callees

- `0x18000d140`
- `0x18000d168`
- `0x18000d730`
- `0x18000d780`
- `0x18000d898`

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
    return dllmain_crt_process_attach();
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
0x18000d730  sub     rsp, 28h
0x18000d734  test    edx, edx
0x18000d736  jz      short loc_18000D771
0x18000d738  sub     edx, 1
0x18000d73b  jz      short loc_18000D765
0x18000d73d  sub     edx, 1
0x18000d740  jz      short loc_18000D758
0x18000d742  cmp     edx, 1
0x18000d745  jz      short loc_18000D751
0x18000d747  mov     eax, 1
0x18000d74c  add     rsp, 28h
0x18000d750  retn
0x18000d751  call    __scrt_dllmain_crt_thread_detach
0x18000d756  jmp     short loc_18000D75D
0x18000d758  call    __scrt_dllmain_crt_thread_attach
0x18000d75d  movzx   eax, al
0x18000d760  add     rsp, 28h
0x18000d764  retn
0x18000d765  mov     rdx, r8
0x18000d768  add     rsp, 28h
0x18000d76c  jmp     dllmain_crt_process_attach
0x18000d771  test    r8, r8
0x18000d774  setnz   cl
0x18000d777  add     rsp, 28h
0x18000d77b  jmp     dllmain_crt_process_detach
```
