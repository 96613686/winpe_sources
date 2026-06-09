# dllmain_crt_dispatch

- ea: `0x1800012b0`
- end: `0x180001300`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001494`

## callees

- `0x1800012b0`
- `0x180001308`
- `0x180001408`
- `0x180001720`
- `0x180001750`

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
0x1800012b0  sub     rsp, 28h
0x1800012b4  test    edx, edx
0x1800012b6  jz      short loc_1800012F1
0x1800012b8  sub     edx, 1
0x1800012bb  jz      short loc_1800012E5
0x1800012bd  sub     edx, 1
0x1800012c0  jz      short loc_1800012D8
0x1800012c2  cmp     edx, 1
0x1800012c5  jz      short loc_1800012D1
0x1800012c7  mov     eax, 1
0x1800012cc  add     rsp, 28h
0x1800012d0  retn
0x1800012d1  call    __scrt_dllmain_crt_thread_detach
0x1800012d6  jmp     short loc_1800012DD
0x1800012d8  call    __scrt_dllmain_crt_thread_attach
0x1800012dd  movzx   eax, al
0x1800012e0  add     rsp, 28h
0x1800012e4  retn
0x1800012e5  mov     rdx, r8
0x1800012e8  add     rsp, 28h
0x1800012ec  jmp     dllmain_crt_process_attach
0x1800012f1  test    r8, r8
0x1800012f4  setnz   cl
0x1800012f7  add     rsp, 28h
0x1800012fb  jmp     dllmain_crt_process_detach
```
