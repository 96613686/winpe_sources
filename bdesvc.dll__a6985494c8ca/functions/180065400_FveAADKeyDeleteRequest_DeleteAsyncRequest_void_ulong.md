# FveAADKeyDeleteRequest::DeleteAsyncRequest(void * *,ulong)

- ea: `0x180065400`
- end: `0x180065aa7`
- name: `?DeleteAsyncRequest@FveAADKeyDeleteRequest@@SAJPEAPEAXK@Z`
- size: `1703`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180063c84`

## callees

- `0x180001fe8`
- `0x1800031c8`
- `0x180009f30`
- `0x180009f60`
- `0x180009fd0`
- `0x18000daf8`
- `0x180024a18`
- `0x180025ed4`
- `0x1800261d8`
- `0x18002f160`
- `0x18002f28c`
- `0x180034070`
- `0x180034d28`
- `0x1800612f8`
- `0x1800621f0`
- `0x180063988`
- `0x180065400`
- `0x180065bd8`
- `0x180065cb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065879`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800658aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065850`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065879`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800658aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006583c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006583c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065896`
- `FVESKYBACKUP!FveDeleteRecoveryPasswordsFromCloudDomain` at `0x180065633`
- `FVESKYBACKUP!FveDeleteRecoveryPasswordsFromCloudDomain` at `0x180065633`

## string_xrefs

- `0x180065686`: `FveDeleteRPFromCloudDomain`

## pseudocode

```c
__int64 __fastcall FveAADKeyDeleteRequest::DeleteAsyncRequest(void **a1, unsigned int a2)
{
  unsigned int v2; // esi
  struct _LIST_ENTRY *v4; // r15
  int v5; // r14d
  int v6; // r12d
  const wchar_t *v7; // r13
  PVOID v8; // rcx
  int OSVolume; // ebx
  int AsyncRequestList; // ebx
  int AADDeletionRequests; // eax
  PVOID *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rdi
  unsigned int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  PVOID *v18; // r10
  HRESULT v19; // eax
  __int64 v20; // r10
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  HANDLE ProcessHeap; // rax
  void *v25; // rdi
  HANDLE v26; // rax
  struct _FVE_AAD_DELETE_INFO_V2 *v27; // rdi
  HANDLE v28; // rax
  unsigned int v30; // r14d
  PVOID *v31; // r10
  int v32; // r15d
  int v33; // eax
  unsigned int PersistentRequestDelayTimer; // eax
  ULONG v35; // edi
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-9Ch] BYREF
  int v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+6Ch] [rbp-94h] BYREF
  ULONG pulResult; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  struct _LIST_ENTRY *v42; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v43; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v44[24]; // [rsp+90h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-58h] BYREF
  struct _FVE_AAD_DELETE_INFO_V2 *v46; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v47; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v48; // [rsp+BCh] [rbp-44h] BYREF
  int v49; // [rsp+C0h] [rbp-40h] BYREF
  int v50[3]; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int16 v51[264]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = a2;
  v37 = a2;
  v49 = 0;
  memset_0(v51, 0, 0x208u);
  v4 = 0;
  v42 = 0;
  v46 = 0;
  v5 = 0;
  lpMem = 0;
  v6 = 0;
  v47 = 0;
  v36 = 0;
  v48 = 0;
  pulResult = 0;
  v50[0] = 0;
  v38 = 0;
  v41 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
  v7 = L"NgscbGetOSVolume";
  OSVolume = NgscbGetOSVolume(v51);
  if ( !OSVolume )
    goto LABEL_9;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
      (unsigned int)OSVolume);
  if ( OSVolume >= 0 )
  {
LABEL_9:
    v47 = v2;
    AsyncRequestList = GetAsyncRequestList(v8, &v42);
    if ( AsyncRequestList < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
          (unsigned int)AsyncRequestList);
      v7 = L"GetAsyncRequestList";
      v38 = AsyncRequestList;
    }
    v4 = v42;
    AADDeletionRequests = FveAADKeyDeleteRequest::GetAADDeletionRequests(
                            a1,
                            v2,
                            v42,
                            &v46,
                            (struct _FVE_AAD_DELETE_REQUEST **)&lpMem,
                            &v47);
    OSVolume = AADDeletionRequests;
    if ( AADDeletionRequests < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
          (unsigned int)AADDeletionRequests);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      v7 = L"GetAADDeletionRequests";
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 )
        WPP_SF_d(v12[2], 78, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, (unsigned int)OSVolume);
      goto LABEL_42;
    }
    v13 = v47;
    v14 = 0;
    v39 = 0;
    if ( v47 )
    {
      while ( 1 )
      {
        v15 = v13 - v14;
        v16 = 16;
        if ( v15 < 0x10 )
          v16 = v15;
        v17 = FveDeleteRecoveryPasswordsFromCloudDomain(
                v51,
                (struct _FVE_AAD_DELETE_REQUEST *)((char *)lpMem + 20 * v14),
                v16,
                0,
                &v49,
                v50,
                &v48);
        OSVolume = v17;
        if ( v17 >= 0 )
          break;
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
            (unsigned int)v17);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        v7 = L"FveDeleteRPFromCloudDomain";
        v6 = OSVolume;
        v41 = OSVolume;
        if ( v49 )
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          {
            WPP_SF_(v18[2], 80, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
            v18 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v50[0] )
          {
            if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
              WPP_SF_d(v18[2], 81, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, v48);
            v19 = ULongLongToULong(1000LL * v48, &pulResult);
            OSVolume = v19;
            if ( v19 >= 0 )
            {
              PersistentRequestDelayTimer = FveGetPersistentRequestDelayTimer();
              v35 = PersistentRequestDelayTimer;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  83,
                  WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
                  PersistentRequestDelayTimer);
              if ( v35 < pulResult )
                FveSetPersistentRequestDelayTimer(pulResult);
            }
            else
            {
              if ( (PVOID *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 2) != 0 )
                WPP_SF_d(*(_QWORD *)(v20 + 16), 82, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, (unsigned int)v19);
              v7 = L"ULongMult";
            }
          }
          v5 = v36;
          v2 = v37;
          goto LABEL_42;
        }
LABEL_75:
        v13 = v47;
        v14 = (unsigned int)(v14 + 16);
        v39 = v14;
        if ( (unsigned int)v14 >= v47 )
        {
          v2 = v37;
          v5 = v36;
          v6 = v41;
          goto LABEL_77;
        }
      }
      v30 = v14;
      if ( (unsigned int)v14 >= v16 + (unsigned int)v14 )
        goto LABEL_75;
      v31 = (PVOID *)WPP_GLOBAL_Control;
      v32 = v36;
      while ( 1 )
      {
        if ( *((_BYTE *)lpMem + 20 * v30 + 16) )
        {
          if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 2) != 0 )
            WPP_SF__guid_(v31[2], 84, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
          v43 = *(struct _GUID *)((char *)v46 + 576 * v30 + 540);
          v33 = FveDeletePersistentRequest(v51, 2u, &v43);
          if ( v33 >= 0 )
          {
            ++v32;
          }
          else
          {
            v31 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_73;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              85,
              WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
              (unsigned int)v33);
          }
        }
        else
        {
          if ( v31 == &WPP_GLOBAL_Control || (*((_BYTE *)v31 + 28) & 2) == 0 )
            goto LABEL_73;
          WPP_SF__guid_(v31[2], 86, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
        }
        v31 = (PVOID *)WPP_GLOBAL_Control;
LABEL_73:
        if ( ++v30 >= v16 + (unsigned int)v14 )
        {
          LODWORD(v14) = v39;
          v36 = v32;
          v4 = v42;
          goto LABEL_75;
        }
      }
    }
LABEL_77:
    if ( v5 == v2 )
      FveAADKeyDeleteRequest::FveDeleteDecryptedVolumePersistentRequests(v51, v4);
  }
LABEL_42:
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v44,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( (OSVolume < 0 || v6 < 0 || v38 < 0)
    && (unsigned int)dword_18009A3B8 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18009A3B8, 0x400000000000LL) )
  {
    pulResult = v47;
    v42 = (struct _LIST_ENTRY *)0x1000000;
    *(_QWORD *)&v43.Data1 = v7;
    v41 = v5;
    v39 = v2;
    v38 = v22;
    v37 = v6;
    v36 = OSVolume;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v21,
      (unsigned int)byte_18008E2CB,
      v22,
      v23,
      (__int64)&v36,
      (__int64)&v37,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&pulResult,
      (__int64)&v41,
      (__int64)&v43,
      (__int64)&v42);
  }
  if ( v4 )
  {
    FveClearAsyncRequestList(v4);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v25 = lpMem;
  if ( lpMem )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
    lpMem = 0;
  }
  v27 = v46;
  if ( v46 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v27);
    v46 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
      (unsigned int)OSVolume);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v44);
  return (unsigned int)OSVolume;
}

```

## disassembly

```asm
0x180065400  mov     [rsp-8+arg_10], rbx
0x180065405  push    rbp
0x180065406  push    rsi
0x180065407  push    rdi
0x180065408  push    r12
0x18006540a  push    r13
0x18006540c  push    r14
0x18006540e  push    r15
0x180065410  lea     rbp, [rsp-1F0h]
0x180065418  sub     rsp, 2F0h
0x18006541f  mov     rax, cs:__security_cookie
0x180065426  xor     rax, rsp
0x180065429  mov     [rbp+220h+var_40], rax
0x180065430  mov     esi, edx
0x180065432  mov     [rsp+320h+var_2BC], edx
0x180065436  mov     rdi, rcx
0x180065439  xor     ebx, ebx
0x18006543b  xor     edx, edx; Val
0x18006543d  mov     [rbp+220h+var_260], ebx
0x180065440  lea     rcx, [rbp+220h+var_250]; void *
0x180065444  mov     r8d, 208h; Size
0x18006544a  call    memset_0
0x18006544f  mov     r15d, ebx
0x180065452  mov     [rsp+320h+var_2A8], rbx
0x180065457  mov     [rbp+220h+var_270], rbx
0x18006545b  mov     r14d, ebx
0x18006545e  mov     [rbp+220h+lpMem], rbx
0x180065462  mov     r12d, ebx
0x180065465  mov     [rbp+220h+var_268], ebx
0x180065468  mov     [rsp+320h+var_2C0], ebx
0x18006546c  mov     [rbp+220h+var_264], ebx
0x18006546f  mov     [rsp+320h+pulResult], ebx
0x180065473  mov     [rbp+220h+var_25C], ebx
0x180065476  mov     [rsp+320h+var_2B8], ebx
0x18006547a  mov     [rsp+320h+var_2AC], ebx
0x18006547e  mov     rcx, cs:WPP_GLOBAL_Control
0x180065485  lea     rax, WPP_GLOBAL_Control
0x18006548c  cmp     rcx, rax
0x18006548f  jz      short loc_1800654AA
0x180065491  test    byte ptr [rcx+1Ch], 20h
0x180065495  jz      short loc_1800654AA
0x180065497  mov     rcx, [rcx+10h]
0x18006549b  lea     edx, [rbx+4Ah]
0x18006549e  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800654a5  call    WPP_SF_
0x1800654aa  lea     rcx, [rbp+220h+var_250]
0x1800654ae  lea     r13, aNgscbgetosvolu; "NgscbGetOSVolume"
0x1800654b5  call    NgscbGetOSVolume
0x1800654ba  mov     ebx, eax
0x1800654bc  test    eax, eax
0x1800654be  jz      short loc_1800654F9
0x1800654c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800654c7  lea     rax, WPP_GLOBAL_Control
0x1800654ce  cmp     rcx, rax
0x1800654d1  jz      short loc_1800654F1
0x1800654d3  test    byte ptr [rcx+1Ch], 40h
0x1800654d7  jz      short loc_1800654F1
0x1800654d9  mov     rcx, [rcx+10h]
0x1800654dd  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800654e4  mov     edx, 4Bh ; 'K'
0x1800654e9  mov     r9d, ebx
0x1800654ec  call    WPP_SF_d
0x1800654f1  test    ebx, ebx
0x1800654f3  js      loc_180065747
0x1800654f9  lea     rdx, [rsp+320h+var_2A8]
0x1800654fe  mov     [rbp+220h+var_268], esi
0x180065501  call    ?GetAsyncRequestList@@YAJW4_FVE_REQUEST_TYPE@@PEAPEAU_LIST_ENTRY@@@Z; GetAsyncRequestList(_FVE_REQUEST_TYPE,_LIST_ENTRY * *)
0x180065506  mov     ebx, eax
0x180065508  test    eax, eax
0x18006550a  jns     short loc_180065548
0x18006550c  mov     rcx, cs:WPP_GLOBAL_Control
0x180065513  lea     rax, WPP_GLOBAL_Control
0x18006551a  cmp     rcx, rax
0x18006551d  jz      short loc_18006553D
0x18006551f  test    byte ptr [rcx+1Ch], 2
0x180065523  jz      short loc_18006553D
0x180065525  mov     rcx, [rcx+10h]
0x180065529  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x180065530  mov     edx, 4Ch ; 'L'
0x180065535  mov     r9d, ebx
0x180065538  call    WPP_SF_d
0x18006553d  lea     r13, aGetasyncreques; "GetAsyncRequestList"
0x180065544  mov     [rsp+320h+var_2B8], ebx
0x180065548  mov     r15, [rsp+320h+var_2A8]
0x18006554d  lea     rax, [rbp+220h+var_268]
0x180065551  mov     [rsp+320h+var_2F8], rax; unsigned int *
0x180065556  lea     r9, [rbp+220h+var_270]; struct _FVE_AAD_DELETE_INFO_V2 **
0x18006555a  lea     rax, [rbp+220h+lpMem]
0x18006555e  mov     r8, r15; struct _LIST_ENTRY *
0x180065561  mov     edx, esi; unsigned int
0x180065563  mov     [rsp+320h+var_300], rax; struct _FVE_AAD_DELETE_REQUEST **
0x180065568  mov     rcx, rdi; void **
0x18006556b  call    ?GetAADDeletionRequests@FveAADKeyDeleteRequest@@SAJPEAPEAXKPEAU_LIST_ENTRY@@PEAPEAU_FVE_AAD_DELETE_INFO_V2@@PEAPEAU_FVE_AAD_DELETE_REQUEST@@PEAK@Z; FveAADKeyDeleteRequest::GetAADDeletionRequests(void * *,ulong,_LIST_ENTRY *,_FVE_AAD_DELETE_INFO_V2 * *,_FVE_AAD_DELETE_REQUEST * *,ulong *)
0x180065570  mov     ebx, eax
0x180065572  test    eax, eax
0x180065574  jns     short loc_1800655E5
0x180065576  mov     rcx, cs:WPP_GLOBAL_Control
0x18006557d  lea     rdi, WPP_GLOBAL_Control
0x180065584  cmp     rcx, rdi
0x180065587  jz      short loc_1800655AE
0x180065589  test    byte ptr [rcx+1Ch], 2
0x18006558d  jz      short loc_1800655AE
0x18006558f  mov     rcx, [rcx+10h]
0x180065593  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x18006559a  mov     edx, 4Dh ; 'M'
0x18006559f  mov     r9d, eax
0x1800655a2  call    WPP_SF_d
0x1800655a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800655ae  lea     r13, aGetaaddeletion; "GetAADDeletionRequests"
0x1800655b5  cmp     rcx, rdi
0x1800655b8  jz      loc_180065747
0x1800655be  test    byte ptr [rcx+1Ch], 40h
0x1800655c2  jz      loc_180065747
0x1800655c8  mov     rcx, [rcx+10h]
0x1800655cc  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800655d3  mov     edx, 4Eh ; 'N'
0x1800655d8  mov     r9d, ebx
0x1800655db  call    WPP_SF_d
0x1800655e0  jmp     loc_180065747
0x1800655e5  mov     eax, [rbp+220h+var_268]
0x1800655e8  xor     edi, edi
0x1800655ea  mov     [rsp+320h+var_2B4], edi
0x1800655ee  test    eax, eax
0x1800655f0  jz      loc_180065A46
0x1800655f6  sub     eax, edi
0x1800655f8  lea     rcx, [rdi+rdi*4]
0x1800655fc  mov     esi, 10h
0x180065601  cmp     eax, esi
0x180065603  cmovb   esi, eax
0x180065606  mov     rax, [rbp+220h+lpMem]
0x18006560a  xor     r9d, r9d
0x18006560d  mov     r8d, esi
0x180065610  lea     rdx, [rax+rcx*4]
0x180065614  lea     rax, [rbp+220h+var_264]
0x180065618  mov     [rsp+320h+var_2F0], rax
0x18006561d  lea     rcx, [rbp+220h+var_250]
0x180065621  lea     rax, [rbp+220h+var_25C]
0x180065625  mov     [rsp+320h+var_2F8], rax
0x18006562a  lea     rax, [rbp+220h+var_260]
0x18006562e  mov     [rsp+320h+var_300], rax
0x180065633  call    cs:__imp_?FveDeleteRecoveryPasswordsFromCloudDomain@@YAJPEBGPEAU_FVE_AAD_DELETE_REQUEST@@KHPEAH2PEAK@Z; FveDeleteRecoveryPasswordsFromCloudDomain(ushort const *,_FVE_AAD_DELETE_REQUEST *,ulong,int,int *,int *,ulong *)
0x18006563a  nop     dword ptr [rax+rax+00h]
0x18006563f  mov     ebx, eax
0x180065641  test    eax, eax
0x180065643  jns     loc_180065925
0x180065649  mov     r10, cs:WPP_GLOBAL_Control
0x180065650  lea     rsi, WPP_GLOBAL_Control
0x180065657  cmp     r10, rsi
0x18006565a  jz      short loc_180065682
0x18006565c  test    byte ptr [r10+1Ch], 2
0x180065661  jz      short loc_180065682
0x180065663  mov     rcx, [r10+10h]
0x180065667  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x18006566e  mov     edx, 4Fh ; 'O'
0x180065673  mov     r9d, eax
0x180065676  call    WPP_SF_d
0x18006567b  mov     r10, cs:WPP_GLOBAL_Control
0x180065682  cmp     [rbp+220h+var_260], 0
0x180065686  lea     r13, aFvedeleterpfro; "FveDeleteRPFromCloudDomain"
0x18006568d  mov     r12d, ebx
0x180065690  mov     [rsp+320h+var_2AC], ebx
0x180065694  jz      loc_180065A26
0x18006569a  mov     r14b, 8
0x18006569d  cmp     r10, rsi
0x1800656a0  jz      short loc_1800656C4
0x1800656a2  test    [r10+1Ch], r14b
0x1800656a6  jz      short loc_1800656C4
0x1800656a8  mov     rcx, [r10+10h]
0x1800656ac  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800656b3  mov     edx, 50h ; 'P'
0x1800656b8  call    WPP_SF_
0x1800656bd  mov     r10, cs:WPP_GLOBAL_Control
0x1800656c4  cmp     [rbp+220h+var_25C], 0
0x1800656c8  jz      short loc_18006573E
0x1800656ca  cmp     r10, rsi
0x1800656cd  jz      short loc_1800656F5
0x1800656cf  test    [r10+1Ch], r14b
0x1800656d3  jz      short loc_1800656F5
0x1800656d5  mov     r9d, [rbp+220h+var_264]
0x1800656d9  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800656e0  mov     rcx, [r10+10h]
0x1800656e4  mov     edx, 51h ; 'Q'
0x1800656e9  call    WPP_SF_d
0x1800656ee  mov     r10, cs:WPP_GLOBAL_Control
0x1800656f5  mov     eax, [rbp+220h+var_264]
0x1800656f8  lea     rdx, [rsp+320h+pulResult]; pulResult
0x1800656fd  imul    rcx, rax, 3E8h; ullOperand
0x180065704  call    ULongLongToULong
0x180065709  mov     ebx, eax
0x18006570b  test    eax, eax
0x18006570d  jns     loc_180065A60
0x180065713  cmp     r10, rsi
0x180065716  jz      short loc_180065737
0x180065718  test    byte ptr [r10+1Ch], 2
0x18006571d  jz      short loc_180065737
0x18006571f  mov     rcx, [r10+10h]
0x180065723  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x18006572a  mov     edx, 52h ; 'R'
0x18006572f  mov     r9d, eax
0x180065732  call    WPP_SF_d
0x180065737  lea     r13, aUlongmult; "ULongMult"
0x18006573e  mov     r14d, [rsp+320h+var_2C0]
0x180065743  mov     esi, [rsp+320h+var_2BC]
0x180065747  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x18006574e  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x180065755  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x18006575c  lea     rcx, [rbp+220h+var_290]; this
0x180065760  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x180065765  mov     r8d, [rsp+320h+var_2B8]
0x18006576a  test    ebx, ebx
0x18006576c  js      short loc_18006577C
0x18006576e  test    r12d, r12d
0x180065771  js      short loc_18006577C
0x180065773  test    r8d, r8d
0x180065776  jns     loc_18006582F
0x18006577c  mov     eax, cs:dword_18009A3B8
0x180065782  cmp     eax, 5
0x180065785  jbe     loc_18006582F
0x18006578b  mov     rdx, 400000000000h
0x180065795  lea     rcx, dword_18009A3B8
0x18006579c  call    _tlgKeywordOn
0x1800657a1  test    al, al
0x1800657a3  jz      loc_18006582F
0x1800657a9  mov     eax, [rbp+220h+var_268]
0x1800657ac  lea     rdx, byte_18008E2CB
0x1800657b3  mov     [rsp+320h+pulResult], eax
0x1800657b7  lea     rax, [rsp+320h+var_2A8]
0x1800657bc  mov     [rsp+320h+var_2C8], rax
0x1800657c1  lea     rax, [rbp+220h+var_2A0]
0x1800657c5  mov     [rsp+320h+var_2D0], rax
0x1800657ca  lea     rax, [rsp+320h+var_2AC]
0x1800657cf  mov     [rsp+320h+var_2D8], rax
0x1800657d4  lea     rax, [rsp+320h+pulResult]
0x1800657d9  mov     [rsp+320h+var_2E0], rax
0x1800657de  lea     rax, [rsp+320h+var_2B4]
0x1800657e3  mov     [rsp+320h+var_2E8], rax
0x1800657e8  lea     rax, [rsp+320h+var_2B8]
0x1800657ed  mov     [rsp+320h+var_2F0], rax
0x1800657f2  lea     rax, [rsp+320h+var_2BC]
0x1800657f7  mov     [rsp+320h+var_2F8], rax
0x1800657fc  lea     rax, [rsp+320h+var_2C0]
0x180065801  mov     [rsp+320h+var_300], rax
0x180065806  mov     [rsp+320h+var_2A8], 1000000h
0x18006580f  mov     qword ptr [rbp+220h+var_2A0], r13
0x180065813  mov     [rsp+320h+var_2AC], r14d
0x180065818  mov     [rsp+320h+var_2B4], esi
0x18006581c  mov     [rsp+320h+var_2B8], r8d
0x180065821  mov     [rsp+320h+var_2BC], r12d
0x180065826  mov     [rsp+320h+var_2C0], ebx
0x18006582a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18006582f  test    r15, r15
0x180065832  jz      short loc_18006585C
0x180065834  mov     rcx, r15; struct _LIST_ENTRY *
0x180065837  call    ?FveClearAsyncRequestList@@YAXPEAU_LIST_ENTRY@@@Z; FveClearAsyncRequestList(_LIST_ENTRY *)
0x18006583c  call    cs:__imp_GetProcessHeap
0x180065843  nop     dword ptr [rax+rax+00h]
0x180065848  mov     r8, r15; lpMem
0x18006584b  xor     edx, edx; dwFlags
0x18006584d  mov     rcx, rax; hHeap
0x180065850  call    cs:__imp_HeapFree
0x180065857  nop     dword ptr [rax+rax+00h]
0x18006585c  mov     rdi, [rbp+220h+lpMem]
0x180065860  test    rdi, rdi
0x180065863  jz      short loc_18006588D
0x180065865  call    cs:__imp_GetProcessHeap
0x18006586c  nop     dword ptr [rax+rax+00h]
0x180065871  mov     r8, rdi; lpMem
0x180065874  xor     edx, edx; dwFlags
0x180065876  mov     rcx, rax; hHeap
0x180065879  call    cs:__imp_HeapFree
0x180065880  nop     dword ptr [rax+rax+00h]
0x180065885  mov     [rbp+220h+lpMem], 0
0x18006588d  mov     rdi, [rbp+220h+var_270]
0x180065891  test    rdi, rdi
0x180065894  jz      short loc_1800658BE
0x180065896  call    cs:__imp_GetProcessHeap
0x18006589d  nop     dword ptr [rax+rax+00h]
0x1800658a2  mov     r8, rdi; lpMem
0x1800658a5  xor     edx, edx; dwFlags
0x1800658a7  mov     rcx, rax; hHeap
0x1800658aa  call    cs:__imp_HeapFree
0x1800658b1  nop     dword ptr [rax+rax+00h]
0x1800658b6  mov     [rbp+220h+var_270], 0
0x1800658be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800658c5  lea     rax, WPP_GLOBAL_Control
0x1800658cc  cmp     rcx, rax
0x1800658cf  jz      short loc_1800658EF
0x1800658d1  test    byte ptr [rcx+1Ch], 20h
0x1800658d5  jz      short loc_1800658EF
0x1800658d7  mov     rcx, [rcx+10h]
0x1800658db  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800658e2  mov     edx, 57h ; 'W'
0x1800658e7  mov     r9d, ebx
0x1800658ea  call    WPP_SF_d
0x1800658ef  lea     rcx, [rbp+220h+var_290]; this
0x1800658f3  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x1800658f8  mov     eax, ebx
0x1800658fa  mov     rcx, [rbp+220h+var_40]
0x180065901  xor     rcx, rsp; StackCookie
0x180065904  call    __security_check_cookie
  ... truncated ...
```
