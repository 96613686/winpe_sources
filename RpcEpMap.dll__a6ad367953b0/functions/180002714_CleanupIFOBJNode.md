# CleanupIFOBJNode

- ea: `0x180002714`
- end: `0x18000278f`
- name: `CleanupIFOBJNode`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014b0`
- `0x1800018a0`
- `0x1800050c0`
- `0x180006e70`

## callees

- `0x180002714`
- `0x180002798`
- `0x18000284c`
- `0x180002864`
- `0x1800028c4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002788`

## pseudocode

```c
BOOL __fastcall CleanupIFOBJNode(__int64 a1)
{
  __int64 **i; // rdi
  void *v3; // rcx

  LogInterfaceUnregisterFromNode();
  for ( i = *(__int64 ***)(a1 + 32); i; i = (__int64 **)*i )
    UpdateEpMapperPortsIfNecessary((char *)i[3], 0);
  DeletePSEPNodeList(*(_QWORD **)(a1 + 32));
  v3 = *(void **)(a1 + 24);
  if ( v3 )
    CloseHandle(v3);
  if ( gFwManagerExtensionState == 1 && *(_DWORD *)(a1 + 144) )
    RpcExtFwEpmapInterfaceUnRegistered(a1 + 104);
  return HeapFree(hEpMapperHeap, 0, (LPVOID)a1);
}

```

## disassembly

```asm
0x180002714  mov     [rsp+arg_0], rbx
0x180002719  push    rdi
0x18000271a  sub     rsp, 20h
0x18000271e  mov     rbx, rcx
0x180002721  call    LogInterfaceUnregisterFromNode
0x180002726  mov     rdi, [rbx+20h]
0x18000272a  jmp     short loc_18000273A
0x18000272c  mov     rcx, [rdi+18h]; String1
0x180002730  xor     edx, edx
0x180002732  call    UpdateEpMapperPortsIfNecessary
0x180002737  mov     rdi, [rdi]
0x18000273a  test    rdi, rdi
0x18000273d  jnz     short loc_18000272C
0x18000273f  mov     rcx, [rbx+20h]; lpMem
0x180002743  call    DeletePSEPNodeList
0x180002748  mov     rcx, [rbx+18h]; hObject
0x18000274c  test    rcx, rcx
0x18000274f  jz      short loc_180002757
0x180002751  call    cs:__imp_CloseHandle
0x180002757  cmp     cs:?gFwManagerExtensionState@@3W4FwManagerExtensionState@@A, 1; FwManagerExtensionState gFwManagerExtensionState
0x18000275e  jnz     short loc_180002772
0x180002760  cmp     dword ptr [rbx+90h], 0
0x180002767  jz      short loc_180002772
0x180002769  lea     rcx, [rbx+68h]
0x18000276d  call    RpcExtFwEpmapInterfaceUnRegistered
0x180002772  mov     rcx, cs:hEpMapperHeap
0x180002779  mov     r8, rbx
0x18000277c  xor     edx, edx
0x18000277e  mov     rbx, [rsp+28h+arg_0]
0x180002783  add     rsp, 20h
0x180002787  pop     rdi
0x180002788  jmp     cs:__imp_HeapFree
```
