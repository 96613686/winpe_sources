# dllmain_crt_dispatch

- ea: `0x180002890`
- end: `0x1800028e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a74`

## callees

- `0x180002890`
- `0x1800028e8`
- `0x1800029e8`
- `0x180002cb0`
- `0x180002ce0`

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
0x180002890  sub     rsp, 28h
0x180002894  test    edx, edx
0x180002896  jz      short loc_1800028D1
0x180002898  sub     edx, 1
0x18000289b  jz      short loc_1800028C5
0x18000289d  sub     edx, 1
0x1800028a0  jz      short loc_1800028B8
0x1800028a2  cmp     edx, 1
0x1800028a5  jz      short loc_1800028B1
0x1800028a7  mov     eax, 1
0x1800028ac  add     rsp, 28h
0x1800028b0  retn
0x1800028b1  call    __scrt_dllmain_crt_thread_detach
0x1800028b6  jmp     short loc_1800028BD
0x1800028b8  call    __scrt_dllmain_crt_thread_attach
0x1800028bd  movzx   eax, al
0x1800028c0  add     rsp, 28h
0x1800028c4  retn
0x1800028c5  mov     rdx, r8
0x1800028c8  add     rsp, 28h
0x1800028cc  jmp     dllmain_crt_process_attach
0x1800028d1  test    r8, r8
0x1800028d4  setnz   cl
0x1800028d7  add     rsp, 28h
0x1800028db  jmp     dllmain_crt_process_detach
```
