# dllmain_crt_dispatch

- ea: `0x180002500`
- end: `0x180002550`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800026f8`

## callees

- `0x180002500`
- `0x180002558`
- `0x180002670`
- `0x18000293c`
- `0x18000296c`

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
0x180002500  sub     rsp, 28h
0x180002504  test    edx, edx
0x180002506  jz      short loc_180002541
0x180002508  sub     edx, 1
0x18000250b  jz      short loc_180002535
0x18000250d  sub     edx, 1
0x180002510  jz      short loc_180002528
0x180002512  cmp     edx, 1
0x180002515  jz      short loc_180002521
0x180002517  mov     eax, 1
0x18000251c  add     rsp, 28h
0x180002520  retn
0x180002521  call    __scrt_dllmain_crt_thread_detach
0x180002526  jmp     short loc_18000252D
0x180002528  call    __scrt_dllmain_crt_thread_attach
0x18000252d  movzx   eax, al
0x180002530  add     rsp, 28h
0x180002534  retn
0x180002535  mov     rdx, r8
0x180002538  add     rsp, 28h
0x18000253c  jmp     dllmain_crt_process_attach
0x180002541  test    r8, r8
0x180002544  setnz   cl
0x180002547  add     rsp, 28h
0x18000254b  jmp     dllmain_crt_process_detach
```
