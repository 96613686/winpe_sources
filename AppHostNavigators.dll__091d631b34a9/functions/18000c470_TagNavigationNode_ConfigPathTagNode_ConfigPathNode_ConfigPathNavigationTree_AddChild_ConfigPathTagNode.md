# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChild(ConfigPathTagNode *)

- ea: `0x18000c470`
- end: `0x18000c504`
- name: `?AddChild@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@QEAAXPEAVConfigPathTagNode@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c9e8`

## callees

- `0x18000c470`
- `0x18000c50c`
- `0x18000cdd0`

## pseudocode

```c
_QWORD *__fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChild(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax
  _QWORD *result; // rax
  __int64 v6; // rdx

  v2 = *(_QWORD *)(a1 + 48);
  if ( v2 && (unsigned int)(*(_DWORD *)(*(_QWORD *)(v2 + 64) - 48LL) + 1) >= 8 )
  {
    if ( !*(_QWORD *)(a1 + 88) )
      TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::InitializeSupportForNavigationKeyedByLocalName(a1);
    TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChildToChildrenTable(
      a1,
      (_QWORD *)a2,
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 64LL) - 56LL);
  }
  result = *(_QWORD **)(a1 + 48);
  if ( result )
  {
    *(_DWORD *)(a2 + 8) = *(_DWORD *)(result[8] - 48LL) + 1;
    v6 = *(_QWORD *)(a1 + 48) + 56LL;
    result = *(_QWORD **)(*(_QWORD *)(a1 + 48) + 64LL);
    *(_QWORD *)(a2 + 56) = v6;
    *(_QWORD *)(a2 + 64) = result;
    *result = a2 + 56;
    *(_QWORD *)(v6 + 8) = a2 + 56;
  }
  else
  {
    *(_DWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a1 + 48) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x18000c470  mov     [rsp+arg_0], rbx
0x18000c475  push    rdi
0x18000c476  sub     rsp, 20h
0x18000c47a  mov     rax, [rcx+30h]
0x18000c47e  mov     rdi, rdx
0x18000c481  mov     rbx, rcx
0x18000c484  test    rax, rax
0x18000c487  jz      short loc_18000C4BD
0x18000c489  mov     rax, [rax+40h]
0x18000c48d  mov     r8d, [rax-30h]
0x18000c491  inc     r8d
0x18000c494  cmp     r8d, 8
0x18000c498  jb      short loc_18000C4BD
0x18000c49a  cmp     qword ptr [rcx+58h], 0
0x18000c49f  jnz     short loc_18000C4A6
0x18000c4a1  call    ?InitializeSupportForNavigationKeyedByLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAXXZ; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::InitializeSupportForNavigationKeyedByLocalName(void)
0x18000c4a6  mov     rax, [rbx+30h]
0x18000c4aa  mov     rdx, rdi
0x18000c4ad  mov     rcx, rbx
0x18000c4b0  mov     r8, [rax+40h]
0x18000c4b4  sub     r8, 38h ; '8'
0x18000c4b8  call    ?AddChildToChildrenTable@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAXPEAVConfigPathTagNode@@0@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChildToChildrenTable(ConfigPathTagNode *,ConfigPathTagNode *)
0x18000c4bd  mov     rax, [rbx+30h]
0x18000c4c1  test    rax, rax
0x18000c4c4  jnz     short loc_18000C4CF
0x18000c4c6  mov     [rdi+8], eax
0x18000c4c9  mov     [rbx+30h], rdi
0x18000c4cd  jmp     short loc_18000C4F9
0x18000c4cf  mov     rax, [rax+40h]
0x18000c4d3  mov     ecx, [rax-30h]
0x18000c4d6  inc     ecx
0x18000c4d8  mov     [rdi+8], ecx
0x18000c4db  lea     rcx, [rdi+38h]
0x18000c4df  mov     rdx, [rbx+30h]
0x18000c4e3  add     rdx, 38h ; '8'
0x18000c4e7  mov     rax, [rdx+8]
0x18000c4eb  mov     [rcx], rdx
0x18000c4ee  mov     [rcx+8], rax
0x18000c4f2  mov     [rax], rcx
0x18000c4f5  mov     [rdx+8], rcx
0x18000c4f9  mov     rbx, [rsp+28h+arg_0]
0x18000c4fe  add     rsp, 20h
0x18000c502  pop     rdi
0x18000c503  retn
```
