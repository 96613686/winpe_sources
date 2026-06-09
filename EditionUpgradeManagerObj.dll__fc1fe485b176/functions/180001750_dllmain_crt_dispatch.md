# dllmain_crt_dispatch

- ea: `0x180001750`
- end: `0x1800017a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001934`

## callees

- `0x180001750`
- `0x1800017a8`
- `0x1800018a8`
- `0x180001b70`
- `0x180001ba0`

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
0x180001750  sub     rsp, 28h
0x180001754  test    edx, edx
0x180001756  jz      short loc_180001791
0x180001758  sub     edx, 1
0x18000175b  jz      short loc_180001785
0x18000175d  sub     edx, 1
0x180001760  jz      short loc_180001778
0x180001762  cmp     edx, 1
0x180001765  jz      short loc_180001771
0x180001767  mov     eax, 1
0x18000176c  add     rsp, 28h
0x180001770  retn
0x180001771  call    __scrt_dllmain_crt_thread_detach
0x180001776  jmp     short loc_18000177D
0x180001778  call    __scrt_dllmain_crt_thread_attach
0x18000177d  movzx   eax, al
0x180001780  add     rsp, 28h
0x180001784  retn
0x180001785  mov     rdx, r8
0x180001788  add     rsp, 28h
0x18000178c  jmp     dllmain_crt_process_attach
0x180001791  test    r8, r8
0x180001794  setnz   cl
0x180001797  add     rsp, 28h
0x18000179b  jmp     dllmain_crt_process_detach
```
