# dllmain_crt_dispatch

- ea: `0x180001440`
- end: `0x180001490`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001624`

## callees

- `0x180001440`
- `0x180001498`
- `0x180001598`
- `0x180001860`
- `0x180001890`

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
0x180001440  sub     rsp, 28h
0x180001444  test    edx, edx
0x180001446  jz      short loc_180001481
0x180001448  sub     edx, 1
0x18000144b  jz      short loc_180001475
0x18000144d  sub     edx, 1
0x180001450  jz      short loc_180001468
0x180001452  cmp     edx, 1
0x180001455  jz      short loc_180001461
0x180001457  mov     eax, 1
0x18000145c  add     rsp, 28h
0x180001460  retn
0x180001461  call    __scrt_dllmain_crt_thread_detach
0x180001466  jmp     short loc_18000146D
0x180001468  call    __scrt_dllmain_crt_thread_attach
0x18000146d  movzx   eax, al
0x180001470  add     rsp, 28h
0x180001474  retn
0x180001475  mov     rdx, r8
0x180001478  add     rsp, 28h
0x18000147c  jmp     dllmain_crt_process_attach
0x180001481  test    r8, r8
0x180001484  setnz   cl
0x180001487  add     rsp, 28h
0x18000148b  jmp     dllmain_crt_process_detach
```
