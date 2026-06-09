# CCounterEvts::EvtCallBackPendingTask(void *,uchar)

- ea: `0x180016a80`
- end: `0x180016ab8`
- name: `?EvtCallBackPendingTask@CCounterEvts@@SAXPEAXE@Z`
- size: `56`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180004bf0`
- `0x180005fdc`
- `0x18000616c`
- `0x180016a80`

## pseudocode

```c
void __fastcall CCounterEvts::EvtCallBackPendingTask(_DWORD *a1)
{
  if ( (unsigned int)GLOB_Monitor_IsRegistred() && a1 && *a1 == 1163152963 )
  {
    if ( (unsigned int)GLOB_IsResyncAllowed() )
      ResyncPerf(3u);
  }
}

```

## disassembly

```asm
0x180016a80  push    rbx
0x180016a82  sub     rsp, 20h
0x180016a86  mov     rbx, rcx
0x180016a89  call    ?GLOB_Monitor_IsRegistred@@YAHXZ; GLOB_Monitor_IsRegistred(void)
0x180016a8e  test    eax, eax
0x180016a90  jz      short loc_180016AB2
0x180016a92  test    rbx, rbx
0x180016a95  jz      short loc_180016AB2
0x180016a97  cmp     dword ptr [rbx], 45544E43h
0x180016a9d  jnz     short loc_180016AB2
0x180016a9f  call    ?GLOB_IsResyncAllowed@@YAHXZ; GLOB_IsResyncAllowed(void)
0x180016aa4  test    eax, eax
0x180016aa6  jz      short loc_180016AB2
0x180016aa8  mov     ecx, 3; unsigned int
0x180016aad  call    ?ResyncPerf@@YAKK@Z; ResyncPerf(ulong)
0x180016ab2  add     rsp, 20h
0x180016ab6  pop     rbx
0x180016ab7  retn
```
