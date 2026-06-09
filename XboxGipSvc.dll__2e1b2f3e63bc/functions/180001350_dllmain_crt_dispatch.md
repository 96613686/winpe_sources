# dllmain_crt_dispatch

- ea: `0x180001350`
- end: `0x1800013a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001534`

## callees

- `0x180001350`
- `0x1800013a8`
- `0x1800014a8`
- `0x18000184c`
- `0x18000187c`

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
0x180001350  sub     rsp, 28h
0x180001354  test    edx, edx
0x180001356  jz      short loc_180001391
0x180001358  sub     edx, 1
0x18000135b  jz      short loc_180001385
0x18000135d  sub     edx, 1
0x180001360  jz      short loc_180001378
0x180001362  cmp     edx, 1
0x180001365  jz      short loc_180001371
0x180001367  mov     eax, 1
0x18000136c  add     rsp, 28h
0x180001370  retn
0x180001371  call    __scrt_dllmain_crt_thread_detach
0x180001376  jmp     short loc_18000137D
0x180001378  call    __scrt_dllmain_crt_thread_attach
0x18000137d  movzx   eax, al
0x180001380  add     rsp, 28h
0x180001384  retn
0x180001385  mov     rdx, r8
0x180001388  add     rsp, 28h
0x18000138c  jmp     dllmain_crt_process_attach
0x180001391  test    r8, r8
0x180001394  setnz   cl
0x180001397  add     rsp, 28h
0x18000139b  jmp     dllmain_crt_process_detach
```
