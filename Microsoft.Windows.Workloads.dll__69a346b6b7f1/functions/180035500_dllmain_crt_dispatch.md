# dllmain_crt_dispatch

- ea: `0x180035500`
- end: `0x180035550`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800356ec`

## callees

- `0x18003512c`
- `0x180035154`
- `0x180035500`
- `0x180035550`
- `0x180035668`

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
0x180035500  sub     rsp, 28h
0x180035504  test    edx, edx
0x180035506  jz      short loc_180035541
0x180035508  sub     edx, 1
0x18003550b  jz      short loc_180035535
0x18003550d  sub     edx, 1
0x180035510  jz      short loc_180035528
0x180035512  cmp     edx, 1
0x180035515  jz      short loc_180035521
0x180035517  mov     eax, 1
0x18003551c  add     rsp, 28h
0x180035520  retn
0x180035521  call    __scrt_dllmain_crt_thread_detach
0x180035526  jmp     short loc_18003552D
0x180035528  call    __scrt_dllmain_crt_thread_attach
0x18003552d  movzx   eax, al
0x180035530  add     rsp, 28h
0x180035534  retn
0x180035535  mov     rdx, r8
0x180035538  add     rsp, 28h
0x18003553c  jmp     dllmain_crt_process_attach
0x180035541  test    r8, r8
0x180035544  setnz   cl
0x180035547  add     rsp, 28h
0x18003554b  jmp     dllmain_crt_process_detach
```
