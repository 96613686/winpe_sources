# dllmain_crt_dispatch

- ea: `0x180001900`
- end: `0x180001950`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ae4`

## callees

- `0x180001900`
- `0x180001958`
- `0x180001a58`
- `0x180001d30`
- `0x180001d60`

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
0x180001900  sub     rsp, 28h
0x180001904  test    edx, edx
0x180001906  jz      short loc_180001941
0x180001908  sub     edx, 1
0x18000190b  jz      short loc_180001935
0x18000190d  sub     edx, 1
0x180001910  jz      short loc_180001928
0x180001912  cmp     edx, 1
0x180001915  jz      short loc_180001921
0x180001917  mov     eax, 1
0x18000191c  add     rsp, 28h
0x180001920  retn
0x180001921  call    __scrt_dllmain_crt_thread_detach
0x180001926  jmp     short loc_18000192D
0x180001928  call    __scrt_dllmain_crt_thread_attach
0x18000192d  movzx   eax, al
0x180001930  add     rsp, 28h
0x180001934  retn
0x180001935  mov     rdx, r8
0x180001938  add     rsp, 28h
0x18000193c  jmp     dllmain_crt_process_attach
0x180001941  test    r8, r8
0x180001944  setnz   cl
0x180001947  add     rsp, 28h
0x18000194b  jmp     dllmain_crt_process_detach
```
