# dllmain_crt_dispatch

- ea: `0x100468bb4`
- end: `0x100468c04`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x100468db4`

## callees

- `0x100468bb4`
- `0x100468c0c`
- `0x100468d28`
- `0x100468fc8`
- `0x100468ff8`

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
    return dllmain_crt_process_attach();
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
0x100468bb4  sub     rsp, 28h
0x100468bb8  test    edx, edx
0x100468bba  jz      short loc_100468BF5
0x100468bbc  sub     edx, 1
0x100468bbf  jz      short loc_100468BE9
0x100468bc1  sub     edx, 1
0x100468bc4  jz      short loc_100468BDC
0x100468bc6  cmp     edx, 1
0x100468bc9  jz      short loc_100468BD5
0x100468bcb  mov     eax, 1
0x100468bd0  add     rsp, 28h
0x100468bd4  retn
0x100468bd5  call    __scrt_dllmain_crt_thread_detach
0x100468bda  jmp     short loc_100468BE1
0x100468bdc  call    __scrt_dllmain_crt_thread_attach
0x100468be1  movzx   eax, al
0x100468be4  add     rsp, 28h
0x100468be8  retn
0x100468be9  mov     rdx, r8
0x100468bec  add     rsp, 28h
0x100468bf0  jmp     dllmain_crt_process_attach
0x100468bf5  test    r8, r8
0x100468bf8  setnz   cl
0x100468bfb  add     rsp, 28h
0x100468bff  jmp     dllmain_crt_process_detach
```
