# dllmain_crt_dispatch

- ea: `0x1800022e0`
- end: `0x180002330`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800024c4`

## callees

- `0x1800022e0`
- `0x180002338`
- `0x180002438`
- `0x1800027d0`
- `0x180002800`

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
0x1800022e0  sub     rsp, 28h
0x1800022e4  test    edx, edx
0x1800022e6  jz      short loc_180002321
0x1800022e8  sub     edx, 1
0x1800022eb  jz      short loc_180002315
0x1800022ed  sub     edx, 1
0x1800022f0  jz      short loc_180002308
0x1800022f2  cmp     edx, 1
0x1800022f5  jz      short loc_180002301
0x1800022f7  mov     eax, 1
0x1800022fc  add     rsp, 28h
0x180002300  retn
0x180002301  call    __scrt_dllmain_crt_thread_detach
0x180002306  jmp     short loc_18000230D
0x180002308  call    __scrt_dllmain_crt_thread_attach
0x18000230d  movzx   eax, al
0x180002310  add     rsp, 28h
0x180002314  retn
0x180002315  mov     rdx, r8
0x180002318  add     rsp, 28h
0x18000231c  jmp     dllmain_crt_process_attach
0x180002321  test    r8, r8
0x180002324  setnz   cl
0x180002327  add     rsp, 28h
0x18000232b  jmp     dllmain_crt_process_detach
```
