# dllmain_crt_dispatch

- ea: `0x18000f1e0`
- end: `0x18000f230`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f3dc`

## callees

- `0x18000ee78`
- `0x18000eea8`
- `0x18000f1e0`
- `0x18000f238`
- `0x18000f350`

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
0x18000f1e0  sub     rsp, 28h
0x18000f1e4  test    edx, edx
0x18000f1e6  jz      short loc_18000F221
0x18000f1e8  sub     edx, 1
0x18000f1eb  jz      short loc_18000F215
0x18000f1ed  sub     edx, 1
0x18000f1f0  jz      short loc_18000F208
0x18000f1f2  cmp     edx, 1
0x18000f1f5  jz      short loc_18000F201
0x18000f1f7  mov     eax, 1
0x18000f1fc  add     rsp, 28h
0x18000f200  retn
0x18000f201  call    __scrt_dllmain_crt_thread_detach
0x18000f206  jmp     short loc_18000F20D
0x18000f208  call    __scrt_dllmain_crt_thread_attach
0x18000f20d  movzx   eax, al
0x18000f210  add     rsp, 28h
0x18000f214  retn
0x18000f215  mov     rdx, r8
0x18000f218  add     rsp, 28h
0x18000f21c  jmp     dllmain_crt_process_attach
0x18000f221  test    r8, r8
0x18000f224  setnz   cl
0x18000f227  add     rsp, 28h
0x18000f22b  jmp     dllmain_crt_process_detach
```
