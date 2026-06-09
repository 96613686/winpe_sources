# dllmain_crt_dispatch

- ea: `0x1800216c0`
- end: `0x180021710`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800218a4`

## callees

- `0x1800216c0`
- `0x180021718`
- `0x180021818`
- `0x180021bf4`
- `0x180021c24`

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
0x1800216c0  sub     rsp, 28h
0x1800216c4  test    edx, edx
0x1800216c6  jz      short loc_180021701
0x1800216c8  sub     edx, 1
0x1800216cb  jz      short loc_1800216F5
0x1800216cd  sub     edx, 1
0x1800216d0  jz      short loc_1800216E8
0x1800216d2  cmp     edx, 1
0x1800216d5  jz      short loc_1800216E1
0x1800216d7  mov     eax, 1
0x1800216dc  add     rsp, 28h
0x1800216e0  retn
0x1800216e1  call    __scrt_dllmain_crt_thread_detach
0x1800216e6  jmp     short loc_1800216ED
0x1800216e8  call    __scrt_dllmain_crt_thread_attach
0x1800216ed  movzx   eax, al
0x1800216f0  add     rsp, 28h
0x1800216f4  retn
0x1800216f5  mov     rdx, r8
0x1800216f8  add     rsp, 28h
0x1800216fc  jmp     dllmain_crt_process_attach
0x180021701  test    r8, r8
0x180021704  setnz   cl
0x180021707  add     rsp, 28h
0x18002170b  jmp     dllmain_crt_process_detach
```
