# dllmain_crt_dispatch

- ea: `0x18001cbe0`
- end: `0x18001cc30`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cdc4`

## callees

- `0x18001cbe0`
- `0x18001cc38`
- `0x18001cd38`
- `0x18001d044`
- `0x18001d074`

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
0x18001cbe0  sub     rsp, 28h
0x18001cbe4  test    edx, edx
0x18001cbe6  jz      short loc_18001CC21
0x18001cbe8  sub     edx, 1
0x18001cbeb  jz      short loc_18001CC15
0x18001cbed  sub     edx, 1
0x18001cbf0  jz      short loc_18001CC08
0x18001cbf2  cmp     edx, 1
0x18001cbf5  jz      short loc_18001CC01
0x18001cbf7  mov     eax, 1
0x18001cbfc  add     rsp, 28h
0x18001cc00  retn
0x18001cc01  call    __scrt_dllmain_crt_thread_detach
0x18001cc06  jmp     short loc_18001CC0D
0x18001cc08  call    __scrt_dllmain_crt_thread_attach
0x18001cc0d  movzx   eax, al
0x18001cc10  add     rsp, 28h
0x18001cc14  retn
0x18001cc15  mov     rdx, r8
0x18001cc18  add     rsp, 28h
0x18001cc1c  jmp     dllmain_crt_process_attach
0x18001cc21  test    r8, r8
0x18001cc24  setnz   cl
0x18001cc27  add     rsp, 28h
0x18001cc2b  jmp     dllmain_crt_process_detach
```
