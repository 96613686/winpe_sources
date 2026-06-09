# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::TryGetLastChildWithLocalName<ConfigPathTagNode>(ushort const *,ConfigPathTagNode * *)

- ea: `0x18000c3b0`
- end: `0x18000c416`
- name: `??$TryGetLastChildWithLocalName@VConfigPathTagNode@@@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@QEAA_NPEBGPEAPEAVConfigPathTagNode@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c50c`
- `0x18000c9e8`

## callees

- `0x180005450`
- `0x180005684`
- `0x18000c3b0`

## pseudocode

```c
bool __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::TryGetLastChildWithLocalName<ConfigPathTagNode>(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 PreviousKnownWithLocalName; // rbx
  __int64 FirstKnownChildWithLocalName; // rax
  __int64 v6; // rax

  PreviousKnownWithLocalName = 0;
  *a3 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    FirstKnownChildWithLocalName = TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryFirstKnownChildWithLocalName(
                                     a1,
                                     a2);
    if ( FirstKnownChildWithLocalName )
      PreviousKnownWithLocalName = *(_QWORD *)(FirstKnownChildWithLocalName + 80) - 72LL;
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 48);
    if ( v6 )
    {
      PreviousKnownWithLocalName = *(_QWORD *)(v6 + 64) - 56LL;
      if ( *(const unsigned __int16 **)(PreviousKnownWithLocalName + 16) != a2 )
        PreviousKnownWithLocalName = TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryPreviousKnownWithLocalName(*(_QWORD *)(v6 + 64) - 56LL);
    }
  }
  *a3 = PreviousKnownWithLocalName;
  return PreviousKnownWithLocalName != 0;
}

```

## disassembly

```asm
0x18000c3b0  mov     [rsp+arg_0], rbx
0x18000c3b5  push    rdi
0x18000c3b6  sub     rsp, 20h
0x18000c3ba  xor     ebx, ebx
0x18000c3bc  mov     qword ptr [r8], 0
0x18000c3c3  mov     rdi, r8
0x18000c3c6  cmp     [rcx+58h], rbx
0x18000c3ca  jz      short loc_18000C3E0
0x18000c3cc  call    ?QueryFirstKnownChildWithLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAPEAVConfigPathTagNode@@PEBG@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryFirstKnownChildWithLocalName(ushort const *)
0x18000c3d1  test    rax, rax
0x18000c3d4  jz      short loc_18000C402
0x18000c3d6  mov     rbx, [rax+50h]
0x18000c3da  sub     rbx, 48h ; 'H'
0x18000c3de  jmp     short loc_18000C402
0x18000c3e0  mov     rax, [rcx+30h]
0x18000c3e4  test    rax, rax
0x18000c3e7  jz      short loc_18000C402
0x18000c3e9  mov     rbx, [rax+40h]
0x18000c3ed  add     rbx, 0FFFFFFFFFFFFFFC8h
0x18000c3f1  cmp     [rbx+10h], rdx
0x18000c3f5  jz      short loc_18000C402
0x18000c3f7  mov     rcx, rbx
0x18000c3fa  call    ?QueryPreviousKnownWithLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAPEAVConfigPathTagNode@@PEBG@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryPreviousKnownWithLocalName(ushort const *)
0x18000c3ff  mov     rbx, rax
0x18000c402  test    rbx, rbx
0x18000c405  mov     [rdi], rbx
0x18000c408  mov     rbx, [rsp+28h+arg_0]
0x18000c40d  setnz   al
0x18000c410  add     rsp, 20h
0x18000c414  pop     rdi
0x18000c415  retn
```
