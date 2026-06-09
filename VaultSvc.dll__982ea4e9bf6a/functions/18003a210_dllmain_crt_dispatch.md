# dllmain_crt_dispatch

- ea: `0x18003a210`
- end: `0x18003a260`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18003a3f4`

## callees

- `0x18003a210`
- `0x18003a268`
- `0x18003a368`
- `0x18003a738`
- `0x18003a768`

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
0x18003a210  sub     rsp, 28h
0x18003a214  test    edx, edx
0x18003a216  jz      short loc_18003A251
0x18003a218  sub     edx, 1
0x18003a21b  jz      short loc_18003A245
0x18003a21d  sub     edx, 1
0x18003a220  jz      short loc_18003A238
0x18003a222  cmp     edx, 1
0x18003a225  jz      short loc_18003A231
0x18003a227  mov     eax, 1
0x18003a22c  add     rsp, 28h
0x18003a230  retn
0x18003a231  call    __scrt_dllmain_crt_thread_detach
0x18003a236  jmp     short loc_18003A23D
0x18003a238  call    __scrt_dllmain_crt_thread_attach
0x18003a23d  movzx   eax, al
0x18003a240  add     rsp, 28h
0x18003a244  retn
0x18003a245  mov     rdx, r8
0x18003a248  add     rsp, 28h
0x18003a24c  jmp     dllmain_crt_process_attach
0x18003a251  test    r8, r8
0x18003a254  setnz   cl
0x18003a257  add     rsp, 28h
0x18003a25b  jmp     dllmain_crt_process_detach
```
