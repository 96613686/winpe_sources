# CApplicationManager::OnStreamStopped(CProcess *,IAudioSessionInfo *,IAudioStreamInfo *)

- ea: `0x180022390`
- end: `0x180022a0c`
- name: `?OnStreamStopped@CApplicationManager@@QEAAJPEAVCProcess@@PEAUIAudioSessionInfo@@PEAUIAudioStreamInfo@@@Z`
- size: `1660`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, struct CProcess *, struct IAudioSessionInfo *, struct IAudioStreamInfo *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180022370`

## callees

- `0x180009090`
- `0x18000a384`
- `0x180015fe0`
- `0x1800161d0`
- `0x18001b5a0`
- `0x18001b6c0`
- `0x18001c8a0`
- `0x18001d580`
- `0x18001d650`
- `0x18001d960`
- `0x18001ece0`
- `0x180022390`
- `0x1800242f0`
- `0x1800279f0`
- `0x18002ba2c`
- `0x180031960`
- `0x180039d70`
- `0x18003ce48`
- `0x18003f33c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800227e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800227e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002282e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002282e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022599`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022599`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CApplicationManager::OnStreamStopped(
        CApplicationManager *this,
        CApplication **a2,
        struct IAudioSessionInfo *a3,
        struct IAudioStreamInfo *a4)
{
  CApplicationManager *v6; // r15
  __int64 v7; // rbx
  _WORD *v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // eax
  CProcess *v13; // rbx
  unsigned int v14; // ecx
  __int64 v15; // rcx
  __int64 v16; // r8
  const unsigned __int16 *v17; // r12
  unsigned __int8 v18; // al
  int v19; // edx
  int v20; // ecx
  CProcess *v21; // rax
  CApplication *v22; // rbx
  struct _RTL_CRITICAL_SECTION *v23; // rsi
  int v24; // r14d
  _QWORD *v25; // rax
  __int64 v26; // rcx
  int v27; // r9d
  int v28; // r8d
  int v29; // r10d
  struct IDuckingController *v30; // rbx
  int v31; // ecx
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh] BYREF
  CApplication *v35; // [rsp+48h] [rbp-B8h] BYREF
  CProcess *v36; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  struct IDuckingController *v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v44; // [rsp+90h] [rbp-70h]
  char v45; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  void *v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+B8h] [rbp-48h]
  int v49; // [rsp+BCh] [rbp-44h]
  _WORD *v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+CCh] [rbp-34h]
  __int64 *v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h]
  int *v55; // [rsp+E0h] [rbp-20h]
  __int64 v56; // [rsp+E8h] [rbp-18h]
  int *v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  int *v59; // [rsp+100h] [rbp+0h]
  __int64 v60; // [rsp+108h] [rbp+8h]
  int *v61; // [rsp+110h] [rbp+10h]
  __int64 v62; // [rsp+118h] [rbp+18h]
  __int64 *v63; // [rsp+120h] [rbp+20h]
  __int64 v64; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v36 = (CProcess *)a2;
  v6 = g_ApplicationManager;
  v35 = a2[28];
  v7 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 4u
    && (*(_QWORD *)(v7 + 16) & 0x8000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x8000LL) == *(_QWORD *)(v7 + 24) )
  {
    v41 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 80LL))(a4);
    v34 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 48LL))(a4);
    v37 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 56LL))(a4);
    v39 = *((_DWORD *)v36 + 40);
    v40 = *((_DWORD *)v35 + 53);
    v42 = *((_QWORD *)v35 + 87);
    v8 = (_WORD *)*((_QWORD *)v35 + 3);
    v63 = &v41;
    v64 = 8;
    v61 = &v34;
    v62 = 4;
    v59 = &v37;
    v60 = 4;
    v57 = &v39;
    v58 = 4;
    v55 = &v40;
    v56 = 4;
    v53 = &v42;
    v54 = 8;
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v10 = 2 * v9 + 2;
    }
    else
    {
      v8 = &unk_180053B30;
      v10 = 2;
    }
    v50 = v8;
    v51 = v10;
    v52 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0x8000;
    UserData.Ptr = *(_QWORD *)(v7 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v47 = &unk_180058944;
    v48 = 94;
    v49 = 1;
    LODWORD(v38) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, 0, 0, 9u, &UserData);
  }
  v33 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 48LL))(a4);
  if ( v11 >= 0x18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\workitem.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  v13 = v36;
  v33 = v11;
  if ( !(*(unsigned int (__fastcall **)(CProcess *))(*(_QWORD *)v36 + 96LL))(v36) )
    goto LABEL_17;
  v14 = v33;
  if ( !dword_180053390[v33] )
    goto LABEL_18;
  if ( (*(unsigned int (__fastcall **)(CProcess *))(*(_QWORD *)v13 + 136LL))(v13)
    || (*(unsigned int (__fastcall **)(CProcess *))(*(_QWORD *)v13 + 376LL))(v13) )
  {
LABEL_17:
    v14 = v33;
  }
  else
  {
    v14 = 0;
    v33 = 0;
  }
LABEL_18:
  if ( v14 == 3 && !(*(unsigned int (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 56LL))(a4) )
    CDuckingManager::OnRenderCommunicationsStreamStateChanged(v15, a3, v16, 0, a4);
  *(_QWORD *)&EventDescriptor.Id = &v36;
  EventDescriptor.Keyword = (ULONGLONG)&v35;
  v44 = &v33;
  v45 = 1;
  v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IAudioSessionInfo *))(*(_QWORD *)a3 + 72LL))(a3);
  v37 = 0;
  v34 = 0;
  v18 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4);
  CProcess::UpdateStreamCountAndProcessCategory(v36, v17, v33, 0, v18, &v37, (enum _APPLICATION_CATEGORY *)&v34);
  if ( v37 && v34 == 1 )
  {
    v19 = *((_DWORD *)v36 + 120);
    v20 = v19 ? *((_DWORD *)v36 + 121) : *((_DWORD *)v36 + 78);
    if ( v20 != 1 && !v19 && !*((_DWORD *)v36 + 104) && !CApplication::GetTotalActiveCaptureStreamCount(v35) )
    {
      v21 = v36;
      if ( *((_DWORD *)v36 + 119) != 3 )
      {
        *((_DWORD *)v36 + 119) = 3;
        *((_DWORD *)v21 + 120) = 1;
        *((_DWORD *)v21 + 121) = 1;
      }
      if ( !*((_DWORD *)v35 + 52) && *((_DWORD *)v35 + 54) )
        CApplication::RestrictAudioPlaybackToPrimaryCategories(v35);
      CProcess::StartInactivityTimer(v36);
    }
  }
  if ( ((unsigned int)CApplication::IsUnrestrictedBackgroundAudioCapable(v35)
     || (unsigned int)CApplication::IsBackgroundMediaRecordingCapable(v35))
    && !*((_DWORD *)v35 + 52)
    && !*((_DWORD *)v36 + 104) )
  {
    CProcess::StartInactivityTimer(v36);
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4) )
  {
    v22 = v35;
    v23 = (struct _RTL_CRITICAL_SECTION *)((char *)v35 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v35 + 32));
    v24 = 0;
    v25 = (_QWORD *)*((_QWORD *)v22 + 9);
    if ( v25 )
    {
      while ( 1 )
      {
        v26 = v25[2];
        if ( !*(_DWORD *)(v26 + 416) )
        {
          if ( *(_DWORD *)(v26 + 440) )
            break;
        }
        v25 = (_QWORD *)*v25;
        if ( !v25 )
          goto LABEL_48;
      }
      v24 = 1;
    }
LABEL_48:
    if ( v23 )
      LeaveCriticalSection(v23);
    if ( v24 )
      CApplicationManager::ApplyPBMPolicyForAllAppsInSession(v6, *((_DWORD *)v35 + 53), 0);
  }
  if ( v33 - 10 <= 1 || v33 - 1 <= 1 )
  {
    v27 = 0;
    v28 = 0;
    v29 = *((_DWORD *)v36 + 68);
    if ( v29 <= 0 )
      goto LABEL_73;
    do
      v27 += *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v36 + 33) + 8LL * (unsigned int)v28++) + 44LL);
    while ( v28 < v29 );
    if ( !v27 )
    {
LABEL_73:
      if ( !CProcess::GetActiveRenderStreamCount(v36, 0xAu)
        && !CProcess::GetActiveRenderStreamCount(v36, 2u)
        && !CProcess::GetActiveRenderStreamCount(v36, 1u) )
      {
        CApplication::SendTrackStateNotification(v35);
      }
    }
  }
  v34 = 0;
  v38 = 0;
  (**(void (__fastcall ***)(struct IAudioStreamInfo *, GUID *, struct IDuckingController **))a4)(
    a4,
    &GUID_390561ae_7375_4558_aff9_667acfe35ac5,
    &v38);
  v30 = v38;
  (*(void (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4);
  TsSessionIdUpdateStreamClassPolicyGains(*((_DWORD *)v36 + 41), v17, v33, 1, v30, &v34);
  if ( v38 )
    (*(void (__fastcall **)(struct IDuckingController *))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v34 )
    CApplicationManager::UpdateVolumeForAllAppsInSession(v6, *((unsigned int *)v35 + 53), 3);
  CApplicationManager::ApplyPBMPolicyForAllAppsInSession(v6, *((_DWORD *)v35 + 53), 0);
  if ( (unsigned int)CApplication::HasBackgroundAudioTask(v35) )
    CApplicationManager::SendBackgroundStreamStateChangedNotifiction(v6);
  if ( *((_DWORD *)v36 + 106) )
  {
    if ( Microsoft_Windows_AudioEnableBits < 0 )
      McTemplateU0zqq_EventWriteTransfer(
        v31,
        (unsigned int)&EVT_PBM_STREAM_STOPPED,
        *((_QWORD *)v35 + 3),
        *((_DWORD *)v36 + 40),
        v33);
  }
  return 0;
}

```

## disassembly

```asm
0x180022390  mov     [rsp-8+arg_0], rbx
0x180022395  push    rbp
0x180022396  push    rsi
0x180022397  push    rdi
0x180022398  push    r12
0x18002239a  push    r13
0x18002239c  push    r14
0x18002239e  push    r15
0x1800223a0  lea     rbp, [rsp-40h]
0x1800223a5  sub     rsp, 140h
0x1800223ac  mov     rax, cs:__security_cookie
0x1800223b3  xor     rax, rsp
0x1800223b6  mov     [rbp+70h+var_40], rax
0x1800223ba  mov     rdi, r9
0x1800223bd  mov     rsi, r8
0x1800223c0  mov     [rsp+170h+var_120], rdx
0x1800223c5  mov     r15, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x1800223cc  mov     rax, [rdx+0E0h]
0x1800223d3  mov     [rsp+170h+var_128], rax
0x1800223d8  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x1800223dd  mov     rbx, [rax+8]
0x1800223e1  mov     eax, [rbx]
0x1800223e3  xor     r13d, r13d
0x1800223e6  cmp     eax, 4
0x1800223e9  jbe     loc_18002259F
0x1800223ef  mov     rcx, [rbx+18h]
0x1800223f3  mov     rax, [rbx+10h]
0x1800223f7  bt      rax, 0Fh
0x1800223fc  jnb     loc_18002259F
0x180022402  mov     rax, rcx
0x180022405  and     eax, 8000h
0x18002240a  cmp     rax, rcx
0x18002240d  jnz     loc_18002259F
0x180022413  mov     rax, [rdi]
0x180022416  mov     rcx, rdi
0x180022419  mov     rax, [rax+50h]
0x18002241d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022422  mov     [rsp+170h+var_100], rax
0x180022427  mov     rax, [rdi]
0x18002242a  mov     rcx, rdi
0x18002242d  mov     rax, [rax+30h]
0x180022431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022436  mov     [rsp+170h+var_12C], eax
0x18002243a  mov     rax, [rdi]
0x18002243d  mov     rcx, rdi
0x180022440  mov     rax, [rax+38h]
0x180022444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022449  mov     [rsp+170h+var_118], eax
0x18002244d  mov     rax, [rsp+170h+var_120]
0x180022452  mov     ecx, [rax+0A0h]
0x180022458  mov     [rsp+170h+var_108], ecx
0x18002245c  mov     rcx, [rsp+170h+var_128]
0x180022461  mov     eax, [rcx+0D4h]
0x180022467  mov     [rsp+170h+var_104], eax
0x18002246b  mov     rax, [rcx+2B8h]
0x180022472  mov     [rsp+170h+var_F8], rax
0x180022477  mov     rdx, [rcx+18h]
0x18002247b  lea     rax, [rsp+170h+var_100]
0x180022480  mov     [rbp+70h+var_50], rax
0x180022484  mov     [rbp+70h+var_48], 8
0x18002248c  lea     rax, [rsp+170h+var_12C]
0x180022491  mov     [rbp+70h+var_60], rax
0x180022495  mov     [rbp+70h+var_58], 4
0x18002249d  lea     rax, [rsp+170h+var_118]
0x1800224a2  mov     [rbp+70h+var_70], rax
0x1800224a6  mov     [rbp+70h+var_68], 4
0x1800224ae  lea     rax, [rsp+170h+var_108]
0x1800224b3  mov     [rbp+70h+var_80], rax
0x1800224b7  mov     [rbp+70h+var_78], 4
0x1800224bf  lea     rax, [rsp+170h+var_104]
0x1800224c4  mov     [rbp+70h+var_90], rax
0x1800224c8  mov     [rbp+70h+var_88], 4
0x1800224d0  lea     rax, [rsp+170h+var_F8]
0x1800224d5  mov     [rbp+70h+var_A0], rax
0x1800224d9  mov     [rbp+70h+var_98], 8
0x1800224e1  test    rdx, rdx
0x1800224e4  jz      short loc_180022504
0x1800224e6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800224ed  nop     dword ptr [rax]
0x1800224f0  lea     rax, [rax+1]
0x1800224f4  cmp     [rdx+rax*2], r13w
0x1800224f9  jnz     short loc_1800224F0
0x1800224fb  lea     eax, ds:2[rax*2]
0x180022502  jmp     short loc_180022510
0x180022504  lea     rdx, unk_180053B30
0x18002250b  mov     eax, 2
0x180022510  mov     [rbp+70h+var_B0], rdx
0x180022514  mov     [rbp+70h+var_A8], eax
0x180022517  mov     [rbp+70h+var_A4], r13d
0x18002251b  mov     dword ptr [rbp+70h+EventDescriptor.Id], 0B000000h
0x180022522  movzx   eax, cs:word_18005893A
0x180022529  mov     dword ptr [rbp+70h+EventDescriptor.Level], eax
0x18002252c  mov     [rbp+70h+EventDescriptor.Keyword], 8000h
0x180022534  mov     rax, [rbx+8]
0x180022538  mov     [rbp+70h+var_D0.Ptr], rax
0x18002253c  movzx   eax, word ptr [rax]
0x18002253f  mov     [rbp+70h+var_D0.Size], eax
0x180022542  mov     dword ptr [rbp+70h+var_D0.0Ch], 2
0x180022549  lea     rax, unk_180058944
0x180022550  mov     [rbp+70h+var_C0], rax
0x180022554  mov     [rbp+70h+var_B8], 5Eh ; '^'
0x18002255b  mov     [rbp+70h+var_B4], 1
0x180022562  lea     rax, _TraceLoggingMetadataEnd
0x180022569  lea     rcx, _TraceLoggingMetadata
0x180022570  sub     eax, ecx
0x180022572  mov     dword ptr [rsp+170h+var_110], eax
0x180022576  mov     eax, dword ptr [rsp+170h+var_110]
0x18002257a  lea     rax, [rbp+70h+var_D0]
0x18002257e  mov     [rsp+170h+UserData], rax; UserData
0x180022583  mov     [rsp+170h+UserDataCount], 9; int
0x18002258b  xor     r9d, r9d; RelatedActivityId
0x18002258e  xor     r8d, r8d; ActivityId
0x180022591  lea     rdx, [rbp+70h+EventDescriptor]; EventDescriptor
0x180022595  mov     rcx, [rbx+20h]; RegHandle
0x180022599  call    cs:__imp_EventWriteTransfer
0x18002259f  mov     [rsp+170h+var_130], r13d
0x1800225a4  mov     rax, [rdi]
0x1800225a7  mov     rcx, rdi
0x1800225aa  mov     rax, [rax+30h]
0x1800225ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b3  cmp     eax, 18h
0x1800225b6  jb      short loc_1800225DD
0x1800225b8  mov     rcx, [rbp+78h]; this
0x1800225bc  mov     r9d, 80070057h; char *
0x1800225c2  lea     r8, aClientcoreMult_3; "clientcore\\multimedia\\audiocore\\serv"...
0x1800225c9  mov     edx, 0AFh; void *
0x1800225ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800225d3  mov     eax, 80070057h
0x1800225d8  jmp     loc_1800229E5
0x1800225dd  mov     rbx, [rsp+170h+var_120]
0x1800225e2  mov     [rsp+170h+var_130], eax
0x1800225e6  mov     rax, [rbx]
0x1800225e9  mov     rcx, rbx
0x1800225ec  mov     rax, [rax+60h]
0x1800225f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f5  test    eax, eax
0x1800225f7  jz      short loc_18002263F
0x1800225f9  mov     ecx, [rsp+170h+var_130]
0x1800225fd  lea     rdx, dword_180053390
0x180022604  cmp     [rdx+rcx*4], r13d
0x180022608  jz      short loc_180022643
0x18002260a  mov     rax, [rbx]
0x18002260d  mov     rcx, rbx
0x180022610  mov     rax, [rax+88h]
0x180022617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002261c  test    eax, eax
0x18002261e  jnz     short loc_18002263F
0x180022620  mov     rax, [rbx]
0x180022623  mov     rcx, rbx
0x180022626  mov     rax, [rax+178h]
0x18002262d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022632  test    eax, eax
0x180022634  jnz     short loc_18002263F
0x180022636  mov     ecx, r13d
0x180022639  mov     [rsp+170h+var_130], ecx
0x18002263d  jmp     short loc_180022643
0x18002263f  mov     ecx, [rsp+170h+var_130]
0x180022643  cmp     ecx, 3
0x180022646  jnz     short loc_18002266B
0x180022648  mov     rax, [rdi]
0x18002264b  mov     rcx, rdi
0x18002264e  mov     rax, [rax+38h]
0x180022652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022657  test    eax, eax
0x180022659  jnz     short loc_18002266B
0x18002265b  mov     qword ptr [rsp+170h+UserDataCount], rdi
0x180022660  xor     r9d, r9d
0x180022663  mov     rdx, rsi
0x180022666  call    ?OnRenderCommunicationsStreamStateChanged@CDuckingManager@@QEAAJPEAUIAudioSessionInfo@@W4_AudioStreamState@@1PEAUIAudioStreamInfo@@@Z; CDuckingManager::OnRenderCommunicationsStreamStateChanged(IAudioSessionInfo *,_AudioStreamState,_AudioStreamState,IAudioStreamInfo *)
0x18002266b  lea     rax, [rsp+170h+var_120]
0x180022670  mov     qword ptr [rbp+70h+EventDescriptor.Id], rax
0x180022674  lea     rax, [rsp+170h+var_128]
0x180022679  mov     [rbp+70h+EventDescriptor.Keyword], rax
0x18002267d  lea     rax, [rsp+170h+var_130]
0x180022682  mov     [rbp+70h+var_E0], rax
0x180022686  mov     [rbp+70h+var_D8], 1
0x18002268a  mov     rax, [rsi]
0x18002268d  mov     rcx, rsi
0x180022690  mov     rax, [rax+48h]
0x180022694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022699  mov     r12, rax
0x18002269c  mov     [rsp+170h+var_118], r13d
0x1800226a1  mov     [rsp+170h+var_12C], r13d
0x1800226a6  mov     rcx, [rdi]
0x1800226a9  mov     rax, [rcx+40h]
0x1800226ad  mov     rcx, rdi
0x1800226b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226b5  movzx   ecx, al
0x1800226b8  lea     rax, [rsp+170h+var_12C]
0x1800226bd  mov     [rsp+170h+var_140], rax; enum _APPLICATION_CATEGORY *
0x1800226c2  lea     rax, [rsp+170h+var_118]
0x1800226c7  mov     [rsp+170h+UserData], rax; int *
0x1800226cc  mov     [rsp+170h+UserDataCount], ecx; int
0x1800226d0  xor     r9d, r9d; int
0x1800226d3  mov     r8d, [rsp+170h+var_130]; unsigned int
0x1800226d8  mov     rdx, r12; unsigned __int16 *
0x1800226db  mov     rcx, [rsp+170h+var_120]; this
0x1800226e0  call    ?UpdateStreamCountAndProcessCategory@CProcess@@IEAAXPEBGKHHPEAHPEAW4_APPLICATION_CATEGORY@@@Z; CProcess::UpdateStreamCountAndProcessCategory(ushort const *,ulong,int,int,int *,_APPLICATION_CATEGORY *)
0x1800226e5  cmp     [rsp+170h+var_118], 0
0x1800226ea  jz      loc_180022789
0x1800226f0  cmp     [rsp+170h+var_12C], 1
0x1800226f5  jnz     loc_180022789
0x1800226fb  mov     rax, [rsp+170h+var_120]
0x180022700  mov     edx, [rax+1E0h]
0x180022706  test    edx, edx
0x180022708  jz      short loc_180022712
0x18002270a  mov     ecx, [rax+1E4h]
0x180022710  jmp     short loc_180022718
0x180022712  mov     ecx, [rax+138h]
0x180022718  cmp     ecx, 1
0x18002271b  jz      short loc_180022789
0x18002271d  test    edx, edx
0x18002271f  jnz     short loc_180022789
0x180022721  cmp     [rax+1A0h], edx
0x180022727  jnz     short loc_180022789
0x180022729  mov     rcx, [rsp+170h+var_128]; this
0x18002272e  call    ?GetTotalActiveCaptureStreamCount@CApplication@@QEAAIXZ; CApplication::GetTotalActiveCaptureStreamCount(void)
0x180022733  test    eax, eax
0x180022735  jnz     short loc_180022789
0x180022737  mov     rax, [rsp+170h+var_120]
0x18002273c  cmp     dword ptr [rax+1DCh], 3
0x180022743  jz      short loc_180022763
0x180022745  mov     dword ptr [rax+1DCh], 3
0x18002274f  mov     dword ptr [rax+1E0h], 1
0x180022759  mov     dword ptr [rax+1E4h], 1
0x180022763  mov     rcx, [rsp+170h+var_128]; this
0x180022768  cmp     dword ptr [rcx+0D0h], 0
0x18002276f  jnz     short loc_18002277F
0x180022771  cmp     dword ptr [rcx+0D8h], 0
0x180022778  jz      short loc_18002277F
0x18002277a  call    ?RestrictAudioPlaybackToPrimaryCategories@CApplication@@QEAAJXZ; CApplication::RestrictAudioPlaybackToPrimaryCategories(void)
0x18002277f  mov     rcx, [rsp+170h+var_120]; this
0x180022784  call    ?StartInactivityTimer@CProcess@@QEAAXXZ; CProcess::StartInactivityTimer(void)
0x180022789  mov     rcx, [rsp+170h+var_128]; this
0x18002278e  call    ?IsUnrestrictedBackgroundAudioCapable@CApplication@@QEAAHXZ; CApplication::IsUnrestrictedBackgroundAudioCapable(void)
0x180022793  test    eax, eax
0x180022795  jnz     short loc_1800227A5
0x180022797  mov     rcx, [rsp+170h+var_128]; this
0x18002279c  call    ?IsBackgroundMediaRecordingCapable@CApplication@@QEAAHXZ; CApplication::IsBackgroundMediaRecordingCapable(void)
0x1800227a1  test    eax, eax
0x1800227a3  jz      short loc_1800227C6
0x1800227a5  mov     rax, [rsp+170h+var_128]
0x1800227aa  cmp     dword ptr [rax+0D0h], 0
0x1800227b1  jnz     short loc_1800227C6
0x1800227b3  mov     rcx, [rsp+170h+var_120]; this
0x1800227b8  cmp     dword ptr [rcx+1A0h], 0
0x1800227bf  jnz     short loc_1800227C6
0x1800227c1  call    ?StartInactivityTimer@CProcess@@QEAAXXZ; CProcess::StartInactivityTimer(void)
0x1800227c6  mov     rax, [rdi]
0x1800227c9  mov     rcx, rdi
0x1800227cc  mov     rax, [rax+40h]
0x1800227d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227d5  test    al, al
0x1800227d7  jz      short loc_18002284F
0x1800227d9  mov     rbx, [rsp+170h+var_128]
0x1800227de  lea     rsi, [rbx+20h]
0x1800227e2  mov     rcx, rsi; lpCriticalSection
0x1800227e5  call    cs:__imp_EnterCriticalSection
0x1800227eb  mov     r14d, r13d
0x1800227ee  mov     rax, [rbx+48h]
0x1800227f2  test    rax, rax
0x1800227f5  jz      short loc_180022826
0x1800227f7  nop     word ptr [rax+rax+00000000h]
0x180022800  mov     rcx, [rax+10h]
0x180022804  cmp     dword ptr [rcx+1A0h], 0
0x18002280b  jnz     short loc_180022816
0x18002280d  cmp     dword ptr [rcx+1B8h], 0
0x180022814  jnz     short loc_180022820
0x180022816  mov     rax, [rax]
0x180022819  test    rax, rax
0x18002281c  jnz     short loc_180022800
0x18002281e  jmp     short loc_180022826
0x180022820  mov     r14d, 1
0x180022826  test    rsi, rsi
0x180022829  jz      short loc_180022834
0x18002282b  mov     rcx, rsi; lpCriticalSection
0x18002282e  call    cs:__imp_LeaveCriticalSection
0x180022834  test    r14d, r14d
0x180022837  jz      short loc_18002284F
0x180022839  xor     r8d, r8d; int
0x18002283c  mov     rdx, [rsp+170h+var_128]
0x180022841  mov     edx, [rdx+0D4h]; unsigned int
0x180022847  mov     rcx, r15; this
0x18002284a  call    ?ApplyPBMPolicyForAllAppsInSession@CApplicationManager@@QEAAJKH@Z; CApplicationManager::ApplyPBMPolicyForAllAppsInSession(ulong,int)
0x18002284f  mov     ecx, [rsp+170h+var_130]
0x180022853  lea     eax, [rcx-0Ah]
0x180022856  cmp     eax, 1
0x180022859  jbe     short loc_180022863
0x18002285b  lea     eax, [rcx-1]
0x18002285e  cmp     eax, 1
0x180022861  ja      short loc_1800228DD
0x180022863  mov     rcx, [rsp+170h+var_120]; this
0x180022868  mov     r9d, r13d
0x18002286b  mov     r8d, r13d
0x18002286e  mov     r10d, [rcx+110h]
0x180022875  test    r10d, r10d
0x180022878  jle     short loc_18002289F
0x18002287a  nop     word ptr [rax+rax+00h]
0x180022880  mov     edx, r8d
0x180022883  mov     rax, [rcx+108h]
  ... truncated ...
```
