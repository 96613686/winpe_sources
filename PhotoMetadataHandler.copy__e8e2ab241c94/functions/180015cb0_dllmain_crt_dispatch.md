# dllmain_crt_dispatch

- ea: `0x180015cb0`
- end: `0x180015d00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180015e94`

## callees

- `0x180015cb0`
- `0x180015d08`
- `0x180015e08`
- `0x180016128`
- `0x180016158`

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
0x180015cb0  sub     rsp, 28h
0x180015cb4  test    edx, edx
0x180015cb6  jz      short loc_180015CF1
0x180015cb8  sub     edx, 1
0x180015cbb  jz      short loc_180015CE5
0x180015cbd  sub     edx, 1
0x180015cc0  jz      short loc_180015CD8
0x180015cc2  cmp     edx, 1
0x180015cc5  jz      short loc_180015CD1
0x180015cc7  mov     eax, 1
0x180015ccc  add     rsp, 28h
0x180015cd0  retn
0x180015cd1  call    __scrt_dllmain_crt_thread_detach
0x180015cd6  jmp     short loc_180015CDD
0x180015cd8  call    __scrt_dllmain_crt_thread_attach
0x180015cdd  movzx   eax, al
0x180015ce0  add     rsp, 28h
0x180015ce4  retn
0x180015ce5  mov     rdx, r8
0x180015ce8  add     rsp, 28h
0x180015cec  jmp     dllmain_crt_process_attach
0x180015cf1  test    r8, r8
0x180015cf4  setnz   cl
0x180015cf7  add     rsp, 28h
0x180015cfb  jmp     dllmain_crt_process_detach
```
