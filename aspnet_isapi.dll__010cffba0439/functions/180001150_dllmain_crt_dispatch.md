# dllmain_crt_dispatch

- ea: `0x180001150`
- end: `0x1800011a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000133c`

## callees

- `0x180001150`
- `0x1800011a0`
- `0x1800012b8`
- `0x1800016dc`
- `0x180001704`

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
0x180001150  sub     rsp, 28h
0x180001154  test    edx, edx
0x180001156  jz      short loc_180001191
0x180001158  sub     edx, 1
0x18000115b  jz      short loc_180001185
0x18000115d  sub     edx, 1
0x180001160  jz      short loc_180001178
0x180001162  cmp     edx, 1
0x180001165  jz      short loc_180001171
0x180001167  mov     eax, 1
0x18000116c  add     rsp, 28h
0x180001170  retn
0x180001171  call    __scrt_dllmain_crt_thread_detach
0x180001176  jmp     short loc_18000117D
0x180001178  call    __scrt_dllmain_crt_thread_attach
0x18000117d  movzx   eax, al
0x180001180  add     rsp, 28h
0x180001184  retn
0x180001185  mov     rdx, r8
0x180001188  add     rsp, 28h
0x18000118c  jmp     dllmain_crt_process_attach
0x180001191  test    r8, r8
0x180001194  setnz   cl
0x180001197  add     rsp, 28h
0x18000119b  jmp     dllmain_crt_process_detach
```
