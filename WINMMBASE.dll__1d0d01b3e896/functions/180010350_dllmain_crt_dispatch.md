# dllmain_crt_dispatch

- ea: `0x180010350`
- end: `0x1800103a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180010534`

## callees

- `0x180010350`
- `0x1800103a8`
- `0x1800104a8`
- `0x18001079c`
- `0x1800107cc`

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
0x180010350  sub     rsp, 28h
0x180010354  test    edx, edx
0x180010356  jz      short loc_180010391
0x180010358  sub     edx, 1
0x18001035b  jz      short loc_180010385
0x18001035d  sub     edx, 1
0x180010360  jz      short loc_180010378
0x180010362  cmp     edx, 1
0x180010365  jz      short loc_180010371
0x180010367  mov     eax, 1
0x18001036c  add     rsp, 28h
0x180010370  retn
0x180010371  call    __scrt_dllmain_crt_thread_detach
0x180010376  jmp     short loc_18001037D
0x180010378  call    __scrt_dllmain_crt_thread_attach
0x18001037d  movzx   eax, al
0x180010380  add     rsp, 28h
0x180010384  retn
0x180010385  mov     rdx, r8
0x180010388  add     rsp, 28h
0x18001038c  jmp     dllmain_crt_process_attach
0x180010391  test    r8, r8
0x180010394  setnz   cl
0x180010397  add     rsp, 28h
0x18001039b  jmp     dllmain_crt_process_detach
```
