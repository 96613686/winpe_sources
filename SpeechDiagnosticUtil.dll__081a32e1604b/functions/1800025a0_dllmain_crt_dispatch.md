# dllmain_crt_dispatch

- ea: `0x1800025a0`
- end: `0x1800025f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002784`

## callees

- `0x1800025a0`
- `0x1800025f8`
- `0x1800026f8`
- `0x1800029c0`
- `0x1800029f0`

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
0x1800025a0  sub     rsp, 28h
0x1800025a4  test    edx, edx
0x1800025a6  jz      short loc_1800025E1
0x1800025a8  sub     edx, 1
0x1800025ab  jz      short loc_1800025D5
0x1800025ad  sub     edx, 1
0x1800025b0  jz      short loc_1800025C8
0x1800025b2  cmp     edx, 1
0x1800025b5  jz      short loc_1800025C1
0x1800025b7  mov     eax, 1
0x1800025bc  add     rsp, 28h
0x1800025c0  retn
0x1800025c1  call    __scrt_dllmain_crt_thread_detach
0x1800025c6  jmp     short loc_1800025CD
0x1800025c8  call    __scrt_dllmain_crt_thread_attach
0x1800025cd  movzx   eax, al
0x1800025d0  add     rsp, 28h
0x1800025d4  retn
0x1800025d5  mov     rdx, r8
0x1800025d8  add     rsp, 28h
0x1800025dc  jmp     dllmain_crt_process_attach
0x1800025e1  test    r8, r8
0x1800025e4  setnz   cl
0x1800025e7  add     rsp, 28h
0x1800025eb  jmp     dllmain_crt_process_detach
```
