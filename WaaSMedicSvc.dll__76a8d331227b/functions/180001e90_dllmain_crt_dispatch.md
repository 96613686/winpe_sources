# dllmain_crt_dispatch

- ea: `0x180001e90`
- end: `0x180001ee0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002074`

## callees

- `0x180001e90`
- `0x180001ee8`
- `0x180001fe8`
- `0x1800022b0`
- `0x1800022e0`

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
0x180001e90  sub     rsp, 28h
0x180001e94  test    edx, edx
0x180001e96  jz      short loc_180001ED1
0x180001e98  sub     edx, 1
0x180001e9b  jz      short loc_180001EC5
0x180001e9d  sub     edx, 1
0x180001ea0  jz      short loc_180001EB8
0x180001ea2  cmp     edx, 1
0x180001ea5  jz      short loc_180001EB1
0x180001ea7  mov     eax, 1
0x180001eac  add     rsp, 28h
0x180001eb0  retn
0x180001eb1  call    __scrt_dllmain_crt_thread_detach
0x180001eb6  jmp     short loc_180001EBD
0x180001eb8  call    __scrt_dllmain_crt_thread_attach
0x180001ebd  movzx   eax, al
0x180001ec0  add     rsp, 28h
0x180001ec4  retn
0x180001ec5  mov     rdx, r8
0x180001ec8  add     rsp, 28h
0x180001ecc  jmp     dllmain_crt_process_attach
0x180001ed1  test    r8, r8
0x180001ed4  setnz   cl
0x180001ed7  add     rsp, 28h
0x180001edb  jmp     dllmain_crt_process_detach
```
