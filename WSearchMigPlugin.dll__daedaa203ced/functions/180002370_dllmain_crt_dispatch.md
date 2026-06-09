# dllmain_crt_dispatch

- ea: `0x180002370`
- end: `0x1800023c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002554`

## callees

- `0x180002370`
- `0x1800023c8`
- `0x1800024c8`
- `0x18000287c`
- `0x1800028ac`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
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

```

## disassembly

```asm
0x180002370  sub     rsp, 28h
0x180002374  test    edx, edx
0x180002376  jz      short loc_1800023B1
0x180002378  sub     edx, 1
0x18000237b  jz      short loc_1800023A5
0x18000237d  sub     edx, 1
0x180002380  jz      short loc_180002398
0x180002382  cmp     edx, 1
0x180002385  jz      short loc_180002391
0x180002387  mov     eax, 1
0x18000238c  add     rsp, 28h
0x180002390  retn
0x180002391  call    __scrt_dllmain_crt_thread_detach
0x180002396  jmp     short loc_18000239D
0x180002398  call    __scrt_dllmain_crt_thread_attach
0x18000239d  movzx   eax, al
0x1800023a0  add     rsp, 28h
0x1800023a4  retn
0x1800023a5  mov     rdx, r8
0x1800023a8  add     rsp, 28h
0x1800023ac  jmp     dllmain_crt_process_attach
0x1800023b1  test    r8, r8
0x1800023b4  setnz   cl
0x1800023b7  add     rsp, 28h
0x1800023bb  jmp     dllmain_crt_process_detach
```
