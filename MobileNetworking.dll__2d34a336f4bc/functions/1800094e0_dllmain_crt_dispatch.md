# dllmain_crt_dispatch

- ea: `0x1800094e0`
- end: `0x180009530`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800096c4`

## callees

- `0x1800094e0`
- `0x180009538`
- `0x180009638`
- `0x180009a08`
- `0x180009a38`

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
0x1800094e0  sub     rsp, 28h
0x1800094e4  test    edx, edx
0x1800094e6  jz      short loc_180009521
0x1800094e8  sub     edx, 1
0x1800094eb  jz      short loc_180009515
0x1800094ed  sub     edx, 1
0x1800094f0  jz      short loc_180009508
0x1800094f2  cmp     edx, 1
0x1800094f5  jz      short loc_180009501
0x1800094f7  mov     eax, 1
0x1800094fc  add     rsp, 28h
0x180009500  retn
0x180009501  call    __scrt_dllmain_crt_thread_detach
0x180009506  jmp     short loc_18000950D
0x180009508  call    __scrt_dllmain_crt_thread_attach
0x18000950d  movzx   eax, al
0x180009510  add     rsp, 28h
0x180009514  retn
0x180009515  mov     rdx, r8
0x180009518  add     rsp, 28h
0x18000951c  jmp     dllmain_crt_process_attach
0x180009521  test    r8, r8
0x180009524  setnz   cl
0x180009527  add     rsp, 28h
0x18000952b  jmp     dllmain_crt_process_detach
```
