# dllmain_crt_dispatch

- ea: `0x180001820`
- end: `0x180001870`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a04`

## callees

- `0x180001820`
- `0x180001878`
- `0x180001978`
- `0x180001d98`
- `0x180001dc8`

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
0x180001820  sub     rsp, 28h
0x180001824  test    edx, edx
0x180001826  jz      short loc_180001861
0x180001828  sub     edx, 1
0x18000182b  jz      short loc_180001855
0x18000182d  sub     edx, 1
0x180001830  jz      short loc_180001848
0x180001832  cmp     edx, 1
0x180001835  jz      short loc_180001841
0x180001837  mov     eax, 1
0x18000183c  add     rsp, 28h
0x180001840  retn
0x180001841  call    __scrt_dllmain_crt_thread_detach
0x180001846  jmp     short loc_18000184D
0x180001848  call    __scrt_dllmain_crt_thread_attach
0x18000184d  movzx   eax, al
0x180001850  add     rsp, 28h
0x180001854  retn
0x180001855  mov     rdx, r8
0x180001858  add     rsp, 28h
0x18000185c  jmp     dllmain_crt_process_attach
0x180001861  test    r8, r8
0x180001864  setnz   cl
0x180001867  add     rsp, 28h
0x18000186b  jmp     dllmain_crt_process_detach
```
