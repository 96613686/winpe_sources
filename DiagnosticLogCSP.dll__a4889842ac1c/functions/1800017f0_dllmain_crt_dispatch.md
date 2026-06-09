# dllmain_crt_dispatch

- ea: `0x1800017f0`
- end: `0x180001840`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800019d4`

## callees

- `0x1800017f0`
- `0x180001848`
- `0x180001948`
- `0x180001d68`
- `0x180001d98`

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
0x1800017f0  sub     rsp, 28h
0x1800017f4  test    edx, edx
0x1800017f6  jz      short loc_180001831
0x1800017f8  sub     edx, 1
0x1800017fb  jz      short loc_180001825
0x1800017fd  sub     edx, 1
0x180001800  jz      short loc_180001818
0x180001802  cmp     edx, 1
0x180001805  jz      short loc_180001811
0x180001807  mov     eax, 1
0x18000180c  add     rsp, 28h
0x180001810  retn
0x180001811  call    __scrt_dllmain_crt_thread_detach
0x180001816  jmp     short loc_18000181D
0x180001818  call    __scrt_dllmain_crt_thread_attach
0x18000181d  movzx   eax, al
0x180001820  add     rsp, 28h
0x180001824  retn
0x180001825  mov     rdx, r8
0x180001828  add     rsp, 28h
0x18000182c  jmp     dllmain_crt_process_attach
0x180001831  test    r8, r8
0x180001834  setnz   cl
0x180001837  add     rsp, 28h
0x18000183b  jmp     dllmain_crt_process_detach
```
