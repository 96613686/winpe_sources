# COSInstaller::Commit(ulong,tagSusDeployData const * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)

- ea: `0x18003d7a8`
- end: `0x18003dc4a`
- name: `?Commit@COSInstaller@@AEAAJKQEBUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z`
- size: `1186`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, _BYTE *)`
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
- `0x18003d7a8`
- `0x18003e3e8`
- `0x18003f448`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d896`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003da95`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003d896`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003da95`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d8a0`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d8a0`

## string_xrefs

- `0x18003daae`: `Commit`
- `0x18003d802`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003dbec`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003d822`: `Enter deployment handler Commit. Count of updates = %lu`
- `0x18003dc02`: `Leave deployment handler Commit`
- `0x18003d987`: `Commit complete for update ID: %ws.%d Return code is 0x%08lX`
- `0x18003d8c9`: `Preparing to commit update ID: %ws.%d`

## pseudocode

```c
__int64 __fastcall COSInstaller::Commit(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5, _BYTE *a6)
{
  __int64 v6; // rbx
  __int64 v8; // rsi
  unsigned int v9; // edi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r13
  __int64 v13; // r12
  int v14; // esi
  int v15; // ebx
  void *v16; // rcx
  int v17; // eax
  int v18; // eax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  bool v24; // [rsp+50h] [rbp-B0h]
  wchar_t v28[40]; // [rsp+80h] [rbp-80h] BYREF
  char *v29; // [rsp+D0h] [rbp-30h]
  void *lpMem; // [rsp+D8h] [rbp-28h] BYREF
  int v31; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+E4h] [rbp-1Ch] BYREF
  void *v33; // [rsp+E8h] [rbp-18h] BYREF
  const char *v34; // [rsp+F0h] [rbp-10h] BYREF
  void *v35; // [rsp+F8h] [rbp-8h] BYREF
  void *v36; // [rsp+100h] [rbp+0h] BYREF
  __int128 v37; // [rsp+108h] [rbp+8h]
  _OWORD v38[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v39; // [rsp+138h] [rbp+38h]
  _BYTE v40[8]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int64 v42; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v43; // [rsp+158h] [rbp+58h]
  unsigned int v44; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v6 = a3;
  v8 = a1;
  v9 = 0;
  LODWORD(v29) = 0;
  if ( !a4 )
  {
    v10 = -2147467261;
    v11 = 531;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v10,
      v22);
    return v10;
  }
  v22 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !a2 )
  {
    v10 = -2145124316;
    v11 = 536;
    goto LABEL_3;
  }
  while ( 1 )
  {
    v12 = v6 + 296LL * v9;
    v13 = *(_QWORD *)(v12 + 56);
    v31 = 0;
    v32 = 0;
    v33 = 0;
    lpMem = 0;
    CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v40);
    v43 = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v24 = SysStringLen(*(BSTR *)(v12 + 24)) != 0;
    Trace::GuidToString::GuidToString(v28, (const struct _GUID *)(v13 + 4));
    WUTrace(0, 0, 4096, 4);
    if ( lpMem )
    {
      SusFree(lpMem);
      lpMem = 0;
    }
    if ( v33 )
    {
      SusFree(v33);
      v33 = 0;
    }
    v14 = COSInstaller::OrchestrateUpdate(v8, v12, 2, -1, 0, &v31, (__int64)&v32, (__int64)&v33, (__int64)&lpMem, 0);
    Trace::GuidToString::GuidToString(v28, (const struct _GUID *)(v13 + 4));
    WUTrace(0, 0, 4096, ((v14 >> 31) & 0xFFFFFFFE) + 4);
    v23 = v14;
    v15 = COSInstaller::NotifyResult(a1, a4, v12);
    v34 = 0;
    v35 = 0;
    v16 = 0;
    v36 = 0;
    v37 = 0;
    memset(v38, 0, sizeof(v38));
    v39 = 0;
    if ( v12 != -112 && *(_BYTE *)(v12 + 112) )
    {
      v17 = DuplicateString<char const *,char *>(v12 + 112, &v35);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFC,
          (int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
          (const char *)(unsigned int)v17);
      v16 = v36;
    }
    if ( a6 && *a6 )
    {
      if ( v16 )
      {
        SusFree(v16);
        v36 = 0;
      }
      v18 = DuplicateString<char const *,char *>(a6, &v36);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x104,
          (int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
          (const char *)(unsigned int)v18);
    }
    QueryUnbiasedInterruptTime(&v42);
    v19 = v42 - UnbiasedTime + v43;
    v43 = v19;
    v34 = "Commit";
    if ( v40[0] )
      v20 = v19 / v44;
    else
      LODWORD(v20) = 0;
    *(_OWORD *)((char *)v38 + 4) = *(_OWORD *)(*(_QWORD *)(v12 + 56) + 4LL);
    BYTE9(v37) = v31 != 0;
    HIDWORD(v37) = v32;
    DWORD1(v37) = v9;
    LOBYTE(v38[0]) = v24;
    *(_QWORD *)((char *)&v38[1] + 4) = __PAIR64__(v14, v15);
    LODWORD(v39) = v20;
    OSDeploymentTelemetry::FirePerUpdateEvent((struct OSDeploymentEventSummary *)&v34);
    if ( v15 < 0 )
    {
      v23 = v15;
      WUTrace(0, 0, 4096, 2);
    }
    if ( v14 < 0 )
    {
      LODWORD(v29) = v14;
      if ( !a5 )
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
    if ( lpMem )
    {
      SusFree(lpMem);
      lpMem = 0;
    }
    if ( v33 )
      SusFree(v33);
    if ( ++v9 >= a2 )
      goto LABEL_46;
    v6 = a3;
    v8 = a1;
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
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v33 )
    SusFree(v33);
LABEL_46:
  v10 = (unsigned int)v29;
  if ( (int)v29 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x274,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v29,
      v23);
  WUTrace(0, 0, 4096, 4);
  return v10;
}

```

## disassembly

```asm
0x18003d7a8  push    rbp
0x18003d7aa  push    rbx
0x18003d7ab  push    rsi
0x18003d7ac  push    rdi
0x18003d7ad  push    r12
0x18003d7af  push    r13
0x18003d7b1  push    r14
0x18003d7b3  push    r15
0x18003d7b5  lea     rbp, [rsp-78h]
0x18003d7ba  sub     rsp, 178h
0x18003d7c1  mov     rax, cs:__security_cookie
0x18003d7c8  xor     rax, rsp
0x18003d7cb  mov     [rbp+0B0h+var_48], rax
0x18003d7cf  mov     [rsp+1B0h+var_150], r9
0x18003d7d4  mov     rbx, r8
0x18003d7d7  mov     [rsp+1B0h+var_148], rbx
0x18003d7dc  mov     r14d, edx
0x18003d7df  mov     rsi, rcx
0x18003d7e2  mov     [rsp+1B0h+var_158], rcx
0x18003d7e7  mov     r15, [rbp+0B0h+arg_28]
0x18003d7ee  xor     edi, edi
0x18003d7f0  mov     dword ptr [rbp+0B0h+var_E0], edi
0x18003d7f3  test    r9, r9
0x18003d7f6  jnz     short loc_18003D81D
0x18003d7f8  mov     ebx, 80004003h
0x18003d7fd  mov     edx, 213h; void *
0x18003d802  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003d809  mov     r9d, ebx; char *
0x18003d80c  mov     rcx, [rbp+0B8h]; this
0x18003d813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d818  jmp     loc_18003DC28
0x18003d81d  mov     dword ptr [rsp+1B0h+var_180], r14d
0x18003d822  lea     rax, aEnterDeploymen_2; "Enter deployment handler Commit. Count "...
0x18003d829  mov     [rsp+1B0h+var_188], rax
0x18003d82e  mov     qword ptr [rsp+1B0h+var_190], rdi
0x18003d833  xor     edx, edx
0x18003d835  xor     ecx, ecx
0x18003d837  lea     r9d, [rdx+4]
0x18003d83b  mov     r8d, 1000h
0x18003d841  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d846  test    r14d, r14d
0x18003d849  jnz     short loc_18003D857
0x18003d84b  mov     ebx, 80240024h
0x18003d850  mov     edx, 218h
0x18003d855  jmp     short loc_18003D802
0x18003d857  lea     rax, [rbp+0B0h+var_E0]
0x18003d85b  mov     [rsp+1B0h+var_140], rax
0x18003d860  mov     [rsp+1B0h+var_138], 1
0x18003d865  mov     eax, edi
0x18003d867  imul    r13, rax, 128h
0x18003d86e  add     r13, rbx
0x18003d871  mov     r12, [r13+38h]
0x18003d875  xor     ebx, ebx
0x18003d877  mov     [rbp+0B0h+var_D0], ebx
0x18003d87a  mov     [rbp+0B0h+var_CC], ebx
0x18003d87d  mov     [rbp+0B0h+var_C8], rbx
0x18003d881  mov     [rbp+0B0h+lpMem], rbx
0x18003d885  lea     rcx, [rbp+0B0h+var_70]; this
0x18003d889  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x18003d88e  mov     [rbp+0B0h+var_58], rbx
0x18003d892  lea     rcx, [rbp+0B0h+UnbiasedTime]; UnbiasedTime
0x18003d896  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003d89c  mov     rcx, [r13+18h]; pbstr
0x18003d8a0  call    cs:__imp_SysStringLen
0x18003d8a6  test    eax, eax
0x18003d8a8  setnz   [rsp+1B0h+var_160]
0x18003d8ad  mov     ebx, [r12+14h]
0x18003d8b2  lea     rdx, [r12+4]; struct _GUID *
0x18003d8b7  lea     rcx, [rbp+0B0h+var_130]; this
0x18003d8bb  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003d8c0  mov     dword ptr [rsp+1B0h+var_178], ebx
0x18003d8c4  mov     [rsp+1B0h+var_180], rax
0x18003d8c9  lea     rax, aPreparingToCom; "Preparing to commit update ID: %ws.%d"
0x18003d8d0  mov     [rsp+1B0h+var_188], rax
0x18003d8d5  xor     ebx, ebx
0x18003d8d7  mov     qword ptr [rsp+1B0h+var_190], rbx
0x18003d8dc  xor     edx, edx
0x18003d8de  xor     ecx, ecx
0x18003d8e0  lea     r9d, [rbx+4]
0x18003d8e4  mov     r8d, 1000h
0x18003d8ea  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d8ef  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x18003d8f3  test    rcx, rcx
0x18003d8f6  jz      short loc_18003D901
0x18003d8f8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d8fd  mov     [rbp+0B0h+lpMem], rbx
0x18003d901  mov     rcx, [rbp+0B0h+var_C8]; lpMem
0x18003d905  test    rcx, rcx
0x18003d908  jz      short loc_18003D913
0x18003d90a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003d90f  mov     [rbp+0B0h+var_C8], rbx
0x18003d913  mov     [rsp+1B0h+var_168], rbx
0x18003d918  lea     rax, [rbp+0B0h+lpMem]
0x18003d91c  mov     [rsp+1B0h+var_170], rax
0x18003d921  lea     rax, [rbp+0B0h+var_C8]
0x18003d925  mov     [rsp+1B0h+var_178], rax
0x18003d92a  lea     rax, [rbp+0B0h+var_CC]
0x18003d92e  mov     [rsp+1B0h+var_180], rax
0x18003d933  lea     rax, [rbp+0B0h+var_D0]
0x18003d937  mov     [rsp+1B0h+var_188], rax
0x18003d93c  mov     qword ptr [rsp+1B0h+var_190], rbx
0x18003d941  or      r9d, 0FFFFFFFFh
0x18003d945  mov     r8d, 2
0x18003d94b  mov     rdx, r13
0x18003d94e  mov     rcx, rsi
0x18003d951  call    ?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z; COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)
0x18003d956  mov     esi, eax
0x18003d958  mov     ebx, [r12+14h]
0x18003d95d  lea     rdx, [r12+4]; struct _GUID *
0x18003d962  lea     rcx, [rbp+0B0h+var_130]; this
0x18003d966  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003d96b  mov     r9d, esi
0x18003d96e  sar     r9d, 1Fh
0x18003d972  and     r9d, 0FFFFFFFEh
0x18003d976  add     r9d, 4
0x18003d97a  mov     dword ptr [rsp+1B0h+var_170], esi
0x18003d97e  mov     dword ptr [rsp+1B0h+var_178], ebx
0x18003d982  mov     [rsp+1B0h+var_180], rax
0x18003d987  lea     rax, aCommitComplete; "Commit complete for update ID: %ws.%d R"...
0x18003d98e  mov     [rsp+1B0h+var_188], rax
0x18003d993  xor     eax, eax
0x18003d995  mov     qword ptr [rsp+1B0h+var_190], rax
0x18003d99a  xor     edx, edx
0x18003d99c  xor     ecx, ecx
0x18003d99e  mov     r8d, 1000h
0x18003d9a4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003d9a9  mov     rax, [rbp+0B0h+lpMem]
0x18003d9ad  mov     rcx, [rbp+0B0h+var_C8]
0x18003d9b1  mov     edx, [rbp+0B0h+var_CC]
0x18003d9b4  mov     r8d, [rbp+0B0h+var_D0]
0x18003d9b8  mov     [rsp+1B0h+var_170], rax
0x18003d9bd  mov     [rsp+1B0h+var_178], rcx
0x18003d9c2  mov     dword ptr [rsp+1B0h+var_180], edx
0x18003d9c6  mov     dword ptr [rsp+1B0h+var_188], r8d
0x18003d9cb  mov     [rsp+1B0h+var_190], esi; int
0x18003d9cf  mov     r8, r13
0x18003d9d2  mov     rdx, [rsp+1B0h+var_150]
0x18003d9d7  mov     rcx, [rsp+1B0h+var_158]
0x18003d9dc  call    ?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z; COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)
0x18003d9e1  mov     ebx, eax
0x18003d9e3  xor     eax, eax
0x18003d9e5  mov     [rbp+0B0h+var_C0], rax
0x18003d9e9  xor     edx, edx
0x18003d9eb  mov     [rbp+0B0h+var_B8], rdx
0x18003d9ef  mov     ecx, edx; lpMem
0x18003d9f1  mov     [rbp+0B0h+var_B0], rdx
0x18003d9f5  xorps   xmm0, xmm0
0x18003d9f8  movups  [rbp+0B0h+var_A8], xmm0
0x18003d9fc  movups  [rbp+0B0h+var_98], xmm0
0x18003da00  movups  [rbp+0B0h+var_88], xmm0
0x18003da04  mov     [rbp+0B0h+var_78], rax
0x18003da08  lea     r12, [r13+70h]
0x18003da0c  test    r12, r12
0x18003da0f  jz      short loc_18003DA4B
0x18003da11  cmp     [r12], dl
0x18003da15  jz      short loc_18003DA4B
0x18003da17  lea     rdx, [rbp+0B0h+var_B8]
0x18003da1b  mov     rcx, r12
0x18003da1e  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x18003da23  mov     rcx, [rbp+0B8h]; this
0x18003da2a  xor     r12d, r12d
0x18003da2d  test    eax, eax
0x18003da2f  jns     short loc_18003DA45
0x18003da31  mov     r9d, eax; char *
0x18003da34  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18003da3b  mov     edx, 0FCh; void *
0x18003da40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003da45  mov     rcx, [rbp+0B0h+var_B0]
0x18003da49  jmp     short loc_18003DA4E
0x18003da4b  xor     r12d, r12d
0x18003da4e  test    r15, r15
0x18003da51  jz      short loc_18003DA91
0x18003da53  cmp     [r15], r12b
0x18003da56  jz      short loc_18003DA91
0x18003da58  test    rcx, rcx
0x18003da5b  jz      short loc_18003DA66
0x18003da5d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003da62  mov     [rbp+0B0h+var_B0], r12
0x18003da66  lea     rdx, [rbp+0B0h+var_B0]
0x18003da6a  mov     rcx, r15
0x18003da6d  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x18003da72  mov     rcx, [rbp+0B8h]; this
0x18003da79  test    eax, eax
0x18003da7b  jns     short loc_18003DA91
0x18003da7d  mov     r9d, eax; char *
0x18003da80  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18003da87  mov     edx, 104h; void *
0x18003da8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003da91  lea     rcx, [rbp+0B0h+var_60]; UnbiasedTime
0x18003da95  call    cs:__imp_QueryUnbiasedInterruptTime
0x18003da9b  mov     rcx, [rbp+0B0h+var_60]
0x18003da9f  sub     rcx, [rbp+0B0h+UnbiasedTime]
0x18003daa3  mov     rax, [rbp+0B0h+var_58]
0x18003daa7  add     rax, rcx
0x18003daaa  mov     [rbp+0B0h+var_58], rax
0x18003daae  lea     rcx, aCommit_0; "Commit"
0x18003dab5  mov     [rbp+0B0h+var_C0], rcx
0x18003dab9  cmp     [rbp+0B0h+var_70], r12b
0x18003dabd  jz      short loc_18003DACC
0x18003dabf  mov     ecx, [rbp+0B0h+var_50]
0x18003dac2  xor     edx, edx
0x18003dac4  div     rcx
0x18003dac7  mov     rcx, rax
0x18003daca  jmp     short loc_18003DACF
0x18003dacc  mov     ecx, r12d
0x18003dacf  mov     rax, [r13+38h]
0x18003dad3  movups  xmm0, xmmword ptr [rax+4]
0x18003dad7  movdqu  [rbp+0B0h+var_98+4], xmm0
0x18003dadc  cmp     [rbp+0B0h+var_D0], r12d
0x18003dae0  setnz   byte ptr [rbp+0B0h+var_A8+9]
0x18003dae4  mov     eax, [rbp+0B0h+var_CC]
0x18003dae7  mov     dword ptr [rbp+0B0h+var_A8+0Ch], eax
0x18003daea  mov     dword ptr [rbp+0B0h+var_A8+4], edi
0x18003daed  mov     al, [rsp+1B0h+var_160]
0x18003daf1  mov     byte ptr [rbp+0B0h+var_98], al
0x18003daf4  mov     dword ptr [rbp+0B0h+var_88+4], ebx
0x18003daf7  mov     dword ptr [rbp+0B0h+var_88+8], esi
0x18003dafa  mov     dword ptr [rbp+0B0h+var_78], ecx
0x18003dafd  lea     rcx, [rbp+0B0h+var_C0]; struct OSDeploymentEventSummary *
0x18003db01  call    ?FirePerUpdateEvent@OSDeploymentTelemetry@@SAXPEAUOSDeploymentEventSummary@@@Z; OSDeploymentTelemetry::FirePerUpdateEvent(OSDeploymentEventSummary *)
0x18003db06  test    ebx, ebx
0x18003db08  jns     short loc_18003DB2D
0x18003db0a  lea     rax, aNotifyFailed; "Notify failed"
0x18003db11  mov     [rsp+1B0h+var_188], rax
0x18003db16  mov     [rsp+1B0h+var_190], ebx; int
0x18003db1a  xor     edx, edx
0x18003db1c  xor     ecx, ecx
0x18003db1e  lea     r9d, [rdx+2]
0x18003db22  mov     r8d, 1000h
0x18003db28  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003db2d  test    esi, esi
0x18003db2f  jns     short loc_18003DB3D
0x18003db31  mov     dword ptr [rbp+0B0h+var_E0], esi
0x18003db34  cmp     [rbp+0B0h+arg_20], r12d
0x18003db3b  jz      short loc_18003DB97
0x18003db3d  mov     rcx, [rbp+0B0h+var_B0]; lpMem
0x18003db41  test    rcx, rcx
0x18003db44  jz      short loc_18003DB4F
0x18003db46  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003db4b  mov     [rbp+0B0h+var_B0], r12
0x18003db4f  mov     rcx, [rbp+0B0h+var_B8]; lpMem
0x18003db53  test    rcx, rcx
0x18003db56  jz      short loc_18003DB61
0x18003db58  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003db5d  mov     [rbp+0B0h+var_B8], r12
0x18003db61  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x18003db65  test    rcx, rcx
0x18003db68  jz      short loc_18003DB73
0x18003db6a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003db6f  mov     [rbp+0B0h+lpMem], r12
0x18003db73  mov     rcx, [rbp+0B0h+var_C8]; lpMem
0x18003db77  test    rcx, rcx
0x18003db7a  jz      short loc_18003DB81
0x18003db7c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003db81  inc     edi
0x18003db83  cmp     edi, r14d
0x18003db86  jnb     short loc_18003DBDB
0x18003db88  mov     rbx, [rsp+1B0h+var_148]
0x18003db8d  mov     rsi, [rsp+1B0h+var_158]
0x18003db92  jmp     loc_18003D865
0x18003db97  mov     rcx, [rbp+0B0h+var_B0]; lpMem
0x18003db9b  test    rcx, rcx
0x18003db9e  jz      short loc_18003DBA9
0x18003dba0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003dba5  mov     [rbp+0B0h+var_B0], r12
0x18003dba9  mov     rcx, [rbp+0B0h+var_B8]; lpMem
0x18003dbad  test    rcx, rcx
0x18003dbb0  jz      short loc_18003DBBB
0x18003dbb2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003dbb7  mov     [rbp+0B0h+var_B8], r12
0x18003dbbb  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x18003dbbf  test    rcx, rcx
0x18003dbc2  jz      short loc_18003DBCD
0x18003dbc4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003dbc9  mov     [rbp+0B0h+lpMem], r12
0x18003dbcd  mov     rcx, [rbp+0B0h+var_C8]; lpMem
0x18003dbd1  test    rcx, rcx
0x18003dbd4  jz      short loc_18003DBDB
0x18003dbd6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003dbdb  mov     ebx, dword ptr [rbp+0B0h+var_E0]
0x18003dbde  test    ebx, ebx
0x18003dbe0  jns     short loc_18003DBFF
0x18003dbe2  mov     rcx, [rbp+0B8h]; this
0x18003dbe9  mov     r9d, ebx; char *
0x18003dbec  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003dbf3  mov     edx, 274h; void *
0x18003dbf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dbfd  jmp     short loc_18003DC02
0x18003dbff  mov     ebx, r12d
0x18003dc02  lea     rax, aLeaveDeploymen_2; "Leave deployment handler Commit"
0x18003dc09  mov     [rsp+1B0h+var_188], rax
0x18003dc0e  mov     ecx, dword ptr [rbp+0B0h+var_E0]
0x18003dc11  mov     [rsp+1B0h+var_190], ecx
0x18003dc15  xor     edx, edx
0x18003dc17  xor     ecx, ecx
0x18003dc19  lea     r9d, [rdx+4]
0x18003dc1d  mov     r8d, 1000h
0x18003dc23  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003dc28  mov     eax, ebx
0x18003dc2a  mov     rcx, [rbp+0B0h+var_48]
  ... truncated ...
```
