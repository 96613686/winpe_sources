# dllmain_crt_dispatch

- ea: `0x180001540`
- end: `0x180001590`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001724`

## callees

- `0x180001540`
- `0x180001598`
- `0x180001698`
- `0x180001a68`
- `0x180001a98`

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
0x180001540  sub     rsp, 28h
0x180001544  test    edx, edx
0x180001546  jz      short loc_180001581
0x180001548  sub     edx, 1
0x18000154b  jz      short loc_180001575
0x18000154d  sub     edx, 1
0x180001550  jz      short loc_180001568
0x180001552  cmp     edx, 1
0x180001555  jz      short loc_180001561
0x180001557  mov     eax, 1
0x18000155c  add     rsp, 28h
0x180001560  retn
0x180001561  call    __scrt_dllmain_crt_thread_detach
0x180001566  jmp     short loc_18000156D
0x180001568  call    __scrt_dllmain_crt_thread_attach
0x18000156d  movzx   eax, al
0x180001570  add     rsp, 28h
0x180001574  retn
0x180001575  mov     rdx, r8
0x180001578  add     rsp, 28h
0x18000157c  jmp     dllmain_crt_process_attach
0x180001581  test    r8, r8
0x180001584  setnz   cl
0x180001587  add     rsp, 28h
0x18000158b  jmp     dllmain_crt_process_detach
```
