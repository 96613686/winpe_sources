# dllmain_crt_dispatch

- ea: `0x1800185d0`
- end: `0x180018620`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800187bc`

## callees

- `0x1800182c8`
- `0x1800182f0`
- `0x1800185d0`
- `0x180018620`
- `0x180018738`

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
    return dllmain_crt_process_attach();
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
0x1800185d0  sub     rsp, 28h
0x1800185d4  test    edx, edx
0x1800185d6  jz      short loc_180018611
0x1800185d8  sub     edx, 1
0x1800185db  jz      short loc_180018605
0x1800185dd  sub     edx, 1
0x1800185e0  jz      short loc_1800185F8
0x1800185e2  cmp     edx, 1
0x1800185e5  jz      short loc_1800185F1
0x1800185e7  mov     eax, 1
0x1800185ec  add     rsp, 28h
0x1800185f0  retn
0x1800185f1  call    __scrt_dllmain_crt_thread_detach
0x1800185f6  jmp     short loc_1800185FD
0x1800185f8  call    __scrt_dllmain_crt_thread_attach
0x1800185fd  movzx   eax, al
0x180018600  add     rsp, 28h
0x180018604  retn
0x180018605  mov     rdx, r8
0x180018608  add     rsp, 28h
0x18001860c  jmp     dllmain_crt_process_attach
0x180018611  test    r8, r8
0x180018614  setnz   cl
0x180018617  add     rsp, 28h
0x18001861b  jmp     dllmain_crt_process_detach
```
