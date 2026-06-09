# dllmain_crt_dispatch

- ea: `0x180012a60`
- end: `0x180012ab0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180012c44`

## callees

- `0x180012a60`
- `0x180012ab8`
- `0x180012bb8`
- `0x180012ec4`
- `0x180012ef4`

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
0x180012a60  sub     rsp, 28h
0x180012a64  test    edx, edx
0x180012a66  jz      short loc_180012AA1
0x180012a68  sub     edx, 1
0x180012a6b  jz      short loc_180012A95
0x180012a6d  sub     edx, 1
0x180012a70  jz      short loc_180012A88
0x180012a72  cmp     edx, 1
0x180012a75  jz      short loc_180012A81
0x180012a77  mov     eax, 1
0x180012a7c  add     rsp, 28h
0x180012a80  retn
0x180012a81  call    __scrt_dllmain_crt_thread_detach
0x180012a86  jmp     short loc_180012A8D
0x180012a88  call    __scrt_dllmain_crt_thread_attach
0x180012a8d  movzx   eax, al
0x180012a90  add     rsp, 28h
0x180012a94  retn
0x180012a95  mov     rdx, r8
0x180012a98  add     rsp, 28h
0x180012a9c  jmp     dllmain_crt_process_attach
0x180012aa1  test    r8, r8
0x180012aa4  setnz   cl
0x180012aa7  add     rsp, 28h
0x180012aab  jmp     dllmain_crt_process_detach
```
