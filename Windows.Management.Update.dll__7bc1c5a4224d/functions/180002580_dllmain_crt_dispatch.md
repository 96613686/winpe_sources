# dllmain_crt_dispatch

- ea: `0x180002580`
- end: `0x1800025d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002764`

## callees

- `0x180002580`
- `0x1800025d8`
- `0x1800026d8`
- `0x1800029a0`
- `0x1800029d0`

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
0x180002580  sub     rsp, 28h
0x180002584  test    edx, edx
0x180002586  jz      short loc_1800025C1
0x180002588  sub     edx, 1
0x18000258b  jz      short loc_1800025B5
0x18000258d  sub     edx, 1
0x180002590  jz      short loc_1800025A8
0x180002592  cmp     edx, 1
0x180002595  jz      short loc_1800025A1
0x180002597  mov     eax, 1
0x18000259c  add     rsp, 28h
0x1800025a0  retn
0x1800025a1  call    __scrt_dllmain_crt_thread_detach
0x1800025a6  jmp     short loc_1800025AD
0x1800025a8  call    __scrt_dllmain_crt_thread_attach
0x1800025ad  movzx   eax, al
0x1800025b0  add     rsp, 28h
0x1800025b4  retn
0x1800025b5  mov     rdx, r8
0x1800025b8  add     rsp, 28h
0x1800025bc  jmp     dllmain_crt_process_attach
0x1800025c1  test    r8, r8
0x1800025c4  setnz   cl
0x1800025c7  add     rsp, 28h
0x1800025cb  jmp     dllmain_crt_process_detach
```
