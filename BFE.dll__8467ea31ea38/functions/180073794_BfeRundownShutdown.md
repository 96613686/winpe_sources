# BfeRundownShutdown

- ea: `0x180073794`
- end: `0x180073820`
- name: `BfeRundownShutdown`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003fca0`
- `0x180046624`

## callees

- `0x18003b440`
- `0x1800595ac`
- `0x180073794`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x1800737be`
- `ntdll!EtwEventUnregister` at `0x1800737be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800737d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800737ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800737d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800737ed`

## pseudocode

```c
void *BfeRundownShutdown()
{
  __int64 v0; // rcx

  if ( dword_1800EB0C8 )
  {
    v0 = qword_1800EB0E8;
    dword_1800EB0C8 = 0;
    qword_1800EB0E8 = 0;
    EtwEventUnregister(v0);
  }
  if ( qword_1800F2738 )
  {
    CloseThreadpoolWork(qword_1800F2738);
    qword_1800F2738 = 0;
  }
  if ( qword_1800F2740 )
  {
    CloseThreadpoolWork(qword_1800F2740);
    qword_1800F2740 = 0;
  }
  WfpCriticalSectionDestroy(&gBfeRundownComponent);
  return memset_0(&gBfeRundownComponent, 0, 0x50u);
}

```

## disassembly

```asm
0x180073794  sub     rsp, 28h
0x180073798  mov     eax, cs:dword_1800EB0C8
0x18007379e  test    eax, eax
0x1800737a0  jz      short loc_1800737C4
0x1800737a2  mov     rcx, cs:qword_1800EB0E8
0x1800737a9  mov     cs:dword_1800EB0C8, 0
0x1800737b3  mov     cs:qword_1800EB0E8, 0
0x1800737be  call    cs:__imp_EtwEventUnregister
0x1800737c4  mov     rcx, cs:qword_1800F2738; pwk
0x1800737cb  test    rcx, rcx
0x1800737ce  jz      short loc_1800737E1
0x1800737d0  call    cs:__imp_CloseThreadpoolWork
0x1800737d6  mov     cs:qword_1800F2738, 0
0x1800737e1  mov     rcx, cs:qword_1800F2740; pwk
0x1800737e8  test    rcx, rcx
0x1800737eb  jz      short loc_1800737FE
0x1800737ed  call    cs:__imp_CloseThreadpoolWork
0x1800737f3  mov     cs:qword_1800F2740, 0
0x1800737fe  lea     rcx, gBfeRundownComponent
0x180073805  call    WfpCriticalSectionDestroy
0x18007380a  xor     edx, edx; Val
0x18007380c  lea     rcx, gBfeRundownComponent; void *
0x180073813  lea     r8d, [rdx+50h]; Size
0x180073817  add     rsp, 28h
0x18007381b  jmp     memset_0
```
