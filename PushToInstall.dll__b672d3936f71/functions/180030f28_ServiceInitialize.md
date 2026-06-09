# ServiceInitialize

- ea: `0x180030f28`
- end: `0x18003144d`
- name: `ServiceInitialize`
- size: `1317`
- prototype: `__int64 __fastcall(int, LPCWCH *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fce0`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000d75c`
- `0x18002c418`
- `0x18002c4b8`
- `0x18002cecc`
- `0x18002e318`
- `0x18002e6ac`
- `0x18002f2bc`
- `0x18002f56c`
- `0x18002f684`
- `0x180030164`
- `0x180030be8`
- `0x180030e48`
- `0x180030f28`
- `0x180044fd8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031270`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031381`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031270`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031381`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031257`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003135e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031257`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003135e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003100c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800310a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003114a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003100c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800310a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003114a`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180030fd1`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x18003105f`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800311a1`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800312cc`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180031321`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180030fd1`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x18003105f`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800311a1`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800312cc`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180031321`
- `RPCRT4!UuidCreate` at `0x180030f6b`
- `RPCRT4!UuidCreate` at `0x180030f6b`

## string_xrefs

- `0x180031034`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x1800310d4`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x180031157`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x1800312a1`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x180031027`: `ServiceInitialize`
- `0x1800310c7`: `ServiceInitialize`
- `0x180031150`: `ServiceInitialize`
- `0x180031294`: `ServiceInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ServiceInitialize(int a1, LPCWCH *a2)
{
  _BYTE *v4; // rbx
  _DWORD *v5; // r14
  _DWORD *v6; // rax
  int AppControlSettingAsInt; // eax
  __int64 v8; // rcx
  _DWORD *v9; // r14
  _DWORD *v10; // rax
  volatile signed __int32 *v11; // rsi
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rsi
  _DWORD *v14; // r14
  _DWORD *v15; // rax
  _DWORD *v16; // r14
  _DWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rsi
  __int64 v21; // rcx
  DWORD LastError; // [rsp+30h] [rbp-78h]
  __int64 v24; // [rsp+48h] [rbp-60h] BYREF
  __int128 v25; // [rsp+50h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-48h] BYREF

  v4 = operator new(0x90u);
  v4[130] = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  v4[129] = 17;
  *((_QWORD *)v4 + 17) = 0x1300000000LL;
  memset_0(v4, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 12, v4);
  *((_WORD *)v4 + 8) = 46;
  _correlationVector = (TraceLoggingCorrelationVector *)v4;
  v24 = 0;
  GetProcessReference(&v24);
  if ( a1 && a2 )
  {
    v25 = 0;
    if ( CompareStringOrdinal(*a2, -1, L"registration", -1, 1) == 2 )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
        0x153u,
        "ServiceInitialize",
        -1,
        L"PTI started with registration");
      v5 = operator new(0x10u);
      *(_QWORD *)v5 = 0;
      v5[2] = 0;
      GetProcessReference(v5);
      v6 = operator new(0x18u);
      v6[2] = 1;
      v6[3] = 1;
      *(_QWORD *)v6 = &std::_Ref_count<WorkItem>::`vftable';
      *((_QWORD *)v6 + 2) = v5;
      *(_QWORD *)&Uuid.Data1 = v5;
      *(_QWORD *)Uuid.Data4 = v6;
    }
    else
    {
      if ( CompareStringOrdinal(*a2, -1, L"login", -1, 1) == 2 )
      {
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          0x158u,
          "ServiceInitialize",
          -1,
          L"PTI started with login");
        AppControlSettingAsInt = GetAppControlSettingAsInt();
        LogStats(AppControlSettingAsInt);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetImpl'::`2'::impl) )
          LogStoreUpdateEvent();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UninstallTencentEmulator>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UninstallTencentEmulator>::GetImpl'::`2'::impl) )
        {
          try
          {
            if ( IsUninstallTencentFlagSetInOneSettings() )
              UninstallTencentEmulator(v8);
          }
          catch ( ... )
          {
            LastError = GetLastError();
            LogMessage(
              2u,
              "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
              0x16Au,
              "ServiceInitialize",
              -1,
              L"Uninstalling tencent failed with error code: %d",
              LastError);
            goto LABEL_21;
          }
        }
        goto LABEL_21;
      }
      if ( CompareStringOrdinal(*a2, -1, L"TriggerStarted", -1, 1) != 2 )
      {
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          0x175u,
          "ServiceInitialize",
          -1,
          L"PTI started with unknown arg %s",
          *a2);
LABEL_19:
        if ( (_QWORD)v25 )
        {
          AcquireSRWLockExclusive(&srwWorkQueue);
          std::deque<std::shared_ptr<WorkItem>>::push_back(v12, &v25);
          ReleaseSRWLockExclusive(&srwWorkQueue);
        }
LABEL_21:
        v13 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
        goto LABEL_27;
      }
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
        0x170u,
        "ServiceInitialize",
        -1,
        L"PTI started with trigger for WNF");
      v9 = operator new(0x10u);
      *(_QWORD *)v9 = 0;
      v9[2] = 1;
      GetProcessReference(v9);
      v10 = operator new(0x18u);
      v10[2] = 1;
      v10[3] = 1;
      *(_QWORD *)v10 = &std::_Ref_count<WorkItem>::`vftable';
      *((_QWORD *)v10 + 2) = v9;
      *(_QWORD *)&Uuid.Data1 = v9;
      *(_QWORD *)Uuid.Data4 = v10;
    }
    std::shared_ptr<WorkItem>::operator=(&v25, &Uuid);
    v11 = *(volatile signed __int32 **)Uuid.Data4;
    if ( *(_QWORD *)Uuid.Data4 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Uuid.Data4 + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    goto LABEL_19;
  }
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
    0x183u,
    "ServiceInitialize",
    -1,
    L"PTI started with no args");
  v14 = operator new(0x10u);
  *(_QWORD *)v14 = 0;
  v14[2] = 0;
  GetProcessReference(v14);
  Uuid = 0;
  v15 = operator new(0x18u);
  v15[2] = 1;
  v15[3] = 1;
  *(_QWORD *)v15 = &std::_Ref_count<WorkItem>::`vftable';
  *((_QWORD *)v15 + 2) = v14;
  *(_QWORD *)&Uuid.Data1 = v14;
  *(_QWORD *)Uuid.Data4 = v15;
  v16 = operator new(0x10u);
  *(_QWORD *)v16 = 0;
  v16[2] = 1;
  GetProcessReference(v16);
  v25 = 0;
  v17 = operator new(0x18u);
  v17[2] = 1;
  v17[3] = 1;
  *(_QWORD *)v17 = &std::_Ref_count<WorkItem>::`vftable';
  *((_QWORD *)v17 + 2) = v16;
  *(_QWORD *)&v25 = v16;
  *((_QWORD *)&v25 + 1) = v17;
  AcquireSRWLockExclusive(&srwWorkQueue);
  std::deque<std::shared_ptr<WorkItem>>::push_back(v18, &Uuid);
  std::deque<std::shared_ptr<WorkItem>>::push_back(v19, &v25);
  ReleaseSRWLockExclusive(&srwWorkQueue);
  v20 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
  if ( *((_QWORD *)&v25 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v13 = *(volatile signed __int32 **)Uuid.Data4;
LABEL_27:
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  ProcessWorkQueue();
  v21 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x180030f28  push    rbx
0x180030f2a  push    rsi
0x180030f2b  push    r12
0x180030f2d  push    r14
0x180030f2f  sub     rsp, 88h
0x180030f36  mov     rax, cs:__security_cookie
0x180030f3d  xor     rax, rsp
0x180030f40  mov     [rsp+0A8h+var_38], rax
0x180030f45  mov     r14, rdx
0x180030f48  mov     esi, ecx
0x180030f4a  mov     ecx, 90h; Size
0x180030f4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030f54  mov     rbx, rax
0x180030f57  mov     byte ptr [rax+82h], 41h ; 'A'
0x180030f5e  xorps   xmm0, xmm0
0x180030f61  movups  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm0
0x180030f66  lea     rcx, [rsp+0A8h+Uuid]; Uuid
0x180030f6b  call    cs:__imp_UuidCreate
0x180030f71  movaps  xmm0, xmmword ptr [rsp+0A8h+Uuid.Data1]
0x180030f76  movdqa  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm0
0x180030f7c  mov     byte ptr [rbx+81h], 11h
0x180030f83  mov     rax, 1300000000h
0x180030f8d  mov     [rbx+88h], rax
0x180030f94  xor     edx, edx; Val
0x180030f96  mov     r8d, 81h; Size
0x180030f9c  mov     rcx, rbx; void *
0x180030f9f  call    memset_0
0x180030fa4  mov     r8, rbx
0x180030fa7  mov     edx, 0Ch
0x180030fac  lea     rcx, [rsp+0A8h+Uuid]
0x180030fb1  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180030fb6  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180030fbc  mov     cs:?_correlationVector@@3PEAVTraceLoggingCorrelationVector@@EA, rbx; TraceLoggingCorrelationVector * _correlationVector
0x180030fc3  mov     [rsp+0A8h+var_60], 0
0x180030fcc  lea     rcx, [rsp+0A8h+var_60]
0x180030fd1  call    cs:__imp_GetProcessReference
0x180030fd7  test    esi, esi
0x180030fd9  jz      loc_180031281
0x180030fdf  test    r14, r14
0x180030fe2  jz      loc_180031281
0x180030fe8  xorps   xmm1, xmm1
0x180030feb  movdqu  [rsp+0A8h+var_58], xmm1
0x180030ff1  mov     esi, 1
0x180030ff6  mov     [rsp+0A8h+bIgnoreCase], esi; bIgnoreCase
0x180030ffa  or      ebx, 0FFFFFFFFh
0x180030ffd  mov     r9d, ebx; cchCount2
0x180031000  lea     r8, aRegistration; "registration"
0x180031007  mov     edx, ebx; cchCount1
0x180031009  mov     rcx, [r14]; lpString1
0x18003100c  call    cs:__imp_CompareStringOrdinal
0x180031012  cmp     eax, 2
0x180031015  jnz     short loc_180031095
0x180031017  lea     rax, aPtiStartedWith_3; "PTI started with registration"
0x18003101e  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x180031023  mov     [rsp+0A8h+bIgnoreCase], ebx; int
0x180031027  lea     r9, aServiceinitial; "ServiceInitialize"
0x18003102e  mov     r8d, 153h; unsigned int
0x180031034  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003103b  lea     ecx, [rsi+2]; unsigned int
0x18003103e  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180031043  lea     ecx, [rsi+0Fh]; Size
0x180031046  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003104b  mov     r14, rax
0x18003104e  mov     qword ptr [rax], 0
0x180031055  mov     dword ptr [rax+8], 0
0x18003105c  mov     rcx, rax
0x18003105f  call    cs:__imp_GetProcessReference
0x180031065  mov     [rsp+0A8h+var_68], r14
0x18003106a  lea     ecx, [rsi+17h]; Size
0x18003106d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031072  mov     [rax+8], esi
0x180031075  mov     [rax+0Ch], esi
0x180031078  lea     r12, ??_7?$_Ref_count@VWorkItem@@@std@@6B@; const std::_Ref_count<WorkItem>::`vftable'
0x18003107f  mov     [rax], r12
0x180031082  mov     [rax+10h], r14
0x180031086  mov     qword ptr [rsp+0A8h+Uuid.Data1], r14
0x18003108b  mov     qword ptr [rsp+0A8h+Uuid.Data4], rax
0x180031090  jmp     loc_1800311D4
0x180031095  mov     [rsp+0A8h+bIgnoreCase], esi; bIgnoreCase
0x180031099  mov     r9d, ebx; cchCount2
0x18003109c  lea     r8, aLogin; "login"
0x1800310a3  mov     edx, ebx; cchCount1
0x1800310a5  mov     rcx, [r14]; lpString1
0x1800310a8  call    cs:__imp_CompareStringOrdinal
0x1800310ae  cmp     eax, 2
0x1800310b1  jnz     loc_180031137
0x1800310b7  lea     rax, aPtiStartedWith_2; "PTI started with login"
0x1800310be  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x1800310c3  mov     [rsp+0A8h+bIgnoreCase], ebx; int
0x1800310c7  lea     r9, aServiceinitial; "ServiceInitialize"
0x1800310ce  mov     r8d, 158h; unsigned int
0x1800310d4  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800310db  mov     ecx, 3; unsigned int
0x1800310e0  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800310e5  call    ?GetAppControlSettingAsInt@@YAHXZ; GetAppControlSettingAsInt(void)
0x1800310ea  movsxd  rcx, eax; unsigned __int64
0x1800310ed  call    ?LogStats@@YAX_K@Z; LogStats(unsigned __int64)
0x1800310f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent> `wil::Feature<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetImpl(void)'::`2'::impl
0x1800310f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::__private_IsEnabled(void)
0x1800310fe  test    al, al
0x180031100  jz      short loc_180031107
0x180031102  call    ?LogStoreUpdateEvent@@YAXXZ; LogStoreUpdateEvent(void)
0x180031107  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UninstallTencentEmulator@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UninstallTencentEmulator@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UninstallTencentEmulator> `wil::Feature<__WilFeatureTraits_Feature_UninstallTencentEmulator>::GetImpl(void)'::`2'::impl
0x18003110e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UninstallTencentEmulator@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UninstallTencentEmulator>::__private_IsEnabled(void)
0x180031113  test    al, al
0x180031115  jz      loc_180031277
0x18003111b  call    ?IsUninstallTencentFlagSetInOneSettings@@YA_NXZ; IsUninstallTencentFlagSetInOneSettings(void)
0x180031120  test    al, al
0x180031122  jz      short loc_18003112A
0x180031124  call    ?UninstallTencentEmulator@@YAXXZ; UninstallTencentEmulator(void)
0x180031129  nop
0x18003112a  jmp     loc_180031277
0x18003112f  or      ebx, 0FFFFFFFFh
0x180031132  jmp     loc_180031277
0x180031137  mov     [rsp+0A8h+bIgnoreCase], esi; bIgnoreCase
0x18003113b  mov     r9d, ebx; cchCount2
0x18003113e  lea     r8, aTriggerstarted; "TriggerStarted"
0x180031145  mov     edx, ebx; cchCount1
0x180031147  mov     rcx, [r14]; lpString1
0x18003114a  call    cs:__imp_CompareStringOrdinal
0x180031150  lea     r9, aServiceinitial; "ServiceInitialize"
0x180031157  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003115e  mov     ecx, 3; unsigned int
0x180031163  cmp     eax, 2
0x180031166  jnz     loc_180031222
0x18003116c  lea     rax, aPtiStartedWith_1; "PTI started with trigger for WNF"
0x180031173  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x180031178  mov     [rsp+0A8h+bIgnoreCase], ebx; int
0x18003117c  mov     r8d, 170h; unsigned int
0x180031182  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180031187  mov     ecx, 10h; Size
0x18003118c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031191  mov     r14, rax
0x180031194  mov     qword ptr [rax], 0
0x18003119b  mov     [rax+8], esi
0x18003119e  mov     rcx, rax
0x1800311a1  call    cs:__imp_GetProcessReference
0x1800311a7  mov     [rsp+0A8h+var_68], r14
0x1800311ac  mov     ecx, 18h; Size
0x1800311b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800311b6  mov     [rax+8], esi
0x1800311b9  mov     [rax+0Ch], esi
0x1800311bc  lea     r12, ??_7?$_Ref_count@VWorkItem@@@std@@6B@; const std::_Ref_count<WorkItem>::`vftable'
0x1800311c3  mov     [rax], r12
0x1800311c6  mov     [rax+10h], r14
0x1800311ca  mov     qword ptr [rsp+0A8h+Uuid.Data1], r14
0x1800311cf  mov     qword ptr [rsp+0A8h+Uuid.Data4], rax
0x1800311d4  lea     rdx, [rsp+0A8h+Uuid]
0x1800311d9  lea     rcx, [rsp+0A8h+var_58]
0x1800311de  call    ??4?$shared_ptr@VWorkItem@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WorkItem>::operator=(std::shared_ptr<WorkItem> &&)
0x1800311e3  mov     rsi, qword ptr [rsp+0A8h+Uuid.Data4]
0x1800311e8  test    rsi, rsi
0x1800311eb  jz      short loc_180031245
0x1800311ed  mov     eax, ebx
0x1800311ef  lock xadd [rsi+8], eax
0x1800311f4  add     eax, ebx
0x1800311f6  jnz     short loc_180031245
0x1800311f8  mov     rax, [rsi]
0x1800311fb  mov     rcx, rsi
0x1800311fe  mov     rax, [rax]
0x180031201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031206  mov     eax, ebx
0x180031208  lock xadd [rsi+0Ch], eax
0x18003120d  add     eax, ebx
0x18003120f  jnz     short loc_180031245
0x180031211  mov     rax, [rsi]
0x180031214  mov     rcx, rsi
0x180031217  mov     rax, [rax+8]
0x18003121b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031220  jmp     short loc_180031245
0x180031222  mov     rax, [r14]
0x180031225  mov     [rsp+0A8h+var_78], rax
0x18003122a  lea     rax, aPtiStartedWith; "PTI started with unknown arg %s"
0x180031231  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x180031236  mov     [rsp+0A8h+bIgnoreCase], ebx; int
0x18003123a  mov     r8d, 175h; unsigned int
0x180031240  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180031245  cmp     qword ptr [rsp+0A8h+var_58], 0
0x18003124b  jz      short loc_180031277
0x18003124d  lea     rsi, ?srwWorkQueue@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock srwWorkQueue
0x180031254  mov     rcx, rsi; SRWLock
0x180031257  call    cs:__imp_AcquireSRWLockExclusive
0x18003125d  mov     [rsp+0A8h+var_68], rsi
0x180031262  lea     rdx, [rsp+0A8h+var_58]
0x180031267  call    ?push_back@?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VWorkItem@@@2@@Z; std::deque<std::shared_ptr<WorkItem>>::push_back(std::shared_ptr<WorkItem> const &)
0x18003126c  nop
0x18003126d  mov     rcx, rsi; SRWLock
0x180031270  call    cs:__imp_ReleaseSRWLockExclusive
0x180031276  nop
0x180031277  mov     rsi, qword ptr [rsp+0A8h+var_58+8]
0x18003127c  jmp     loc_1800313CB
0x180031281  lea     rax, aPtiStartedWith_0; "PTI started with no args"
0x180031288  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x18003128d  or      ebx, 0FFFFFFFFh
0x180031290  mov     [rsp+0A8h+bIgnoreCase], ebx; int
0x180031294  lea     r9, aServiceinitial; "ServiceInitialize"
0x18003129b  mov     r8d, 183h; unsigned int
0x1800312a1  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800312a8  lea     ecx, [rbx+4]; unsigned int
0x1800312ab  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800312b0  lea     ecx, [rbx+11h]; Size
0x1800312b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800312b8  mov     r14, rax
0x1800312bb  mov     qword ptr [rax], 0
0x1800312c2  mov     dword ptr [rax+8], 0
0x1800312c9  mov     rcx, rax
0x1800312cc  call    cs:__imp_GetProcessReference
0x1800312d2  xorps   xmm0, xmm0
0x1800312d5  movdqu  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm0
0x1800312db  mov     [rsp+0A8h+var_68], r14
0x1800312e0  lea     ecx, [rbx+19h]; Size
0x1800312e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800312e8  lea     esi, [rbx+2]
0x1800312eb  mov     [rax+8], esi
0x1800312ee  mov     [rax+0Ch], esi
0x1800312f1  lea     r12, ??_7?$_Ref_count@VWorkItem@@@std@@6B@; const std::_Ref_count<WorkItem>::`vftable'
0x1800312f8  mov     [rax], r12
0x1800312fb  mov     [rax+10h], r14
0x1800312ff  mov     qword ptr [rsp+0A8h+Uuid.Data1], r14
0x180031304  mov     qword ptr [rsp+0A8h+Uuid.Data4], rax
0x180031309  lea     ecx, [rbx+11h]; Size
0x18003130c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031311  mov     r14, rax
0x180031314  mov     qword ptr [rax], 0
0x18003131b  mov     [rax+8], esi
0x18003131e  mov     rcx, rax
0x180031321  call    cs:__imp_GetProcessReference
0x180031327  xorps   xmm0, xmm0
0x18003132a  movdqu  [rsp+0A8h+var_58], xmm0
0x180031330  mov     [rsp+0A8h+var_68], r14
0x180031335  lea     ecx, [rbx+19h]; Size
0x180031338  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003133d  mov     [rax+8], esi
0x180031340  mov     [rax+0Ch], esi
0x180031343  mov     [rax], r12
0x180031346  mov     [rax+10h], r14
0x18003134a  mov     qword ptr [rsp+0A8h+var_58], r14
0x18003134f  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x180031354  lea     rsi, ?srwWorkQueue@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock srwWorkQueue
0x18003135b  mov     rcx, rsi; SRWLock
0x18003135e  call    cs:__imp_AcquireSRWLockExclusive
0x180031364  mov     [rsp+0A8h+var_68], rsi
0x180031369  lea     rdx, [rsp+0A8h+Uuid]
0x18003136e  call    ?push_back@?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VWorkItem@@@2@@Z; std::deque<std::shared_ptr<WorkItem>>::push_back(std::shared_ptr<WorkItem> const &)
0x180031373  lea     rdx, [rsp+0A8h+var_58]
0x180031378  call    ?push_back@?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VWorkItem@@@2@@Z; std::deque<std::shared_ptr<WorkItem>>::push_back(std::shared_ptr<WorkItem> const &)
0x18003137d  nop
0x18003137e  mov     rcx, rsi; SRWLock
0x180031381  call    cs:__imp_ReleaseSRWLockExclusive
0x180031387  nop
0x180031388  mov     rsi, qword ptr [rsp+0A8h+var_58+8]
0x18003138d  test    rsi, rsi
0x180031390  jz      short loc_1800313C6
0x180031392  mov     eax, ebx
0x180031394  lock xadd [rsi+8], eax
0x180031399  add     eax, ebx
0x18003139b  jnz     short loc_1800313C6
0x18003139d  mov     rax, [rsi]
0x1800313a0  mov     rcx, rsi
0x1800313a3  mov     rax, [rax]
0x1800313a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313ab  mov     eax, ebx
0x1800313ad  lock xadd [rsi+0Ch], eax
0x1800313b2  add     eax, ebx
0x1800313b4  jnz     short loc_1800313C6
0x1800313b6  mov     rax, [rsi]
0x1800313b9  mov     rcx, rsi
0x1800313bc  mov     rax, [rax+8]
0x1800313c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313c5  nop
0x1800313c6  mov     rsi, qword ptr [rsp+0A8h+Uuid.Data4]
0x1800313cb  test    rsi, rsi
0x1800313ce  jz      short loc_180031403
0x1800313d0  mov     eax, ebx
0x1800313d2  lock xadd [rsi+8], eax
0x1800313d7  add     eax, ebx
0x1800313d9  jnz     short loc_180031403
0x1800313db  mov     rax, [rsi]
0x1800313de  mov     rcx, rsi
0x1800313e1  mov     rax, [rax]
0x1800313e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313e9  mov     eax, ebx
0x1800313eb  lock xadd [rsi+0Ch], eax
0x1800313f0  add     eax, ebx
0x1800313f2  jnz     short loc_180031403
0x1800313f4  mov     rax, [rsi]
0x1800313f7  mov     rcx, rsi
0x1800313fa  mov     rax, [rax+8]
0x1800313fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031403  call    ?ProcessWorkQueue@@YAXXZ; ProcessWorkQueue(void)
0x180031408  nop
0x180031409  mov     rcx, [rsp+0A8h+var_60]
0x18003140e  test    rcx, rcx
0x180031411  jz      short loc_180031429
0x180031413  mov     [rsp+0A8h+var_60], 0
0x18003141c  mov     rax, [rcx]
0x18003141f  mov     rax, [rax+10h]
0x180031423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031428  nop
0x180031429  xor     eax, eax
  ... truncated ...
```
