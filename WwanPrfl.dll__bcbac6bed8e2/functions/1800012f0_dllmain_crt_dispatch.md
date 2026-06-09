# dllmain_crt_dispatch

- ea: `0x1800012f0`
- end: `0x180001340`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014d4`

## callees

- `0x1800012f0`
- `0x180001348`
- `0x180001448`
- `0x180001758`
- `0x180001788`

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
0x1800012f0  sub     rsp, 28h
0x1800012f4  test    edx, edx
0x1800012f6  jz      short loc_180001331
0x1800012f8  sub     edx, 1
0x1800012fb  jz      short loc_180001325
0x1800012fd  sub     edx, 1
0x180001300  jz      short loc_180001318
0x180001302  cmp     edx, 1
0x180001305  jz      short loc_180001311
0x180001307  mov     eax, 1
0x18000130c  add     rsp, 28h
0x180001310  retn
0x180001311  call    __scrt_dllmain_crt_thread_detach
0x180001316  jmp     short loc_18000131D
0x180001318  call    __scrt_dllmain_crt_thread_attach
0x18000131d  movzx   eax, al
0x180001320  add     rsp, 28h
0x180001324  retn
0x180001325  mov     rdx, r8
0x180001328  add     rsp, 28h
0x18000132c  jmp     dllmain_crt_process_attach
0x180001331  test    r8, r8
0x180001334  setnz   cl
0x180001337  add     rsp, 28h
0x18000133b  jmp     dllmain_crt_process_detach
```
