# CApplicationManager::OnStreamStarted(CProcess *,IAudioSessionInfo *,IAudioStreamInfo *)

- ea: `0x180024bf0`
- end: `0x180025281`
- name: `?OnStreamStarted@CApplicationManager@@QEAAJPEAVCProcess@@PEAUIAudioSessionInfo@@PEAUIAudioStreamInfo@@@Z`
- size: `1681`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, struct CProcess *, struct IAudioSessionInfo *, struct IAudioStreamInfo *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024bd0`

## callees

- `0x180009090`
- `0x18000a384`
- `0x180015fe0`
- `0x1800161d0`
- `0x180016a30`
- `0x18001b5a0`
- `0x18001b6c0`
- `0x18001c4f8`
- `0x18001c774`
- `0x18001d580`
- `0x18001d960`
- `0x18001ece0`
- `0x1800242f0`
- `0x180024ac4`
- `0x180024bf0`
- `0x1800267d8`
- `0x1800279f0`
- `0x18002e490`
- `0x180031960`
- `0x18003a324`
- `0x18003ce48`
- `0x18003f33c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024df9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024df9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CApplicationManager::OnStreamStarted(
        CApplicationManager *this,
        CApplication **a2,
        struct IAudioSessionInfo *a3,
        struct IAudioStreamInfo *a4)
{
  CApplicationManager *v6; // r13
  int v7; // r12d
  __int64 v8; // rbx
  __int64 *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v14; // ecx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int16 *v17; // rbx
  int v18; // r14d
  int v19; // edx
  int v20; // r8d
  int v21; // r15d
  int i; // edx
  int j; // edx
  __int64 v24; // rcx
  int v25; // esi
  signed int k; // edx
  unsigned __int8 v27; // al
  CProcess *v28; // rax
  unsigned int v29; // ecx
  CApplication *v30; // rbx
  struct IDuckingController *v31; // rbx
  int v32; // ecx
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  unsigned int v34; // [rsp+40h] [rbp-C0h] BYREF
  CApplication *v35; // [rsp+48h] [rbp-B8h] BYREF
  CProcess *v36; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  struct IDuckingController *v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+6Ch] [rbp-94h] BYREF
  int v41; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v42; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v45; // [rsp+98h] [rbp-68h]
  char v46; // [rsp+A0h] [rbp-60h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  __int16 *v48; // [rsp+C0h] [rbp-40h]
  int v49; // [rsp+C8h] [rbp-38h]
  int v50; // [rsp+CCh] [rbp-34h]
  __int64 *v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  int v53; // [rsp+DCh] [rbp-24h]
  unsigned __int16 **v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  int *v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  int *v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+108h] [rbp+8h]
  int *v60; // [rsp+110h] [rbp+10h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  int *v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  __int64 *v64; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v36 = (CProcess *)a2;
  v6 = g_ApplicationManager;
  v35 = a2[28];
  v7 = 0;
  v34 = 0;
  v8 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v8 > 4u
    && (*(_QWORD *)(v8 + 16) & 0x8000LL) != 0
    && (*(_QWORD *)(v8 + 24) & 0x8000LL) == *(_QWORD *)(v8 + 24) )
  {
    v43 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 80LL))(a4);
    v37 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 48LL))(a4);
    v39 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 56LL))(a4);
    v40 = *((_DWORD *)v36 + 40);
    v41 = *((_DWORD *)v35 + 53);
    v42 = (unsigned __int16 *)*((_QWORD *)v35 + 87);
    v9 = (__int64 *)*((_QWORD *)v35 + 3);
    v64 = &v43;
    v65 = 8;
    v62 = &v37;
    v63 = 4;
    v60 = &v39;
    v61 = 4;
    v58 = &v40;
    v59 = 4;
    v56 = &v41;
    v57 = 4;
    v54 = &v42;
    v55 = 8;
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)v9 + v10) );
      v11 = 2 * v10 + 2;
    }
    else
    {
      v9 = &qword_180053B30;
      v11 = 2;
    }
    v51 = v9;
    v52 = v11;
    v53 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0x8000;
    UserData.Ptr = *(_QWORD *)(v8 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v48 = &word_1800589AE;
    v49 = 94;
    v50 = 1;
    LODWORD(v38) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v8 + 32), &EventDescriptor, 0, 0, 9u, &UserData);
  }
  v12 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 48LL))(a4);
  if ( v12 >= 0x18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\workitem.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  v34 = v12;
  if ( !(*(unsigned int (__fastcall **)(CProcess *))(*(_QWORD *)v36 + 96LL))(v36) )
    goto LABEL_17;
  v14 = v34;
  if ( !*((_DWORD *)&qword_180053390 + v34) )
    goto LABEL_18;
  if ( (*(unsigned int (__fastcall **)(CProcess *))(*(_QWORD *)v36 + 136LL))(v36)
    || (*(unsigned int (__fastcall **)(CProcess *))(*(_QWORD *)v36 + 376LL))(v36) )
  {
LABEL_17:
    v14 = v34;
  }
  else
  {
    v14 = 0;
    v34 = 0;
  }
LABEL_18:
  if ( v14 == 3 && !(*(unsigned int (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 56LL))(a4) )
    CDuckingManager::OnRenderCommunicationsStreamStateChanged(v15, a3, v16, 1, a4);
  *(_QWORD *)&EventDescriptor.Id = &v36;
  EventDescriptor.Keyword = (ULONGLONG)&v35;
  v45 = &v34;
  v46 = 1;
  v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IAudioSessionInfo *))(*(_QWORD *)a3 + 72LL))(a3);
  v42 = v17;
  v18 = 0;
  v19 = 0;
  v20 = *((_DWORD *)v36 + 68);
  if ( v20 <= 0 )
  {
    v25 = 0;
    v18 = 0;
    v21 = 0;
  }
  else
  {
    do
      v18 += *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v36 + 33) + 8LL * (unsigned int)v19++) + 44LL);
    while ( v19 < v20 );
    v21 = 0;
    for ( i = 0; i < v20; ++i )
      v21 += *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v36 + 33) + 8LL * i) + 40LL);
    for ( j = 0; j < v20; ++j )
    {
      v24 = *(_QWORD *)(*((_QWORD *)v36 + 33) + 8LL * j);
      v7 += *(_DWORD *)(v24 + 8);
    }
    v25 = 0;
    for ( k = 0; k < v20; ++k )
    {
      if ( k < 0 || k >= v20 )
      {
        ATL::_AtlRaiseException(v24, k);
        JUMPOUT(0x180025281LL);
      }
      v24 = *(_QWORD *)(*((_QWORD *)v36 + 33) + 8LL * k);
      v25 += *(_DWORD *)(v24 + 4);
    }
  }
  v27 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4);
  CProcess::UpdateStreamCountAndProcessCategory(v36, v17, v34, 1, v27, 0, 0);
  if ( (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4)
    || v34 == 2
    || (unsigned int)CApplication::IsUnrestrictedBackgroundAudioCapable(v35) )
  {
    v28 = v36;
    if ( *((_DWORD *)v36 + 119) == 3 )
    {
      *(_QWORD *)((char *)v36 + 476) = 0;
      *((_DWORD *)v28 + 121) = 4;
    }
    CApplication::RemoveAudioPlaybackRestriction(v35);
    CProcess::DeleteInactivityTimer(v36);
    CApplication::CleanupBCMStartupLatencyGracePeriod(v35);
  }
  v29 = v34;
  if ( v34 == 2 )
  {
    CApplication::ApplySmtcRelatedPolicy(v35);
    v29 = v34;
  }
  if ( *((_DWORD *)v36 + 106) && (v29 == 2 || (unsigned int)CApplication::IsUnrestrictedBackgroundAudioCapable(v35)) )
  {
    v30 = v35;
    if ( *((_DWORD *)v35 + 108) )
    {
      CApplication::CleanupGoodFaithExemptionTimer(v35);
      if ( *((_DWORD *)v30 + 155) == 2 )
      {
        *(_QWORD *)((char *)v30 + 620) = 0;
        *(_QWORD *)((char *)v30 + 628) = 0;
        *(_QWORD *)((char *)v30 + 636) = 0;
        *((_DWORD *)v30 + 161) = 1;
      }
      *((_DWORD *)v30 + 108) = 0;
      CApplicationManager::ApplyPBMPolicy(g_ApplicationManager, v30, 0xD1u, 0);
    }
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4)
    && (unsigned int)CApplication::IsBackgroundMediaRecordingCapable(v35) )
  {
    CApplicationManager::ApplyPBMPolicyForAllAppsInSession(v6, *((_DWORD *)v35 + 53), 0);
  }
  v37 = 0;
  v38 = 0;
  (**(void (__fastcall ***)(struct IAudioStreamInfo *, GUID *, struct IDuckingController **))a4)(
    a4,
    &GUID_390561ae_7375_4558_aff9_667acfe35ac5,
    &v38);
  v31 = v38;
  (*(void (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a4 + 64LL))(a4);
  TsSessionIdUpdateStreamClassPolicyGains(*((_DWORD *)v36 + 41), v42, v34, 0, v31, &v37);
  if ( v38 )
    (*(void (__fastcall **)(struct IDuckingController *))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v37 )
    CApplicationManager::UpdateVolumeForAllAppsInSession(v6, *((unsigned int *)v35 + 53), 3);
  CApplicationManager::ApplyPBMPolicyForAllAppsInSession(v6, *((_DWORD *)v35 + 53), 0);
  if ( (v34 - 10 <= 1 || v34 - 1 <= 1) && !(v18 + v21 + v25 + v7) )
    CApplication::SendTrackStateNotification(v35);
  if ( (unsigned int)CApplication::HasBackgroundAudioTask(v35) )
    CApplicationManager::SendBackgroundStreamStateChangedNotifiction(v6);
  if ( *((_DWORD *)v36 + 106) )
  {
    if ( Microsoft_Windows_AudioEnableBits < 0 )
      McTemplateU0zqq_EventWriteTransfer(
        v32,
        (unsigned int)EVT_PBM_STREAM_STARTED,
        *((_QWORD *)v35 + 3),
        *((_DWORD *)v36 + 40),
        v34);
  }
  return 0;
}

```

## disassembly

```asm
0x180024bf0  mov     [rsp-8+arg_0], rbx
0x180024bf5  push    rbp
0x180024bf6  push    rsi
0x180024bf7  push    rdi
0x180024bf8  push    r12
0x180024bfa  push    r13
0x180024bfc  push    r14
0x180024bfe  push    r15
0x180024c00  lea     rbp, [rsp-50h]
0x180024c05  sub     rsp, 150h
0x180024c0c  mov     rax, cs:__security_cookie
0x180024c13  xor     rax, rsp
0x180024c16  mov     [rbp+80h+var_40], rax
0x180024c1a  mov     rdi, r9
0x180024c1d  mov     rsi, r8
0x180024c20  mov     [rsp+180h+var_130], rdx
0x180024c25  mov     r13, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x180024c2c  mov     rax, [rdx+0E0h]
0x180024c33  mov     [rsp+180h+var_138], rax
0x180024c38  xor     r12d, r12d
0x180024c3b  mov     [rsp+180h+var_140], r12d
0x180024c40  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180024c45  mov     rbx, [rax+8]
0x180024c49  mov     eax, [rbx]
0x180024c4b  cmp     eax, 4
0x180024c4e  jbe     loc_180024DFF
0x180024c54  mov     rcx, [rbx+18h]
0x180024c58  mov     rax, [rbx+10h]
0x180024c5c  bt      rax, 0Fh
0x180024c61  jnb     loc_180024DFF
0x180024c67  mov     rax, rcx
0x180024c6a  and     eax, 8000h
0x180024c6f  cmp     rax, rcx
0x180024c72  jnz     loc_180024DFF
0x180024c78  mov     rax, [rdi]
0x180024c7b  mov     rcx, rdi
0x180024c7e  mov     rax, [rax+50h]
0x180024c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c87  mov     [rbp+80h+var_100], rax
0x180024c8b  mov     rax, [rdi]
0x180024c8e  mov     rcx, rdi
0x180024c91  mov     rax, [rax+30h]
0x180024c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c9a  mov     [rsp+180h+var_128], eax
0x180024c9e  mov     rax, [rdi]
0x180024ca1  mov     rcx, rdi
0x180024ca4  mov     rax, [rax+38h]
0x180024ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cad  mov     [rsp+180h+var_118], eax
0x180024cb1  mov     rax, [rsp+180h+var_130]
0x180024cb6  mov     ecx, [rax+0A0h]
0x180024cbc  mov     [rsp+180h+var_114], ecx
0x180024cc0  mov     rcx, [rsp+180h+var_138]
0x180024cc5  mov     eax, [rcx+0D4h]
0x180024ccb  mov     [rsp+180h+var_110], eax
0x180024ccf  mov     rax, [rcx+2B8h]
0x180024cd6  mov     [rsp+180h+var_108], rax
0x180024cdb  mov     rdx, [rcx+18h]
0x180024cdf  lea     rax, [rbp+80h+var_100]
0x180024ce3  mov     [rbp+80h+var_50], rax
0x180024ce7  mov     [rbp+80h+var_48], 8
0x180024cef  lea     rax, [rsp+180h+var_128]
0x180024cf4  mov     [rbp+80h+var_60], rax
0x180024cf8  mov     [rbp+80h+var_58], 4
0x180024d00  lea     rax, [rsp+180h+var_118]
0x180024d05  mov     [rbp+80h+var_70], rax
0x180024d09  mov     [rbp+80h+var_68], 4
0x180024d11  lea     rax, [rsp+180h+var_114]
0x180024d16  mov     [rbp+80h+var_80], rax
0x180024d1a  mov     [rbp+80h+var_78], 4
0x180024d22  lea     rax, [rsp+180h+var_110]
0x180024d27  mov     [rbp+80h+var_90], rax
0x180024d2b  mov     [rbp+80h+var_88], 4
0x180024d33  lea     rax, [rsp+180h+var_108]
0x180024d38  mov     [rbp+80h+var_A0], rax
0x180024d3c  mov     [rbp+80h+var_98], 8
0x180024d44  test    rdx, rdx
0x180024d47  jz      short loc_180024D64
0x180024d49  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180024d50  lea     rax, [rax+1]
0x180024d54  cmp     [rdx+rax*2], r12w
0x180024d59  jnz     short loc_180024D50
0x180024d5b  lea     eax, ds:2[rax*2]
0x180024d62  jmp     short loc_180024D70
0x180024d64  lea     rdx, qword_180053B30
0x180024d6b  mov     eax, 2
0x180024d70  mov     [rbp+80h+var_B0], rdx
0x180024d74  mov     [rbp+80h+var_A8], eax
0x180024d77  mov     [rbp+80h+var_A4], r12d
0x180024d7b  mov     dword ptr [rbp+80h+EventDescriptor.Id], 0B000000h
0x180024d82  movzx   eax, cs:word_1800589A4
0x180024d89  mov     dword ptr [rbp+80h+EventDescriptor.Level], eax
0x180024d8c  mov     [rbp+80h+EventDescriptor.Keyword], 8000h
0x180024d94  mov     rax, [rbx+8]
0x180024d98  mov     [rbp+80h+var_D0.Ptr], rax
0x180024d9c  movzx   eax, word ptr [rax]
0x180024d9f  mov     [rbp+80h+var_D0.Size], eax
0x180024da2  mov     dword ptr [rbp+80h+var_D0.0Ch], 2
0x180024da9  lea     rax, word_1800589AE
0x180024db0  mov     [rbp+80h+var_C0], rax
0x180024db4  mov     [rbp+80h+var_B8], 5Eh ; '^'
0x180024dbb  mov     [rbp+80h+var_B4], 1
0x180024dc2  lea     rax, _TraceLoggingMetadataEnd
0x180024dc9  lea     rcx, _TraceLoggingMetadata
0x180024dd0  sub     eax, ecx
0x180024dd2  mov     dword ptr [rsp+180h+var_120], eax
0x180024dd6  mov     eax, dword ptr [rsp+180h+var_120]
0x180024dda  lea     rax, [rbp+80h+var_D0]
0x180024dde  mov     [rsp+180h+UserData], rax; UserData
0x180024de3  mov     [rsp+180h+UserDataCount], 9; int
0x180024deb  xor     r9d, r9d; RelatedActivityId
0x180024dee  xor     r8d, r8d; ActivityId
0x180024df1  lea     rdx, [rbp+80h+EventDescriptor]; EventDescriptor
0x180024df5  mov     rcx, [rbx+20h]; RegHandle
0x180024df9  call    cs:__imp_EventWriteTransfer
0x180024dff  mov     rax, [rdi]
0x180024e02  mov     rcx, rdi
0x180024e05  mov     rax, [rax+30h]
0x180024e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e0e  cmp     eax, 18h
0x180024e11  jb      short loc_180024E3B
0x180024e13  mov     rcx, [rbp+88h]; this
0x180024e1a  mov     r9d, 80070057h; char *
0x180024e20  lea     r8, aClientcoreMult_3; "clientcore\\multimedia\\audiocore\\serv"...
0x180024e27  mov     edx, 27h ; '''; void *
0x180024e2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e31  mov     eax, 80070057h
0x180024e36  jmp     loc_180025254
0x180024e3b  mov     rbx, [rsp+180h+var_130]
0x180024e40  mov     [rsp+180h+var_140], eax
0x180024e44  mov     rax, [rbx]
0x180024e47  mov     rcx, rbx
0x180024e4a  mov     rax, [rax+60h]
0x180024e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e53  test    eax, eax
0x180024e55  jz      short loc_180024E9D
0x180024e57  mov     ecx, [rsp+180h+var_140]
0x180024e5b  lea     rdx, qword_180053390
0x180024e62  cmp     [rdx+rcx*4], r12d
0x180024e66  jz      short loc_180024EA1
0x180024e68  mov     rax, [rbx]
0x180024e6b  mov     rcx, rbx
0x180024e6e  mov     rax, [rax+88h]
0x180024e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e7a  test    eax, eax
0x180024e7c  jnz     short loc_180024E9D
0x180024e7e  mov     rax, [rbx]
0x180024e81  mov     rcx, rbx
0x180024e84  mov     rax, [rax+178h]
0x180024e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e90  test    eax, eax
0x180024e92  jnz     short loc_180024E9D
0x180024e94  mov     ecx, r12d
0x180024e97  mov     [rsp+180h+var_140], ecx
0x180024e9b  jmp     short loc_180024EA1
0x180024e9d  mov     ecx, [rsp+180h+var_140]
0x180024ea1  cmp     ecx, 3
0x180024ea4  jnz     short loc_180024ECC
0x180024ea6  mov     rax, [rdi]
0x180024ea9  mov     rcx, rdi
0x180024eac  mov     rax, [rax+38h]
0x180024eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eb5  test    eax, eax
0x180024eb7  jnz     short loc_180024ECC
0x180024eb9  mov     qword ptr [rsp+180h+UserDataCount], rdi
0x180024ebe  mov     r9d, 1
0x180024ec4  mov     rdx, rsi
0x180024ec7  call    ?OnRenderCommunicationsStreamStateChanged@CDuckingManager@@QEAAJPEAUIAudioSessionInfo@@W4_AudioStreamState@@1PEAUIAudioStreamInfo@@@Z; CDuckingManager::OnRenderCommunicationsStreamStateChanged(IAudioSessionInfo *,_AudioStreamState,_AudioStreamState,IAudioStreamInfo *)
0x180024ecc  lea     rax, [rsp+180h+var_130]
0x180024ed1  mov     qword ptr [rbp+80h+EventDescriptor.Id], rax
0x180024ed5  lea     rax, [rsp+180h+var_138]
0x180024eda  mov     [rbp+80h+EventDescriptor.Keyword], rax
0x180024ede  lea     rax, [rsp+180h+var_140]
0x180024ee3  mov     [rbp+80h+var_E8], rax
0x180024ee7  mov     [rbp+80h+var_E0], 1
0x180024eeb  mov     rax, [rsi]
0x180024eee  mov     rcx, rsi
0x180024ef1  mov     rax, [rax+48h]
0x180024ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024efa  mov     rbx, rax
0x180024efd  mov     [rsp+180h+var_108], rax
0x180024f02  mov     r9, [rsp+180h+var_130]
0x180024f07  mov     r14d, r12d
0x180024f0a  mov     edx, r12d
0x180024f0d  mov     r8d, [r9+110h]
0x180024f14  test    r8d, r8d
0x180024f17  jle     loc_180024FAB
0x180024f1d  nop     dword ptr [rax]
0x180024f20  mov     ecx, edx
0x180024f22  mov     rax, [r9+108h]
0x180024f29  mov     rcx, [rax+rcx*8]
0x180024f2d  add     r14d, [rcx+2Ch]
0x180024f31  inc     edx
0x180024f33  cmp     edx, r8d
0x180024f36  jl      short loc_180024F20
0x180024f38  mov     r15d, r12d
0x180024f3b  mov     edx, r12d
0x180024f3e  xchg    ax, ax
0x180024f40  movsxd  rcx, edx
0x180024f43  mov     rax, [r9+108h]
0x180024f4a  mov     rcx, [rax+rcx*8]
0x180024f4e  add     r15d, [rcx+28h]
0x180024f52  inc     edx
0x180024f54  cmp     edx, r8d
0x180024f57  jl      short loc_180024F40
0x180024f59  xor     edx, edx
0x180024f5b  nop     dword ptr [rax+rax+00h]
0x180024f60  movsxd  rcx, edx
0x180024f63  mov     rax, [r9+108h]
0x180024f6a  mov     rcx, [rax+rcx*8]; unsigned int
0x180024f6e  add     r12d, [rcx+8]
0x180024f72  inc     edx
0x180024f74  cmp     edx, r8d
0x180024f77  jl      short loc_180024F60
0x180024f79  xor     esi, esi
0x180024f7b  xor     edx, edx; unsigned int
0x180024f7d  nop     dword ptr [rax]
0x180024f80  test    edx, edx
0x180024f82  js      loc_18002527B
0x180024f88  cmp     edx, r8d
0x180024f8b  jge     loc_18002527B
0x180024f91  movsxd  rcx, edx
0x180024f94  mov     rax, [r9+108h]
0x180024f9b  mov     rcx, [rax+rcx*8]
0x180024f9f  add     esi, [rcx+4]
0x180024fa2  inc     edx
0x180024fa4  cmp     edx, r8d
0x180024fa7  jl      short loc_180024F80
0x180024fa9  jmp     short loc_180024FB4
0x180024fab  mov     esi, r12d
0x180024fae  mov     r14d, r12d
0x180024fb1  mov     r15d, r12d
0x180024fb4  mov     rax, [rdi]
0x180024fb7  mov     rcx, rdi
0x180024fba  mov     rax, [rax+40h]
0x180024fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fc3  movzx   eax, al
0x180024fc6  xor     ecx, ecx
0x180024fc8  mov     [rsp+180h+var_150], rcx; enum _APPLICATION_CATEGORY *
0x180024fcd  mov     [rsp+180h+UserData], rcx; int *
0x180024fd2  mov     [rsp+180h+UserDataCount], eax; int
0x180024fd6  mov     r9d, 1; int
0x180024fdc  mov     r8d, [rsp+180h+var_140]; unsigned int
0x180024fe1  mov     rdx, rbx; unsigned __int16 *
0x180024fe4  mov     rcx, [rsp+180h+var_130]; this
0x180024fe9  call    ?UpdateStreamCountAndProcessCategory@CProcess@@IEAAXPEBGKHHPEAHPEAW4_APPLICATION_CATEGORY@@@Z; CProcess::UpdateStreamCountAndProcessCategory(ushort const *,ulong,int,int,int *,_APPLICATION_CATEGORY *)
0x180024fee  mov     rax, [rdi]
0x180024ff1  mov     rcx, rdi
0x180024ff4  mov     rax, [rax+40h]
0x180024ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ffd  test    al, al
0x180024fff  jnz     short loc_180025016
0x180025001  cmp     [rsp+180h+var_140], 2
0x180025006  jz      short loc_180025016
0x180025008  mov     rcx, [rsp+180h+var_138]; this
0x18002500d  call    ?IsUnrestrictedBackgroundAudioCapable@CApplication@@QEAAHXZ; CApplication::IsUnrestrictedBackgroundAudioCapable(void)
0x180025012  test    eax, eax
0x180025014  jz      short loc_180025055
0x180025016  mov     rax, [rsp+180h+var_130]
0x18002501b  cmp     dword ptr [rax+1DCh], 3
0x180025022  jnz     short loc_180025037
0x180025024  xor     ecx, ecx
0x180025026  mov     [rax+1DCh], rcx
0x18002502d  mov     dword ptr [rax+1E4h], 4
0x180025037  mov     rcx, [rsp+180h+var_138]; this
0x18002503c  call    ?RemoveAudioPlaybackRestriction@CApplication@@QEAAJXZ; CApplication::RemoveAudioPlaybackRestriction(void)
0x180025041  mov     rcx, [rsp+180h+var_130]; this
0x180025046  call    ?DeleteInactivityTimer@CProcess@@QEAAXXZ; CProcess::DeleteInactivityTimer(void)
0x18002504b  mov     rcx, [rsp+180h+var_138]; this
0x180025050  call    ?CleanupBCMStartupLatencyGracePeriod@CApplication@@QEAAXXZ; CApplication::CleanupBCMStartupLatencyGracePeriod(void)
0x180025055  mov     ecx, [rsp+180h+var_140]
0x180025059  cmp     ecx, 2
0x18002505c  jnz     short loc_18002506C
0x18002505e  mov     rcx, [rsp+180h+var_138]; this
0x180025063  call    ?ApplySmtcRelatedPolicy@CApplication@@QEAAXXZ; CApplication::ApplySmtcRelatedPolicy(void)
0x180025068  mov     ecx, [rsp+180h+var_140]
0x18002506c  mov     rax, [rsp+180h+var_130]
0x180025071  cmp     dword ptr [rax+1A8h], 0
0x180025078  jz      short loc_1800250EB
0x18002507a  cmp     ecx, 2
0x18002507d  jz      short loc_18002508D
0x18002507f  mov     rcx, [rsp+180h+var_138]; this
0x180025084  call    ?IsUnrestrictedBackgroundAudioCapable@CApplication@@QEAAHXZ; CApplication::IsUnrestrictedBackgroundAudioCapable(void)
0x180025089  test    eax, eax
0x18002508b  jz      short loc_1800250EB
0x18002508d  mov     rbx, [rsp+180h+var_138]
0x180025092  cmp     dword ptr [rbx+1B0h], 0
0x180025099  jz      short loc_1800250EB
0x18002509b  mov     rcx, rbx; this
0x18002509e  call    ?CleanupGoodFaithExemptionTimer@CApplication@@QEAAJXZ; CApplication::CleanupGoodFaithExemptionTimer(void)
0x1800250a3  xor     eax, eax
0x1800250a5  cmp     dword ptr [rbx+26Ch], 2
0x1800250ac  jnz     short loc_1800250CD
0x1800250ae  mov     [rbx+26Ch], rax
0x1800250b5  mov     [rbx+274h], rax
0x1800250bc  mov     [rbx+27Ch], rax
0x1800250c3  mov     dword ptr [rbx+284h], 1
0x1800250cd  mov     [rbx+1B0h], eax
0x1800250d3  xor     r9d, r9d; int
0x1800250d6  mov     r8d, 0D1h; unsigned int
  ... truncated ...
```
