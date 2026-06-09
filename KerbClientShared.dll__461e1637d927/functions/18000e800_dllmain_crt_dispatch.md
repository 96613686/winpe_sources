# dllmain_crt_dispatch

- ea: `0x18000e800`
- end: `0x18000e850`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e9e4`

## callees

- `0x18000e800`
- `0x18000e858`
- `0x18000e958`
- `0x18000ec20`
- `0x18000ec50`

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
0x18000e800  sub     rsp, 28h
0x18000e804  test    edx, edx
0x18000e806  jz      short loc_18000E841
0x18000e808  sub     edx, 1
0x18000e80b  jz      short loc_18000E835
0x18000e80d  sub     edx, 1
0x18000e810  jz      short loc_18000E828
0x18000e812  cmp     edx, 1
0x18000e815  jz      short loc_18000E821
0x18000e817  mov     eax, 1
0x18000e81c  add     rsp, 28h
0x18000e820  retn
0x18000e821  call    __scrt_dllmain_crt_thread_detach
0x18000e826  jmp     short loc_18000E82D
0x18000e828  call    __scrt_dllmain_crt_thread_attach
0x18000e82d  movzx   eax, al
0x18000e830  add     rsp, 28h
0x18000e834  retn
0x18000e835  mov     rdx, r8
0x18000e838  add     rsp, 28h
0x18000e83c  jmp     dllmain_crt_process_attach
0x18000e841  test    r8, r8
0x18000e844  setnz   cl
0x18000e847  add     rsp, 28h
0x18000e84b  jmp     dllmain_crt_process_detach
```
