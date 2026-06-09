# dllmain_crt_dispatch

- ea: `0x180001b60`
- end: `0x180001bb0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d44`

## callees

- `0x180001b60`
- `0x180001bb8`
- `0x180001cb8`
- `0x180001f80`
- `0x180001fb0`

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
0x180001b60  sub     rsp, 28h
0x180001b64  test    edx, edx
0x180001b66  jz      short loc_180001BA1
0x180001b68  sub     edx, 1
0x180001b6b  jz      short loc_180001B95
0x180001b6d  sub     edx, 1
0x180001b70  jz      short loc_180001B88
0x180001b72  cmp     edx, 1
0x180001b75  jz      short loc_180001B81
0x180001b77  mov     eax, 1
0x180001b7c  add     rsp, 28h
0x180001b80  retn
0x180001b81  call    __scrt_dllmain_crt_thread_detach
0x180001b86  jmp     short loc_180001B8D
0x180001b88  call    __scrt_dllmain_crt_thread_attach
0x180001b8d  movzx   eax, al
0x180001b90  add     rsp, 28h
0x180001b94  retn
0x180001b95  mov     rdx, r8
0x180001b98  add     rsp, 28h
0x180001b9c  jmp     dllmain_crt_process_attach
0x180001ba1  test    r8, r8
0x180001ba4  setnz   cl
0x180001ba7  add     rsp, 28h
0x180001bab  jmp     dllmain_crt_process_detach
```
