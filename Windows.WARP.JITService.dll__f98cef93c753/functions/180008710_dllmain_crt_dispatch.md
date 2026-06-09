# dllmain_crt_dispatch

- ea: `0x180008710`
- end: `0x180008760`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800088f4`

## callees

- `0x180008710`
- `0x180008768`
- `0x180008868`
- `0x180008b30`
- `0x180008b60`

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
0x180008710  sub     rsp, 28h
0x180008714  test    edx, edx
0x180008716  jz      short loc_180008751
0x180008718  sub     edx, 1
0x18000871b  jz      short loc_180008745
0x18000871d  sub     edx, 1
0x180008720  jz      short loc_180008738
0x180008722  cmp     edx, 1
0x180008725  jz      short loc_180008731
0x180008727  mov     eax, 1
0x18000872c  add     rsp, 28h
0x180008730  retn
0x180008731  call    __scrt_dllmain_crt_thread_detach
0x180008736  jmp     short loc_18000873D
0x180008738  call    __scrt_dllmain_crt_thread_attach
0x18000873d  movzx   eax, al
0x180008740  add     rsp, 28h
0x180008744  retn
0x180008745  mov     rdx, r8
0x180008748  add     rsp, 28h
0x18000874c  jmp     dllmain_crt_process_attach
0x180008751  test    r8, r8
0x180008754  setnz   cl
0x180008757  add     rsp, 28h
0x18000875b  jmp     dllmain_crt_process_detach
```
