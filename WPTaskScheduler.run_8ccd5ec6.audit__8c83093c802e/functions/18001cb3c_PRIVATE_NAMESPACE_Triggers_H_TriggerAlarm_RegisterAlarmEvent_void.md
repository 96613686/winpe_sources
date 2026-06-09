# PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::RegisterAlarmEvent(void)

- ea: `0x18001cb3c`
- end: `0x18001cd51`
- name: `?RegisterAlarmEvent@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ`
- size: `533`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cd60`
- `0x18001d650`

## callees

- `0x180001cd0`
- `0x180005c30`
- `0x18000d8c0`
- `0x18001cb3c`
- `0x180020a64`
- `0x180020c02`
- `0x180020c30`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001cd1a`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001cd1a`
- `TimeBrokerClient!TbCreateCEvent` at `0x18001ccd5`
- `TimeBrokerClient!TbCreateCEvent` at `0x18001ccd5`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::RegisterAlarmEvent(
        PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *this)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  int CEvent; // edi
  int v5; // eax
  _OWORD v7[3]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[48]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v9; // [rsp+A0h] [rbp-60h]
  __int128 v10; // [rsp+B0h] [rbp-50h]
  __int128 v11; // [rsp+C0h] [rbp-40h]
  __int128 v12; // [rsp+D0h] [rbp-30h]
  __int128 v13; // [rsp+E0h] [rbp-20h]
  __int128 v14; // [rsp+F0h] [rbp-10h]
  __int128 v15; // [rsp+100h] [rbp+0h]
  __int128 v16; // [rsp+110h] [rbp+10h]
  __int128 v17; // [rsp+120h] [rbp+20h]
  __int128 v18; // [rsp+130h] [rbp+30h]
  __int128 v19; // [rsp+140h] [rbp+40h]
  __int128 v20; // [rsp+150h] [rbp+50h]
  __int64 v21; // [rsp+160h] [rbp+60h]
  _OWORD v22[15]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v23; // [rsp+260h] [rbp+160h]
  TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+270h] [rbp+170h] BYREF
  __int128 v25; // [rsp+350h] [rbp+250h]

  if ( *((_DWORD *)this + 28) )
  {
    v2 = *(_OWORD *)((char *)this + 88);
    v7[0] = *(_OWORD *)((char *)this + 72);
    v3 = *(_OWORD *)((char *)this + 104);
  }
  else
  {
    if ( !*((_DWORD *)this + 62) )
      return (unsigned int)-2147467259;
    v2 = *((_OWORD *)this + 14);
    v7[0] = *((_OWORD *)this + 13);
    v3 = *((_OWORD *)this + 15);
  }
  v7[2] = v3;
  v7[1] = v2;
  TimeInfo::TimeInfo(&TimeZoneInformation);
  if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
    TimeInfo::SetUTC(&TimeZoneInformation, (const struct TimeValue *)v7);
  else
    TimeInfo::SetLocal(&TimeZoneInformation, (const struct TimeValue *)v7);
  memset_0(v8, 0, 0xF8u);
  *(_OWORD *)&v8[8] = v25;
  *(_QWORD *)&v8[28] = 1;
  *(_DWORD *)v8 = 4;
  v22[0] = *(_OWORD *)v8;
  *(_DWORD *)&v8[24] = 0;
  v22[2] = *(_OWORD *)&v8[32];
  BYTE5(v9) = 1;
  v22[1] = *(_OWORD *)&v8[16];
  v23 = v21;
  v22[4] = v10;
  v22[3] = v9;
  v22[6] = v12;
  v22[5] = v11;
  v22[8] = v14;
  v22[7] = v13;
  v22[10] = v16;
  v22[9] = v15;
  v22[12] = v18;
  v22[11] = v17;
  v22[14] = v20;
  v22[13] = v19;
  CEvent = TbCreateCEvent(v22, (char *)this + 304);
  if ( CEvent >= 0 )
  {
    v5 = RtlSubscribeWnfStateChangeNotification(
           (char *)this + 312,
           *((_QWORD *)this + 38),
           0,
           CScheduleMgr::BaseBrokerCallback,
           *((_QWORD *)this + 22),
           0,
           0,
           0);
    if ( v5 < 0 )
      return (unsigned int)HRESULTFromNTSTATUS(v5);
  }
  return (unsigned int)CEvent;
}

```

## disassembly

```asm
0x18001cb3c  push    rbp
0x18001cb3e  push    rbx
0x18001cb3f  push    rsi
0x18001cb40  push    rdi
0x18001cb41  lea     rbp, [rsp-298h]
0x18001cb49  sub     rsp, 398h
0x18001cb50  mov     rax, cs:__security_cookie
0x18001cb57  xor     rax, rsp
0x18001cb5a  mov     [rbp+2B0h+var_30], rax
0x18001cb61  cmp     dword ptr [rcx+70h], 0
0x18001cb65  mov     rbx, rcx
0x18001cb68  jz      short loc_18001CB7D
0x18001cb6a  movups  xmm0, xmmword ptr [rcx+48h]
0x18001cb6e  movups  xmm1, xmmword ptr [rcx+58h]
0x18001cb72  movups  [rsp+3B0h+var_370], xmm0
0x18001cb77  movups  xmm0, xmmword ptr [rcx+68h]
0x18001cb7b  jmp     short loc_18001CBA4
0x18001cb7d  cmp     dword ptr [rcx+0F8h], 0
0x18001cb84  jz      loc_18001CD2F
0x18001cb8a  movups  xmm0, xmmword ptr [rcx+0D0h]
0x18001cb91  movups  xmm1, xmmword ptr [rcx+0E0h]
0x18001cb98  movups  [rsp+3B0h+var_370], xmm0
0x18001cb9d  movups  xmm0, xmmword ptr [rcx+0F0h]
0x18001cba4  lea     rcx, [rbp+2B0h+TimeZoneInformation]; lpTimeZoneInformation
0x18001cbab  movups  [rsp+3B0h+var_350], xmm0
0x18001cbb0  movups  [rsp+3B0h+var_360], xmm1
0x18001cbb5  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18001cbba  mov     rax, [rbx+0B0h]
0x18001cbc1  lea     rdx, [rsp+3B0h+var_370]; struct TimeValue *
0x18001cbc6  lea     rcx, [rbp+2B0h+TimeZoneInformation]; lpTimeZoneInformation
0x18001cbcd  test    byte ptr [rax+2Ch], 8
0x18001cbd1  jz      short loc_18001CBDA
0x18001cbd3  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18001cbd8  jmp     short loc_18001CBDF
0x18001cbda  call    ?SetLocal@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetLocal(TimeValue const &)
0x18001cbdf  xor     edx, edx; Val
0x18001cbe1  lea     rcx, [rsp+3B0h+var_340]; void *
0x18001cbe6  mov     r8d, 0F8h; Size
0x18001cbec  call    memset_0
0x18001cbf1  movaps  xmm0, [rbp+2B0h+var_60]
0x18001cbf8  lea     rsi, [rbx+130h]
0x18001cbff  mov     rax, [rbp+2B0h+var_250]
0x18001cc03  lea     rcx, [rbp+2B0h+var_240]
0x18001cc07  movdqu  [rsp+3B0h+var_340+8], xmm0
0x18001cc0d  mov     qword ptr [rbp+2B0h+var_324], 1
0x18001cc15  mov     rdx, rsi
0x18001cc18  mov     dword ptr [rsp+3B0h+var_340], 4
0x18001cc20  movaps  xmm0, [rsp+3B0h+var_340]
0x18001cc25  movups  [rbp+2B0h+var_240], xmm0
0x18001cc29  mov     [rbp+2B0h+var_328], 0
0x18001cc30  movaps  xmm0, [rbp+2B0h+var_324+4]
0x18001cc34  movaps  xmm1, xmmword ptr [rbp-80h]
0x18001cc38  movups  [rbp+2B0h+var_220], xmm0
0x18001cc3f  mov     [rbp+2B0h+var_30B], 1
0x18001cc43  movaps  xmm0, [rbp+2B0h+var_300]
0x18001cc47  movups  [rbp+2B0h+var_230], xmm1
0x18001cc4e  mov     [rbp+2B0h+var_150], rax
0x18001cc55  movaps  xmm1, xmmword ptr [rbp-60h]
0x18001cc59  movups  [rbp+2B0h+var_200], xmm0
0x18001cc60  movaps  xmm0, [rbp+2B0h+var_2E0]
0x18001cc64  movups  [rbp+2B0h+var_210], xmm1
0x18001cc6b  movaps  xmm1, [rbp+2B0h+var_2F0]
0x18001cc6f  movups  [rbp+2B0h+var_1E0], xmm0
0x18001cc76  movaps  xmm0, [rbp+2B0h+var_2C0]
0x18001cc7a  movups  [rbp+2B0h+var_1F0], xmm1
0x18001cc81  movaps  xmm1, [rbp+2B0h+var_2D0]
0x18001cc85  movups  [rbp+2B0h+var_1C0], xmm0
0x18001cc8c  movaps  xmm0, [rbp+2B0h+var_2A0]
0x18001cc90  movups  [rbp+2B0h+var_1D0], xmm1
0x18001cc97  movaps  xmm1, [rbp+2B0h+var_2B0]
0x18001cc9b  movups  [rbp+2B0h+var_1A0], xmm0
0x18001cca2  movaps  xmm0, [rbp+2B0h+var_280]
0x18001cca6  movups  [rbp+2B0h+var_1B0], xmm1
0x18001ccad  movaps  xmm1, [rbp+2B0h+var_290]
0x18001ccb1  movups  [rbp+2B0h+var_180], xmm0
0x18001ccb8  movaps  xmm0, [rbp+2B0h+var_260]
0x18001ccbc  movups  [rbp+2B0h+var_190], xmm1
0x18001ccc3  movaps  xmm1, [rbp+2B0h+var_270]
0x18001ccc7  movups  [rbp+2B0h+var_160], xmm0
0x18001ccce  movups  [rbp+2B0h+var_170], xmm1
0x18001ccd5  call    cs:__imp_TbCreateCEvent
0x18001ccdb  mov     edi, eax
0x18001ccdd  test    eax, eax
0x18001ccdf  js      short loc_18001CD34
0x18001cce1  mov     r8, [rbx+0B0h]
0x18001cce8  lea     rcx, [rbx+138h]
0x18001ccef  mov     rdx, [rsi]
0x18001ccf2  lea     r9, ?BaseBrokerCallback@CScheduleMgr@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXQEAXK@Z; CScheduleMgr::BaseBrokerCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void * const,ulong)
0x18001ccf9  mov     [rsp+3B0h+var_378], 0
0x18001cd01  mov     [rsp+3B0h+var_380], 0
0x18001cd09  mov     [rsp+3B0h+var_388], 0
0x18001cd12  mov     [rsp+3B0h+var_390], r8
0x18001cd17  xor     r8d, r8d
0x18001cd1a  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001cd20  test    eax, eax
0x18001cd22  jns     short loc_18001CD34
0x18001cd24  mov     ecx, eax; int
0x18001cd26  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x18001cd2b  mov     edi, eax
0x18001cd2d  jmp     short loc_18001CD34
0x18001cd2f  mov     edi, 80004005h
0x18001cd34  mov     eax, edi
0x18001cd36  mov     rcx, [rbp+2B0h+var_30]
0x18001cd3d  xor     rcx, rsp; StackCookie
0x18001cd40  call    __security_check_cookie
0x18001cd45  add     rsp, 398h
0x18001cd4c  pop     rdi
0x18001cd4d  pop     rsi
0x18001cd4e  pop     rbx
0x18001cd4f  pop     rbp
0x18001cd50  retn
```
