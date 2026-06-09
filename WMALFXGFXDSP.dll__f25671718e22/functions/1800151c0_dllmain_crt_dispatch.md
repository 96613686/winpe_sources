# dllmain_crt_dispatch

- ea: `0x1800151c0`
- end: `0x180015210`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800153a4`

## callees

- `0x1800151c0`
- `0x180015218`
- `0x180015318`
- `0x1800156c4`
- `0x1800156f4`

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
0x1800151c0  sub     rsp, 28h
0x1800151c4  test    edx, edx
0x1800151c6  jz      short loc_180015201
0x1800151c8  sub     edx, 1
0x1800151cb  jz      short loc_1800151F5
0x1800151cd  sub     edx, 1
0x1800151d0  jz      short loc_1800151E8
0x1800151d2  cmp     edx, 1
0x1800151d5  jz      short loc_1800151E1
0x1800151d7  mov     eax, 1
0x1800151dc  add     rsp, 28h
0x1800151e0  retn
0x1800151e1  call    __scrt_dllmain_crt_thread_detach
0x1800151e6  jmp     short loc_1800151ED
0x1800151e8  call    __scrt_dllmain_crt_thread_attach
0x1800151ed  movzx   eax, al
0x1800151f0  add     rsp, 28h
0x1800151f4  retn
0x1800151f5  mov     rdx, r8
0x1800151f8  add     rsp, 28h
0x1800151fc  jmp     dllmain_crt_process_attach
0x180015201  test    r8, r8
0x180015204  setnz   cl
0x180015207  add     rsp, 28h
0x18001520b  jmp     dllmain_crt_process_detach
```
