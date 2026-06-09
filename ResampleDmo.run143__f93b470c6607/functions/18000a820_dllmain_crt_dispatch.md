# dllmain_crt_dispatch

- ea: `0x18000a820`
- end: `0x18000a870`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aa04`

## callees

- `0x18000a820`
- `0x18000a878`
- `0x18000a978`
- `0x18000add4`
- `0x18000ae04`

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
0x18000a820  sub     rsp, 28h
0x18000a824  test    edx, edx
0x18000a826  jz      short loc_18000A861
0x18000a828  sub     edx, 1
0x18000a82b  jz      short loc_18000A855
0x18000a82d  sub     edx, 1
0x18000a830  jz      short loc_18000A848
0x18000a832  cmp     edx, 1
0x18000a835  jz      short loc_18000A841
0x18000a837  mov     eax, 1
0x18000a83c  add     rsp, 28h
0x18000a840  retn
0x18000a841  call    __scrt_dllmain_crt_thread_detach
0x18000a846  jmp     short loc_18000A84D
0x18000a848  call    __scrt_dllmain_crt_thread_attach
0x18000a84d  movzx   eax, al
0x18000a850  add     rsp, 28h
0x18000a854  retn
0x18000a855  mov     rdx, r8
0x18000a858  add     rsp, 28h
0x18000a85c  jmp     dllmain_crt_process_attach
0x18000a861  test    r8, r8
0x18000a864  setnz   cl
0x18000a867  add     rsp, 28h
0x18000a86b  jmp     dllmain_crt_process_detach
```
