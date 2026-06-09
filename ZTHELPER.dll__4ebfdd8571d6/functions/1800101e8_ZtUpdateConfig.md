# ZtUpdateConfig

- ea: `0x1800101e8`
- end: `0x18001026d`
- name: `ZtUpdateConfig`
- size: `133`
- prototype: `void __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800039e4`
- `0x1800046ec`

## callees

- `0x180004218`
- `0x1800101e8`

## pseudocode

```c
void __fastcall ZtUpdateConfig(__int64 a1, __int64 a2, _BYTE *a3)
{
  _DWORD *v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r10
  __int128 v7; // xmm1
  __int128 v8; // xmm0

  WxZeroOut<_DNS_ZT_CONFIG>(a3);
  if ( v4 )
  {
    if ( v5 )
    {
      *(_OWORD *)v5 = *(_OWORD *)v4;
      *(_OWORD *)(v5 + 16) = *(_OWORD *)(v4 + 16);
      *(_OWORD *)(v5 + 32) = *(_OWORD *)(v4 + 32);
      *(_QWORD *)(v5 + 48) = *(_QWORD *)(v4 + 48);
    }
    if ( !g_fVelocityZtdns )
      *(_DWORD *)(v6 + 16) = 0;
    v7 = *(_OWORD *)(v6 + 16);
    *(_OWORD *)v4 = *(_OWORD *)v6;
    v8 = *(_OWORD *)(v6 + 32);
    *(_OWORD *)(v4 + 16) = v7;
    *(_QWORD *)&v7 = *(_QWORD *)(v6 + 48);
    *(_OWORD *)(v4 + 32) = v8;
    *(_QWORD *)(v4 + 48) = v7;
    *v3 = 1;
  }
}

```

## disassembly

```asm
0x1800101e8  sub     rsp, 28h
0x1800101ec  mov     r10, rcx
0x1800101ef  mov     rcx, r8
0x1800101f2  call    ??$WxZeroOut@U_DNS_ZT_CONFIG@@@@YAXPEAU_DNS_ZT_CONFIG@@@Z; WxZeroOut<_DNS_ZT_CONFIG>(_DNS_ZT_CONFIG *)
0x1800101f7  test    r8, r8
0x1800101fa  jz      short loc_180010268
0x1800101fc  test    r9, r9
0x1800101ff  jz      short loc_180010229
0x180010201  movups  xmm0, xmmword ptr [r8]
0x180010205  movups  xmmword ptr [r9], xmm0
0x180010209  movups  xmm1, xmmword ptr [r8+10h]
0x18001020e  movups  xmmword ptr [r9+10h], xmm1
0x180010213  movups  xmm0, xmmword ptr [r8+20h]
0x180010218  movups  xmmword ptr [r9+20h], xmm0
0x18001021d  movsd   xmm1, qword ptr [r8+30h]
0x180010223  movsd   qword ptr [r9+30h], xmm1
0x180010229  cmp     cs:g_fVelocityZtdns, 0
0x180010230  jnz     short loc_18001023A
0x180010232  mov     dword ptr [r10+10h], 0
0x18001023a  movaps  xmm0, xmmword ptr [r10]
0x18001023e  movaps  xmm1, xmmword ptr [r10+10h]
0x180010243  movups  xmmword ptr [r8], xmm0
0x180010247  movaps  xmm0, xmmword ptr [r10+20h]
0x18001024c  movups  xmmword ptr [r8+10h], xmm1
0x180010251  movsd   xmm1, qword ptr [r10+30h]
0x180010257  movups  xmmword ptr [r8+20h], xmm0
0x18001025c  movsd   qword ptr [r8+30h], xmm1
0x180010262  mov     dword ptr [rdx], 1
0x180010268  add     rsp, 28h
0x18001026c  retn
```
