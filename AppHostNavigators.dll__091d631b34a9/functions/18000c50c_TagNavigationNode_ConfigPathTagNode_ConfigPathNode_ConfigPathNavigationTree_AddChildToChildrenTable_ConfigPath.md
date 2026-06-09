# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChildToChildrenTable(ConfigPathTagNode *,ConfigPathTagNode *)

- ea: `0x18000c50c`
- end: `0x18000c59c`
- name: `?AddChildToChildrenTable@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAXPEAVConfigPathTagNode@@0@Z`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c470`
- `0x18000cdd0`

## callees

- `0x18000a2fc`
- `0x18000c3b0`
- `0x18000c50c`
- `0x180012f3c`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChildToChildrenTable(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+40h] [rbp+18h] BYREF

  pExceptionObject = a3;
  if ( a3 && *(_QWORD *)(a3 + 16) == a2[2] )
    goto LABEL_5;
  if ( (unsigned __int8)TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::TryGetLastChildWithLocalName<ConfigPathTagNode>(
                          a1,
                          a2[2],
                          &pExceptionObject) )
  {
    a3 = pExceptionObject;
LABEL_5:
    result = *(_QWORD *)(a3 + 72);
    a2[9] = result;
    a2[10] = a3 + 72;
    *(_QWORD *)(result + 8) = a2 + 9;
    *(_QWORD *)(a3 + 72) = a2 + 9;
    return result;
  }
  a2[10] = a2 + 9;
  a2[9] = a2 + 9;
  result = HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::InsertRecord(
             *(RTL_SRWLOCK **)(a1 + 88),
             (__int64)a2);
  if ( (int)result < 0 )
  {
    LODWORD(pExceptionObject) = result;
    throw (long *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000c50c  mov     [rsp+arg_0], rbx
0x18000c511  push    rdi
0x18000c512  sub     rsp, 20h
0x18000c516  mov     [rsp+28h+pExceptionObject], r8
0x18000c51b  mov     rbx, rdx
0x18000c51e  mov     rdi, rcx
0x18000c521  test    r8, r8
0x18000c524  jz      short loc_18000C530
0x18000c526  mov     rax, [rdx+10h]
0x18000c52a  cmp     [r8+10h], rax
0x18000c52e  jz      short loc_18000C547
0x18000c530  mov     rdx, [rdx+10h]
0x18000c534  lea     r8, [rsp+28h+pExceptionObject]
0x18000c539  call    ??$TryGetLastChildWithLocalName@VConfigPathTagNode@@@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@QEAA_NPEBGPEAPEAVConfigPathTagNode@@@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::TryGetLastChildWithLocalName<ConfigPathTagNode>(ushort const *,ConfigPathTagNode * *)
0x18000c53e  test    al, al
0x18000c540  jz      short loc_18000C56B
0x18000c542  mov     r8, [rsp+28h+pExceptionObject]
0x18000c547  lea     rcx, [rbx+48h]
0x18000c54b  lea     rdx, [r8+48h]
0x18000c54f  mov     rax, [rdx]
0x18000c552  mov     [rcx], rax
0x18000c555  mov     [rcx+8], rdx
0x18000c559  mov     [rax+8], rcx
0x18000c55d  mov     [rdx], rcx
0x18000c560  mov     rbx, [rsp+28h+arg_0]
0x18000c565  add     rsp, 20h
0x18000c569  pop     rdi
0x18000c56a  retn
0x18000c56b  lea     rax, [rbx+48h]
0x18000c56f  mov     rdx, rbx
0x18000c572  mov     [rax+8], rax
0x18000c576  mov     [rax], rax
0x18000c579  mov     rcx, [rdi+58h]
0x18000c57d  call    ?InsertRecord@?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@QEAAJPEAVVDirMappingOwnerDescriptor@@@Z; HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::InsertRecord(VDirMappingOwnerDescriptor *)
0x18000c582  test    eax, eax
0x18000c584  jns     short loc_18000C560
0x18000c586  lea     rdx, _TI1J; pThrowInfo
0x18000c58d  mov     dword ptr [rsp+28h+pExceptionObject], eax
0x18000c591  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c596  call    _CxxThrowException_0
```
