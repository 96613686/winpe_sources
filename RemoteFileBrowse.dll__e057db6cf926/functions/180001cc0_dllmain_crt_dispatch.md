# dllmain_crt_dispatch

- ea: `0x180001cc0`
- end: `0x180001d10`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ea4`

## callees

- `0x180001cc0`
- `0x180001d18`
- `0x180001e18`
- `0x18000218c`
- `0x1800021bc`

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
0x180001cc0  sub     rsp, 28h
0x180001cc4  test    edx, edx
0x180001cc6  jz      short loc_180001D01
0x180001cc8  sub     edx, 1
0x180001ccb  jz      short loc_180001CF5
0x180001ccd  sub     edx, 1
0x180001cd0  jz      short loc_180001CE8
0x180001cd2  cmp     edx, 1
0x180001cd5  jz      short loc_180001CE1
0x180001cd7  mov     eax, 1
0x180001cdc  add     rsp, 28h
0x180001ce0  retn
0x180001ce1  call    __scrt_dllmain_crt_thread_detach
0x180001ce6  jmp     short loc_180001CED
0x180001ce8  call    __scrt_dllmain_crt_thread_attach
0x180001ced  movzx   eax, al
0x180001cf0  add     rsp, 28h
0x180001cf4  retn
0x180001cf5  mov     rdx, r8
0x180001cf8  add     rsp, 28h
0x180001cfc  jmp     dllmain_crt_process_attach
0x180001d01  test    r8, r8
0x180001d04  setnz   cl
0x180001d07  add     rsp, 28h
0x180001d0b  jmp     dllmain_crt_process_detach
```
