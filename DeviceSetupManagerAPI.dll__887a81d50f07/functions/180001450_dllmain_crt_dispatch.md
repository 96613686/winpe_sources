# dllmain_crt_dispatch

- ea: `0x180001450`
- end: `0x1800014a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001634`

## callees

- `0x180001450`
- `0x1800014a8`
- `0x1800015a8`
- `0x18000194c`
- `0x18000197c`

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
0x180001450  sub     rsp, 28h
0x180001454  test    edx, edx
0x180001456  jz      short loc_180001491
0x180001458  sub     edx, 1
0x18000145b  jz      short loc_180001485
0x18000145d  sub     edx, 1
0x180001460  jz      short loc_180001478
0x180001462  cmp     edx, 1
0x180001465  jz      short loc_180001471
0x180001467  mov     eax, 1
0x18000146c  add     rsp, 28h
0x180001470  retn
0x180001471  call    __scrt_dllmain_crt_thread_detach
0x180001476  jmp     short loc_18000147D
0x180001478  call    __scrt_dllmain_crt_thread_attach
0x18000147d  movzx   eax, al
0x180001480  add     rsp, 28h
0x180001484  retn
0x180001485  mov     rdx, r8
0x180001488  add     rsp, 28h
0x18000148c  jmp     dllmain_crt_process_attach
0x180001491  test    r8, r8
0x180001494  setnz   cl
0x180001497  add     rsp, 28h
0x18000149b  jmp     dllmain_crt_process_detach
```
