# dllmain_crt_dispatch

- ea: `0x180001280`
- end: `0x1800012d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001464`

## callees

- `0x180001280`
- `0x1800012d8`
- `0x1800013d8`
- `0x180001770`
- `0x1800017a0`

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
0x180001280  sub     rsp, 28h
0x180001284  test    edx, edx
0x180001286  jz      short loc_1800012C1
0x180001288  sub     edx, 1
0x18000128b  jz      short loc_1800012B5
0x18000128d  sub     edx, 1
0x180001290  jz      short loc_1800012A8
0x180001292  cmp     edx, 1
0x180001295  jz      short loc_1800012A1
0x180001297  mov     eax, 1
0x18000129c  add     rsp, 28h
0x1800012a0  retn
0x1800012a1  call    __scrt_dllmain_crt_thread_detach
0x1800012a6  jmp     short loc_1800012AD
0x1800012a8  call    __scrt_dllmain_crt_thread_attach
0x1800012ad  movzx   eax, al
0x1800012b0  add     rsp, 28h
0x1800012b4  retn
0x1800012b5  mov     rdx, r8
0x1800012b8  add     rsp, 28h
0x1800012bc  jmp     dllmain_crt_process_attach
0x1800012c1  test    r8, r8
0x1800012c4  setnz   cl
0x1800012c7  add     rsp, 28h
0x1800012cb  jmp     dllmain_crt_process_detach
```
