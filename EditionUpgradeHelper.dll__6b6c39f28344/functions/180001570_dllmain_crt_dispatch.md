# dllmain_crt_dispatch

- ea: `0x180001570`
- end: `0x1800015c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001754`

## callees

- `0x180001570`
- `0x1800015c8`
- `0x1800016c8`
- `0x180001990`
- `0x1800019c0`

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
0x180001570  sub     rsp, 28h
0x180001574  test    edx, edx
0x180001576  jz      short loc_1800015B1
0x180001578  sub     edx, 1
0x18000157b  jz      short loc_1800015A5
0x18000157d  sub     edx, 1
0x180001580  jz      short loc_180001598
0x180001582  cmp     edx, 1
0x180001585  jz      short loc_180001591
0x180001587  mov     eax, 1
0x18000158c  add     rsp, 28h
0x180001590  retn
0x180001591  call    __scrt_dllmain_crt_thread_detach
0x180001596  jmp     short loc_18000159D
0x180001598  call    __scrt_dllmain_crt_thread_attach
0x18000159d  movzx   eax, al
0x1800015a0  add     rsp, 28h
0x1800015a4  retn
0x1800015a5  mov     rdx, r8
0x1800015a8  add     rsp, 28h
0x1800015ac  jmp     dllmain_crt_process_attach
0x1800015b1  test    r8, r8
0x1800015b4  setnz   cl
0x1800015b7  add     rsp, 28h
0x1800015bb  jmp     dllmain_crt_process_detach
```
