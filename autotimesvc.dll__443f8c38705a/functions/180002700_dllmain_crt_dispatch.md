# dllmain_crt_dispatch

- ea: `0x180002700`
- end: `0x180002750`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800028e4`

## callees

- `0x180002700`
- `0x180002758`
- `0x180002858`
- `0x180002c58`
- `0x180002c88`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
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
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x180002700  sub     rsp, 28h
0x180002704  test    edx, edx
0x180002706  jz      short loc_180002741
0x180002708  sub     edx, 1
0x18000270b  jz      short loc_180002735
0x18000270d  sub     edx, 1
0x180002710  jz      short loc_180002728
0x180002712  cmp     edx, 1
0x180002715  jz      short loc_180002721
0x180002717  mov     eax, 1
0x18000271c  add     rsp, 28h
0x180002720  retn
0x180002721  call    __scrt_dllmain_crt_thread_detach
0x180002726  jmp     short loc_18000272D
0x180002728  call    __scrt_dllmain_crt_thread_attach
0x18000272d  movzx   eax, al
0x180002730  add     rsp, 28h
0x180002734  retn
0x180002735  mov     rdx, r8
0x180002738  add     rsp, 28h
0x18000273c  jmp     dllmain_crt_process_attach
0x180002741  test    r8, r8
0x180002744  setnz   cl
0x180002747  add     rsp, 28h
0x18000274b  jmp     dllmain_crt_process_detach
```
