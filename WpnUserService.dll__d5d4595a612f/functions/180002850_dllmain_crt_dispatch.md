# dllmain_crt_dispatch

- ea: `0x180002850`
- end: `0x1800028a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a34`

## callees

- `0x180002850`
- `0x1800028a8`
- `0x1800029a8`
- `0x180002c70`
- `0x180002ca0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
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
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x180002850  sub     rsp, 28h
0x180002854  test    edx, edx
0x180002856  jz      short loc_180002891
0x180002858  sub     edx, 1
0x18000285b  jz      short loc_180002885
0x18000285d  sub     edx, 1
0x180002860  jz      short loc_180002878
0x180002862  cmp     edx, 1
0x180002865  jz      short loc_180002871
0x180002867  mov     eax, 1
0x18000286c  add     rsp, 28h
0x180002870  retn
0x180002871  call    __scrt_dllmain_crt_thread_detach
0x180002876  jmp     short loc_18000287D
0x180002878  call    __scrt_dllmain_crt_thread_attach
0x18000287d  movzx   eax, al
0x180002880  add     rsp, 28h
0x180002884  retn
0x180002885  mov     rdx, r8
0x180002888  add     rsp, 28h
0x18000288c  jmp     dllmain_crt_process_attach
0x180002891  test    r8, r8
0x180002894  setnz   cl
0x180002897  add     rsp, 28h
0x18000289b  jmp     dllmain_crt_process_detach
```
