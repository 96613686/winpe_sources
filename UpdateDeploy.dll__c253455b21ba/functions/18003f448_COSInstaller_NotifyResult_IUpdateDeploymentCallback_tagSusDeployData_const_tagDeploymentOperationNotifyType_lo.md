# COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)

- ea: `0x18003f448`
- end: `0x18003f75a`
- name: `?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z`
- size: `786`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003cc10`
- `0x18003d2b8`
- `0x18003d7a8`

## callees

- `0x180003180`
- `0x180008b30`
- `0x18000c0ac`
- `0x1800110fc`
- `0x180011b44`
- `0x18003f448`
- `0x180040ae8`
- `0x18004f56c`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18003f55a`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f55a`

## string_xrefs

- `0x18003f4e9`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003f6e8`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003f5d8`: `Update with ID: %ws.%d %ws require explicit commit call`
- `0x18003f68a`: `COSInstaller::NotifyResult`
- `0x18003f65a`: `(deploymentCompleteData.rgpszDriverRecoveryIds == nullptr && deploymentCompleteData.cDriverRecoveryIds == 0) || (deploymentCompleteData.rgpszDriverRecoveryIds != nullptr && deploymentCompleteData.cDriverRecoveryIds != 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::NotifyResult(
        COSInstaller *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        wchar_t *a8,
        wchar_t *a9)
{
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdx
  const struct _GUID *v15; // rdx
  unsigned int Data1; // ebx
  __int64 v17; // rax
  const wchar_t *v18; // rcx
  __int64 v19; // rax
  wchar_t **v21; // [rsp+20h] [rbp-E0h]
  __int128 v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  wchar_t **v25; // [rsp+78h] [rbp-88h]
  int *v26; // [rsp+80h] [rbp-80h]
  char v27; // [rsp+88h] [rbp-78h]
  char v28[80]; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v30[28]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v29 = 0;
  memset(v30, 0, 0xD8u);
  v24 = 0;
  WUTrace(0, 0, 4096, 4, 0, L"Enter deployment handler NotifyResult");
  if ( !a2 )
  {
    v12 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80004003LL,
      (int)v21);
    return (unsigned int)v12;
  }
  v25 = v30;
  v26 = &v29;
  v27 = 1;
  LODWORD(v30[0]) = 2;
  HIDWORD(v30[4]) = a5;
  LODWORD(v30[2]) = a6;
  if ( a5 == -2145116152 )
  {
    LODWORD(v30[1]) = 2;
  }
  else if ( a5 )
  {
    LODWORD(v30[1]) = 0;
  }
  else
  {
    LODWORD(v30[1]) = a6 != 0 ? 3 : 1;
    if ( SysStringLen(*(BSTR *)(a3 + 24)) )
      DuplicateString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 24), &v30[19]);
    if ( a6 )
    {
      v13 = *(_QWORD *)(a3 + 56);
      if ( !a9 )
      {
        v12 = -2147467261;
        v14 = 1383;
        goto LABEL_23;
      }
      HIDWORD(v30[2]) = a7;
      LODWORD(v30[3]) = a7 == 2;
      v15 = (const struct _GUID *)(v13 + 4);
      Data1 = v15[1].Data1;
      v17 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v28, v15);
      v18 = L"does";
      if ( a7 == 1 )
        v18 = L"does not";
      WUTrace(0, 0, 4096, 4, 0, L"Update with ID: %ws.%d %ws require explicit commit call", v17, Data1, v18);
      v12 = COSInstaller::PopulateReportingCookieData(a1, (const struct tagSusDeployData *)a3, a9, a8, &v30[7]);
      v29 = v12;
      if ( v12 < 0 )
      {
        v14 = 1401;
        goto LABEL_23;
      }
    }
  }
  if ( v30[20] )
  {
    if ( !LODWORD(v30[21]) )
    {
LABEL_20:
      WUTrace(
        "COSInstaller::NotifyResult",
        1416,
        32,
        3,
        0,
        L"TelemetryAssert (%ws): %ws",
        L"(deploymentCompleteData.rgpszDriverRecoveryIds == nullptr && deploymentCompleteData.cDriverRecoveryIds == 0) || "
         "(deploymentCompleteData.rgpszDriverRecoveryIds != nullptr && deploymentCompleteData.cDriverRecoveryIds != 0)",
        L"Failed");
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
    }
  }
  else if ( LODWORD(v30[21]) )
  {
    goto LABEL_20;
  }
  v19 = *(_QWORD *)(a3 + 56);
  v22 = *(_OWORD *)(v19 + 4);
  v23 = *(_DWORD *)(v19 + 20);
  v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, wchar_t **, __int64))(*(_QWORD *)a2 + 24LL))(
          a2,
          &v22,
          v30,
          a3 + 32);
  v29 = v12;
  if ( v12 >= 0 )
  {
    v12 = 0;
    goto LABEL_25;
  }
  v14 = 1422;
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)(unsigned int)v12,
    (int)v21);
LABEL_25:
  if ( LODWORD(v30[0]) == 2 )
    ResetDeploymentComplete((struct tagUpdateDeploymentCompleteNotifyType *)&v30[1]);
  LODWORD(v21) = v29;
  WUTrace(0, 0, 4096, 4, v21, L"Leave deployment handler NotifyResult");
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003f448  mov     [rsp-8+arg_18], rbx
0x18003f44d  push    rbp
0x18003f44e  push    rsi
0x18003f44f  push    rdi
0x18003f450  push    r12
0x18003f452  push    r13
0x18003f454  push    r14
0x18003f456  push    r15
0x18003f458  lea     rbp, [rsp-0E0h]
0x18003f460  sub     rsp, 1E0h
0x18003f467  mov     rax, cs:__security_cookie
0x18003f46e  xor     rax, rsp
0x18003f471  mov     [rbp+110h+var_40], rax
0x18003f478  mov     rdi, r8
0x18003f47b  mov     rsi, rdx
0x18003f47e  mov     r12, rcx
0x18003f481  mov     r15d, [rbp+110h+arg_30]
0x18003f488  mov     r13, [rbp+110h+arg_38]
0x18003f48f  mov     r14, [rbp+110h+arg_40]
0x18003f496  xor     ebx, ebx
0x18003f498  mov     [rbp+110h+var_130], ebx
0x18003f49b  xor     edx, edx; Val
0x18003f49d  mov     r8d, 0D8h; Size
0x18003f4a3  lea     rcx, [rbp+110h+var_120]; void *
0x18003f4a7  call    memset
0x18003f4ac  mov     [rsp+210h+var_1A0], rbx
0x18003f4b1  lea     rax, aEnterDeploymen_0; "Enter deployment handler NotifyResult"
0x18003f4b8  mov     [rsp+210h+var_1E8], rax
0x18003f4bd  mov     [rsp+210h+var_1F0], rbx; int
0x18003f4c2  xor     edx, edx
0x18003f4c4  xor     ecx, ecx
0x18003f4c6  lea     r9d, [rbx+4]
0x18003f4ca  mov     r8d, 1000h
0x18003f4d0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f4d5  test    rsi, rsi
0x18003f4d8  jnz     short loc_18003F4FF
0x18003f4da  mov     rcx, [rbp+118h]; this
0x18003f4e1  mov     ebx, 80004003h
0x18003f4e6  mov     r9d, ebx; char *
0x18003f4e9  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003f4f0  mov     edx, 53Eh; void *
0x18003f4f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f4fa  jmp     loc_18003F72E
0x18003f4ff  lea     rax, [rbp+110h+var_120]
0x18003f503  mov     [rsp+210h+var_198], rax
0x18003f508  lea     rax, [rbp+110h+var_130]
0x18003f50c  mov     [rbp+110h+var_190], rax
0x18003f510  mov     [rbp+110h+var_188], 1
0x18003f514  mov     edx, 2
0x18003f519  mov     [rbp+110h+var_120], edx
0x18003f51c  mov     eax, [rbp+110h+arg_20]
0x18003f522  mov     [rbp+110h+var_FC], eax
0x18003f525  mov     ebx, [rbp+110h+arg_28]
0x18003f52b  mov     [rbp+110h+var_110], ebx
0x18003f52e  cmp     eax, 80242008h
0x18003f533  jz      loc_18003F62D
0x18003f539  test    eax, eax
0x18003f53b  jz      short loc_18003F549
0x18003f53d  mov     [rbp+110h+var_118], 0
0x18003f544  jmp     loc_18003F630
0x18003f549  mov     eax, ebx
0x18003f54b  neg     eax
0x18003f54d  sbb     ecx, ecx
0x18003f54f  and     ecx, edx
0x18003f551  inc     ecx
0x18003f553  mov     [rbp+110h+var_118], ecx
0x18003f556  mov     rcx, [rdi+18h]; pbstr
0x18003f55a  call    cs:__imp_SysStringLen
0x18003f560  test    eax, eax
0x18003f562  jz      short loc_18003F574
0x18003f564  lea     rdx, [rbp+110h+var_88]
0x18003f56b  mov     rcx, [rdi+18h]
0x18003f56f  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18003f574  test    ebx, ebx
0x18003f576  jz      loc_18003F630
0x18003f57c  mov     rdx, [rdi+38h]
0x18003f580  test    r14, r14
0x18003f583  jnz     short loc_18003F594
0x18003f585  mov     ebx, 80004003h
0x18003f58a  mov     edx, 567h
0x18003f58f  jmp     loc_18003F6DE
0x18003f594  mov     [rbp+110h+var_10C], r15d
0x18003f598  xor     eax, eax
0x18003f59a  cmp     r15d, 2
0x18003f59e  setz    al
0x18003f5a1  mov     [rbp+110h+var_108], eax
0x18003f5a4  add     rdx, 4; struct _GUID *
0x18003f5a8  mov     ebx, [rdx+10h]
0x18003f5ab  lea     rcx, [rbp+110h+var_180]; this
0x18003f5af  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003f5b4  lea     rdx, aDoesNot; "does not"
0x18003f5bb  lea     rcx, aDoes; "does"
0x18003f5c2  cmp     r15d, 1
0x18003f5c6  cmovz   rcx, rdx
0x18003f5ca  mov     [rsp+210h+var_1D0], rcx
0x18003f5cf  mov     dword ptr [rsp+210h+var_1D8], ebx
0x18003f5d3  mov     [rsp+210h+var_1E0], rax
0x18003f5d8  lea     rax, aUpdateWithIdWs; "Update with ID: %ws.%d %ws require expl"...
0x18003f5df  mov     [rsp+210h+var_1E8], rax
0x18003f5e4  mov     [rsp+210h+var_1F0], 0
0x18003f5ed  xor     edx, edx
0x18003f5ef  xor     ecx, ecx
0x18003f5f1  lea     r9d, [rdx+4]
0x18003f5f5  mov     r8d, 1000h
0x18003f5fb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f600  lea     rax, [rbp+110h+var_E8]
0x18003f604  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x18003f609  mov     r9, r13; wchar_t *
0x18003f60c  mov     r8, r14; wchar_t *
0x18003f60f  mov     rdx, rdi; struct tagSusDeployData *
0x18003f612  mov     rcx, r12; this
0x18003f615  call    ?PopulateReportingCookieData@COSInstaller@@AEAAJAEBUtagSusDeployData@@PEB_W1PEAPEA_W@Z; COSInstaller::PopulateReportingCookieData(tagSusDeployData const &,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003f61a  mov     ebx, eax
0x18003f61c  mov     [rbp+110h+var_130], eax
0x18003f61f  test    eax, eax
0x18003f621  jns     short loc_18003F630
0x18003f623  mov     edx, 579h
0x18003f628  jmp     loc_18003F6DE
0x18003f62d  mov     [rbp+110h+var_118], edx
0x18003f630  cmp     [rbp+110h+var_80], 0
0x18003f638  jnz     short loc_18003F645
0x18003f63a  cmp     [rbp+110h+var_78], 0
0x18003f641  jz      short loc_18003F6A0
0x18003f643  jmp     short loc_18003F64E
0x18003f645  cmp     [rbp+110h+var_78], 0
0x18003f64c  jnz     short loc_18003F6A0
0x18003f64e  lea     rax, aFailed; "Failed"
0x18003f655  mov     [rsp+210h+var_1D8], rax
0x18003f65a  lea     rax, aDeploymentcomp; "(deploymentCompleteData.rgpszDriverReco"...
0x18003f661  mov     [rsp+210h+var_1E0], rax
0x18003f666  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x18003f66d  mov     [rsp+210h+var_1E8], rax
0x18003f672  mov     [rsp+210h+var_1F0], 0; int
0x18003f67b  mov     edx, 588h
0x18003f680  mov     r9d, 3
0x18003f686  lea     r8d, [r9+1Dh]
0x18003f68a  lea     rcx, aCosinstallerNo; "COSInstaller::NotifyResult"
0x18003f691  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f696  or      ecx, 0FFFFFFFFh; unsigned int
0x18003f699  mov     edx, ecx; unsigned int
0x18003f69b  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x18003f6a0  mov     rax, [rdi+38h]
0x18003f6a4  movups  xmm0, xmmword ptr [rax+4]
0x18003f6a8  movaps  [rsp+210h+var_1C0], xmm0
0x18003f6ad  mov     eax, [rax+14h]
0x18003f6b0  mov     [rsp+210h+var_1B0], eax
0x18003f6b4  lea     r9, [rdi+20h]
0x18003f6b8  mov     rax, [rsi]
0x18003f6bb  lea     r8, [rbp+110h+var_120]
0x18003f6bf  lea     rdx, [rsp+210h+var_1C0]
0x18003f6c4  mov     rcx, rsi
0x18003f6c7  mov     rax, [rax+18h]
0x18003f6cb  call    _guard_dispatch_icall
0x18003f6d0  mov     ebx, eax
0x18003f6d2  mov     [rbp+110h+var_130], eax
0x18003f6d5  test    eax, eax
0x18003f6d7  jns     short loc_18003F6F6
0x18003f6d9  mov     edx, 58Eh; void *
0x18003f6de  mov     rcx, [rbp+118h]; this
0x18003f6e5  mov     r9d, ebx; char *
0x18003f6e8  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003f6ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f6f4  jmp     short loc_18003F6F8
0x18003f6f6  xor     ebx, ebx
0x18003f6f8  cmp     [rbp+110h+var_120], 2
0x18003f6fc  jnz     short loc_18003F707
0x18003f6fe  lea     rcx, [rbp+110h+var_118]; struct tagUpdateDeploymentCompleteNotifyType *
0x18003f702  call    ?ResetDeploymentComplete@@YAXPEAUtagUpdateDeploymentCompleteNotifyType@@@Z; ResetDeploymentComplete(tagUpdateDeploymentCompleteNotifyType *)
0x18003f707  lea     rax, aLeaveDeploymen; "Leave deployment handler NotifyResult"
0x18003f70e  mov     [rsp+210h+var_1E8], rax
0x18003f713  mov     ecx, [rbp+110h+var_130]
0x18003f716  mov     dword ptr [rsp+210h+var_1F0], ecx
0x18003f71a  xor     edx, edx
0x18003f71c  xor     ecx, ecx
0x18003f71e  lea     r9d, [rdx+4]
0x18003f722  mov     r8d, 1000h
0x18003f728  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f72d  nop
0x18003f72e  mov     eax, ebx
0x18003f730  mov     rcx, [rbp+110h+var_40]
0x18003f737  xor     rcx, rsp; StackCookie
0x18003f73a  call    __security_check_cookie
0x18003f73f  mov     rbx, [rsp+210h+arg_18]
0x18003f747  add     rsp, 1E0h
0x18003f74e  pop     r15
0x18003f750  pop     r14
0x18003f752  pop     r13
0x18003f754  pop     r12
0x18003f756  pop     rdi
0x18003f757  pop     rsi
0x18003f758  pop     rbp
0x18003f759  retn
```
