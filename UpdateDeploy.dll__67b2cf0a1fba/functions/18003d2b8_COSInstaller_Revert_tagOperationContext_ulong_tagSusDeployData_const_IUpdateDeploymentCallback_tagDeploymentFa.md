# COSInstaller::Revert(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)

- ea: `0x18003d2b8`
- end: `0x18003d79f`
- name: `?Revert@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z`
- size: `1255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
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
- `0x18003bd48`
- `0x18003c074`
- `0x18003d2b8`
- `0x18003e3e8`
- `0x18003f448`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d3d1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d5e8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d3d1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d5e8`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d3db`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d3db`

## string_xrefs

- `0x18003d356`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003d741`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003d319`: `Enter Deployment handler Revert. Count of updates = %lu`
- `0x18003d4de`: `Revert complete for update ID: %ws.%d Return code is 0x%08lX. Requires Reboot:%ws`
- `0x18003d400`: `Preparing to revert update ID: %ws.%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COSInstaller::Revert(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _BYTE *a7)
{
  __int64 v7; // rbx
  __int64 v10; // r14
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // r13
  const struct _GUID *v15; // rdi
  int v16; // r14d
  int v17; // ebx
  void *v18; // rcx
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  bool v25; // [rsp+50h] [rbp-B0h]
  wchar_t v29[40]; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v31[3]; // [rsp+E4h] [rbp-1Ch] BYREF
  int v32; // [rsp+F0h] [rbp-10h] BYREF
  void *lpMem; // [rsp+F8h] [rbp-8h] BYREF
  const char *v34; // [rsp+100h] [rbp+0h] BYREF
  void *v35; // [rsp+108h] [rbp+8h] BYREF
  void *v36; // [rsp+110h] [rbp+10h] BYREF
  __int128 v37; // [rsp+118h] [rbp+18h]
  _OWORD v38[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v39; // [rsp+148h] [rbp+48h]
  _BYTE v40[8]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v42; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v43; // [rsp+168h] [rbp+68h]
  unsigned int v44; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v7 = a4;
  v10 = a5;
  v31[0] = 0;
  v24 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !v7 )
  {
    v11 = 414;
LABEL_3:
    v12 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80004003LL,
      0);
    return v12;
  }
  if ( !a5 )
  {
    v11 = 415;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v11 = 416;
    goto LABEL_3;
  }
  v13 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v14 = v7 + 296LL * v13;
      v15 = (const struct _GUID *)(*(_QWORD *)(v14 + 56) + 4LL);
      v30 = 0;
      v32 = 0;
      lpMem = 0;
      *(_QWORD *)&v31[1] = 0;
      CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v40);
      v43 = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v25 = SysStringLen(*(BSTR *)(v14 + 24)) != 0;
      Trace::GuidToString::GuidToString(v29, v15);
      WUTrace(0, 0, 4096, 4);
      if ( *(_QWORD *)&v31[1] )
      {
        SusFree(*(void **)&v31[1]);
        *(_QWORD *)&v31[1] = 0;
      }
      if ( lpMem )
      {
        SusFree(lpMem);
        lpMem = 0;
      }
      v16 = COSInstaller::OrchestrateUpdate(
              a1,
              v14,
              4,
              *(_DWORD *)(a2 + 16),
              v10,
              &v30,
              (__int64)&v32,
              (__int64)&lpMem,
              (__int64)&v31[1],
              0);
      Trace::GuidToString::GuidToString(v29, v15);
      WUTrace(0, 0, 4096, ((v16 >> 31) & 0xFFFFFFFE) + 4);
      v24 = v16;
      v17 = COSInstaller::NotifyResult(a1, a5, v14);
      v34 = 0;
      v35 = 0;
      v18 = 0;
      v36 = 0;
      v37 = 0;
      memset(v38, 0, sizeof(v38));
      v39 = 0;
      if ( v14 != -112 && *(_BYTE *)(v14 + 112) )
      {
        v19 = DuplicateString<char const *,char *>(v14 + 112, &v35);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFC,
            (int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v19);
        v18 = v36;
      }
      if ( a7 && *a7 )
      {
        if ( v18 )
        {
          SusFree(v18);
          v36 = 0;
        }
        v20 = DuplicateString<char const *,char *>(a7, &v36);
        if ( v20 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x104,
            (int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v20);
      }
      QueryUnbiasedInterruptTime(&v42);
      v21 = v42 - UnbiasedTime + v43;
      v43 = v21;
      v34 = "Revert";
      LODWORD(v22) = 0;
      if ( v40[0] )
        v22 = v21 / v44;
      *(_OWORD *)((char *)v38 + 4) = *(_OWORD *)(*(_QWORD *)(v14 + 56) + 4LL);
      BYTE9(v37) = v30 != 0;
      HIDWORD(v37) = v32;
      DWORD1(v37) = v13;
      LOBYTE(v38[0]) = v25;
      *(_QWORD *)((char *)&v38[1] + 4) = __PAIR64__(v16, v17);
      LODWORD(v39) = v22;
      OSDeploymentTelemetry::FirePerUpdateEvent((struct OSDeploymentEventSummary *)&v34);
      if ( v17 < 0 )
      {
        v24 = v17;
        WUTrace(0, 0, 4096, 2);
      }
      if ( v16 < 0 )
      {
        v31[0] = v16;
        if ( !a6 )
          break;
      }
      if ( v36 )
      {
        SusFree(v36);
        v36 = 0;
      }
      if ( v35 )
      {
        SusFree(v35);
        v35 = 0;
      }
      if ( *(_QWORD *)&v31[1] )
      {
        SusFree(*(void **)&v31[1]);
        *(_QWORD *)&v31[1] = 0;
      }
      if ( lpMem )
        SusFree(lpMem);
      if ( ++v13 >= a3 )
        goto LABEL_48;
      v7 = a4;
      v10 = a5;
    }
    if ( v36 )
    {
      SusFree(v36);
      v36 = 0;
    }
    if ( v35 )
    {
      SusFree(v35);
      v35 = 0;
    }
    if ( *(_QWORD *)&v31[1] )
    {
      SusFree(*(void **)&v31[1]);
      *(_QWORD *)&v31[1] = 0;
    }
    if ( lpMem )
      SusFree(lpMem);
  }
LABEL_48:
  v12 = v31[0];
  if ( v31[0] >= 0 )
    v12 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v31[0],
      v24);
  WUTrace(0, 0, 4096, 4);
  return v12;
}

```

## disassembly

```asm
0x18003d2b8  push    rbp
0x18003d2ba  push    rbx
0x18003d2bb  push    rsi
0x18003d2bc  push    rdi
0x18003d2bd  push    r12
0x18003d2bf  push    r13
0x18003d2c1  push    r14
0x18003d2c3  push    r15
0x18003d2c5  lea     rbp, [rsp-88h]
0x18003d2cd  sub     rsp, 188h
0x18003d2d4  mov     rax, cs:__security_cookie
0x18003d2db  xor     rax, rsp
0x18003d2de  mov     [rbp+0C0h+var_48], rax
0x18003d2e2  mov     rbx, r9
0x18003d2e5  mov     [rsp+1C0h+var_148], rbx
0x18003d2ea  mov     r15d, r8d
0x18003d2ed  mov     rdi, rdx
0x18003d2f0  mov     [rsp+1C0h+var_158], rdx
0x18003d2f5  mov     [rsp+1C0h+var_168], rcx
0x18003d2fa  mov     r14, [rbp+0C0h+arg_20]
0x18003d301  mov     [rsp+1C0h+var_160], r14
0x18003d306  mov     r12, [rbp+0C0h+arg_30]
0x18003d30d  xor     r13d, r13d
0x18003d310  mov     dword ptr [rbp+0C0h+var_DC], r13d
0x18003d314  mov     dword ptr [rsp+1C0h+var_190], r8d
0x18003d319  lea     rax, aEnterDeploymen; "Enter Deployment handler Revert. Count "...
0x18003d320  mov     [rsp+1C0h+var_198], rax
0x18003d325  mov     qword ptr [rsp+1C0h+var_1A0], r13; int
0x18003d32a  xor     edx, edx
0x18003d32c  xor     ecx, ecx
0x18003d32e  lea     r9d, [r13+4]
0x18003d332  mov     r8d, 1000h
0x18003d338  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d33d  test    rbx, rbx
0x18003d340  jnz     short loc_18003D367
0x18003d342  mov     edx, 19Eh; void *
0x18003d347  mov     ebx, 80004003h
0x18003d34c  mov     rcx, [rbp+0C8h]; this
0x18003d353  mov     r9d, ebx; char *
0x18003d356  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003d35d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d362  jmp     loc_18003D77D
0x18003d367  test    r14, r14
0x18003d36a  jnz     short loc_18003D373
0x18003d36c  mov     edx, 19Fh
0x18003d371  jmp     short loc_18003D347
0x18003d373  test    rdi, rdi
0x18003d376  jnz     short loc_18003D37F
0x18003d378  mov     edx, 1A0h
0x18003d37d  jmp     short loc_18003D347
0x18003d37f  lea     rax, [rbp+0C0h+var_DC]
0x18003d383  mov     [rbp+0C0h+var_140], rax
0x18003d387  mov     [rbp+0C0h+var_138], 1
0x18003d38b  mov     esi, r13d
0x18003d38e  test    r15d, r15d
0x18003d391  jz      loc_18003D730
0x18003d397  mov     eax, esi
0x18003d399  imul    r13, rax, 128h
0x18003d3a0  add     r13, rbx
0x18003d3a3  mov     rdi, [r13+38h]
0x18003d3a7  add     rdi, 4
0x18003d3ab  mov     [rsp+1C0h+var_150], rdi
0x18003d3b0  xor     ebx, ebx
0x18003d3b2  mov     [rbp+0C0h+var_E0], ebx
0x18003d3b5  mov     [rbp+0C0h+var_D0], ebx
0x18003d3b8  mov     [rbp+0C0h+lpMem], rbx
0x18003d3bc  mov     qword ptr [rbp+0C0h+var_DC+4], rbx
0x18003d3c0  lea     rcx, [rbp+0C0h+var_70]; this
0x18003d3c4  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x18003d3c9  mov     [rbp+0C0h+var_58], rbx
0x18003d3cd  lea     rcx, [rbp+0C0h+UnbiasedTime]; UnbiasedTime
0x18003d3d1  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003d3d7  mov     rcx, [r13+18h]; pbstr
0x18003d3db  call    cs:__imp_SysStringLen
0x18003d3e1  test    eax, eax
0x18003d3e3  setnz   [rsp+1C0h+var_170]
0x18003d3e8  mov     ebx, [rdi+10h]
0x18003d3eb  mov     rdx, rdi; struct _GUID *
0x18003d3ee  lea     rcx, [rbp+0C0h+var_130]; this
0x18003d3f2  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003d3f7  mov     dword ptr [rsp+1C0h+var_188], ebx
0x18003d3fb  mov     [rsp+1C0h+var_190], rax
0x18003d400  lea     rax, aPreparingToRev; "Preparing to revert update ID: %ws.%d"
0x18003d407  mov     [rsp+1C0h+var_198], rax
0x18003d40c  xor     ebx, ebx
0x18003d40e  mov     qword ptr [rsp+1C0h+var_1A0], rbx
0x18003d413  lea     edi, [rbx+4]
0x18003d416  mov     r9d, edi
0x18003d419  xor     edx, edx
0x18003d41b  xor     ecx, ecx
0x18003d41d  mov     r8d, 1000h
0x18003d423  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d428  mov     rcx, qword ptr [rbp+0C0h+var_DC+4]; lpMem
0x18003d42c  test    rcx, rcx
0x18003d42f  jz      short loc_18003D43A
0x18003d431  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d436  mov     qword ptr [rbp+0C0h+var_DC+4], rbx
0x18003d43a  mov     rcx, [rbp+0C0h+lpMem]; lpMem
0x18003d43e  test    rcx, rcx
0x18003d441  jz      short loc_18003D44C
0x18003d443  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d448  mov     [rbp+0C0h+lpMem], rbx
0x18003d44c  mov     [rsp+1C0h+var_178], rbx
0x18003d451  lea     rax, [rbp+0C0h+var_DC+4]
0x18003d455  mov     [rsp+1C0h+var_180], rax
0x18003d45a  lea     rax, [rbp+0C0h+lpMem]
0x18003d45e  mov     [rsp+1C0h+var_188], rax
0x18003d463  lea     rax, [rbp+0C0h+var_D0]
0x18003d467  mov     [rsp+1C0h+var_190], rax
0x18003d46c  lea     rax, [rbp+0C0h+var_E0]
0x18003d470  mov     [rsp+1C0h+var_198], rax
0x18003d475  mov     qword ptr [rsp+1C0h+var_1A0], r14
0x18003d47a  mov     rax, [rsp+1C0h+var_158]
0x18003d47f  mov     r9d, [rax+10h]
0x18003d483  mov     r8d, edi
0x18003d486  mov     rdx, r13
0x18003d489  mov     rcx, [rsp+1C0h+var_168]
0x18003d48e  call    ?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z; COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)
0x18003d493  mov     r14d, eax
0x18003d496  lea     rax, aYes; "Yes"
0x18003d49d  lea     rdi, aNo; "No"
0x18003d4a4  cmp     [rbp+0C0h+var_E0], ebx
0x18003d4a7  cmovnz  rdi, rax
0x18003d4ab  mov     rdx, [rsp+1C0h+var_150]; struct _GUID *
0x18003d4b0  mov     ebx, [rdx+10h]
0x18003d4b3  lea     rcx, [rbp+0C0h+var_130]; this
0x18003d4b7  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003d4bc  mov     r9d, r14d
0x18003d4bf  sar     r9d, 1Fh
0x18003d4c3  and     r9d, 0FFFFFFFEh
0x18003d4c7  add     r9d, 4
0x18003d4cb  mov     [rsp+1C0h+var_178], rdi
0x18003d4d0  mov     dword ptr [rsp+1C0h+var_180], r14d
0x18003d4d5  mov     dword ptr [rsp+1C0h+var_188], ebx
0x18003d4d9  mov     [rsp+1C0h+var_190], rax
0x18003d4de  lea     rax, aRevertComplete; "Revert complete for update ID: %ws.%d R"...
0x18003d4e5  mov     [rsp+1C0h+var_198], rax
0x18003d4ea  xor     edx, edx
0x18003d4ec  mov     qword ptr [rsp+1C0h+var_1A0], rdx
0x18003d4f1  xor     ecx, ecx
0x18003d4f3  mov     r8d, 1000h
0x18003d4f9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d4fe  mov     rax, qword ptr [rbp+0C0h+var_DC+4]
0x18003d502  mov     rcx, [rbp+0C0h+lpMem]
0x18003d506  mov     edx, [rbp+0C0h+var_D0]
0x18003d509  mov     r8d, [rbp+0C0h+var_E0]
0x18003d50d  mov     [rsp+1C0h+var_180], rax
0x18003d512  mov     [rsp+1C0h+var_188], rcx
0x18003d517  mov     dword ptr [rsp+1C0h+var_190], edx
0x18003d51b  mov     dword ptr [rsp+1C0h+var_198], r8d
0x18003d520  mov     [rsp+1C0h+var_1A0], r14d; int
0x18003d525  mov     r8, r13
0x18003d528  mov     rdx, [rsp+1C0h+var_160]
0x18003d52d  mov     rcx, [rsp+1C0h+var_168]
0x18003d532  call    ?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z; COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)
0x18003d537  mov     ebx, eax
0x18003d539  xor     eax, eax
0x18003d53b  mov     [rbp+0C0h+var_C0], rax
0x18003d53f  xor     edx, edx
0x18003d541  mov     [rbp+0C0h+var_B8], rdx
0x18003d545  mov     ecx, edx
0x18003d547  mov     [rbp+0C0h+var_B0], rdx
0x18003d54b  xorps   xmm0, xmm0
0x18003d54e  movups  [rbp+0C0h+var_A8], xmm0
0x18003d552  movups  [rbp+0C0h+var_98], xmm0
0x18003d556  movups  [rbp+0C0h+var_88], xmm0
0x18003d55a  mov     [rbp+0C0h+var_78], rax
0x18003d55e  lea     rdi, [r13+70h]
0x18003d562  test    rdi, rdi
0x18003d565  jz      short loc_18003D59E
0x18003d567  cmp     [rdi], dl
0x18003d569  jz      short loc_18003D59E
0x18003d56b  lea     rdx, [rbp+0C0h+var_B8]
0x18003d56f  mov     rcx, rdi
0x18003d572  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x18003d577  mov     rcx, [rbp+0C8h]; this
0x18003d57e  xor     edx, edx
0x18003d580  test    eax, eax
0x18003d582  jns     short loc_18003D59A
0x18003d584  mov     r9d, eax; char *
0x18003d587  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18003d58e  mov     edx, 0FCh; void *
0x18003d593  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d598  xor     edx, edx
0x18003d59a  mov     rcx, [rbp+0C0h+var_B0]; lpMem
0x18003d59e  test    r12, r12
0x18003d5a1  jz      short loc_18003D5E4
0x18003d5a3  cmp     [r12], dl
0x18003d5a7  jz      short loc_18003D5E4
0x18003d5a9  test    rcx, rcx
0x18003d5ac  jz      short loc_18003D5B9
0x18003d5ae  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d5b3  xor     eax, eax
0x18003d5b5  mov     [rbp+0C0h+var_B0], rax
0x18003d5b9  lea     rdx, [rbp+0C0h+var_B0]
0x18003d5bd  mov     rcx, r12
0x18003d5c0  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x18003d5c5  mov     rcx, [rbp+0C8h]; this
0x18003d5cc  test    eax, eax
0x18003d5ce  jns     short loc_18003D5E4
0x18003d5d0  mov     r9d, eax; char *
0x18003d5d3  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18003d5da  mov     edx, 104h; void *
0x18003d5df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d5e4  lea     rcx, [rbp+0C0h+var_60]; UnbiasedTime
0x18003d5e8  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003d5ee  mov     rcx, [rbp+0C0h+var_60]
0x18003d5f2  sub     rcx, [rbp+0C0h+UnbiasedTime]
0x18003d5f6  mov     rax, [rbp+0C0h+var_58]
0x18003d5fa  add     rax, rcx
0x18003d5fd  mov     [rbp+0C0h+var_58], rax
0x18003d601  lea     rcx, aRevert; "Revert"
0x18003d608  mov     [rbp+0C0h+var_C0], rcx
0x18003d60c  xor     ecx, ecx
0x18003d60e  cmp     [rbp+0C0h+var_70], cl
0x18003d611  jz      short loc_18003D61E
0x18003d613  mov     ecx, [rbp+0C0h+var_50]
0x18003d616  xor     edx, edx
0x18003d618  div     rcx
0x18003d61b  mov     rcx, rax
0x18003d61e  mov     rax, [r13+38h]
0x18003d622  movups  xmm0, xmmword ptr [rax+4]
0x18003d626  movdqu  [rbp+0C0h+var_98+4], xmm0
0x18003d62b  xor     r13d, r13d
0x18003d62e  cmp     [rbp+0C0h+var_E0], r13d
0x18003d632  setnz   byte ptr [rbp+0C0h+var_A8+9]
0x18003d636  mov     eax, [rbp+0C0h+var_D0]
0x18003d639  mov     dword ptr [rbp+0C0h+var_A8+0Ch], eax
0x18003d63c  mov     dword ptr [rbp+0C0h+var_A8+4], esi
0x18003d63f  mov     al, [rsp+1C0h+var_170]
0x18003d643  mov     byte ptr [rbp+0C0h+var_98], al
0x18003d646  mov     dword ptr [rbp+0C0h+var_88+4], ebx
0x18003d649  mov     dword ptr [rbp+0C0h+var_88+8], r14d
0x18003d64d  mov     dword ptr [rbp+0C0h+var_78], ecx
0x18003d650  lea     rcx, [rbp+0C0h+var_C0]; struct OSDeploymentEventSummary *
0x18003d654  call    ?FirePerUpdateEvent@OSDeploymentTelemetry@@SAXPEAUOSDeploymentEventSummary@@@Z; OSDeploymentTelemetry::FirePerUpdateEvent(OSDeploymentEventSummary *)
0x18003d659  test    ebx, ebx
0x18003d65b  jns     short loc_18003D680
0x18003d65d  lea     rax, aNotifyFailed; "Notify failed"
0x18003d664  mov     [rsp+1C0h+var_198], rax
0x18003d669  mov     [rsp+1C0h+var_1A0], ebx; int
0x18003d66d  xor     edx, edx
0x18003d66f  xor     ecx, ecx
0x18003d671  lea     r9d, [r13+2]
0x18003d675  mov     r8d, 1000h
0x18003d67b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d680  test    r14d, r14d
0x18003d683  jns     short loc_18003D692
0x18003d685  mov     dword ptr [rbp+0C0h+var_DC], r14d
0x18003d689  cmp     [rbp+0C0h+arg_28], r13d
0x18003d690  jz      short loc_18003D6EC
0x18003d692  mov     rcx, [rbp+0C0h+var_B0]; lpMem
0x18003d696  test    rcx, rcx
0x18003d699  jz      short loc_18003D6A4
0x18003d69b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d6a0  mov     [rbp+0C0h+var_B0], r13
0x18003d6a4  mov     rcx, [rbp+0C0h+var_B8]; lpMem
0x18003d6a8  test    rcx, rcx
0x18003d6ab  jz      short loc_18003D6B6
0x18003d6ad  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d6b2  mov     [rbp+0C0h+var_B8], r13
0x18003d6b6  mov     rcx, qword ptr [rbp+0C0h+var_DC+4]; lpMem
0x18003d6ba  test    rcx, rcx
0x18003d6bd  jz      short loc_18003D6C8
0x18003d6bf  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d6c4  mov     qword ptr [rbp+0C0h+var_DC+4], r13
0x18003d6c8  mov     rcx, [rbp+0C0h+lpMem]; lpMem
0x18003d6cc  test    rcx, rcx
0x18003d6cf  jz      short loc_18003D6D6
0x18003d6d1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d6d6  inc     esi
0x18003d6d8  cmp     esi, r15d
0x18003d6db  jnb     short loc_18003D730
0x18003d6dd  mov     rbx, [rsp+1C0h+var_148]
0x18003d6e2  mov     r14, [rsp+1C0h+var_160]
0x18003d6e7  jmp     loc_18003D397
0x18003d6ec  mov     rcx, [rbp+0C0h+var_B0]; lpMem
0x18003d6f0  test    rcx, rcx
0x18003d6f3  jz      short loc_18003D6FE
0x18003d6f5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d6fa  mov     [rbp+0C0h+var_B0], r13
0x18003d6fe  mov     rcx, [rbp+0C0h+var_B8]; lpMem
0x18003d702  test    rcx, rcx
0x18003d705  jz      short loc_18003D710
0x18003d707  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d70c  mov     [rbp+0C0h+var_B8], r13
0x18003d710  mov     rcx, qword ptr [rbp+0C0h+var_DC+4]; lpMem
0x18003d714  test    rcx, rcx
0x18003d717  jz      short loc_18003D722
0x18003d719  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d71e  mov     qword ptr [rbp+0C0h+var_DC+4], r13
0x18003d722  mov     rcx, [rbp+0C0h+lpMem]; lpMem
0x18003d726  test    rcx, rcx
0x18003d729  jz      short loc_18003D730
0x18003d72b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d730  mov     ebx, dword ptr [rbp+0C0h+var_DC]
0x18003d733  test    ebx, ebx
0x18003d735  jns     short loc_18003D754
0x18003d737  mov     rcx, [rbp+0C8h]; this
0x18003d73e  mov     r9d, ebx; char *
  ... truncated ...
```
