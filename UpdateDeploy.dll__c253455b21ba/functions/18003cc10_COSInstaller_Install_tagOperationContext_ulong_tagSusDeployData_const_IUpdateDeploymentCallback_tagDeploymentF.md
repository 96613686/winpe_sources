# COSInstaller::Install(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)

- ea: `0x18003cc10`
- end: `0x18003d2b2`
- name: `?Install@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z`
- size: `1698`
- prototype: `__int64 __fastcall(COSInstaller *, __int64, unsigned int, struct tagSusDeployData *, struct IUpdateDeploymentCallback *, int, _BYTE *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003c970`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180008ea8`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011b44`
- `0x180011bf0`
- `0x18003bd48`
- `0x18003c074`
- `0x18003cc10`
- `0x18003e3e8`
- `0x18003f448`
- `0x18003fd7c`
- `0x180043394`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003cde6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d097`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003cde6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d097`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cdf0`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cdf0`

## string_xrefs

- `0x18003d0bc`: `Install`
- `0x18003ccd2`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003d25a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003cd6b`: `Merge updates complete`
- `0x18003cc80`: `Enter Deployment handler install. Count of updates = %lu`
- `0x18003ce20`: `Skipping installing update ID: %ws as the dependent merged update failed to install`
- `0x18003ce7d`: `Preparing to install update ID: %ws.%d Update was %ws`
- `0x18003cf6f`: `Install complete for update ID: %ws.%d Return code is 0x%08lX. Requires Reboot:%ws`

## pseudocode

```c
__int64 __fastcall COSInstaller::Install(
        COSInstaller *a1,
        __int64 a2,
        unsigned int a3,
        struct tagSusDeployData *a4,
        struct IUpdateDeploymentCallback *a5,
        int a6,
        _BYTE *a7)
{
  COSInstaller *v7; // rdi
  __int64 v8; // r15
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // r14d
  char *v14; // r13
  __int64 v15; // rsi
  UINT v16; // eax
  UINT v17; // r12d
  int v18; // r15d
  __int64 updated; // rax
  int v20; // ebx
  __int64 v21; // rax
  const wchar_t *v22; // rcx
  char *v23; // rbx
  const WCHAR *v24; // rdi
  int v25; // ebx
  __int64 v26; // rax
  int v27; // edi
  void *v28; // rcx
  int v29; // eax
  int v30; // eax
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rcx
  bool *v34; // [rsp+20h] [rbp-E0h]
  bool *v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+38h] [rbp-C8h]
  __int64 v37; // [rsp+38h] [rbp-C8h]
  __int64 v38; // [rsp+40h] [rbp-C0h]
  bool v39; // [rsp+50h] [rbp-B0h]
  _QWORD v42[7]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v43[112]; // [rsp+B0h] [rbp-50h] BYREF
  int v44; // [rsp+120h] [rbp+20h] BYREF
  struct tagSusDeployData *v45; // [rsp+128h] [rbp+28h] BYREF
  char v46; // [rsp+130h] [rbp+30h] BYREF
  bool v47; // [rsp+131h] [rbp+31h] BYREF
  unsigned int v48; // [rsp+138h] [rbp+38h] BYREF
  char *v49; // [rsp+140h] [rbp+40h] BYREF
  void *v50; // [rsp+148h] [rbp+48h] BYREF
  int v51; // [rsp+150h] [rbp+50h] BYREF
  void *v52; // [rsp+158h] [rbp+58h] BYREF
  void *lpMem; // [rsp+160h] [rbp+60h] BYREF
  const char *v54; // [rsp+170h] [rbp+70h] BYREF
  void *v55; // [rsp+178h] [rbp+78h] BYREF
  void *v56; // [rsp+180h] [rbp+80h] BYREF
  __int128 v57; // [rsp+188h] [rbp+88h]
  _OWORD v58[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v59; // [rsp+1B8h] [rbp+B8h]
  _BYTE v60[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int64 v62; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v63; // [rsp+1D8h] [rbp+D8h]
  unsigned int v64; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v7 = a1;
  v48 = a3;
  v45 = a4;
  v8 = (__int64)a5;
  LODWORD(v49) = 0;
  v47 = 0;
  v46 = 0;
  lpMem = 0;
  WUTrace(0, 0, 4096, 4, 0, L"Enter Deployment handler install. Count of updates = %lu");
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 225;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v9,
      (int)v34);
    goto LABEL_71;
  }
  v11 = v48;
  if ( !v48 )
  {
    v9 = -2145124316;
    v10 = 228;
    goto LABEL_5;
  }
  v42[5] = 1;
  v42[0] = &v46;
  v42[1] = v7;
  v42[2] = &v48;
  v42[3] = &v45;
  v42[4] = &v49;
  if ( v48 > 1 )
  {
    LODWORD(v49) = COSInstaller::MergeUpdates(v7, v48, v45, a5, &v47, (wchar_t **)&lpMem);
    LODWORD(v35) = (_DWORD)v49;
    WUTrace(0, 0, 4096, (((int)v49 >> 31) & 0xFFFFFFFE) + 4, v35, L"Merge updates complete");
    v9 = (unsigned int)v49;
    if ( (int)v49 < 0 )
    {
      v12 = 261;
      goto LABEL_68;
    }
    v11 = v48;
  }
  v13 = 0;
  if ( v11 )
  {
    while ( 1 )
    {
      v14 = (char *)v45 + 296 * v13;
      v44 = 0;
      v51 = 0;
      v15 = *((_QWORD *)v14 + 7) + 4LL;
      v52 = 0;
      v50 = 0;
      CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v60);
      v63 = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v16 = SysStringLen(*((BSTR *)v14 + 3));
      v17 = v16;
      v39 = v16 != 0;
      if ( !v46 )
        goto LABEL_14;
      if ( v16 )
      {
        v18 = -2145079035;
        updated = Trace::UpdateIdToString::UpdateIdToString(
                    (Trace::UpdateIdToString *)v43,
                    (const struct tagDSGlobalUpdateId *)v15);
        WUTrace(
          0,
          0,
          4096,
          3,
          0,
          L"Skipping installing update ID: %ws as the dependent merged update failed to install",
          updated);
      }
      else
      {
LABEL_14:
        v20 = *(_DWORD *)(v15 + 16);
        v21 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v43, (const struct _GUID *)v15);
        v22 = L"not merged";
        if ( v17 )
          v22 = L"merged";
        LODWORD(v36) = v20;
        WUTrace(0, 0, 4096, 4, 0, L"Preparing to install update ID: %ws.%d Update was %ws", v21, v36, v22);
        v23 = (char *)((unsigned __int64)lpMem & -(__int64)(v17 != 0));
        if ( v50 )
        {
          SusFree(v50);
          v50 = 0;
        }
        if ( v52 )
        {
          SusFree(v52);
          v52 = 0;
        }
        v18 = COSInstaller::OrchestrateUpdate(
                (__int64)v7,
                (__int64)v14,
                1,
                *(_DWORD *)(a2 + 16),
                v8,
                &v44,
                (__int64)&v51,
                (__int64)&v52,
                (__int64)&v50,
                v23);
        v24 = L"No";
        if ( v44 )
          v24 = L"Yes";
        v25 = *(_DWORD *)(v15 + 16);
        v26 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v43, (const struct _GUID *)v15);
        LODWORD(v38) = v18;
        LODWORD(v37) = v25;
        WUTrace(
          0,
          0,
          4096,
          ((v18 >> 31) & 0xFFFFFFFE) + 4,
          0,
          L"Install complete for update ID: %ws.%d Return code is 0x%08lX. Requires Reboot:%ws",
          v26,
          v37,
          v38,
          v24);
        v7 = a1;
      }
      HIDWORD(v36) = HIDWORD(v52);
      LODWORD(v34) = v18;
      v27 = COSInstaller::NotifyResult(v7, a5, v14);
      v54 = 0;
      v55 = 0;
      v28 = 0;
      v56 = 0;
      v57 = 0;
      memset(v58, 0, sizeof(v58));
      v59 = 0;
      if ( v14 != (char *)-112LL && v14[112] )
      {
        v29 = DuplicateString<char const *,char *>(v14 + 112, &v55);
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFC,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v29,
            v18);
        v28 = v56;
      }
      if ( a7 && *a7 )
      {
        if ( v28 )
        {
          SusFree(v28);
          v56 = 0;
        }
        v30 = DuplicateString<char const *,char *>(a7, &v56);
        if ( v30 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v30,
            (int)v34);
      }
      QueryUnbiasedInterruptTime(&v62);
      v31 = v62 - UnbiasedTime + v63;
      v63 = v31;
      v54 = "Install";
      if ( v60[0] )
        v32 = v31 / v64;
      else
        LODWORD(v32) = 0;
      *(_OWORD *)((char *)v58 + 4) = *(_OWORD *)(*((_QWORD *)v14 + 7) + 4LL);
      BYTE9(v57) = v44 != 0;
      HIDWORD(v57) = v51;
      DWORD1(v57) = v13;
      LOBYTE(v58[0]) = v39;
      *(_QWORD *)((char *)&v58[1] + 4) = __PAIR64__(v18, v27);
      LODWORD(v59) = v32;
      OSDeploymentTelemetry::FirePerUpdateEvent((struct OSDeploymentEventSummary *)&v54);
      if ( v27 < 0 )
      {
        LODWORD(v34) = v27;
        WUTrace(0, 0, 4096, 2, v34, L"Notify failed");
      }
      if ( v18 < 0 )
      {
        LODWORD(v49) = v18;
        if ( v17 )
          v46 = 1;
        if ( !a6 )
          break;
      }
      if ( v56 )
      {
        SusFree(v56);
        v56 = 0;
      }
      if ( v55 )
      {
        SusFree(v55);
        v55 = 0;
      }
      if ( v50 )
      {
        SusFree(v50);
        v50 = 0;
      }
      if ( v52 )
      {
        SusFree(v52);
        v52 = 0;
      }
      if ( ++v13 >= v48 )
        goto LABEL_61;
      v7 = a1;
      v8 = (__int64)a5;
    }
    if ( v56 )
    {
      SusFree(v56);
      v56 = 0;
    }
    if ( v55 )
    {
      SusFree(v55);
      v55 = 0;
    }
    if ( v50 )
    {
      SusFree(v50);
      v50 = 0;
    }
    if ( v52 )
      SusFree(v52);
  }
LABEL_61:
  v9 = (unsigned int)v49;
  if ( (int)v49 >= 0 )
  {
    v9 = 0;
    goto LABEL_70;
  }
  if ( (_DWORD)v49 == -2145116147
    || (_DWORD)v49 == -2147024894
    || (_DWORD)v49 == -1047526943
    || (unsigned int)((_DWORD)v49 + 1047526898) <= 1
    || (_DWORD)v49 == -1047526903 )
  {
    goto LABEL_70;
  }
  v12 = 385;
LABEL_68:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)v9,
    (int)v34);
LABEL_70:
  wil::details::lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___::_lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___(v42);
LABEL_71:
  if ( lpMem )
    SusFree(lpMem);
  return v9;
}

```

## disassembly

```asm
0x18003cc10  push    rbp
0x18003cc12  push    rbx
0x18003cc13  push    rsi
0x18003cc14  push    rdi
0x18003cc15  push    r12
0x18003cc17  push    r13
0x18003cc19  push    r14
0x18003cc1b  push    r15
0x18003cc1d  lea     rbp, [rsp-0F8h]
0x18003cc25  sub     rsp, 1F8h
0x18003cc2c  mov     rax, cs:__security_cookie
0x18003cc33  xor     rax, rsp
0x18003cc36  mov     [rbp+130h+var_48], rax
0x18003cc3d  mov     [rsp+230h+var_1C8], rdx
0x18003cc42  mov     rdi, rcx
0x18003cc45  mov     [rsp+230h+var_1D8], rcx
0x18003cc4a  mov     [rbp+130h+var_F8], r8d
0x18003cc4e  mov     [rbp+130h+var_108], r9
0x18003cc52  mov     r15, [rbp+130h+arg_20]
0x18003cc59  mov     [rsp+230h+var_1D0], r15
0x18003cc5e  mov     rbx, [rbp+130h+arg_30]
0x18003cc65  mov     [rsp+230h+var_1C0], rbx
0x18003cc6a  xor     esi, esi
0x18003cc6c  mov     dword ptr [rbp+130h+var_F0], esi
0x18003cc6f  mov     [rbp+130h+var_FF], sil
0x18003cc73  mov     [rbp+130h+var_100], sil
0x18003cc77  mov     [rbp+130h+lpMem], rsi
0x18003cc7b  mov     dword ptr [rsp+230h+var_200], r8d
0x18003cc80  lea     rax, aEnterDeploymen_1; "Enter Deployment handler install. Count"...
0x18003cc87  mov     [rsp+230h+var_208], rax
0x18003cc8c  mov     [rsp+230h+var_210], rsi; int
0x18003cc91  mov     ebx, 1000h
0x18003cc96  lea     r9d, [rsi+4]
0x18003cc9a  mov     r8d, ebx
0x18003cc9d  xor     edx, edx
0x18003cc9f  xor     ecx, ecx
0x18003cca1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003cca6  test    r15, r15
0x18003cca9  jnz     short loc_18003CCB7
0x18003ccab  mov     ebx, 80004003h
0x18003ccb0  mov     edx, 0E1h
0x18003ccb5  jmp     short loc_18003CCC8
0x18003ccb7  mov     eax, [rbp+130h+var_F8]
0x18003ccba  test    eax, eax
0x18003ccbc  jnz     short loc_18003CCE3
0x18003ccbe  mov     ebx, 80240024h
0x18003ccc3  mov     edx, 0E4h; void *
0x18003ccc8  mov     rcx, [rbp+138h]; this
0x18003cccf  mov     r9d, ebx; char *
0x18003ccd2  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003ccd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ccde  jmp     loc_18003D27F
0x18003cce3  xorps   xmm0, xmm0
0x18003cce6  movups  [rsp+230h+var_1B8], xmm0
0x18003cceb  movups  [rbp+130h+var_1A8], xmm0
0x18003ccef  movups  [rbp+130h+var_198], xmm0
0x18003ccf3  lea     rcx, [rbp+130h+var_100]
0x18003ccf7  mov     qword ptr [rsp+230h+var_1B8], rcx
0x18003ccfc  mov     qword ptr [rbp+130h+var_1B8+8], rdi
0x18003cd00  lea     rcx, [rbp+130h+var_F8]
0x18003cd04  mov     qword ptr [rbp+130h+var_1A8], rcx
0x18003cd08  lea     rcx, [rbp+130h+var_108]
0x18003cd0c  mov     qword ptr [rbp+130h+var_1A8+8], rcx
0x18003cd10  lea     rcx, [rbp+130h+var_F0]
0x18003cd14  mov     qword ptr [rbp+130h+var_198], rcx
0x18003cd18  mov     byte ptr [rbp+130h+var_198+8], 1
0x18003cd1c  cmp     eax, 1
0x18003cd1f  jbe     short loc_18003CD9B
0x18003cd21  mov     rcx, [rbp+130h+lpMem]; lpMem
0x18003cd25  test    rcx, rcx
0x18003cd28  jz      short loc_18003CD36
0x18003cd2a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003cd2f  mov     [rbp+130h+lpMem], rsi
0x18003cd33  mov     eax, [rbp+130h+var_F8]
0x18003cd36  lea     rcx, [rbp+130h+lpMem]
0x18003cd3a  mov     [rsp+230h+var_208], rcx; wchar_t **
0x18003cd3f  lea     rcx, [rbp+130h+var_FF]
0x18003cd43  mov     [rsp+230h+var_210], rcx; bool *
0x18003cd48  mov     r9, r15; struct IUpdateDeploymentCallback *
0x18003cd4b  mov     r8, [rbp+130h+var_108]; struct tagSusDeployData *
0x18003cd4f  mov     edx, eax; unsigned int
0x18003cd51  mov     rcx, rdi; this
0x18003cd54  call    ?MergeUpdates@COSInstaller@@AEAAJKQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@PEA_NPEAPEA_W@Z; COSInstaller::MergeUpdates(ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,bool *,wchar_t * *)
0x18003cd59  mov     dword ptr [rbp+130h+var_F0], eax
0x18003cd5c  mov     r9d, eax
0x18003cd5f  sar     r9d, 1Fh
0x18003cd63  and     r9d, 0FFFFFFFEh
0x18003cd67  add     r9d, 4
0x18003cd6b  lea     rcx, aMergeUpdatesCo; "Merge updates complete"
0x18003cd72  mov     [rsp+230h+var_208], rcx
0x18003cd77  mov     dword ptr [rsp+230h+var_210], eax
0x18003cd7b  mov     r8d, ebx
0x18003cd7e  xor     edx, edx
0x18003cd80  xor     ecx, ecx
0x18003cd82  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003cd87  mov     ebx, dword ptr [rbp+130h+var_F0]
0x18003cd8a  test    ebx, ebx
0x18003cd8c  jns     short loc_18003CD98
0x18003cd8e  mov     edx, 105h
0x18003cd93  jmp     loc_18003D25A
0x18003cd98  mov     eax, [rbp+130h+var_F8]
0x18003cd9b  mov     r14d, esi
0x18003cd9e  test    eax, eax
0x18003cda0  jz      loc_18003D223
0x18003cda6  mov     eax, r14d
0x18003cda9  imul    r13, rax, 128h
0x18003cdb0  add     r13, [rbp+130h+var_108]
0x18003cdb4  mov     [rbp+130h+var_110], esi
0x18003cdb7  mov     [rbp+130h+var_E0], esi
0x18003cdba  mov     rsi, [r13+38h]
0x18003cdbe  add     rsi, 4
0x18003cdc2  xor     ebx, ebx
0x18003cdc4  mov     [rbp+130h+var_D8], rbx
0x18003cdc8  mov     [rbp+130h+var_E8], rbx
0x18003cdcc  lea     rcx, [rbp+130h+var_70]; this
0x18003cdd3  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x18003cdd8  mov     [rbp+130h+var_58], rbx
0x18003cddf  lea     rcx, [rbp+130h+UnbiasedTime]; UnbiasedTime
0x18003cde6  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003cdec  mov     rcx, [r13+18h]; pbstr
0x18003cdf0  call    cs:__imp_SysStringLen
0x18003cdf6  mov     r12d, eax
0x18003cdf9  test    eax, eax
0x18003cdfb  setnz   [rsp+230h+var_1E0]
0x18003ce00  cmp     [rbp+130h+var_100], bl
0x18003ce03  jz      short loc_18003CE4B
0x18003ce05  test    eax, eax
0x18003ce07  jz      short loc_18003CE4B
0x18003ce09  mov     r15d, 8024B105h
0x18003ce0f  mov     rdx, rsi; struct tagDSGlobalUpdateId *
0x18003ce12  lea     rcx, [rbp+130h+var_180]; this
0x18003ce16  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18003ce1b  mov     [rsp+230h+var_200], rax
0x18003ce20  lea     rax, aSkippingInstal; "Skipping installing update ID: %ws as t"...
0x18003ce27  mov     [rsp+230h+var_208], rax
0x18003ce2c  xor     esi, esi
0x18003ce2e  mov     [rsp+230h+var_210], rsi
0x18003ce33  xor     edx, edx
0x18003ce35  xor     ecx, ecx
0x18003ce37  lea     r9d, [rbx+3]
0x18003ce3b  mov     r8d, 1000h
0x18003ce41  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003ce46  jmp     loc_18003CF96
0x18003ce4b  mov     ebx, [rsi+10h]
0x18003ce4e  mov     rdx, rsi; struct _GUID *
0x18003ce51  lea     rcx, [rbp+130h+var_180]; this
0x18003ce55  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003ce5a  lea     rdx, aMerged; "merged"
0x18003ce61  lea     rcx, aNotMerged; "not merged"
0x18003ce68  test    r12d, r12d
0x18003ce6b  cmovnz  rcx, rdx
0x18003ce6f  mov     [rsp+230h+var_1F0], rcx
0x18003ce74  mov     dword ptr [rsp+230h+var_1F8], ebx
0x18003ce78  mov     [rsp+230h+var_200], rax
0x18003ce7d  lea     rax, aPreparingToIns; "Preparing to install update ID: %ws.%d "...
0x18003ce84  mov     [rsp+230h+var_208], rax
0x18003ce89  mov     [rsp+230h+var_210], 0
0x18003ce92  xor     edx, edx
0x18003ce94  xor     ecx, ecx
0x18003ce96  lea     r9d, [rdx+4]
0x18003ce9a  mov     r8d, 1000h
0x18003cea0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003cea5  mov     eax, r12d
0x18003cea8  neg     eax
0x18003ceaa  sbb     rbx, rbx
0x18003cead  and     rbx, [rbp+130h+lpMem]
0x18003ceb1  mov     rcx, [rbp+130h+var_E8]; lpMem
0x18003ceb5  test    rcx, rcx
0x18003ceb8  jz      short loc_18003CEC7
0x18003ceba  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003cebf  mov     [rbp+130h+var_E8], 0
0x18003cec7  mov     rcx, [rbp+130h+var_D8]; lpMem
0x18003cecb  test    rcx, rcx
0x18003cece  jz      short loc_18003CEDD
0x18003ced0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003ced5  mov     [rbp+130h+var_D8], 0
0x18003cedd  mov     [rsp+230h+var_1E8], rbx
0x18003cee2  lea     rax, [rbp+130h+var_E8]
0x18003cee6  mov     [rsp+230h+var_1F0], rax
0x18003ceeb  lea     rax, [rbp+130h+var_D8]
0x18003ceef  mov     [rsp+230h+var_1F8], rax
0x18003cef4  lea     rax, [rbp+130h+var_E0]
0x18003cef8  mov     [rsp+230h+var_200], rax
0x18003cefd  lea     rax, [rbp+130h+var_110]
0x18003cf01  mov     [rsp+230h+var_208], rax
0x18003cf06  mov     [rsp+230h+var_210], r15
0x18003cf0b  mov     rax, [rsp+230h+var_1C8]
0x18003cf10  mov     r9d, [rax+10h]
0x18003cf14  mov     r8d, 1
0x18003cf1a  mov     rdx, r13
0x18003cf1d  mov     rcx, rdi
0x18003cf20  call    ?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z; COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)
0x18003cf25  mov     r15d, eax
0x18003cf28  lea     rax, aYes; "Yes"
0x18003cf2f  lea     rdi, aNo; "No"
0x18003cf36  cmp     [rbp+130h+var_110], 0
0x18003cf3a  cmovnz  rdi, rax
0x18003cf3e  mov     ebx, [rsi+10h]
0x18003cf41  mov     rdx, rsi; struct _GUID *
0x18003cf44  lea     rcx, [rbp+130h+var_180]; this
0x18003cf48  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003cf4d  mov     r9d, r15d
0x18003cf50  sar     r9d, 1Fh
0x18003cf54  and     r9d, 0FFFFFFFEh
0x18003cf58  add     r9d, 4
0x18003cf5c  mov     [rsp+230h+var_1E8], rdi
0x18003cf61  mov     dword ptr [rsp+230h+var_1F0], r15d
0x18003cf66  mov     dword ptr [rsp+230h+var_1F8], ebx
0x18003cf6a  mov     [rsp+230h+var_200], rax
0x18003cf6f  lea     rax, aInstallComplet; "Install complete for update ID: %ws.%d "...
0x18003cf76  mov     [rsp+230h+var_208], rax
0x18003cf7b  xor     esi, esi
0x18003cf7d  mov     [rsp+230h+var_210], rsi
0x18003cf82  xor     edx, edx
0x18003cf84  xor     ecx, ecx
0x18003cf86  mov     r8d, 1000h
0x18003cf8c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003cf91  mov     rdi, [rsp+230h+var_1D8]
0x18003cf96  mov     rax, [rbp+130h+var_E8]
0x18003cf9a  mov     rcx, [rbp+130h+var_D8]
0x18003cf9e  mov     edx, [rbp+130h+var_E0]
0x18003cfa1  mov     r8d, [rbp+130h+var_110]
0x18003cfa5  mov     [rsp+230h+var_1F0], rax
0x18003cfaa  mov     [rsp+230h+var_1F8], rcx
0x18003cfaf  mov     dword ptr [rsp+230h+var_200], edx
0x18003cfb3  mov     dword ptr [rsp+230h+var_208], r8d
0x18003cfb8  mov     dword ptr [rsp+230h+var_210], r15d; int
0x18003cfbd  mov     r8, r13
0x18003cfc0  mov     rdx, [rsp+230h+var_1D0]
0x18003cfc5  mov     rcx, rdi
0x18003cfc8  call    ?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z; COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)
0x18003cfcd  mov     edi, eax
0x18003cfcf  xor     eax, eax
0x18003cfd1  mov     [rbp+130h+var_C0], rax
0x18003cfd5  mov     [rbp+130h+var_B8], rsi
0x18003cfd9  mov     rcx, rsi
0x18003cfdc  mov     [rbp+130h+var_B0], rcx
0x18003cfe3  xorps   xmm0, xmm0
0x18003cfe6  movups  [rbp+130h+var_A8], xmm0
0x18003cfed  movups  [rbp+130h+var_98], xmm0
0x18003cff4  movups  [rbp+130h+var_88], xmm0
0x18003cffb  mov     [rbp+130h+var_78], rax
0x18003d002  lea     rbx, [r13+70h]
0x18003d006  test    rbx, rbx
0x18003d009  jz      short loc_18003D042
0x18003d00b  cmp     [rbx], sil
0x18003d00e  jz      short loc_18003D042
0x18003d010  lea     rdx, [rbp+130h+var_B8]
0x18003d014  mov     rcx, rbx
0x18003d017  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x18003d01c  mov     rcx, [rbp+138h]; this
0x18003d023  test    eax, eax
0x18003d025  jns     short loc_18003D03B
0x18003d027  mov     r9d, eax; char *
0x18003d02a  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18003d031  mov     edx, 0FCh; void *
0x18003d036  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d03b  mov     rcx, [rbp+130h+var_B0]; lpMem
0x18003d042  mov     rbx, [rsp+230h+var_1C0]
0x18003d047  test    rbx, rbx
0x18003d04a  jz      short loc_18003D090
0x18003d04c  cmp     [rbx], sil
0x18003d04f  jz      short loc_18003D090
0x18003d051  test    rcx, rcx
0x18003d054  jz      short loc_18003D062
0x18003d056  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d05b  mov     [rbp+130h+var_B0], rsi
0x18003d062  lea     rdx, [rbp+130h+var_B0]
0x18003d069  mov     rcx, rbx
0x18003d06c  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x18003d071  mov     rcx, [rbp+138h]; this
0x18003d078  test    eax, eax
0x18003d07a  jns     short loc_18003D090
0x18003d07c  mov     r9d, eax; char *
0x18003d07f  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18003d086  mov     edx, 104h; void *
0x18003d08b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d090  lea     rcx, [rbp+130h+var_60]; UnbiasedTime
0x18003d097  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003d09d  mov     rcx, [rbp+130h+var_60]
0x18003d0a4  sub     rcx, [rbp+130h+UnbiasedTime]
0x18003d0ab  mov     rax, [rbp+130h+var_58]
0x18003d0b2  add     rax, rcx
0x18003d0b5  mov     [rbp+130h+var_58], rax
0x18003d0bc  lea     rcx, aInstall_0; "Install"
0x18003d0c3  mov     [rbp+130h+var_C0], rcx
0x18003d0c7  cmp     [rbp+130h+var_70], sil
0x18003d0ce  jz      short loc_18003D0E0
0x18003d0d0  mov     ecx, [rbp+130h+var_50]
0x18003d0d6  xor     edx, edx
0x18003d0d8  div     rcx
0x18003d0db  mov     rcx, rax
0x18003d0de  jmp     short loc_18003D0E2
0x18003d0e0  mov     ecx, esi
0x18003d0e2  mov     rax, [r13+38h]
0x18003d0e6  movups  xmm0, xmmword ptr [rax+4]
0x18003d0ea  movdqu  [rbp+130h+var_98+4], xmm0
0x18003d0f2  cmp     [rbp+130h+var_110], esi
0x18003d0f5  setnz   byte ptr [rbp+130h+var_A8+9]
0x18003d0fc  mov     eax, [rbp+130h+var_E0]
  ... truncated ...
```
