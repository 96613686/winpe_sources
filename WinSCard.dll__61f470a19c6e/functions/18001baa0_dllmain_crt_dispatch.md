# dllmain_crt_dispatch

- ea: `0x18001baa0`
- end: `0x18001baf0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001bc84`

## callees

- `0x18001baa0`
- `0x18001baf8`
- `0x18001bbf8`
- `0x18001bedc`
- `0x18001bf0c`

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
0x18001baa0  sub     rsp, 28h
0x18001baa4  test    edx, edx
0x18001baa6  jz      short loc_18001BAE1
0x18001baa8  sub     edx, 1
0x18001baab  jz      short loc_18001BAD5
0x18001baad  sub     edx, 1
0x18001bab0  jz      short loc_18001BAC8
0x18001bab2  cmp     edx, 1
0x18001bab5  jz      short loc_18001BAC1
0x18001bab7  mov     eax, 1
0x18001babc  add     rsp, 28h
0x18001bac0  retn
0x18001bac1  call    __scrt_dllmain_crt_thread_detach
0x18001bac6  jmp     short loc_18001BACD
0x18001bac8  call    __scrt_dllmain_crt_thread_attach
0x18001bacd  movzx   eax, al
0x18001bad0  add     rsp, 28h
0x18001bad4  retn
0x18001bad5  mov     rdx, r8
0x18001bad8  add     rsp, 28h
0x18001badc  jmp     dllmain_crt_process_attach
0x18001bae1  test    r8, r8
0x18001bae4  setnz   cl
0x18001bae7  add     rsp, 28h
0x18001baeb  jmp     dllmain_crt_process_detach
```
