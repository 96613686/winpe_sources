# BfeRundownShutdown

- ea: `0x180076164`
- end: `0x180076202`
- name: `BfeRundownShutdown`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040d70`
- `0x180048490`

## callees

- `0x180039b64`
- `0x18005b4fc`
- `0x180076164`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18007618e`
- `ntdll!EtwEventUnregister` at `0x18007618e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800761a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800761c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800761a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800761c9`

## pseudocode

```c
void *BfeRundownShutdown()
{
  __int64 v0; // rcx

  if ( dword_1800EE0C8 )
  {
    v0 = qword_1800EE0E8;
    dword_1800EE0C8 = 0;
    qword_1800EE0E8 = 0;
    EtwEventUnregister(v0);
  }
  if ( qword_1800F5758 )
  {
    CloseThreadpoolWork(qword_1800F5758);
    qword_1800F5758 = 0;
  }
  if ( qword_1800F5760 )
  {
    CloseThreadpoolWork(qword_1800F5760);
    qword_1800F5760 = 0;
  }
  WfpCriticalSectionDestroy(&gBfeRundownComponent);
  return memset_0(&gBfeRundownComponent, 0, 0x50u);
}

```

## disassembly

```asm
0x180076164  sub     rsp, 28h
0x180076168  mov     eax, cs:dword_1800EE0C8
0x18007616e  test    eax, eax
0x180076170  jz      short loc_18007619A
0x180076172  mov     rcx, cs:qword_1800EE0E8
0x180076179  mov     cs:dword_1800EE0C8, 0
0x180076183  mov     cs:qword_1800EE0E8, 0
0x18007618e  call    cs:__imp_EtwEventUnregister
0x180076195  nop     dword ptr [rax+rax+00h]
0x18007619a  mov     rcx, cs:qword_1800F5758; pwk
0x1800761a1  test    rcx, rcx
0x1800761a4  jz      short loc_1800761BD
0x1800761a6  call    cs:__imp_CloseThreadpoolWork
0x1800761ad  nop     dword ptr [rax+rax+00h]
0x1800761b2  mov     cs:qword_1800F5758, 0
0x1800761bd  mov     rcx, cs:qword_1800F5760; pwk
0x1800761c4  test    rcx, rcx
0x1800761c7  jz      short loc_1800761E0
0x1800761c9  call    cs:__imp_CloseThreadpoolWork
0x1800761d0  nop     dword ptr [rax+rax+00h]
0x1800761d5  mov     cs:qword_1800F5760, 0
0x1800761e0  lea     rcx, gBfeRundownComponent
0x1800761e7  call    WfpCriticalSectionDestroy
0x1800761ec  xor     edx, edx; Val
0x1800761ee  lea     rcx, gBfeRundownComponent; void *
0x1800761f5  lea     r8d, [rdx+50h]; Size
0x1800761f9  add     rsp, 28h
0x1800761fd  jmp     memset_0
```
