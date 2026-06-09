# dllmain_crt_dispatch

- ea: `0x180001fe0`
- end: `0x180002030`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800021c4`

## callees

- `0x180001fe0`
- `0x180002038`
- `0x180002138`
- `0x180002500`
- `0x180002530`

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
0x180001fe0  sub     rsp, 28h
0x180001fe4  test    edx, edx
0x180001fe6  jz      short loc_180002021
0x180001fe8  sub     edx, 1
0x180001feb  jz      short loc_180002015
0x180001fed  sub     edx, 1
0x180001ff0  jz      short loc_180002008
0x180001ff2  cmp     edx, 1
0x180001ff5  jz      short loc_180002001
0x180001ff7  mov     eax, 1
0x180001ffc  add     rsp, 28h
0x180002000  retn
0x180002001  call    __scrt_dllmain_crt_thread_detach
0x180002006  jmp     short loc_18000200D
0x180002008  call    __scrt_dllmain_crt_thread_attach
0x18000200d  movzx   eax, al
0x180002010  add     rsp, 28h
0x180002014  retn
0x180002015  mov     rdx, r8
0x180002018  add     rsp, 28h
0x18000201c  jmp     dllmain_crt_process_attach
0x180002021  test    r8, r8
0x180002024  setnz   cl
0x180002027  add     rsp, 28h
0x18000202b  jmp     dllmain_crt_process_detach
```
