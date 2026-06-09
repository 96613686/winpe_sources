# dllmain_crt_dispatch

- ea: `0x180001140`
- end: `0x180001190`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001324`

## callees

- `0x180001140`
- `0x180001198`
- `0x180001298`
- `0x1800015b0`
- `0x1800015e0`

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
0x180001140  sub     rsp, 28h
0x180001144  test    edx, edx
0x180001146  jz      short loc_180001181
0x180001148  sub     edx, 1
0x18000114b  jz      short loc_180001175
0x18000114d  sub     edx, 1
0x180001150  jz      short loc_180001168
0x180001152  cmp     edx, 1
0x180001155  jz      short loc_180001161
0x180001157  mov     eax, 1
0x18000115c  add     rsp, 28h
0x180001160  retn
0x180001161  call    __scrt_dllmain_crt_thread_detach
0x180001166  jmp     short loc_18000116D
0x180001168  call    __scrt_dllmain_crt_thread_attach
0x18000116d  movzx   eax, al
0x180001170  add     rsp, 28h
0x180001174  retn
0x180001175  mov     rdx, r8
0x180001178  add     rsp, 28h
0x18000117c  jmp     dllmain_crt_process_attach
0x180001181  test    r8, r8
0x180001184  setnz   cl
0x180001187  add     rsp, 28h
0x18000118b  jmp     dllmain_crt_process_detach
```
