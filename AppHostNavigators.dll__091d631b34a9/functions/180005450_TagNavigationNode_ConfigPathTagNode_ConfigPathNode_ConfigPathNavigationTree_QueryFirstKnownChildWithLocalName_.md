# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryFirstKnownChildWithLocalName(ushort const *)

- ea: `0x180005450`
- end: `0x1800054af`
- name: `?QueryFirstKnownChildWithLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAPEAVConfigPathTagNode@@PEBG@Z`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004eb0`
- `0x18000c3b0`

## callees

- `0x180004d5c`
- `0x180005450`
- `0x1800055f0`
- `0x1800112e4`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryFirstKnownChildWithLocalName(
        __int64 a1,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  if ( NavigationNodeBase::IsWildCardName(a2) )
    return *(_QWORD *)(v4 + 48);
  v5 = *(_QWORD *)(v4 + 88);
  if ( v5 )
  {
    HASH_TABLE<FileSystemTagNode,unsigned short const *>::FindKey(v5, v2, &v8);
    return v8;
  }
  else
  {
    v6 = *(_QWORD *)(v4 + 48);
    if ( v6 )
    {
      if ( *(_QWORD *)(v6 + 16) == v2 )
        return *(_QWORD *)(v4 + 48);
      else
        return TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryNextKnownWithLocalName();
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005450  sub     rsp, 28h
0x180005454  mov     r9, rcx
0x180005457  xor     r8d, r8d
0x18000545a  mov     rcx, rdx; unsigned __int16 *
0x18000545d  mov     [rsp+28h+arg_10], r8
0x180005462  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x180005467  test    al, al
0x180005469  jz      short loc_180005471
0x18000546b  mov     r8, [r9+30h]
0x18000546f  jmp     short loc_1800054A7
0x180005471  mov     rcx, [r9+58h]
0x180005475  test    rcx, rcx
0x180005478  jz      short loc_18000548B
0x18000547a  lea     r8, [rsp+28h+arg_10]
0x18000547f  call    ?FindKey@?$HASH_TABLE@VFileSystemTagNode@@PEBG@@QEAAXPEBGPEAPEAVFileSystemTagNode@@@Z; HASH_TABLE<FileSystemTagNode,ushort const *>::FindKey(ushort const *,FileSystemTagNode * *)
0x180005484  mov     r8, [rsp+28h+arg_10]
0x180005489  jmp     short loc_1800054A7
0x18000548b  mov     rcx, [r9+30h]
0x18000548f  test    rcx, rcx
0x180005492  jz      short loc_1800054A7
0x180005494  cmp     [rcx+10h], rdx
0x180005498  jnz     short loc_18000549F
0x18000549a  mov     r8, rcx
0x18000549d  jmp     short loc_1800054A7
0x18000549f  call    ?QueryNextKnownWithLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAPEAVConfigPathTagNode@@PEBG@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryNextKnownWithLocalName(ushort const *)
0x1800054a4  mov     r8, rax
0x1800054a7  mov     rax, r8
0x1800054aa  add     rsp, 28h
0x1800054ae  retn
```
