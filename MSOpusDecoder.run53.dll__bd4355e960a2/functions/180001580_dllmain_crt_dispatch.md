# dllmain_crt_dispatch

- ea: `0x180001580`
- end: `0x1800015d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001764`

## callees

- `0x180001580`
- `0x1800015d8`
- `0x1800016d8`
- `0x1800019cc`
- `0x1800019fc`

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
0x180001580  sub     rsp, 28h
0x180001584  test    edx, edx
0x180001586  jz      short loc_1800015C1
0x180001588  sub     edx, 1
0x18000158b  jz      short loc_1800015B5
0x18000158d  sub     edx, 1
0x180001590  jz      short loc_1800015A8
0x180001592  cmp     edx, 1
0x180001595  jz      short loc_1800015A1
0x180001597  mov     eax, 1
0x18000159c  add     rsp, 28h
0x1800015a0  retn
0x1800015a1  call    __scrt_dllmain_crt_thread_detach
0x1800015a6  jmp     short loc_1800015AD
0x1800015a8  call    __scrt_dllmain_crt_thread_attach
0x1800015ad  movzx   eax, al
0x1800015b0  add     rsp, 28h
0x1800015b4  retn
0x1800015b5  mov     rdx, r8
0x1800015b8  add     rsp, 28h
0x1800015bc  jmp     dllmain_crt_process_attach
0x1800015c1  test    r8, r8
0x1800015c4  setnz   cl
0x1800015c7  add     rsp, 28h
0x1800015cb  jmp     dllmain_crt_process_detach
```
