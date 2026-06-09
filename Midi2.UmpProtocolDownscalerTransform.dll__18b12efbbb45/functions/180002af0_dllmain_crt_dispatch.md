# dllmain_crt_dispatch

- ea: `0x180002af0`
- end: `0x180002b40`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002cd4`

## callees

- `0x180002af0`
- `0x180002b48`
- `0x180002c48`
- `0x180003060`
- `0x180003090`

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
0x180002af0  sub     rsp, 28h
0x180002af4  test    edx, edx
0x180002af6  jz      short loc_180002B31
0x180002af8  sub     edx, 1
0x180002afb  jz      short loc_180002B25
0x180002afd  sub     edx, 1
0x180002b00  jz      short loc_180002B18
0x180002b02  cmp     edx, 1
0x180002b05  jz      short loc_180002B11
0x180002b07  mov     eax, 1
0x180002b0c  add     rsp, 28h
0x180002b10  retn
0x180002b11  call    __scrt_dllmain_crt_thread_detach
0x180002b16  jmp     short loc_180002B1D
0x180002b18  call    __scrt_dllmain_crt_thread_attach
0x180002b1d  movzx   eax, al
0x180002b20  add     rsp, 28h
0x180002b24  retn
0x180002b25  mov     rdx, r8
0x180002b28  add     rsp, 28h
0x180002b2c  jmp     dllmain_crt_process_attach
0x180002b31  test    r8, r8
0x180002b34  setnz   cl
0x180002b37  add     rsp, 28h
0x180002b3b  jmp     dllmain_crt_process_detach
```
