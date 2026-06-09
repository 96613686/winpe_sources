# TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(ushort const *)

- ea: `0x180006360`
- end: `0x1800063bf`
- name: `?QueryFirstKnownChildWithLocalName@?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@AEAAPEAVConfigLocationTagNode@@PEBG@Z`
- size: `95`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006130`
- `0x180009d54`
- `0x180009e80`
- `0x18000a030`
- `0x18000acd0`
- `0x18000aea0`
- `0x18000b360`

## callees

- `0x180004d5c`
- `0x180006360`
- `0x180006500`
- `0x1800112e4`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryFirstKnownChildWithLocalName(
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
    return *(_QWORD *)(v4 + 32);
  v5 = *(_QWORD *)(v4 + 72);
  if ( v5 )
  {
    HASH_TABLE<FileSystemTagNode,unsigned short const *>::FindKey(v5, v2, &v8);
    return v8;
  }
  else
  {
    v6 = *(_QWORD *)(v4 + 32);
    if ( v6 )
    {
      if ( *(_QWORD *)(v6 + 16) == v2 )
        return *(_QWORD *)(v4 + 32);
      else
        return TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(v6, v2);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180006360  sub     rsp, 28h
0x180006364  mov     r9, rcx
0x180006367  xor     r8d, r8d
0x18000636a  mov     rcx, rdx; unsigned __int16 *
0x18000636d  mov     [rsp+28h+arg_10], r8
0x180006372  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x180006377  test    al, al
0x180006379  jz      short loc_180006381
0x18000637b  mov     r8, [r9+20h]
0x18000637f  jmp     short loc_1800063B7
0x180006381  mov     rcx, [r9+48h]
0x180006385  test    rcx, rcx
0x180006388  jz      short loc_18000639B
0x18000638a  lea     r8, [rsp+28h+arg_10]
0x18000638f  call    ?FindKey@?$HASH_TABLE@VFileSystemTagNode@@PEBG@@QEAAXPEBGPEAPEAVFileSystemTagNode@@@Z; HASH_TABLE<FileSystemTagNode,ushort const *>::FindKey(ushort const *,FileSystemTagNode * *)
0x180006394  mov     r8, [rsp+28h+arg_10]
0x180006399  jmp     short loc_1800063B7
0x18000639b  mov     rcx, [r9+20h]
0x18000639f  test    rcx, rcx
0x1800063a2  jz      short loc_1800063B7
0x1800063a4  cmp     [rcx+10h], rdx
0x1800063a8  jnz     short loc_1800063AF
0x1800063aa  mov     r8, rcx
0x1800063ad  jmp     short loc_1800063B7
0x1800063af  call    ?QueryNextKnownWithLocalName@?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@AEAAPEAVConfigTagNode@@PEBG@Z; TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(ushort const *)
0x1800063b4  mov     r8, rax
0x1800063b7  mov     rax, r8
0x1800063ba  add     rsp, 28h
0x1800063be  retn
```
