# dllmain_crt_dispatch

- ea: `0x180001ae0`
- end: `0x180001b30`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001cc4`

## callees

- `0x180001ae0`
- `0x180001b38`
- `0x180001c38`
- `0x180001f80`
- `0x180001fb0`

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
0x180001ae0  sub     rsp, 28h
0x180001ae4  test    edx, edx
0x180001ae6  jz      short loc_180001B21
0x180001ae8  sub     edx, 1
0x180001aeb  jz      short loc_180001B15
0x180001aed  sub     edx, 1
0x180001af0  jz      short loc_180001B08
0x180001af2  cmp     edx, 1
0x180001af5  jz      short loc_180001B01
0x180001af7  mov     eax, 1
0x180001afc  add     rsp, 28h
0x180001b00  retn
0x180001b01  call    __scrt_dllmain_crt_thread_detach
0x180001b06  jmp     short loc_180001B0D
0x180001b08  call    __scrt_dllmain_crt_thread_attach
0x180001b0d  movzx   eax, al
0x180001b10  add     rsp, 28h
0x180001b14  retn
0x180001b15  mov     rdx, r8
0x180001b18  add     rsp, 28h
0x180001b1c  jmp     dllmain_crt_process_attach
0x180001b21  test    r8, r8
0x180001b24  setnz   cl
0x180001b27  add     rsp, 28h
0x180001b2b  jmp     dllmain_crt_process_detach
```
