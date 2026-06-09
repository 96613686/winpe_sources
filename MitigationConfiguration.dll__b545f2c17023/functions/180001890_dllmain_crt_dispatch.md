# dllmain_crt_dispatch

- ea: `0x180001890`
- end: `0x1800018e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a74`

## callees

- `0x180001890`
- `0x1800018e8`
- `0x1800019e8`
- `0x180001cf4`
- `0x180001d24`

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
0x180001890  sub     rsp, 28h
0x180001894  test    edx, edx
0x180001896  jz      short loc_1800018D1
0x180001898  sub     edx, 1
0x18000189b  jz      short loc_1800018C5
0x18000189d  sub     edx, 1
0x1800018a0  jz      short loc_1800018B8
0x1800018a2  cmp     edx, 1
0x1800018a5  jz      short loc_1800018B1
0x1800018a7  mov     eax, 1
0x1800018ac  add     rsp, 28h
0x1800018b0  retn
0x1800018b1  call    __scrt_dllmain_crt_thread_detach
0x1800018b6  jmp     short loc_1800018BD
0x1800018b8  call    __scrt_dllmain_crt_thread_attach
0x1800018bd  movzx   eax, al
0x1800018c0  add     rsp, 28h
0x1800018c4  retn
0x1800018c5  mov     rdx, r8
0x1800018c8  add     rsp, 28h
0x1800018cc  jmp     dllmain_crt_process_attach
0x1800018d1  test    r8, r8
0x1800018d4  setnz   cl
0x1800018d7  add     rsp, 28h
0x1800018db  jmp     dllmain_crt_process_detach
```
