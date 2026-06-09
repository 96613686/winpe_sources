# FveEnableEAS::BackupRecoveryPasswordWithRetry(void *,eFveVolumeType,_GUID const *,_GUID const *,_FVE_AUTH_ELEMENT const *)

- ea: `0x1800771a8`
- end: `0x180077791`
- name: `?BackupRecoveryPasswordWithRetry@FveEnableEAS@@IEAAJPEAXW4eFveVolumeType@@PEBU_GUID@@2PEBU_FVE_AUTH_ELEMENT@@@Z`
- size: `1513`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, const char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180075754`

## callees

- `0x180001fe8`
- `0x1800036b4`
- `0x180009f30`
- `0x180009f60`
- `0x18001cde8`
- `0x180023c1c`
- `0x18002b6ac`
- `0x180047104`
- `0x18007200c`
- `0x1800755dc`
- `0x1800771a8`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800773c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800773c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077662`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007776e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007776e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180077436`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180077436`
- `FVESKYBACKUP!FveBackupRecoveryPasswordToSkyDrive` at `0x1800774ce`
- `FVESKYBACKUP!FveBackupRecoveryPasswordToSkyDrive` at `0x1800774ce`

## string_xrefs

- `0x180077628`: `InitializeCom.Initialize`
- `0x18007728f`: `FVE_E_MSA_BACKUP_CACHE_NOT_ALLOCATED`
- `0x18007757e`: `FveEasNetworkStatusCreate`

## pseudocode

```c
__int64 __fastcall FveEnableEAS::BackupRecoveryPasswordWithRetry(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        const char *a5)
{
  FveEasNetworkStatus *v7; // rdi
  int v8; // r14d
  PVOID *v9; // rcx
  BOOL v10; // r15d
  HRESULT CurrentStatus; // ebx
  int v12; // r15d
  int v13; // eax
  PVOID *v14; // rdx
  const char *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const char *v21; // [rsp+28h] [rbp-61h]
  int v22; // [rsp+60h] [rbp-29h] BYREF
  DWORD dwindex; // [rsp+64h] [rbp-25h] BYREF
  struct FveEasNetworkStatus *v24; // [rsp+68h] [rbp-21h] BYREF
  HANDLE pHandles; // [rsp+70h] [rbp-19h] BYREF
  __int64 v26; // [rsp+78h] [rbp-11h] BYREF
  __int64 v27; // [rsp+80h] [rbp-9h] BYREF
  const char *v28; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]
  char v30; // [rsp+E0h] [rbp+57h] BYREF
  __int64 v31; // [rsp+E8h] [rbp+5Fh]
  char v32; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v33; // [rsp+F8h] [rbp+6Fh]

  v33 = a4;
  v31 = a2;
  v32 = 0;
  v30 = 0;
  pHandles = 0;
  v7 = 0;
  v24 = 0;
  dwindex = 0;
  v8 = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = a3 == 0;
  v22 = v10;
  if ( *(_QWORD *)(a1 + 32) )
  {
    CurrentStatus = 0;
    v12 = 0;
    while ( 1 )
    {
      if ( v12 )
      {
        CurrentStatus = CInitializeCom::Initialize((CInitializeCom *)&v30);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)CurrentStatus);
        if ( CurrentStatus < 0 )
        {
          v15 = "InitializeCom.Initialize";
          v16 = 493;
          goto LABEL_57;
        }
        if ( !v7 )
        {
          CurrentStatus = FveEasNetworkStatus::Create(&v24);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
              (unsigned int)CurrentStatus);
          if ( CurrentStatus < 0 )
          {
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x1F4,
              (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
              (const char *)(unsigned int)CurrentStatus,
              (int)"FveEasNetworkStatusCreate",
              v21);
            v7 = v24;
            goto LABEL_58;
          }
          v7 = v24;
        }
        CurrentStatus = FveEasNetworkStatusImpl::GetCurrentStatus(*(_QWORD *)v7 + 8LL, &v32);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)CurrentStatus);
        if ( CurrentStatus < 0 )
        {
          v15 = "GetCurrentStatus";
          v16 = 503;
          goto LABEL_57;
        }
        if ( !v32 )
        {
          if ( !pHandles )
          {
            pHandles = CreateEventW(0, 0, 0, 0);
            v26 = (__int64)pHandles;
            CurrentStatus = FveEasNetworkStatus::RegisterForStatusChange__lambda_cbacfa1d190aca0c9e6974e5309c7bfa___(
                              v7,
                              &v26);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                60,
                &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
                (unsigned int)CurrentStatus);
            if ( CurrentStatus < 0 )
            {
              v15 = "RegisterForStatusChange";
              v16 = 527;
LABEL_57:
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)v16,
                (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
                (const char *)(unsigned int)CurrentStatus,
                (int)v15,
                v21);
              goto LABEL_58;
            }
          }
          CurrentStatus = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
              (unsigned int)CurrentStatus);
          if ( CurrentStatus < 0 )
          {
            v15 = "RegisterForStatusChange";
            v16 = 540;
            goto LABEL_57;
          }
          if ( dwindex )
            break;
        }
      }
      v21 = a5;
      v8 = FveBackupRecoveryPasswordToSkyDrive(v31, 0, 0, a3, v33);
      v13 = (***(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64, const char *, int))(a1 + 32))(
              *(_QWORD *)(a1 + 32),
              a3,
              v33,
              a5,
              v8);
      if ( v13 < 0 )
      {
        v14 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)v13);
      }
      if ( v8 < 0
        && !*(_BYTE *)(a1 + 64)
        && (unsigned int)(v8 + 2144272190) > 1
        && (v8 & 0x1FFF0000) != 0x860000
        && (unsigned int)++v12 < 3 )
      {
        continue;
      }
      goto LABEL_58;
    }
    CurrentStatus = -2147483622;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x21F,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)0x8000001ALL,
      (int)"CoWaitForMultipleHandles",
      v21);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, 2147483674LL);
LABEL_58:
    if ( v7 )
      FveEasNetworkStatus::`scalar deleting destructor'(v7, (unsigned int)v14);
    v10 = v22;
  }
  else
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
    {
      WPP_SF_(v9[2], 55, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    CurrentStatus = -2144272131;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 )
      WPP_SF_d(v9[2], 56, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, 2150695165LL);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)0x803100FDLL,
      (int)"FVE_E_MSA_BACKUP_CACHE_NOT_ALLOCATED",
      v21);
  }
  if ( pHandles )
  {
    CloseHandle(pHandles);
    pHandles = 0;
  }
  if ( CurrentStatus >= 0 && v8 < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x256,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)v8,
      (int)"FveBackupRecoveryPasswordToSkyDrive",
      v21);
    CurrentStatus = v8;
  }
  if ( (unsigned int)dword_18009A548 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A548, 0x400000000000LL) )
  {
    v26 = 0x1000000;
    v32 = *(_BYTE *)(a1 + 64);
    v27 = v33;
    v22 = CurrentStatus;
    LODWORD(v24) = v10;
    v28 = "BackupRecoveryPW";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
      v17,
      (int)byte_18008EA3B,
      v18,
      v19,
      (const unsigned __int16 **)&v28,
      (__int64)&v24,
      (__int64)&v22,
      &v27,
      (__int64)&v32,
      (__int64)&v26);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
      (unsigned int)CurrentStatus);
  if ( v30 )
    CoUninitialize();
  return (unsigned int)CurrentStatus;
}

```

## disassembly

```asm
0x1800771a8  mov     [rsp-8+arg_18], r9
0x1800771ad  mov     [rsp-8+arg_8], rdx
0x1800771b2  push    rbp
0x1800771b3  push    rbx
0x1800771b4  push    rsi
0x1800771b5  push    rdi
0x1800771b6  push    r12
0x1800771b8  push    r13
0x1800771ba  push    r14
0x1800771bc  push    r15
0x1800771be  lea     rbp, [rsp-0Fh]
0x1800771c3  sub     rsp, 98h
0x1800771ca  mov     r12d, r8d
0x1800771cd  mov     r13, rcx
0x1800771d0  mov     [rbp+47h+arg_10], 0
0x1800771d4  mov     [rbp+47h+arg_0], 0
0x1800771d8  mov     [rbp+47h+pHandles], 0
0x1800771e0  xor     edi, edi
0x1800771e2  mov     [rbp+47h+var_68], rdi
0x1800771e6  mov     [rbp+47h+dwindex], edi
0x1800771e9  xor     r14d, r14d
0x1800771ec  lea     rax, WPP_GLOBAL_Control
0x1800771f3  lea     rsi, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x1800771fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180077201  cmp     rcx, rax
0x180077204  jz      short loc_180077229
0x180077206  test    byte ptr [rcx+1Ch], 20h
0x18007720a  jz      short loc_180077229
0x18007720c  lea     edx, [rdi+36h]
0x18007720f  mov     r8, rsi
0x180077212  mov     rcx, [rcx+10h]
0x180077216  call    WPP_SF_
0x18007721b  mov     rcx, cs:WPP_GLOBAL_Control
0x180077222  lea     rax, WPP_GLOBAL_Control
0x180077229  xor     r15d, r15d
0x18007722c  test    r12d, r12d
0x18007722f  setz    r15b
0x180077233  mov     [rbp+47h+var_70], r15d
0x180077237  cmp     [r13+20h], rdi
0x18007723b  jnz     short loc_1800772B7
0x18007723d  cmp     rcx, rax
0x180077240  jz      short loc_180077267
0x180077242  test    byte ptr [rcx+1Ch], 2
0x180077246  jz      short loc_180077267
0x180077248  mov     edx, 37h ; '7'
0x18007724d  mov     r8, rsi
0x180077250  mov     rcx, [rcx+10h]
0x180077254  call    WPP_SF_
0x180077259  mov     rcx, cs:WPP_GLOBAL_Control
0x180077260  lea     rax, WPP_GLOBAL_Control
0x180077267  mov     ebx, 803100FDh
0x18007726c  cmp     rcx, rax
0x18007726f  jz      short loc_18007728B
0x180077271  test    byte ptr [rcx+1Ch], 40h
0x180077275  jz      short loc_18007728B
0x180077277  mov     edx, 38h ; '8'
0x18007727c  mov     r9d, ebx
0x18007727f  mov     r8, rsi
0x180077282  mov     rcx, [rcx+10h]
0x180077286  call    WPP_SF_d
0x18007728b  mov     rcx, [rbp+4Fh]; this
0x18007728f  lea     rax, aFveEMsaBackupC; "FVE_E_MSA_BACKUP_CACHE_NOT_ALLOCATED"
0x180077296  mov     [rsp+0D0h+lpdwindex], rax; int
0x18007729b  mov     r9d, ebx; char *
0x18007729e  lea     rsi, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x1800772a5  mov     r8, rsi; unsigned int
0x1800772a8  mov     edx, 1DDh; void *
0x1800772ad  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800772b2  jmp     loc_180077659
0x1800772b7  xor     ebx, ebx
0x1800772b9  xor     r15d, r15d
0x1800772bc  lea     rsi, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x1800772c3  test    r15d, r15d
0x1800772c6  jz      loc_180077487
0x1800772cc  lea     rcx, [rbp+47h+arg_0]; this
0x1800772d0  call    ?Initialize@CInitializeCom@@QEAAJXZ; CInitializeCom::Initialize(void)
0x1800772d5  mov     ebx, eax
0x1800772d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800772de  lea     rax, WPP_GLOBAL_Control
0x1800772e5  cmp     rcx, rax
0x1800772e8  jz      short loc_180077308
0x1800772ea  test    byte ptr [rcx+1Ch], 40h
0x1800772ee  jz      short loc_180077308
0x1800772f0  mov     edx, 39h ; '9'
0x1800772f5  mov     r9d, ebx
0x1800772f8  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x1800772ff  mov     rcx, [rcx+10h]
0x180077303  call    WPP_SF_d
0x180077308  test    ebx, ebx
0x18007730a  js      loc_180077628
0x180077310  test    rdi, rdi
0x180077313  jnz     short loc_18007735B
0x180077315  lea     rcx, [rbp+47h+var_68]; struct FveEasNetworkStatus **
0x180077319  call    ?Create@FveEasNetworkStatus@@SAJPEAPEAV1@@Z; FveEasNetworkStatus::Create(FveEasNetworkStatus * *)
0x18007731e  mov     ebx, eax
0x180077320  mov     rcx, cs:WPP_GLOBAL_Control
0x180077327  lea     rax, WPP_GLOBAL_Control
0x18007732e  cmp     rcx, rax
0x180077331  jz      short loc_18007734F
0x180077333  test    byte ptr [rcx+1Ch], 40h
0x180077337  jz      short loc_18007734F
0x180077339  lea     edx, [rdi+3Ah]
0x18007733c  mov     r9d, ebx
0x18007733f  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180077346  mov     rcx, [rcx+10h]
0x18007734a  call    WPP_SF_d
0x18007734f  test    ebx, ebx
0x180077351  js      loc_18007757A
0x180077357  mov     rdi, [rbp+47h+var_68]
0x18007735b  mov     rcx, [rdi]
0x18007735e  add     rcx, 8
0x180077362  lea     rdx, [rbp+47h+arg_10]
0x180077366  call    ?GetCurrentStatus@FveEasNetworkStatusImpl@@SAJAEBV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@AEAUFveEasNetworkStatusArgs@@@Z; FveEasNetworkStatusImpl::GetCurrentStatus(Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> const &,FveEasNetworkStatusArgs &)
0x18007736b  mov     ebx, eax
0x18007736d  mov     rcx, cs:WPP_GLOBAL_Control
0x180077374  lea     rax, WPP_GLOBAL_Control
0x18007737b  cmp     rcx, rax
0x18007737e  jz      short loc_18007739E
0x180077380  test    byte ptr [rcx+1Ch], 40h
0x180077384  jz      short loc_18007739E
0x180077386  mov     edx, 3Bh ; ';'
0x18007738b  mov     r9d, ebx
0x18007738e  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180077395  mov     rcx, [rcx+10h]
0x180077399  call    WPP_SF_d
0x18007739e  test    ebx, ebx
0x1800773a0  js      loc_18007761A
0x1800773a6  cmp     [rbp+47h+arg_10], 0
0x1800773aa  jnz     loc_180077487
0x1800773b0  cmp     [rbp+47h+pHandles], 0
0x1800773b5  jnz     short loc_18007741C
0x1800773b7  xor     r9d, r9d; lpName
0x1800773ba  xor     r8d, r8d; bInitialState
0x1800773bd  xor     edx, edx; bManualReset
0x1800773bf  xor     ecx, ecx; lpEventAttributes
0x1800773c1  call    cs:__imp_CreateEventW
0x1800773c8  nop     dword ptr [rax+rax+00h]
0x1800773cd  mov     [rbp+47h+pHandles], rax
0x1800773d1  mov     [rbp+47h+var_58], rax
0x1800773d5  lea     rdx, [rbp+47h+var_58]
0x1800773d9  mov     rcx, rdi
0x1800773dc  call    FveEasNetworkStatus__RegisterForStatusChange__lambda_cbacfa1d190aca0c9e6974e5309c7bfa___
0x1800773e1  mov     ebx, eax
0x1800773e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800773ea  lea     rax, WPP_GLOBAL_Control
0x1800773f1  cmp     rcx, rax
0x1800773f4  jz      short loc_180077414
0x1800773f6  test    byte ptr [rcx+1Ch], 40h
0x1800773fa  jz      short loc_180077414
0x1800773fc  mov     edx, 3Ch ; '<'
0x180077401  mov     r9d, ebx
0x180077404  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x18007740b  mov     rcx, [rcx+10h]
0x18007740f  call    WPP_SF_d
0x180077414  test    ebx, ebx
0x180077416  js      loc_1800775A3
0x18007741c  lea     rax, [rbp+47h+dwindex]
0x180077420  mov     [rsp+0D0h+lpdwindex], rax; lpdwindex
0x180077425  lea     r9, [rbp+47h+pHandles]; pHandles
0x180077429  mov     r8d, 1; cHandles
0x18007742f  or      edx, 0FFFFFFFFh; dwTimeout
0x180077432  lea     ecx, [r8+17h]; dwFlags
0x180077436  call    cs:__imp_CoWaitForMultipleHandles
0x18007743d  nop     dword ptr [rax+rax+00h]
0x180077442  mov     ebx, eax
0x180077444  mov     rcx, cs:WPP_GLOBAL_Control
0x18007744b  lea     rax, WPP_GLOBAL_Control
0x180077452  cmp     rcx, rax
0x180077455  jz      short loc_180077475
0x180077457  test    byte ptr [rcx+1Ch], 40h
0x18007745b  jz      short loc_180077475
0x18007745d  mov     edx, 3Dh ; '='
0x180077462  mov     r9d, ebx
0x180077465  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x18007746c  mov     rcx, [rcx+10h]
0x180077470  call    WPP_SF_d
0x180077475  test    ebx, ebx
0x180077477  js      loc_18007760C
0x18007747d  cmp     [rbp+47h+dwindex], 0
0x180077481  jnz     loc_1800775B4
0x180077487  mov     [rsp+0D0h+var_80], 0
0x18007748f  mov     dword ptr [rsp+0D0h+var_88], 1
0x180077497  mov     dword ptr [rsp+0D0h+var_90], 1
0x18007749f  mov     dword ptr [rsp+0D0h+var_98], 0
0x1800774a7  mov     rax, [rbp+47h+arg_28]
0x1800774ab  mov     [rsp+0D0h+var_A0], rax
0x1800774b0  mov     rax, [rbp+47h+arg_20]
0x1800774b4  mov     [rsp+0D0h+var_A8], rax
0x1800774b9  mov     rax, [rbp+47h+arg_18]
0x1800774bd  mov     [rsp+0D0h+lpdwindex], rax
0x1800774c2  mov     r9d, r12d
0x1800774c5  xor     r8d, r8d
0x1800774c8  xor     edx, edx
0x1800774ca  mov     rcx, [rbp+47h+arg_8]
0x1800774ce  call    cs:__imp_?FveBackupRecoveryPasswordToSkyDrive@@YAJPEAXHHW4eFveVolumeType@@PEBU_GUID@@2PEBU_FVE_AUTH_ELEMENT@@HHHH@Z; FveBackupRecoveryPasswordToSkyDrive(void *,int,int,eFveVolumeType,_GUID const *,_GUID const *,_FVE_AUTH_ELEMENT const *,int,int,int,int)
0x1800774d5  nop     dword ptr [rax+rax+00h]
0x1800774da  mov     r14d, eax
0x1800774dd  mov     rcx, [r13+20h]
0x1800774e1  mov     rdx, [rcx]
0x1800774e4  mov     rax, [rdx]
0x1800774e7  mov     dword ptr [rsp+0D0h+lpdwindex], r14d
0x1800774ec  mov     r9, [rbp+47h+arg_20]
0x1800774f0  mov     r8, [rbp+47h+arg_18]
0x1800774f4  mov     edx, r12d
0x1800774f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774fc  test    eax, eax
0x1800774fe  jns     short loc_180077531
0x180077500  mov     rcx, cs:WPP_GLOBAL_Control
0x180077507  lea     rdx, WPP_GLOBAL_Control
0x18007750e  cmp     rcx, rdx
0x180077511  jz      short loc_180077531
0x180077513  test    byte ptr [rcx+1Ch], 2
0x180077517  jz      short loc_180077531
0x180077519  mov     edx, 3Fh ; '?'
0x18007751e  mov     r9d, eax
0x180077521  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180077528  mov     rcx, [rcx+10h]
0x18007752c  call    WPP_SF_d
0x180077531  test    r14d, r14d
0x180077534  jns     loc_180077648
0x18007753a  cmp     byte ptr [r13+40h], 0
0x18007753f  jnz     loc_180077648
0x180077545  lea     eax, [r14+7FCEFF3Eh]
0x18007754c  cmp     eax, 1
0x18007754f  jbe     loc_180077648
0x180077555  mov     eax, r14d
0x180077558  and     eax, 1FFF0000h
0x18007755d  cmp     eax, 860000h
0x180077562  jz      loc_180077648
0x180077568  inc     r15d
0x18007756b  cmp     r15d, 3
0x18007756f  jb      loc_1800772BC
0x180077575  jmp     loc_180077648
0x18007757a  mov     rcx, [rbp+4Fh]; this
0x18007757e  lea     rax, aFveeasnetworks; "FveEasNetworkStatusCreate"
0x180077585  mov     [rsp+0D0h+lpdwindex], rax; int
0x18007758a  mov     r9d, ebx; char *
0x18007758d  mov     r8, rsi; unsigned int
0x180077590  mov     edx, 1F4h; void *
0x180077595  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007759a  mov     rdi, [rbp+47h+var_68]
0x18007759e  jmp     loc_180077648
0x1800775a3  lea     rax, aRegisterforsta; "RegisterForStatusChange"
0x1800775aa  mov     edx, 20Fh
0x1800775af  jmp     loc_180077634
0x1800775b4  mov     ebx, 8000001Ah
0x1800775b9  mov     rcx, [rbp+4Fh]; this
0x1800775bd  lea     rax, aCowaitformulti; "CoWaitForMultipleHandles"
0x1800775c4  mov     [rsp+0D0h+lpdwindex], rax; int
0x1800775c9  mov     r9d, ebx; char *
0x1800775cc  mov     r8, rsi; unsigned int
0x1800775cf  mov     edx, 21Fh; void *
0x1800775d4  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800775d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800775e0  lea     rax, WPP_GLOBAL_Control
0x1800775e7  cmp     rcx, rax
0x1800775ea  jz      short loc_180077648
0x1800775ec  test    byte ptr [rcx+1Ch], 40h
0x1800775f0  jz      short loc_180077648
0x1800775f2  mov     edx, 3Eh ; '>'
0x1800775f7  mov     r9d, ebx
0x1800775fa  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180077601  mov     rcx, [rcx+10h]
0x180077605  call    WPP_SF_d
0x18007760a  jmp     short loc_180077648
0x18007760c  lea     rax, aRegisterforsta; "RegisterForStatusChange"
0x180077613  mov     edx, 21Ch
0x180077618  jmp     short loc_180077634
0x18007761a  lea     rax, aGetcurrentstat; "GetCurrentStatus"
0x180077621  mov     edx, 1F7h
0x180077626  jmp     short loc_180077634
0x180077628  lea     rax, aInitializecomI; "InitializeCom.Initialize"
0x18007762f  mov     edx, 1EDh; void *
0x180077634  mov     [rsp+0D0h+lpdwindex], rax; int
0x180077639  mov     r9d, ebx; char *
0x18007763c  mov     r8, rsi; unsigned int
0x18007763f  mov     rcx, [rbp+4Fh]; this
0x180077643  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180077648  test    rdi, rdi
0x18007764b  jz      short loc_180077655
0x18007764d  mov     rcx, rdi; this
0x180077650  call    ??_GFveEasNetworkStatus@@QEAAPEAXI@Z; FveEasNetworkStatus::`scalar deleting destructor'(uint)
0x180077655  mov     r15d, [rbp+47h+var_70]
0x180077659  mov     rcx, [rbp+47h+pHandles]; hObject
0x18007765d  test    rcx, rcx
0x180077660  jz      short loc_180077676
0x180077662  call    cs:__imp_CloseHandle
0x180077669  nop     dword ptr [rax+rax+00h]
0x18007766e  mov     [rbp+47h+pHandles], 0
0x180077676  test    ebx, ebx
0x180077678  js      short loc_1800776A2
0x18007767a  test    r14d, r14d
0x18007767d  jns     short loc_1800776A2
0x18007767f  mov     rcx, [rbp+4Fh]; this
0x180077683  lea     rax, aFvebackuprecov_1; "FveBackupRecoveryPasswordToSkyDrive"
0x18007768a  mov     [rsp+0D0h+lpdwindex], rax; int
0x18007768f  mov     r9d, r14d; char *
0x180077692  mov     r8, rsi; unsigned int
0x180077695  mov     edx, 256h; void *
0x18007769a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
  ... truncated ...
```
