# dllmain_crt_dispatch

- ea: `0x180004900`
- end: `0x180004950`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004ae4`

## callees

- `0x180004900`
- `0x180004958`
- `0x180004a58`
- `0x180004d44`
- `0x180004d74`

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
0x180004900  sub     rsp, 28h
0x180004904  test    edx, edx
0x180004906  jz      short loc_180004941
0x180004908  sub     edx, 1
0x18000490b  jz      short loc_180004935
0x18000490d  sub     edx, 1
0x180004910  jz      short loc_180004928
0x180004912  cmp     edx, 1
0x180004915  jz      short loc_180004921
0x180004917  mov     eax, 1
0x18000491c  add     rsp, 28h
0x180004920  retn
0x180004921  call    __scrt_dllmain_crt_thread_detach
0x180004926  jmp     short loc_18000492D
0x180004928  call    __scrt_dllmain_crt_thread_attach
0x18000492d  movzx   eax, al
0x180004930  add     rsp, 28h
0x180004934  retn
0x180004935  mov     rdx, r8
0x180004938  add     rsp, 28h
0x18000493c  jmp     dllmain_crt_process_attach
0x180004941  test    r8, r8
0x180004944  setnz   cl
0x180004947  add     rsp, 28h
0x18000494b  jmp     dllmain_crt_process_detach
```
