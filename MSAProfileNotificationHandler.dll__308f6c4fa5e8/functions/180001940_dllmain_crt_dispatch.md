# dllmain_crt_dispatch

- ea: `0x180001940`
- end: `0x180001990`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b24`

## callees

- `0x180001940`
- `0x180001998`
- `0x180001a98`
- `0x180001ebc`
- `0x180001eec`

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
0x180001940  sub     rsp, 28h
0x180001944  test    edx, edx
0x180001946  jz      short loc_180001981
0x180001948  sub     edx, 1
0x18000194b  jz      short loc_180001975
0x18000194d  sub     edx, 1
0x180001950  jz      short loc_180001968
0x180001952  cmp     edx, 1
0x180001955  jz      short loc_180001961
0x180001957  mov     eax, 1
0x18000195c  add     rsp, 28h
0x180001960  retn
0x180001961  call    __scrt_dllmain_crt_thread_detach
0x180001966  jmp     short loc_18000196D
0x180001968  call    __scrt_dllmain_crt_thread_attach
0x18000196d  movzx   eax, al
0x180001970  add     rsp, 28h
0x180001974  retn
0x180001975  mov     rdx, r8
0x180001978  add     rsp, 28h
0x18000197c  jmp     dllmain_crt_process_attach
0x180001981  test    r8, r8
0x180001984  setnz   cl
0x180001987  add     rsp, 28h
0x18000198b  jmp     dllmain_crt_process_detach
```
