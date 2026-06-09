# dllmain_crt_dispatch

- ea: `0x1800013b0`
- end: `0x180001400`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001594`

## callees

- `0x1800013b0`
- `0x180001408`
- `0x180001508`
- `0x180001824`
- `0x180001854`

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
0x1800013b0  sub     rsp, 28h
0x1800013b4  test    edx, edx
0x1800013b6  jz      short loc_1800013F1
0x1800013b8  sub     edx, 1
0x1800013bb  jz      short loc_1800013E5
0x1800013bd  sub     edx, 1
0x1800013c0  jz      short loc_1800013D8
0x1800013c2  cmp     edx, 1
0x1800013c5  jz      short loc_1800013D1
0x1800013c7  mov     eax, 1
0x1800013cc  add     rsp, 28h
0x1800013d0  retn
0x1800013d1  call    __scrt_dllmain_crt_thread_detach
0x1800013d6  jmp     short loc_1800013DD
0x1800013d8  call    __scrt_dllmain_crt_thread_attach
0x1800013dd  movzx   eax, al
0x1800013e0  add     rsp, 28h
0x1800013e4  retn
0x1800013e5  mov     rdx, r8
0x1800013e8  add     rsp, 28h
0x1800013ec  jmp     dllmain_crt_process_attach
0x1800013f1  test    r8, r8
0x1800013f4  setnz   cl
0x1800013f7  add     rsp, 28h
0x1800013fb  jmp     dllmain_crt_process_detach
```
