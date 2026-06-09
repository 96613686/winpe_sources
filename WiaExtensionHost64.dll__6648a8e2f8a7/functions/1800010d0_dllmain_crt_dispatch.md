# dllmain_crt_dispatch

- ea: `0x1800010d0`
- end: `0x180001120`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800012b4`

## callees

- `0x1800010d0`
- `0x180001128`
- `0x180001228`
- `0x180001630`
- `0x180001660`

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
0x1800010d0  sub     rsp, 28h
0x1800010d4  test    edx, edx
0x1800010d6  jz      short loc_180001111
0x1800010d8  sub     edx, 1
0x1800010db  jz      short loc_180001105
0x1800010dd  sub     edx, 1
0x1800010e0  jz      short loc_1800010F8
0x1800010e2  cmp     edx, 1
0x1800010e5  jz      short loc_1800010F1
0x1800010e7  mov     eax, 1
0x1800010ec  add     rsp, 28h
0x1800010f0  retn
0x1800010f1  call    __scrt_dllmain_crt_thread_detach
0x1800010f6  jmp     short loc_1800010FD
0x1800010f8  call    __scrt_dllmain_crt_thread_attach
0x1800010fd  movzx   eax, al
0x180001100  add     rsp, 28h
0x180001104  retn
0x180001105  mov     rdx, r8
0x180001108  add     rsp, 28h
0x18000110c  jmp     dllmain_crt_process_attach
0x180001111  test    r8, r8
0x180001114  setnz   cl
0x180001117  add     rsp, 28h
0x18000111b  jmp     dllmain_crt_process_detach
```
