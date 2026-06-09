# BampComputePpmPolicyFromWindowState

- ea: `0x1400110d8`
- end: `0x140011156`
- name: `BampComputePpmPolicyFromWindowState`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010a30`

## callees

- `0x140001814`
- `0x140011090`
- `0x1400110d8`
- `0x1400113a0`
- `0x1400113f0`

## pseudocode

```c
__int64 __fastcall BampComputePpmPolicyFromWindowState(__int64 a1)
{
  BOOL v1; // ebx
  char v2; // al
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  v4 = 0;
  v5 = 0;
  BampThrottledProcessGetEffectiveState(a1, &v4);
  if ( (unsigned int)Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline() )
  {
    BampAcquireThrottlingWorkerLock();
    v1 = HIDWORD(xmmword_140007540) == 0;
    BampReleaseThrottlingWorkerLock();
    v2 = v4;
    if ( (v4 & 0x12) != 0 )
      return v1 ? 9 : 7;
  }
  else
  {
    v2 = v4;
    if ( (v4 & 0x12) != 0 )
      return 7;
  }
  if ( (v2 & 4) != 0 )
    return 6;
  else
    return (v2 & 8 | 0x20u) >> 3;
}

```

## disassembly

```asm
0x1400110d8  push    rbx
0x1400110da  sub     rsp, 40h
0x1400110de  xorps   xmm0, xmm0
0x1400110e1  lea     rdx, [rsp+48h+var_28]
0x1400110e6  xor     eax, eax
0x1400110e8  movups  [rsp+48h+var_28], xmm0
0x1400110ed  mov     [rsp+48h+var_18], rax
0x1400110f2  call    BampThrottledProcessGetEffectiveState
0x1400110f7  call    Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline
0x1400110fc  test    eax, eax
0x1400110fe  jz      short loc_140011129
0x140011100  call    BampAcquireThrottlingWorkerLock
0x140011105  xor     ebx, ebx
0x140011107  cmp     dword ptr cs:xmmword_140007540+0Ch, ebx
0x14001110d  setz    bl
0x140011110  call    BampReleaseThrottlingWorkerLock
0x140011115  mov     eax, dword ptr [rsp+48h+var_28]
0x140011119  test    al, 12h
0x14001111b  jz      short loc_140011131
0x14001111d  neg     ebx
0x14001111f  sbb     eax, eax
0x140011121  and     eax, 2
0x140011124  add     eax, 7
0x140011127  jmp     short loc_14001114F
0x140011129  mov     eax, dword ptr [rsp+48h+var_28]
0x14001112d  test    al, 12h
0x14001112f  jnz     short loc_14001114A
0x140011131  test    al, 4
0x140011133  jz      short loc_14001113C
0x140011135  mov     eax, 6
0x14001113a  jmp     short loc_14001114F
0x14001113c  movzx   eax, al
0x14001113f  and     eax, 8
0x140011142  or      eax, 20h
0x140011145  shr     eax, 3
0x140011148  jmp     short loc_14001114F
0x14001114a  mov     eax, 7
0x14001114f  add     rsp, 40h
0x140011153  pop     rbx
0x140011154  retn
```
