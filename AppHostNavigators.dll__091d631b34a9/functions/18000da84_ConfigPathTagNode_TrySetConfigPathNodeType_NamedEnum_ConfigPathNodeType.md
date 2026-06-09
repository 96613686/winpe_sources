# ConfigPathTagNode::TrySetConfigPathNodeType(NamedEnum<ConfigPathNodeType> &)

- ea: `0x18000da84`
- end: `0x18000dac1`
- name: `?TrySetConfigPathNodeType@ConfigPathTagNode@@IEAA_NAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004164`
- `0x18000c9bc`
- `0x18000c9e8`

## callees

- `0x18000c968`
- `0x18000da84`

## pseudocode

```c
char __fastcall ConfigPathTagNode::TrySetConfigPathNodeType(__int64 a1, _OWORD *a2)
{
  _OWORD *v2; // r9
  _OWORD *v3; // r10
  __int64 v4; // r10
  unsigned int NodeTypePrecedence; // eax
  unsigned int v6; // r8d
  char result; // al

  v2 = (_OWORD *)(a1 + 104);
  v3 = a2;
  if ( *(_DWORD *)(a1 + 104) )
  {
    ConfigPathTagNode::GetNodeTypePrecedence(a1 + 104);
    NodeTypePrecedence = ConfigPathTagNode::GetNodeTypePrecedence(v4);
    if ( NodeTypePrecedence >= v6 )
      return 0;
  }
  result = 1;
  *v2 = *v3;
  return result;
}

```

## disassembly

```asm
0x18000da84  sub     rsp, 28h
0x18000da88  lea     r9, [rcx+68h]
0x18000da8c  mov     r10, rdx
0x18000da8f  cmp     dword ptr [r9], 0
0x18000da93  jz      short loc_18000DAB1
0x18000da95  mov     rcx, r9
0x18000da98  call    ?GetNodeTypePrecedence@ConfigPathTagNode@@CAKAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetNodeTypePrecedence(NamedEnum<ConfigPathNodeType> &)
0x18000da9d  mov     rcx, r10
0x18000daa0  mov     r8d, eax
0x18000daa3  call    ?GetNodeTypePrecedence@ConfigPathTagNode@@CAKAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetNodeTypePrecedence(NamedEnum<ConfigPathNodeType> &)
0x18000daa8  cmp     eax, r8d
0x18000daab  jb      short loc_18000DAB1
0x18000daad  xor     al, al
0x18000daaf  jmp     short loc_18000DABC
0x18000dab1  movups  xmm0, xmmword ptr [r10]
0x18000dab5  mov     al, 1
0x18000dab7  movdqu  xmmword ptr [r9], xmm0
0x18000dabc  add     rsp, 28h
0x18000dac0  retn
```
