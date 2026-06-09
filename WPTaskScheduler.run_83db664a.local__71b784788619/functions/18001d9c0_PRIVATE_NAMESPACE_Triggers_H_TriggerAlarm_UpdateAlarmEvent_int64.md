# PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UpdateAlarmEvent(__int64)

- ea: `0x18001d9c0`
- end: `0x18001db82`
- name: `?UpdateAlarmEvent@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAAJ_J@Z`
- size: `450`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d920`

## callees

- `0x180001cd0`
- `0x180005c30`
- `0x18000d8c0`
- `0x18001d9c0`
- `0x180020c02`
- `0x180020c30`

## import_xrefs

- `TimeBrokerClient!TbUpdateCEvent` at `0x18001db55`
- `TimeBrokerClient!TbUpdateCEvent` at `0x18001db55`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UpdateAlarmEvent(
        PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *this)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int64 v4; // rcx
  _OWORD v6[3]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v7[48]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v8; // [rsp+80h] [rbp-80h]
  __int128 v9; // [rsp+90h] [rbp-70h]
  __int128 v10; // [rsp+A0h] [rbp-60h]
  __int128 v11; // [rsp+B0h] [rbp-50h]
  __int128 v12; // [rsp+C0h] [rbp-40h]
  __int128 v13; // [rsp+D0h] [rbp-30h]
  __int128 v14; // [rsp+E0h] [rbp-20h]
  __int128 v15; // [rsp+F0h] [rbp-10h]
  __int128 v16; // [rsp+100h] [rbp+0h]
  __int128 v17; // [rsp+110h] [rbp+10h]
  __int128 v18; // [rsp+120h] [rbp+20h]
  __int128 v19; // [rsp+130h] [rbp+30h]
  __int64 v20; // [rsp+140h] [rbp+40h]
  _OWORD v21[15]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v22; // [rsp+240h] [rbp+140h]
  TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+250h] [rbp+150h] BYREF
  __int128 v24; // [rsp+330h] [rbp+230h]

  if ( *((_DWORD *)this + 28) )
  {
    v2 = *(_OWORD *)((char *)this + 88);
    v6[0] = *(_OWORD *)((char *)this + 72);
    v3 = *(_OWORD *)((char *)this + 104);
  }
  else
  {
    if ( !*((_DWORD *)this + 62) )
      return 2147500037LL;
    v2 = *((_OWORD *)this + 14);
    v6[0] = *((_OWORD *)this + 13);
    v3 = *((_OWORD *)this + 15);
  }
  v6[2] = v3;
  v6[1] = v2;
  TimeInfo::TimeInfo(&TimeZoneInformation);
  if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
    TimeInfo::SetUTC(&TimeZoneInformation, (const struct TimeValue *)v6);
  else
    TimeInfo::SetLocal(&TimeZoneInformation, (const struct TimeValue *)v6);
  memset_0(v7, 0, 0xF8u);
  v4 = *((_QWORD *)this + 38);
  *(_OWORD *)&v7[8] = v24;
  *(_QWORD *)&v7[28] = 1;
  *(_DWORD *)v7 = 4;
  v21[0] = *(_OWORD *)v7;
  *(_DWORD *)&v7[24] = 0;
  v21[2] = *(_OWORD *)&v7[32];
  BYTE5(v8) = 1;
  v21[1] = *(_OWORD *)&v7[16];
  v22 = v20;
  v21[4] = v9;
  v21[3] = v8;
  v21[6] = v11;
  v21[5] = v10;
  v21[8] = v13;
  v21[7] = v12;
  v21[10] = v15;
  v21[9] = v14;
  v21[12] = v17;
  v21[11] = v16;
  v21[14] = v19;
  v21[13] = v18;
  return TbUpdateCEvent(v4, v21);
}

```

## disassembly

```asm
0x18001d9c0  mov     [rsp-8+arg_8], rbx
0x18001d9c5  push    rbp
0x18001d9c6  lea     rbp, [rsp-270h]
0x18001d9ce  sub     rsp, 370h
0x18001d9d5  mov     rax, cs:__security_cookie
0x18001d9dc  xor     rax, rsp
0x18001d9df  mov     [rbp+270h+var_10], rax
0x18001d9e6  cmp     dword ptr [rcx+70h], 0
0x18001d9ea  mov     rbx, rcx
0x18001d9ed  jz      short loc_18001DA02
0x18001d9ef  movups  xmm0, xmmword ptr [rcx+48h]
0x18001d9f3  movups  xmm1, xmmword ptr [rcx+58h]
0x18001d9f7  movups  [rsp+370h+var_350], xmm0
0x18001d9fc  movups  xmm0, xmmword ptr [rcx+68h]
0x18001da00  jmp     short loc_18001DA29
0x18001da02  cmp     dword ptr [rcx+0F8h], 0
0x18001da09  jz      loc_18001DB5D
0x18001da0f  movups  xmm0, xmmword ptr [rcx+0D0h]
0x18001da16  movups  xmm1, xmmword ptr [rcx+0E0h]
0x18001da1d  movups  [rsp+370h+var_350], xmm0
0x18001da22  movups  xmm0, xmmword ptr [rcx+0F0h]
0x18001da29  lea     rcx, [rbp+270h+TimeZoneInformation]; lpTimeZoneInformation
0x18001da30  movups  [rsp+370h+var_330], xmm0
0x18001da35  movups  [rsp+370h+var_340], xmm1
0x18001da3a  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18001da3f  mov     rax, [rbx+0B0h]
0x18001da46  lea     rdx, [rsp+370h+var_350]; struct TimeValue *
0x18001da4b  lea     rcx, [rbp+270h+TimeZoneInformation]; lpTimeZoneInformation
0x18001da52  test    byte ptr [rax+2Ch], 8
0x18001da56  jz      short loc_18001DA5F
0x18001da58  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18001da5d  jmp     short loc_18001DA64
0x18001da5f  call    ?SetLocal@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetLocal(TimeValue const &)
0x18001da64  xor     edx, edx; Val
0x18001da66  lea     rcx, [rsp+370h+var_320]; void *
0x18001da6b  mov     r8d, 0F8h; Size
0x18001da71  call    memset_0
0x18001da76  movaps  xmm0, [rbp+270h+var_40]
0x18001da7d  lea     rdx, [rbp+270h+var_220]
0x18001da81  mov     rax, [rbp+270h+var_230]
0x18001da85  mov     rcx, [rbx+130h]
0x18001da8c  movdqu  [rsp+370h+var_320+8], xmm0
0x18001da92  mov     qword ptr [rsp+370h+var_304], 1
0x18001da9b  mov     dword ptr [rsp+370h+var_320], 4
0x18001daa3  movaps  xmm0, [rsp+370h+var_320]
0x18001daa8  movups  [rbp+270h+var_220], xmm0
0x18001daac  mov     [rsp+370h+var_308], 0
0x18001dab4  movaps  xmm0, [rsp+370h+var_304+4]
0x18001dab9  movaps  xmm1, xmmword ptr [rsp+60h]
0x18001dabe  movups  [rbp+270h+var_200], xmm0
0x18001dac2  mov     [rbp+270h+var_2EB], 1
0x18001dac6  movaps  xmm0, [rbp+270h+var_2E0]
0x18001daca  movups  [rbp+270h+var_210], xmm1
0x18001dace  mov     [rbp+270h+var_130], rax
0x18001dad5  movaps  xmm1, xmmword ptr [rbp-80h]
0x18001dad9  movups  [rbp+270h+var_1E0], xmm0
0x18001dae0  movaps  xmm0, [rbp+270h+var_2C0]
0x18001dae4  movups  [rbp+270h+var_1F0], xmm1
0x18001daeb  movaps  xmm1, [rbp+270h+var_2D0]
0x18001daef  movups  [rbp+270h+var_1C0], xmm0
0x18001daf6  movaps  xmm0, [rbp+270h+var_2A0]
0x18001dafa  movups  [rbp+270h+var_1D0], xmm1
0x18001db01  movaps  xmm1, [rbp+270h+var_2B0]
0x18001db05  movups  [rbp+270h+var_1A0], xmm0
0x18001db0c  movaps  xmm0, [rbp+270h+var_280]
0x18001db10  movups  [rbp+270h+var_1B0], xmm1
0x18001db17  movaps  xmm1, [rbp+270h+var_290]
0x18001db1b  movups  [rbp+270h+var_180], xmm0
0x18001db22  movaps  xmm0, [rbp+270h+var_260]
0x18001db26  movups  [rbp+270h+var_190], xmm1
0x18001db2d  movaps  xmm1, [rbp+270h+var_270]
0x18001db31  movups  [rbp+270h+var_160], xmm0
0x18001db38  movaps  xmm0, [rbp+270h+var_240]
0x18001db3c  movups  [rbp+270h+var_170], xmm1
0x18001db43  movaps  xmm1, [rbp+270h+var_250]
0x18001db47  movups  [rbp+270h+var_140], xmm0
0x18001db4e  movups  [rbp+270h+var_150], xmm1
0x18001db55  call    cs:__imp_TbUpdateCEvent
0x18001db5b  jmp     short loc_18001DB62
0x18001db5d  mov     eax, 80004005h
0x18001db62  mov     rcx, [rbp+270h+var_10]
0x18001db69  xor     rcx, rsp; StackCookie
0x18001db6c  call    __security_check_cookie
0x18001db71  mov     rbx, [rsp+370h+arg_8]
0x18001db79  add     rsp, 370h
0x18001db80  pop     rbp
0x18001db81  retn
```
