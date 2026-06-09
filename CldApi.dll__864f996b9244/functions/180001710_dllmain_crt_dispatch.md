# dllmain_crt_dispatch

- ea: `0x180001710`
- end: `0x180001760`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800018f4`

## callees

- `0x180001710`
- `0x180001768`
- `0x180001868`
- `0x180001c38`
- `0x180001c68`

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
0x180001710  sub     rsp, 28h
0x180001714  test    edx, edx
0x180001716  jz      short loc_180001751
0x180001718  sub     edx, 1
0x18000171b  jz      short loc_180001745
0x18000171d  sub     edx, 1
0x180001720  jz      short loc_180001738
0x180001722  cmp     edx, 1
0x180001725  jz      short loc_180001731
0x180001727  mov     eax, 1
0x18000172c  add     rsp, 28h
0x180001730  retn
0x180001731  call    __scrt_dllmain_crt_thread_detach
0x180001736  jmp     short loc_18000173D
0x180001738  call    __scrt_dllmain_crt_thread_attach
0x18000173d  movzx   eax, al
0x180001740  add     rsp, 28h
0x180001744  retn
0x180001745  mov     rdx, r8
0x180001748  add     rsp, 28h
0x18000174c  jmp     dllmain_crt_process_attach
0x180001751  test    r8, r8
0x180001754  setnz   cl
0x180001757  add     rsp, 28h
0x18000175b  jmp     dllmain_crt_process_detach
```
