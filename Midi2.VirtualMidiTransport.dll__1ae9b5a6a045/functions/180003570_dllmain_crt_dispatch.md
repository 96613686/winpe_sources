# dllmain_crt_dispatch

- ea: `0x180003570`
- end: `0x1800035c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003754`

## callees

- `0x180003570`
- `0x1800035c8`
- `0x1800036c8`
- `0x180003a10`
- `0x180003a40`

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
0x180003570  sub     rsp, 28h
0x180003574  test    edx, edx
0x180003576  jz      short loc_1800035B1
0x180003578  sub     edx, 1
0x18000357b  jz      short loc_1800035A5
0x18000357d  sub     edx, 1
0x180003580  jz      short loc_180003598
0x180003582  cmp     edx, 1
0x180003585  jz      short loc_180003591
0x180003587  mov     eax, 1
0x18000358c  add     rsp, 28h
0x180003590  retn
0x180003591  call    __scrt_dllmain_crt_thread_detach
0x180003596  jmp     short loc_18000359D
0x180003598  call    __scrt_dllmain_crt_thread_attach
0x18000359d  movzx   eax, al
0x1800035a0  add     rsp, 28h
0x1800035a4  retn
0x1800035a5  mov     rdx, r8
0x1800035a8  add     rsp, 28h
0x1800035ac  jmp     dllmain_crt_process_attach
0x1800035b1  test    r8, r8
0x1800035b4  setnz   cl
0x1800035b7  add     rsp, 28h
0x1800035bb  jmp     dllmain_crt_process_detach
```
