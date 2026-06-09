# dllmain_crt_dispatch

- ea: `0x180001e00`
- end: `0x180001e50`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001fe4`

## callees

- `0x180001e00`
- `0x180001e58`
- `0x180001f58`
- `0x180002220`
- `0x180002250`

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
0x180001e00  sub     rsp, 28h
0x180001e04  test    edx, edx
0x180001e06  jz      short loc_180001E41
0x180001e08  sub     edx, 1
0x180001e0b  jz      short loc_180001E35
0x180001e0d  sub     edx, 1
0x180001e10  jz      short loc_180001E28
0x180001e12  cmp     edx, 1
0x180001e15  jz      short loc_180001E21
0x180001e17  mov     eax, 1
0x180001e1c  add     rsp, 28h
0x180001e20  retn
0x180001e21  call    __scrt_dllmain_crt_thread_detach
0x180001e26  jmp     short loc_180001E2D
0x180001e28  call    __scrt_dllmain_crt_thread_attach
0x180001e2d  movzx   eax, al
0x180001e30  add     rsp, 28h
0x180001e34  retn
0x180001e35  mov     rdx, r8
0x180001e38  add     rsp, 28h
0x180001e3c  jmp     dllmain_crt_process_attach
0x180001e41  test    r8, r8
0x180001e44  setnz   cl
0x180001e47  add     rsp, 28h
0x180001e4b  jmp     dllmain_crt_process_detach
```
