# WxPowerPolicy::AddWakeOnIncomingActionFrame(ConfigurableActionFrameWakePatterns)

- ea: `0x1400d151c`
- end: `0x1400d17a5`
- name: `?AddWakeOnIncomingActionFrame@WxPowerPolicy@@QEAAHW4ConfigurableActionFrameWakePatterns@@@Z`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400c7038`
- `0x1400c7138`

## callees

- `0x14001eed0`
- `0x140024428`
- `0x1400d151c`
- `0x1400d17ac`
- `0x1400d1848`
- `0x1400d1984`
- `0x1400d233c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d1651`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d1651`

## pseudocode

```c
__int64 __fastcall WxPowerPolicy::AddWakeOnIncomingActionFrame(WxPowerPolicy *a1, int a2, int a3)
{
  unsigned int v3; // edi
  __int64 v5; // rax
  int v6; // r9d
  int v7; // edx
  int v8; // r8d
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  int v12; // r8d
  _QWORD *PoolWithTag; // rax
  int v14; // edx
  int v15; // r8d
  _QWORD *v16; // rsi
  char v17; // [rsp+58h] [rbp+10h] BYREF
  char v18; // [rsp+59h] [rbp+11h]
  char v19; // [rsp+5Ah] [rbp+12h]

  v3 = a2;
  if ( a2 >= 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        29,
        (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
        *((_QWORD *)a1 + 3),
        v3);
    }
    return 3221225485LL;
  }
  else
  {
    if ( *(_BYTE *)a1 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 0;
      v5 = *((_QWORD *)a1 + 3);
      v6 = 30;
LABEL_21:
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        v6,
        (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
        v5,
        v3);
      return 0;
    }
    if ( (unsigned __int8)WxPowerPolicy::CanConfigureActionFrameWakePattern() )
    {
      v10 = (_QWORD *)*((_QWORD *)a1 + 4);
      GetWakeOnIncomingActionFrameParameters(&v17, v3);
      while ( v10 )
      {
        if ( *((_DWORD *)v10 + 4) == 2
          && IsMatch(
               (const struct WakeOnIncomingActionFrameParameters *)&v17,
               (const struct WxWakeOnIncomingActionFramePowerOffload *)(v10 - 3)) )
        {
          if ( v11 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v11) = 2;
              WPP_RECORDER_SF_qD(
                WPP_GLOBAL_Control->DeviceExtension,
                v11,
                v12,
                32,
                (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
                *((_QWORD *)a1 + 3),
                v3);
            }
            return 255;
          }
          break;
        }
        v10 = (_QWORD *)*v10;
      }
      GetWakeOnIncomingActionFrameParameters(&v17, v3);
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x38u, 0x45507857u);
      v16 = PoolWithTag;
      if ( PoolWithTag )
      {
        PoolWithTag[1] = *((_QWORD *)a1 + 3);
        *((_BYTE *)PoolWithTag + 16) = 0;
        PoolWithTag[3] = 0;
        PoolWithTag[4] = 0;
        *((_BYTE *)PoolWithTag + 44) = 0;
        *PoolWithTag = &WxWakeOnClientDriverDiagnostic::`vftable';
        *((_BYTE *)PoolWithTag + 48) = v17;
        *((_BYTE *)PoolWithTag + 49) = v18;
        *((_BYTE *)PoolWithTag + 50) = v19;
        *((_DWORD *)PoolWithTag + 10) = 2;
        WxPowerPolicy::UpdatePowerOffloadEntryEnabledField(a1, (struct WxPowerOffload *)PoolWithTag);
        v16[3] = *((_QWORD *)a1 + 4);
        *((_QWORD *)a1 + 4) = v16 + 3;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 0;
        v5 = *((_QWORD *)a1 + 3);
        v6 = 34;
        goto LABEL_21;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          v15,
          33,
          (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
          *((_QWORD *)a1 + 3));
      }
      return 3221225473LL;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          v8,
          31,
          (__int64)WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids,
          *((_QWORD *)a1 + 3),
          v3);
      }
      return 3221225659LL;
    }
  }
}

```

## disassembly

```asm
0x1400d151c  mov     [rsp+arg_0], rbx
0x1400d1521  mov     [rsp+arg_10], rsi
0x1400d1526  push    rdi
0x1400d1527  sub     rsp, 40h
0x1400d152b  mov     edi, edx
0x1400d152d  mov     rbx, rcx
0x1400d1530  cmp     edx, 3
0x1400d1533  jge     loc_1400D174E
0x1400d1539  cmp     byte ptr [rcx], 0
0x1400d153c  jz      short loc_1400D1561
0x1400d153e  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d1545  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d154c  jz      loc_1400D1703
0x1400d1552  mov     rax, [rcx+18h]
0x1400d1556  mov     r9d, 1Eh
0x1400d155c  jmp     loc_1400D16DC
0x1400d1561  call    ?CanConfigureActionFrameWakePattern@WxPowerPolicy@@QEBA_NW4ConfigurableActionFrameWakePatterns@@@Z; WxPowerPolicy::CanConfigureActionFrameWakePattern(ConfigurableActionFrameWakePatterns)
0x1400d1566  test    al, al
0x1400d1568  jnz     short loc_1400D15B5
0x1400d156a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d1571  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d1578  jz      short loc_1400D15AB
0x1400d157a  mov     rax, [rbx+18h]
0x1400d157e  mov     r9d, 1Fh
0x1400d1584  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d158b  mov     dl, 4
0x1400d158d  mov     [rsp+48h+var_18], edi
0x1400d1591  mov     [rsp+48h+var_20], rax
0x1400d1596  lea     rax, WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids
0x1400d159d  mov     [rsp+48h+var_28], rax
0x1400d15a2  mov     rcx, [rcx+40h]
0x1400d15a6  call    WPP_RECORDER_SF_qD
0x1400d15ab  mov     eax, 0C00000BBh
0x1400d15b0  jmp     loc_1400D1794
0x1400d15b5  mov     rsi, [rbx+20h]
0x1400d15b9  lea     rcx, [rsp+48h+arg_8]
0x1400d15be  mov     edx, edi
0x1400d15c0  call    ?GetWakeOnIncomingActionFrameParameters@@YA?AUWakeOnIncomingActionFrameParameters@@W4ConfigurableActionFrameWakePatterns@@@Z; GetWakeOnIncomingActionFrameParameters(ConfigurableActionFrameWakePatterns)
0x1400d15c5  test    rsi, rsi
0x1400d15c8  jz      short loc_1400D1637
0x1400d15ca  lea     rdx, [rsi-18h]; struct WxWakeOnIncomingActionFramePowerOffload *
0x1400d15ce  cmp     dword ptr [rdx+28h], 2
0x1400d15d2  jnz     short loc_1400D15E2
0x1400d15d4  lea     rcx, [rsp+48h+arg_8]; struct WakeOnIncomingActionFrameParameters *
0x1400d15d9  call    ?IsMatch@@YA_NAEBUWakeOnIncomingActionFrameParameters@@AEBVWxWakeOnIncomingActionFramePowerOffload@@@Z; IsMatch(WakeOnIncomingActionFrameParameters const &,WxWakeOnIncomingActionFramePowerOffload const &)
0x1400d15de  test    al, al
0x1400d15e0  jnz     short loc_1400D15E7
0x1400d15e2  mov     rsi, [rsi]
0x1400d15e5  jmp     short loc_1400D15C5
0x1400d15e7  test    rdx, rdx
0x1400d15ea  jz      short loc_1400D1637
0x1400d15ec  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d15f3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d15fa  jz      short loc_1400D162D
0x1400d15fc  mov     rax, [rbx+18h]
0x1400d1600  mov     r9d, 20h ; ' '
0x1400d1606  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d160d  mov     dl, 2
0x1400d160f  mov     [rsp+48h+var_18], edi
0x1400d1613  mov     [rsp+48h+var_20], rax
0x1400d1618  lea     rax, WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids
0x1400d161f  mov     [rsp+48h+var_28], rax
0x1400d1624  mov     rcx, [rcx+40h]
0x1400d1628  call    WPP_RECORDER_SF_qD
0x1400d162d  mov     eax, 0FFh
0x1400d1632  jmp     loc_1400D1794
0x1400d1637  mov     edx, edi
0x1400d1639  lea     rcx, [rsp+48h+arg_8]
0x1400d163e  call    ?GetWakeOnIncomingActionFrameParameters@@YA?AUWakeOnIncomingActionFrameParameters@@W4ConfigurableActionFrameWakePatterns@@@Z; GetWakeOnIncomingActionFrameParameters(ConfigurableActionFrameWakePatterns)
0x1400d1643  mov     edx, 38h ; '8'; NumberOfBytes
0x1400d1648  mov     r8d, 45507857h; Tag
0x1400d164e  lea     ecx, [rdx-37h]; PoolType
0x1400d1651  call    cs:__imp_ExAllocatePoolWithTag
0x1400d1658  nop     dword ptr [rax+rax+00h]
0x1400d165d  mov     rsi, rax
0x1400d1660  test    rax, rax
0x1400d1663  jz      loc_1400D170A
0x1400d1669  mov     rcx, [rbx+18h]
0x1400d166d  mov     rdx, rsi; struct WxPowerOffload *
0x1400d1670  mov     [rax+8], rcx
0x1400d1674  mov     rcx, rbx; this
0x1400d1677  mov     byte ptr [rax+10h], 0
0x1400d167b  xor     eax, eax
0x1400d167d  mov     [rsi+18h], rax
0x1400d1681  mov     [rsi+20h], rax
0x1400d1685  mov     [rsi+2Ch], al
0x1400d1688  lea     rax, ??_7WxWakeOnClientDriverDiagnostic@@6B@; const WxWakeOnClientDriverDiagnostic::`vftable'
0x1400d168f  mov     [rsi], rax
0x1400d1692  mov     al, [rsp+48h+arg_8]
0x1400d1696  mov     [rsi+30h], al
0x1400d1699  mov     al, [rsp+48h+arg_9]
0x1400d169d  mov     [rsi+31h], al
0x1400d16a0  mov     al, [rsp+48h+arg_A]
0x1400d16a4  mov     [rsi+32h], al
0x1400d16a7  mov     dword ptr [rsi+28h], 2
0x1400d16ae  call    ?UpdatePowerOffloadEntryEnabledField@WxPowerPolicy@@AEAAXPEAVWxPowerOffload@@@Z; WxPowerPolicy::UpdatePowerOffloadEntryEnabledField(WxPowerOffload *)
0x1400d16b3  mov     rax, [rbx+20h]
0x1400d16b7  lea     rcx, [rsi+18h]
0x1400d16bb  mov     [rcx], rax
0x1400d16be  mov     [rbx+20h], rcx
0x1400d16c2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d16c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d16d0  jz      short loc_1400D1703
0x1400d16d2  mov     rax, [rbx+18h]
0x1400d16d6  mov     r9d, 22h ; '"'
0x1400d16dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d16e3  mov     dl, 4
0x1400d16e5  mov     [rsp+48h+var_18], edi
0x1400d16e9  mov     [rsp+48h+var_20], rax
0x1400d16ee  lea     rax, WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids
0x1400d16f5  mov     [rsp+48h+var_28], rax
0x1400d16fa  mov     rcx, [rcx+40h]
0x1400d16fe  call    WPP_RECORDER_SF_qD
0x1400d1703  xor     eax, eax
0x1400d1705  jmp     loc_1400D1794
0x1400d170a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d1711  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d1718  jz      short loc_1400D1747
0x1400d171a  mov     rax, [rbx+18h]
0x1400d171e  mov     r9d, 21h ; '!'
0x1400d1724  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d172b  mov     dl, 2
0x1400d172d  mov     [rsp+48h+var_20], rax
0x1400d1732  lea     rax, WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids
0x1400d1739  mov     [rsp+48h+var_28], rax
0x1400d173e  mov     rcx, [rcx+40h]
0x1400d1742  call    WPP_RECORDER_SF_q
0x1400d1747  mov     eax, 0C0000001h
0x1400d174c  jmp     short loc_1400D1794
0x1400d174e  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d1755  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d175c  jz      short loc_1400D178F
0x1400d175e  mov     rax, [rcx+18h]
0x1400d1762  mov     r9d, 1Dh
0x1400d1768  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d176f  mov     dl, 4
0x1400d1771  mov     [rsp+48h+var_18], edi
0x1400d1775  mov     [rsp+48h+var_20], rax
0x1400d177a  lea     rax, WPP_6c7cf644900539dd2087bb65bedb2bd0_Traceguids
0x1400d1781  mov     [rsp+48h+var_28], rax
0x1400d1786  mov     rcx, [rcx+40h]
0x1400d178a  call    WPP_RECORDER_SF_qD
0x1400d178f  mov     eax, 0C000000Dh
0x1400d1794  mov     rbx, [rsp+48h+arg_0]
0x1400d1799  mov     rsi, [rsp+48h+arg_10]
0x1400d179e  add     rsp, 40h
0x1400d17a2  pop     rdi
0x1400d17a3  retn
```
