# dllmain_crt_dispatch

- ea: `0x1800031b0`
- end: `0x180003200`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003394`

## callees

- `0x1800031b0`
- `0x180003208`
- `0x180003308`
- `0x180003708`
- `0x180003738`

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
0x1800031b0  sub     rsp, 28h
0x1800031b4  test    edx, edx
0x1800031b6  jz      short loc_1800031F1
0x1800031b8  sub     edx, 1
0x1800031bb  jz      short loc_1800031E5
0x1800031bd  sub     edx, 1
0x1800031c0  jz      short loc_1800031D8
0x1800031c2  cmp     edx, 1
0x1800031c5  jz      short loc_1800031D1
0x1800031c7  mov     eax, 1
0x1800031cc  add     rsp, 28h
0x1800031d0  retn
0x1800031d1  call    __scrt_dllmain_crt_thread_detach
0x1800031d6  jmp     short loc_1800031DD
0x1800031d8  call    __scrt_dllmain_crt_thread_attach
0x1800031dd  movzx   eax, al
0x1800031e0  add     rsp, 28h
0x1800031e4  retn
0x1800031e5  mov     rdx, r8
0x1800031e8  add     rsp, 28h
0x1800031ec  jmp     dllmain_crt_process_attach
0x1800031f1  test    r8, r8
0x1800031f4  setnz   cl
0x1800031f7  add     rsp, 28h
0x1800031fb  jmp     dllmain_crt_process_detach
```
