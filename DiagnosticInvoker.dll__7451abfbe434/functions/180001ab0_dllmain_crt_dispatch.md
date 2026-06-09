# dllmain_crt_dispatch

- ea: `0x180001ab0`
- end: `0x180001b00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001c94`

## callees

- `0x180001ab0`
- `0x180001b08`
- `0x180001c08`
- `0x180001fa0`
- `0x180001fd0`

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
0x180001ab0  sub     rsp, 28h
0x180001ab4  test    edx, edx
0x180001ab6  jz      short loc_180001AF1
0x180001ab8  sub     edx, 1
0x180001abb  jz      short loc_180001AE5
0x180001abd  sub     edx, 1
0x180001ac0  jz      short loc_180001AD8
0x180001ac2  cmp     edx, 1
0x180001ac5  jz      short loc_180001AD1
0x180001ac7  mov     eax, 1
0x180001acc  add     rsp, 28h
0x180001ad0  retn
0x180001ad1  call    __scrt_dllmain_crt_thread_detach
0x180001ad6  jmp     short loc_180001ADD
0x180001ad8  call    __scrt_dllmain_crt_thread_attach
0x180001add  movzx   eax, al
0x180001ae0  add     rsp, 28h
0x180001ae4  retn
0x180001ae5  mov     rdx, r8
0x180001ae8  add     rsp, 28h
0x180001aec  jmp     dllmain_crt_process_attach
0x180001af1  test    r8, r8
0x180001af4  setnz   cl
0x180001af7  add     rsp, 28h
0x180001afb  jmp     dllmain_crt_process_detach
```
