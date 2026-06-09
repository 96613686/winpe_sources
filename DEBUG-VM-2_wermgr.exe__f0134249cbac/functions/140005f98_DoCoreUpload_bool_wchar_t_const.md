# DoCoreUpload(bool,wchar_t const * *)

- ea: `0x140005f98`
- end: `0x140006596`
- name: `?DoCoreUpload@@YAJ_NPEAPEB_W@Z`
- size: `1534`
- prototype: `__int64 __fastcall(bool, const wchar_t **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000e49c`

## callees

- `0x1400013f0`
- `0x14000162c`
- `0x140003200`
- `0x1400058ec`
- `0x140005f98`
- `0x140007554`
- `0x140007684`
- `0x140008c40`
- `0x14000a070`
- `0x14000e340`
- `0x14001acd8`
- `0x14001ad44`
- `0x14001aec4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000622c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000652d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000622c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000652d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006566`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006011`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006011`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000613a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006216`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400064be`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006517`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006550`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000613a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006216`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400064be`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006517`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006550`
- `wer!WerpDestroyWerString` at `0x1400061fe`
- `wer!WerpDestroyWerString` at `0x1400063fe`
- `wer!WerpDestroyWerString` at `0x1400064a6`
- `wer!WerpDestroyWerString` at `0x1400064ff`
- `wer!WerpDestroyWerString` at `0x1400061fe`
- `wer!WerpDestroyWerString` at `0x1400063fe`
- `wer!WerpDestroyWerString` at `0x1400064a6`
- `wer!WerpDestroyWerString` at `0x1400064ff`
- `wer!WerpCloseStore` at `0x14000620f`
- `wer!WerpCloseStore` at `0x1400064b7`
- `wer!WerpCloseStore` at `0x140006510`
- `wer!WerpCloseStore` at `0x140006549`
- `wer!WerpCloseStore` at `0x14000620f`
- `wer!WerpCloseStore` at `0x1400064b7`
- `wer!WerpCloseStore` at `0x140006510`
- `wer!WerpCloseStore` at `0x140006549`
- `wer!WerpSubmitReportFromStore` at `0x1400062c2`
- `wer!WerpSubmitReportFromStore` at `0x1400062c2`
- `wer!WerpGetWerStringData` at `0x140006253`
- `wer!WerpGetWerStringData` at `0x140006253`
- `wer!WerpEnumerateStoreNext` at `0x1400061c8`
- `wer!WerpEnumerateStoreNext` at `0x14000640e`
- `wer!WerpEnumerateStoreNext` at `0x1400061c8`
- `wer!WerpEnumerateStoreNext` at `0x14000640e`
- `wer!WerpEnumerateStoreStart` at `0x140006195`
- `wer!WerpEnumerateStoreStart` at `0x140006195`
- `wer!WerpOpenMachineQueue` at `0x140006177`
- `wer!WerpOpenMachineQueue` at `0x140006177`
- `wer!WerpIsOnBattery` at `0x140006055`
- `wer!WerpIsOnBattery` at `0x140006055`

## string_xrefs

- `0x14000653a`: `Failed to open machine store`
- `0x1400064e1`: `Unexpected report with NULL report path`
- `0x1400063c6`: `Upload completed for report %ws. (SubmitResult = %d)`
- `0x140006488`: `Core uploader complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoCoreUpload(char a1, const wchar_t **a2)
{
  HRESULT v4; // eax
  int GlobalLockForUploadingReports; // ebx
  unsigned int IsNetworkConnected; // ebx
  int IsNetworkRestricted; // r14d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  HANDLE v11; // rcx
  bool v12; // cc
  unsigned int v13; // r15d
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // esi
  __int64 *v17; // rcx
  unsigned int v19; // ebx
  const char *WerStringData; // rax
  char *v21; // rsi
  int v22; // r14d
  const wchar_t *ReportIdFromReportPath; // r12
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rax
  int v28; // eax
  wil::details *v29; // [rsp+20h] [rbp-E0h]
  wil::details *v30; // [rsp+20h] [rbp-E0h]
  wil::details *v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+28h] [rbp-D8h]
  char *v33; // [rsp+30h] [rbp-D0h]
  __int64 v34; // [rsp+38h] [rbp-C8h]
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int ReportAgeInSeconds; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v43; // [rsp+88h] [rbp-78h] BYREF
  HRESULT v44; // [rsp+90h] [rbp-70h]
  char v45[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  unsigned int *v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  int *v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+E8h] [rbp-18h]
  const wchar_t **v52; // [rsp+F0h] [rbp-10h]
  __int64 v53; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+138h] [rbp+38h]

  v42 = 4;
  hObject = 0;
  LODWORD(v29) = 0x80000000;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x3DD,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "DoCoreUpload",
    v29,
    (int)"Core uploader begin",
    v33);
  v4 = CoInitializeEx(0, 0);
  GlobalLockForUploadingReports = v4;
  v44 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v30) = v4;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x3E0,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "DoCoreUpload",
      v30,
      v32);
    return (unsigned int)GlobalLockForUploadingReports;
  }
  IsNetworkConnected = UtilIsNetworkConnected();
  IsNetworkRestricted = UtilIsNetworkRestricted();
  v9 = (unsigned int)WerpIsOnBattery();
  v10 = 0x400000000000LL;
  if ( (unsigned int)dword_14002C000 > 5 )
  {
    v8 = qword_14002C018;
    if ( (qword_14002C010 & 0x400000000000LL) != 0 && (qword_14002C018 & 0x400000000000LL) == qword_14002C018 )
    {
      LODWORD(v43) = v9;
      v38 = IsNetworkRestricted;
      ReportAgeInSeconds = IsNetworkConnected;
      v40 = 0x1000000;
      v52 = &v43;
      v53 = 4;
      v50 = &v38;
      v51 = 4;
      v48 = &ReportAgeInSeconds;
      v49 = 4;
      v46 = &v40;
      v47 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, byte_140025ED3, 0, 0, 6, v45);
    }
  }
  GlobalLockForUploadingReports = GetGlobalLockForUploadingReports(&hObject, v8, v9, v10);
  if ( GlobalLockForUploadingReports < 0 )
  {
    *a2 = L"Another instance of wermgr is uploading reports";
    CoUninitialize();
    v11 = hObject;
    v12 = (unsigned __int64)hObject + 1 <= 1;
LABEL_63:
    if ( !v12 )
      CloseHandle(v11);
    return (unsigned int)GlobalLockForUploadingReports;
  }
  v13 = a1 != 0 ? -2147434496 : 0x80000000;
  v36 = 0;
  GlobalLockForUploadingReports = WerpOpenMachineQueue(&v36);
  v14 = v36;
  if ( GlobalLockForUploadingReports < 0 || !v36 )
  {
    *a2 = L"Failed to open machine store";
    goto LABEL_60;
  }
  GlobalLockForUploadingReports = WerpEnumerateStoreStart(v36);
  if ( GlobalLockForUploadingReports < 0 )
  {
    *a2 = L"WerpEnumerateStoreStart failed";
    v14 = v36;
LABEL_60:
    if ( v14 )
      WerpCloseStore(v14);
    CoUninitialize();
    v11 = hObject;
    v12 = (unsigned __int64)hObject + 1 <= 1;
    goto LABEL_63;
  }
  v35 = 0;
  v15 = WerpEnumerateStoreNext(v36, &v35);
  v16 = v15;
  if ( ((v15 + 0x80000000) & 0x80000000) == 0 && v15 != -2147024878 )
  {
    *a2 = L"WerpEnumerateStoreNext failed";
    if ( !v35 )
    {
LABEL_18:
      if ( v36 )
        WerpCloseStore(v36);
      CoUninitialize();
      if ( (unsigned __int64)hObject + 1 > 1 )
        CloseHandle(hObject);
      return v16;
    }
    v40 = v35;
    v17 = &v40;
LABEL_17:
    WerpDestroyWerString(v17);
    goto LABEL_18;
  }
  v19 = 0;
  if ( !v15 && v35 )
  {
    while ( 1 )
    {
      WerStringData = (const char *)WerpGetWerStringData(v35);
      v21 = (char *)WerStringData;
      if ( !WerStringData )
      {
        *a2 = L"Unexpected report with NULL report path";
        if ( v35 )
        {
          v41 = v35;
          WerpDestroyWerString(&v41);
        }
        if ( v36 )
          WerpCloseStore(v36);
        CoUninitialize();
        if ( (unsigned __int64)hObject + 1 > 1 )
          CloseHandle(hObject);
        return 2147942413LL;
      }
      LODWORD(v30) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x433,
        (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
        "DoCoreUpload",
        v30,
        (int)"Uploading report %ws",
        WerStringData);
      v22 = WerpSubmitReportFromStore(v36, v21, 0, 0, 0, v13, &v42);
      if ( v22 >= 0 )
      {
        LODWORD(v34) = v42;
        LODWORD(v31) = 0x80000000;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x45A,
          (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
          "DoCoreUpload",
          v31,
          (int)"Upload completed for report %ws. (SubmitResult = %d)",
          v21,
          v34);
      }
      else
      {
        LODWORD(v31) = v22;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x43E,
          (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
          "DoCoreUpload",
          v31,
          (int)"Upload failed for report %ws",
          v21);
        ReportIdFromReportPath = UtilGetReportIdFromReportPath((const wchar_t *const)v21);
        if ( (unsigned int)dword_14002C000 > 5
          && (qword_14002C010 & 0x400000000000LL) != 0
          && (qword_14002C018 & 0x400000000000LL) == qword_14002C018 )
        {
          ReportAgeInSeconds = GetReportAgeInSeconds((const wchar_t *)v21);
          v40 = (__int64)v21;
          v43 = ReportIdFromReportPath;
          v38 = v22;
          v41 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v24,
            (unsigned int)byte_140025E6D,
            v25,
            v26,
            (__int64)&v41,
            (__int64)&v38,
            (__int64)&v43,
            (__int64)&v40,
            (__int64)&ReportAgeInSeconds);
        }
        if ( v22 == -2147023504 )
          DeleteCorruptedReportFromStore((wchar_t *)v21);
      }
      v27 = v35;
      v35 = 0;
      if ( v27 )
      {
        v40 = v27;
        WerpDestroyWerString(&v40);
      }
      v28 = WerpEnumerateStoreNext(v36, &v35);
      v16 = v28;
      if ( v28 == -2147024878 )
      {
        ++v19;
        goto LABEL_42;
      }
      if ( v28 < 0 )
        break;
      ++v19;
    }
    *a2 = L"WerpEnumerateStoreNext2 failed";
    if ( !v35 )
      goto LABEL_18;
    v41 = v35;
    v17 = &v41;
    goto LABEL_17;
  }
LABEL_42:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids, v19);
  *a2 = L"Core uploader complete";
  if ( v35 )
  {
    v41 = v35;
    WerpDestroyWerString(&v41);
  }
  if ( v36 )
    WerpCloseStore(v36);
  CoUninitialize();
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x140005f98  mov     [rsp-8+arg_0], rbx
0x140005f9d  mov     [rsp-8+arg_10], rsi
0x140005fa2  push    rbp
0x140005fa3  push    rdi
0x140005fa4  push    r12
0x140005fa6  push    r14
0x140005fa8  push    r15
0x140005faa  lea     rbp, [rsp-10h]
0x140005faf  sub     rsp, 110h
0x140005fb6  mov     rax, cs:__security_cookie
0x140005fbd  xor     rax, rsp
0x140005fc0  mov     [rbp+30h+var_30], rax
0x140005fc4  mov     rdi, rdx
0x140005fc7  mov     sil, cl
0x140005fca  mov     r12d, 4
0x140005fd0  mov     [rbp+30h+var_B0], r12d
0x140005fd4  mov     [rsp+130h+hObject], 0
0x140005fdd  mov     rcx, [rbp+38h]; this
0x140005fe1  lea     rax, aCoreUploaderBe; "Core uploader begin"
0x140005fe8  mov     qword ptr [rsp+130h+var_108], rax; int
0x140005fed  mov     dword ptr [rsp+130h+var_110], 80000000h; wil::details *
0x140005ff5  lea     r9, aDocoreupload; "DoCoreUpload"
0x140005ffc  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140006003  mov     edx, 3DDh; void *
0x140006008  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000600d  xor     edx, edx; dwCoInit
0x14000600f  xor     ecx, ecx; pvReserved
0x140006011  call    cs:__imp_CoInitializeEx
0x140006017  mov     ebx, eax
0x140006019  mov     [rbp+30h+var_A0], eax
0x14000601c  test    eax, eax
0x14000601e  jns     short loc_140006046
0x140006020  mov     rcx, [rbp+38h]; this
0x140006024  mov     dword ptr [rsp+130h+var_110], eax; wil::details *
0x140006028  lea     r9, aDocoreupload; "DoCoreUpload"
0x14000602f  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140006036  mov     edx, 3E0h; void *
0x14000603b  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140006040  nop
0x140006041  jmp     loc_14000656C
0x140006046  call    ?UtilIsNetworkConnected@@YAHXZ; UtilIsNetworkConnected(void)
0x14000604b  mov     ebx, eax
0x14000604d  call    ?UtilIsNetworkRestricted@@YAHXZ; UtilIsNetworkRestricted(void)
0x140006052  mov     r14d, eax
0x140006055  call    cs:__imp_WerpIsOnBattery
0x14000605b  mov     r8d, eax
0x14000605e  mov     ecx, cs:dword_14002C000
0x140006064  mov     r9, 400000000000h
0x14000606e  cmp     ecx, 5
0x140006071  jbe     loc_140006120
0x140006077  mov     rdx, cs:qword_14002C018
0x14000607e  mov     rcx, cs:qword_14002C010
0x140006085  test    r9, rcx
0x140006088  jz      loc_140006120
0x14000608e  mov     rax, rdx
0x140006091  and     rax, r9
0x140006094  cmp     rax, rdx
0x140006097  jnz     loc_140006120
0x14000609d  mov     dword ptr [rbp+30h+var_A8], r8d
0x1400060a1  mov     [rsp+130h+var_C8], r14d
0x1400060a6  mov     [rsp+130h+var_C4], ebx
0x1400060aa  mov     [rsp+130h+var_C0], 1000000h
0x1400060b3  lea     rax, [rbp+30h+var_A8]
0x1400060b7  mov     [rbp+30h+var_40], rax
0x1400060bb  mov     [rbp+30h+var_38], 4
0x1400060c3  lea     rax, [rsp+130h+var_C8]
0x1400060c8  mov     [rbp+30h+var_50], rax
0x1400060cc  mov     [rbp+30h+var_48], 4
0x1400060d4  lea     rax, [rsp+130h+var_C4]
0x1400060d9  mov     [rbp+30h+var_60], rax
0x1400060dd  mov     [rbp+30h+var_58], 4
0x1400060e5  lea     rax, [rsp+130h+var_C0]
0x1400060ea  mov     [rbp+30h+var_70], rax
0x1400060ee  mov     [rbp+30h+var_68], 8
0x1400060f6  lea     rax, [rbp+30h+var_90]
0x1400060fa  mov     qword ptr [rsp+130h+var_108], rax
0x1400060ff  mov     dword ptr [rsp+130h+var_110], 6
0x140006107  xor     r9d, r9d
0x14000610a  xor     r8d, r8d
0x14000610d  lea     rdx, byte_140025ED3
0x140006114  lea     rcx, dword_14002C000
0x14000611b  call    _tlgWriteTransfer_EventWriteTransfer
0x140006120  lea     rcx, [rsp+130h+hObject]
0x140006125  call    GetGlobalLockForUploadingReports
0x14000612a  mov     ebx, eax
0x14000612c  test    eax, eax
0x14000612e  jns     short loc_140006153
0x140006130  lea     rax, aAnotherInstanc; "Another instance of wermgr is uploading"...
0x140006137  mov     [rdi], rax
0x14000613a  call    cs:__imp_CoUninitialize
0x140006140  nop
0x140006141  mov     rcx, [rsp+130h+hObject]
0x140006146  lea     rdx, [rcx+1]
0x14000614a  cmp     rdx, 1
0x14000614e  jmp     loc_140006564
0x140006153  neg     sil
0x140006156  sbb     r15d, r15d
0x140006159  and     r15d, 0C000h
0x140006160  mov     r14d, 80000000h
0x140006166  add     r15d, r14d
0x140006169  mov     [rsp+130h+var_D8], 0
0x140006172  lea     rcx, [rsp+130h+var_D8]
0x140006177  call    cs:__imp_WerpOpenMachineQueue
0x14000617d  mov     ebx, eax
0x14000617f  mov     rcx, [rsp+130h+var_D8]
0x140006184  test    eax, eax
0x140006186  js      loc_14000653A
0x14000618c  test    rcx, rcx
0x14000618f  jz      loc_14000653A
0x140006195  call    cs:__imp_WerpEnumerateStoreStart
0x14000619b  mov     ebx, eax
0x14000619d  test    eax, eax
0x14000619f  jns     short loc_1400061B5
0x1400061a1  lea     rax, aWerpenumerates_1; "WerpEnumerateStoreStart failed"
0x1400061a8  mov     [rdi], rax
0x1400061ab  mov     rcx, [rsp+130h+var_D8]
0x1400061b0  jmp     loc_140006544
0x1400061b5  mov     [rsp+130h+var_E0], 0
0x1400061be  lea     rdx, [rsp+130h+var_E0]
0x1400061c3  mov     rcx, [rsp+130h+var_D8]
0x1400061c8  call    cs:__imp_WerpEnumerateStoreNext
0x1400061ce  mov     esi, eax
0x1400061d0  lea     ecx, [rax+r14]
0x1400061d4  test    r14d, ecx
0x1400061d7  jnz     short loc_140006239
0x1400061d9  cmp     eax, 80070012h
0x1400061de  jz      short loc_140006239
0x1400061e0  lea     rax, aWerpenumerates_0; "WerpEnumerateStoreNext failed"
0x1400061e7  mov     [rdi], rax
0x1400061ea  mov     rax, [rsp+130h+var_E0]
0x1400061ef  test    rax, rax
0x1400061f2  jz      short loc_140006205
0x1400061f4  mov     [rsp+130h+var_C0], rax
0x1400061f9  lea     rcx, [rsp+130h+var_C0]
0x1400061fe  call    cs:__imp_WerpDestroyWerString
0x140006204  nop
0x140006205  mov     rcx, [rsp+130h+var_D8]
0x14000620a  test    rcx, rcx
0x14000620d  jz      short loc_140006216
0x14000620f  call    cs:__imp_WerpCloseStore
0x140006215  nop
0x140006216  call    cs:__imp_CoUninitialize
0x14000621c  nop
0x14000621d  mov     rcx, [rsp+130h+hObject]; hObject
0x140006222  lea     rax, [rcx+1]
0x140006226  cmp     rax, 1
0x14000622a  jbe     short loc_140006232
0x14000622c  call    cs:__imp_CloseHandle
0x140006232  mov     eax, esi
0x140006234  jmp     loc_14000656E
0x140006239  xor     ebx, ebx
0x14000623b  test    esi, esi
0x14000623d  jnz     loc_140006457
0x140006243  cmp     [rsp+130h+var_E0], rbx
0x140006248  jz      loc_140006457
0x14000624e  mov     rcx, [rsp+130h+var_E0]
0x140006253  call    cs:__imp_WerpGetWerStringData
0x140006259  mov     rsi, rax
0x14000625c  test    rax, rax
0x14000625f  jz      loc_1400064E1
0x140006265  mov     rcx, [rbp+38h]; this
0x140006269  mov     [rsp+130h+var_100], rax; char *
0x14000626e  lea     rax, aUploadingRepor; "Uploading report %ws"
0x140006275  mov     qword ptr [rsp+130h+var_108], rax; int
0x14000627a  mov     r12d, 80000000h
0x140006280  mov     dword ptr [rsp+130h+var_110], r12d; wil::details *
0x140006285  lea     r9, aDocoreupload; "DoCoreUpload"
0x14000628c  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140006293  mov     edx, 433h; void *
0x140006298  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000629d  lea     rax, [rbp+30h+var_B0]
0x1400062a1  mov     [rsp+130h+var_100], rax
0x1400062a6  mov     [rsp+130h+var_108], r15d
0x1400062ab  mov     [rsp+130h+var_110], 0
0x1400062b4  xor     r9d, r9d
0x1400062b7  xor     r8d, r8d
0x1400062ba  mov     rdx, rsi
0x1400062bd  mov     rcx, [rsp+130h+var_D8]
0x1400062c2  call    cs:__imp_WerpSubmitReportFromStore
0x1400062c8  mov     r14d, eax
0x1400062cb  mov     rcx, [rbp+38h]; this
0x1400062cf  lea     r9, aDocoreupload; "DoCoreUpload"
0x1400062d6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400062dd  test    eax, eax
0x1400062df  jns     loc_1400063BA
0x1400062e5  mov     [rsp+130h+var_100], rsi; char *
0x1400062ea  lea     rax, aUploadFailedFo; "Upload failed for report %ws"
0x1400062f1  mov     qword ptr [rsp+130h+var_108], rax; int
0x1400062f6  mov     dword ptr [rsp+130h+var_110], r14d; wil::details *
0x1400062fb  mov     edx, 43Eh; void *
0x140006300  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140006305  mov     rcx, rsi; wchar_t *
0x140006308  call    ?UtilGetReportIdFromReportPath@@YAPEB_WQEB_W@Z; UtilGetReportIdFromReportPath(wchar_t const * const)
0x14000630d  mov     r12, rax
0x140006310  mov     ecx, cs:dword_14002C000
0x140006316  cmp     ecx, 5
0x140006319  jbe     loc_1400063A7
0x14000631f  mov     rdx, cs:qword_14002C018
0x140006326  mov     rcx, cs:qword_14002C010
0x14000632d  mov     rax, 400000000000h
0x140006337  test    rax, rcx
0x14000633a  jz      short loc_1400063A7
0x14000633c  mov     rcx, rdx
0x14000633f  and     rcx, rax
0x140006342  cmp     rcx, rdx
0x140006345  jnz     short loc_1400063A7
0x140006347  mov     rcx, rsi; wchar_t *
0x14000634a  call    ?GetReportAgeInSeconds@@YAKPEB_W@Z; GetReportAgeInSeconds(wchar_t const *)
0x14000634f  mov     [rsp+130h+var_C4], eax
0x140006353  mov     [rsp+130h+var_C0], rsi
0x140006358  mov     [rbp+30h+var_A8], r12
0x14000635c  mov     [rsp+130h+var_C8], r14d
0x140006361  mov     [rsp+130h+var_B8], 1000000h
0x14000636a  lea     rax, [rsp+130h+var_C4]
0x14000636f  mov     [rsp+130h+var_F0], rax
0x140006374  lea     rax, [rsp+130h+var_C0]
0x140006379  mov     [rsp+130h+var_F8], rax
0x14000637e  lea     rax, [rbp+30h+var_A8]
0x140006382  mov     [rsp+130h+var_100], rax
0x140006387  lea     rax, [rsp+130h+var_C8]
0x14000638c  mov     qword ptr [rsp+130h+var_108], rax
0x140006391  lea     rax, [rsp+130h+var_B8]
0x140006396  mov     [rsp+130h+var_110], rax
0x14000639b  lea     rdx, byte_140025E6D
0x1400063a2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1400063a7  cmp     r14d, 80070570h
0x1400063ae  jnz     short loc_1400063E1
0x1400063b0  mov     rcx, rsi; wchar_t *
0x1400063b3  call    ?DeleteCorruptedReportFromStore@@YAJPEB_W@Z; DeleteCorruptedReportFromStore(wchar_t const *)
0x1400063b8  jmp     short loc_1400063E1
0x1400063ba  mov     eax, [rbp+30h+var_B0]
0x1400063bd  mov     dword ptr [rsp+130h+var_F8], eax
0x1400063c1  mov     [rsp+130h+var_100], rsi; char *
0x1400063c6  lea     rax, aUploadComplete; "Upload completed for report %ws. (Submi"...
0x1400063cd  mov     qword ptr [rsp+130h+var_108], rax; int
0x1400063d2  mov     dword ptr [rsp+130h+var_110], r12d; wil::details *
0x1400063d7  mov     edx, 45Ah; void *
0x1400063dc  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400063e1  mov     rax, [rsp+130h+var_E0]
0x1400063e6  mov     [rsp+130h+var_E0], 0
0x1400063ef  test    rax, rax
0x1400063f2  jz      short loc_140006404
0x1400063f4  mov     [rsp+130h+var_C0], rax
0x1400063f9  lea     rcx, [rsp+130h+var_C0]
0x1400063fe  call    cs:__imp_WerpDestroyWerString
0x140006404  lea     rdx, [rsp+130h+var_E0]
0x140006409  mov     rcx, [rsp+130h+var_D8]
0x14000640e  call    cs:__imp_WerpEnumerateStoreNext
0x140006414  mov     esi, eax
0x140006416  cmp     eax, 80070012h
0x14000641b  jz      short loc_14000644F
0x14000641d  test    eax, eax
0x14000641f  js      short loc_140006428
0x140006421  inc     ebx
0x140006423  jmp     loc_14000624E
0x140006428  lea     rax, aWerpenumerates; "WerpEnumerateStoreNext2 failed"
0x14000642f  mov     [rdi], rax
0x140006432  mov     rax, [rsp+130h+var_E0]
0x140006437  test    rax, rax
0x14000643a  jz      loc_140006205
0x140006440  mov     [rsp+130h+var_B8], rax
0x140006445  lea     rcx, [rsp+130h+var_B8]
0x14000644a  jmp     loc_1400061FE
0x14000644f  inc     ebx
0x140006451  mov     r12d, 4
0x140006457  lea     rax, WPP_GLOBAL_Control
0x14000645e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006465  cmp     rcx, rax
0x140006468  jz      short loc_140006488
0x14000646a  test    [rcx+1Ch], r12b
0x14000646e  jz      short loc_140006488
0x140006470  mov     edx, 22h ; '"'
0x140006475  mov     r9d, ebx
0x140006478  lea     r8, WPP_9d8c324f5ff538d6084a6c746c899545_Traceguids
0x14000647f  mov     rcx, [rcx+10h]
0x140006483  call    WPP_SF_d
0x140006488  lea     rax, aCoreUploaderCo; "Core uploader complete"
0x14000648f  mov     [rdi], rax
0x140006492  mov     rax, [rsp+130h+var_E0]
0x140006497  test    rax, rax
0x14000649a  jz      short loc_1400064AD
0x14000649c  mov     [rsp+130h+var_B8], rax
0x1400064a1  lea     rcx, [rsp+130h+var_B8]
0x1400064a6  call    cs:__imp_WerpDestroyWerString
0x1400064ac  nop
0x1400064ad  mov     rcx, [rsp+130h+var_D8]
0x1400064b2  test    rcx, rcx
0x1400064b5  jz      short loc_1400064BE
0x1400064b7  call    cs:__imp_WerpCloseStore
0x1400064bd  nop
0x1400064be  call    cs:__imp_CoUninitialize
0x1400064c4  nop
0x1400064c5  mov     rcx, [rsp+130h+hObject]; hObject
0x1400064ca  lea     rax, [rcx+1]
0x1400064ce  cmp     rax, 1
0x1400064d2  jbe     short loc_1400064DA
0x1400064d4  call    cs:__imp_CloseHandle
0x1400064da  xor     eax, eax
0x1400064dc  jmp     loc_14000656E
0x1400064e1  lea     rax, aUnexpectedRepo; "Unexpected report with NULL report path"
  ... truncated ...
```
