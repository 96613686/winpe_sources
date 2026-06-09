# dllmain_crt_dispatch

- ea: `0x1800021d0`
- end: `0x180002220`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800023b4`

## callees

- `0x1800021d0`
- `0x180002228`
- `0x180002328`
- `0x180002600`
- `0x180002630`

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
0x1800021d0  sub     rsp, 28h
0x1800021d4  test    edx, edx
0x1800021d6  jz      short loc_180002211
0x1800021d8  sub     edx, 1
0x1800021db  jz      short loc_180002205
0x1800021dd  sub     edx, 1
0x1800021e0  jz      short loc_1800021F8
0x1800021e2  cmp     edx, 1
0x1800021e5  jz      short loc_1800021F1
0x1800021e7  mov     eax, 1
0x1800021ec  add     rsp, 28h
0x1800021f0  retn
0x1800021f1  call    __scrt_dllmain_crt_thread_detach
0x1800021f6  jmp     short loc_1800021FD
0x1800021f8  call    __scrt_dllmain_crt_thread_attach
0x1800021fd  movzx   eax, al
0x180002200  add     rsp, 28h
0x180002204  retn
0x180002205  mov     rdx, r8
0x180002208  add     rsp, 28h
0x18000220c  jmp     dllmain_crt_process_attach
0x180002211  test    r8, r8
0x180002214  setnz   cl
0x180002217  add     rsp, 28h
0x18000221b  jmp     dllmain_crt_process_detach
```
