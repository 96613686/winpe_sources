# FamilyNotifications::NotifyIfAccountIsFamilyRelated(IExecutionContextLite *,ushort const *)

- ea: `0x180017d88`
- end: `0x180017f28`
- name: `?NotifyIfAccountIsFamilyRelated@FamilyNotifications@@SAJPEAVIExecutionContextLite@@PEBG@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x18001495c`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x1800178bc`
- `0x180017a00`
- `0x180017c20`
- `0x180017d88`
- `0x180017f30`
- `0x1800267c0`
- `0x180026c8c`

## string_xrefs

- `0x180017e12`: `hr = FamilyNotifications::GetUserSid(pExecutionContextLite, pUserName, spSid)`
- `0x180017e4e`: `hr = FamilyNotifications::GetFlagFromSystemStore(pExecutionContextLite, spSid, familySafetySetting)`
- `0x180017ea7`: `hr = FamilyNotifications::GetFamilyIDFromSystemStore(pExecutionContextLite, spSid, spExistingFamilyID)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FamilyNotifications::NotifyIfAccountIsFamilyRelated(
        struct IExecutionContextLite *a1,
        const unsigned __int16 *a2)
{
  int UserSid; // eax
  __int64 v5; // rdx
  int v6; // r8d
  int FlagFromSystemStore; // eax
  int FamilyIDFromSystemStore; // eax
  unsigned int v9; // ebx
  char *v11; // [rsp+20h] [rbp-60h]
  unsigned __int16 *v12[3]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v14[4]; // [rsp+60h] [rbp-20h] BYREF
  int v15; // [rsp+C8h] [rbp+48h] BYREF

  v15 = 0;
  memset(v12, 0, sizeof(v12));
  memset(v13, 0, sizeof(v13));
  v14[0] = "FamilyNotifications::NotifyIfAccountIsFamilyRelated";
  v14[1] = &v15;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
    "FamilyNotifications::NotifyIfAccountIsFamilyRelated",
    (const char *)0xE1,
    0,
    (const unsigned __int16 *)v11);
  UserSid = FamilyNotifications::GetUserSid((__int64)a1, a2, v12);
  v15 = UserSid;
  if ( UserSid >= 0 )
  {
    FlagFromSystemStore = FamilyNotifications::GetFlagFromSystemStore(a1);
    v15 = FlagFromSystemStore;
    if ( FlagFromSystemStore >= 0 )
    {
      FamilyIDFromSystemStore = FamilyNotifications::GetFamilyIDFromSystemStore(a1, v12, v13);
      v15 = FamilyIDFromSystemStore;
      if ( FamilyIDFromSystemStore >= 0 )
      {
        if ( v13[0] && *(_WORD *)v13[0] )
        {
          TracePrintW(
            4u,
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
            0xF0u,
            L"Sending WNF notification because a Family ID value is present.");
          FamilyNotifications::SendWNFNotification(WNF_WFS_FAMILYMEMBERLOGIN);
        }
      }
      else
      {
        Telemetry::IfFailExit(
          (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
          "FamilyNotifications::NotifyIfAccountIsFamilyRelated",
          237,
          FamilyIDFromSystemStore,
          "hr = FamilyNotifications::GetFamilyIDFromSystemStore(pExecutionContextLite, spSid, spExistingFamilyID)");
      }
    }
    else
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
        "FamilyNotifications::NotifyIfAccountIsFamilyRelated",
        229,
        FlagFromSystemStore,
        "hr = FamilyNotifications::GetFlagFromSystemStore(pExecutionContextLite, spSid, familySafetySetting)");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\familynotifications\\familynotifications.cpp",
      "FamilyNotifications::NotifyIfAccountIsFamilyRelated",
      227,
      UserSid,
      "hr = FamilyNotifications::GetUserSid(pExecutionContextLite, pUserName, spSid)");
  }
  v9 = v15;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v14, v5, v6);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v13);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v12);
  return v9;
}

```

## disassembly

```asm
0x180017d88  mov     [rsp-28h+arg_0], rbx
0x180017d8d  push    rbp
0x180017d8e  push    rsi
0x180017d8f  push    rdi
0x180017d90  push    r14
0x180017d92  push    r15
0x180017d94  mov     rbp, rsp
0x180017d97  sub     rsp, 80h
0x180017d9e  mov     rbx, rdx
0x180017da1  mov     rdi, rcx
0x180017da4  xor     esi, esi
0x180017da6  mov     [rbp+arg_10], sil
0x180017daa  mov     [rbp+arg_18], esi
0x180017dad  mov     [rbp+var_50], rsi
0x180017db1  mov     [rbp+var_40], rsi
0x180017db5  mov     [rbp+var_48], rsi
0x180017db9  mov     [rbp+var_38], rsi
0x180017dbd  mov     [rbp+var_28], rsi
0x180017dc1  mov     [rbp+var_30], rsi
0x180017dc5  lea     r15, aFamilynotifica_3; "FamilyNotifications::NotifyIfAccountIsF"...
0x180017dcc  mov     [rbp+var_20], r15
0x180017dd0  lea     rax, [rbp+arg_18]
0x180017dd4  mov     [rbp+var_18], rax
0x180017dd8  mov     [rbp+var_10], rsi
0x180017ddc  mov     [rbp+var_8], rsi
0x180017de0  xor     r9d, r9d; unsigned int
0x180017de3  mov     r8d, 0E1h; char *
0x180017de9  mov     rdx, r15; char *
0x180017dec  lea     r14, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180017df3  mov     rcx, r14; this
0x180017df6  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180017dfb  nop
0x180017dfc  lea     r8, [rbp+var_50]
0x180017e00  mov     rdx, rbx
0x180017e03  mov     rcx, rdi
0x180017e06  call    ?GetUserSid@FamilyNotifications@@CAJPEAVIExecutionContextLite@@PEBGAEAV?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@@Z; FamilyNotifications::GetUserSid(IExecutionContextLite *,ushort const *,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &)
0x180017e0b  mov     [rbp+arg_18], eax
0x180017e0e  test    eax, eax
0x180017e10  jns     short loc_180017E37
0x180017e12  lea     r8, aHrFamilynotifi_2; "hr = FamilyNotifications::GetUserSid(pE"...
0x180017e19  mov     [rsp+80h+var_60], r8; char *
0x180017e1e  mov     r8d, 0E3h; unsigned int
0x180017e24  mov     r9d, eax; int
0x180017e27  mov     rdx, r15; char *
0x180017e2a  mov     rcx, r14; char *
0x180017e2d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180017e32  jmp     loc_180017EEF
0x180017e37  lea     r8, [rbp+arg_10]
0x180017e3b  lea     rdx, [rbp+var_50]
0x180017e3f  mov     rcx, rdi; struct IExecutionContextLite *
0x180017e42  call    ?GetFlagFromSystemStore@FamilyNotifications@@CAJPEAVIExecutionContextLite@@AEAV?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@AEA_N@Z; FamilyNotifications::GetFlagFromSystemStore(IExecutionContextLite *,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &,bool &)
0x180017e47  mov     [rbp+arg_18], eax
0x180017e4a  test    eax, eax
0x180017e4c  jns     short loc_180017E62
0x180017e4e  lea     rcx, aHrFamilynotifi_0; "hr = FamilyNotifications::GetFlagFromSy"...
0x180017e55  mov     [rsp+80h+var_60], rcx
0x180017e5a  mov     r8d, 0E5h
0x180017e60  jmp     short loc_180017E24
0x180017e62  mov     ebx, 4
0x180017e67  cmp     [rbp+arg_10], 1
0x180017e6b  jnz     short loc_180017E90
0x180017e6d  lea     r9, aSendingWnfNoti_0; "Sending WNF notification because the Fa"...
0x180017e74  mov     r8d, 0E9h; unsigned int
0x180017e7a  mov     rdx, r14; char *
0x180017e7d  mov     ecx, ebx; unsigned __int8
0x180017e7f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180017e84  mov     rcx, qword ptr cs:WNF_WFS_SETTINGS.Data; struct _WNF_STATE_NAME
0x180017e8b  call    ?SendWNFNotification@FamilyNotifications@@CAJU_WNF_STATE_NAME@@@Z; FamilyNotifications::SendWNFNotification(_WNF_STATE_NAME)
0x180017e90  lea     r8, [rbp+var_38]
0x180017e94  lea     rdx, [rbp+var_50]
0x180017e98  mov     rcx, rdi
0x180017e9b  call    ?GetFamilyIDFromSystemStore@FamilyNotifications@@CAJPEAVIExecutionContextLite@@AEAV?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@1@Z; FamilyNotifications::GetFamilyIDFromSystemStore(IExecutionContextLite *,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &,Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext> &)
0x180017ea0  mov     [rbp+arg_18], eax
0x180017ea3  test    eax, eax
0x180017ea5  jns     short loc_180017EBE
0x180017ea7  lea     rcx, aHrFamilynotifi; "hr = FamilyNotifications::GetFamilyIDFr"...
0x180017eae  mov     [rsp+80h+var_60], rcx
0x180017eb3  mov     r8d, 0EDh
0x180017eb9  jmp     loc_180017E24
0x180017ebe  mov     rax, [rbp+var_38]
0x180017ec2  test    rax, rax
0x180017ec5  jz      short loc_180017EEF
0x180017ec7  cmp     [rax], si
0x180017eca  jz      short loc_180017EEF
0x180017ecc  lea     r9, aSendingWnfNoti; "Sending WNF notification because a Fami"...
0x180017ed3  mov     r8d, 0F0h; unsigned int
0x180017ed9  mov     rdx, r14; char *
0x180017edc  mov     ecx, ebx; unsigned __int8
0x180017ede  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180017ee3  mov     rcx, qword ptr cs:WNF_WFS_FAMILYMEMBERLOGIN.Data; struct _WNF_STATE_NAME
0x180017eea  call    ?SendWNFNotification@FamilyNotifications@@CAJU_WNF_STATE_NAME@@@Z; FamilyNotifications::SendWNFNotification(_WNF_STATE_NAME)
0x180017eef  mov     ebx, [rbp+arg_18]
0x180017ef2  lea     rcx, [rbp+var_20]
0x180017ef6  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180017efb  nop
0x180017efc  lea     rcx, [rbp+var_38]
0x180017f00  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180017f05  nop
0x180017f06  lea     rcx, [rbp+var_50]
0x180017f0a  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180017f0f  mov     eax, ebx
0x180017f11  mov     rbx, [rsp+80h+arg_0]
0x180017f19  add     rsp, 80h
0x180017f20  pop     r15
0x180017f22  pop     r14
0x180017f24  pop     rdi
0x180017f25  pop     rsi
0x180017f26  pop     rbp
0x180017f27  retn
```
