# dllmain_crt_dispatch

- ea: `0x180001110`
- end: `0x180001160`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800012f4`

## callees

- `0x180001110`
- `0x180001168`
- `0x180001268`
- `0x180001638`
- `0x180001668`

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
0x180001110  sub     rsp, 28h
0x180001114  test    edx, edx
0x180001116  jz      short loc_180001151
0x180001118  sub     edx, 1
0x18000111b  jz      short loc_180001145
0x18000111d  sub     edx, 1
0x180001120  jz      short loc_180001138
0x180001122  cmp     edx, 1
0x180001125  jz      short loc_180001131
0x180001127  mov     eax, 1
0x18000112c  add     rsp, 28h
0x180001130  retn
0x180001131  call    __scrt_dllmain_crt_thread_detach
0x180001136  jmp     short loc_18000113D
0x180001138  call    __scrt_dllmain_crt_thread_attach
0x18000113d  movzx   eax, al
0x180001140  add     rsp, 28h
0x180001144  retn
0x180001145  mov     rdx, r8
0x180001148  add     rsp, 28h
0x18000114c  jmp     dllmain_crt_process_attach
0x180001151  test    r8, r8
0x180001154  setnz   cl
0x180001157  add     rsp, 28h
0x18000115b  jmp     dllmain_crt_process_detach
```
