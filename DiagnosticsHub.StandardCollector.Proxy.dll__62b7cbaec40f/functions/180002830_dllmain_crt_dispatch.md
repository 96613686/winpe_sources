# dllmain_crt_dispatch

- ea: `0x180002830`
- end: `0x180002880`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a1c`
- `0x180002b60`

## callees

- `0x180002830`
- `0x180002880`
- `0x180002998`
- `0x180003200`
- `0x180003228`

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
0x180002830  sub     rsp, 28h
0x180002834  test    edx, edx
0x180002836  jz      short loc_180002871
0x180002838  sub     edx, 1
0x18000283b  jz      short loc_180002865
0x18000283d  sub     edx, 1
0x180002840  jz      short loc_180002858
0x180002842  cmp     edx, 1
0x180002845  jz      short loc_180002851
0x180002847  mov     eax, 1
0x18000284c  add     rsp, 28h
0x180002850  retn
0x180002851  call    __scrt_dllmain_crt_thread_detach
0x180002856  jmp     short loc_18000285D
0x180002858  call    __scrt_dllmain_crt_thread_attach
0x18000285d  movzx   eax, al
0x180002860  add     rsp, 28h
0x180002864  retn
0x180002865  mov     rdx, r8
0x180002868  add     rsp, 28h
0x18000286c  jmp     dllmain_crt_process_attach
0x180002871  test    r8, r8
0x180002874  setnz   cl
0x180002877  add     rsp, 28h
0x18000287b  jmp     dllmain_crt_process_detach
```
