# dllmain_crt_dispatch

- ea: `0x180015780`
- end: `0x1800157d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180015964`

## callees

- `0x180015780`
- `0x1800157d8`
- `0x1800158d8`
- `0x180015c28`
- `0x180015c58`

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
0x180015780  sub     rsp, 28h
0x180015784  test    edx, edx
0x180015786  jz      short loc_1800157C1
0x180015788  sub     edx, 1
0x18001578b  jz      short loc_1800157B5
0x18001578d  sub     edx, 1
0x180015790  jz      short loc_1800157A8
0x180015792  cmp     edx, 1
0x180015795  jz      short loc_1800157A1
0x180015797  mov     eax, 1
0x18001579c  add     rsp, 28h
0x1800157a0  retn
0x1800157a1  call    __scrt_dllmain_crt_thread_detach
0x1800157a6  jmp     short loc_1800157AD
0x1800157a8  call    __scrt_dllmain_crt_thread_attach
0x1800157ad  movzx   eax, al
0x1800157b0  add     rsp, 28h
0x1800157b4  retn
0x1800157b5  mov     rdx, r8
0x1800157b8  add     rsp, 28h
0x1800157bc  jmp     dllmain_crt_process_attach
0x1800157c1  test    r8, r8
0x1800157c4  setnz   cl
0x1800157c7  add     rsp, 28h
0x1800157cb  jmp     dllmain_crt_process_detach
```
