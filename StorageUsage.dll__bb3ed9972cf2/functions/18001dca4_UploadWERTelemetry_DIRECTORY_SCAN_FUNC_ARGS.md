# UploadWERTelemetry(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x18001dca4`
- end: `0x18001dee7`
- name: `?UploadWERTelemetry@@YAJPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ad40`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18001dca4`
- `0x180022684`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd1d`
- `wer!WerReportCreate` at `0x18001dd4b`
- `wer!WerReportCreate` at `0x18001dd4b`
- `wer!WerReportAddFile` at `0x18001de05`
- `wer!WerReportAddFile` at `0x18001de05`
- `wer!WerReportSetParameter` at `0x18001dd7c`
- `wer!WerReportSetParameter` at `0x18001ddac`
- `wer!WerReportSetParameter` at `0x18001ddd6`
- `wer!WerReportSetParameter` at `0x18001dd7c`
- `wer!WerReportSetParameter` at `0x18001ddac`
- `wer!WerReportSetParameter` at `0x18001ddd6`
- `wer!WerReportSubmit` at `0x18001de3e`
- `wer!WerReportSubmit` at `0x18001de3e`
- `wer!WerReportCloseHandle` at `0x18001de92`
- `wer!WerReportCloseHandle` at `0x18001de92`

## pseudocode

```c
__int64 __fastcall UploadWERTelemetry(struct DIRECTORY_SCAN_FUNC_ARGS *a1)
{
  char *v2; // rcx
  const WCHAR *v3; // rcx
  HRESULT v4; // eax
  int v5; // ebx
  int v6; // r9d
  HRESULT v7; // eax
  HRESULT v8; // eax
  unsigned int v9; // esi
  unsigned int v11; // [rsp+20h] [rbp-E0h]
  HREPORT phReportHandle; // [rsp+30h] [rbp-D0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[96]; // [rsp+40h] [rbp-C0h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+A0h] [rbp-60h] BYREF

  phReportHandle = 0;
  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  memset_0(v14, 0, sizeof(v14));
  v2 = (char *)*((_QWORD *)a1 + 21);
  if ( (unsigned __int64)(v2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v5 = 0;
    v11 = 1438;
    v6 = 0;
    goto LABEL_18;
  }
  CloseHandle(v2);
  v3 = pwzEventType;
  *((_QWORD *)a1 + 21) = -1;
  pReportInformation.dwSize = 2208;
  pReportInformation.hProcess = 0;
  v4 = WerReportCreate(v3, WerReportNonCritical, &pReportInformation, &phReportHandle);
  v5 = v4;
  if ( v4 < 0 || !phReportHandle )
  {
    v11 = 1450;
    goto LABEL_6;
  }
  v4 = WerReportSetParameter(phReportHandle, 0, L"Parameter0", L"0");
  v5 = v4;
  if ( v4 < 0 )
  {
    v11 = 1457;
LABEL_6:
    v6 = v4;
LABEL_18:
    RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v14, a1, (wchar_t *)L"<WER_Failure>", v6, v11);
    goto LABEL_19;
  }
  v4 = WerReportSetParameter(phReportHandle, 1u, L"Parameter1", L"0");
  v5 = v4;
  if ( v4 < 0 )
  {
    v11 = 1458;
    goto LABEL_6;
  }
  v4 = WerReportSetParameter(phReportHandle, 2u, L"Parameter2", L"0");
  v5 = v4;
  if ( v4 < 0 )
  {
    v11 = 1459;
    goto LABEL_6;
  }
  v7 = WerReportAddFile(phReportHandle, (PCWSTR)a1 + 88, WerFileTypeOther, 3u);
  v5 = v7;
  if ( v7 < 0 )
  {
    RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v14, a1, (wchar_t *)a1 + 88, v7, 0x5BBu);
    goto LABEL_19;
  }
  pSubmitResult = 0;
  v4 = WerReportSubmit(phReportHandle, WerConsentApproved, 0x2020u, &pSubmitResult);
  v5 = v4;
  if ( v4 < 0 || pSubmitResult != WerReportUploaded )
  {
    v11 = 1479;
    goto LABEL_6;
  }
LABEL_19:
  if ( phReportHandle )
  {
    v8 = WerReportCloseHandle(phReportHandle);
    v9 = v8;
    if ( v8 < 0 )
      RecordDirScanFailures((struct _FILE_ID_EXTD_DIR_INFORMATION *)v14, a1, (wchar_t *)L"<WER_Failure>", v8, 0x5D0u);
    if ( v5 >= 0 )
      return v9;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001dca4  mov     [rsp-8+arg_8], rbx
0x18001dca9  mov     [rsp-8+arg_10], rsi
0x18001dcae  push    rbp
0x18001dcaf  push    rdi
0x18001dcb0  push    r15
0x18001dcb2  lea     rbp, [rsp-850h]
0x18001dcba  sub     rsp, 950h
0x18001dcc1  mov     rax, cs:__security_cookie
0x18001dcc8  xor     rax, rsp
0x18001dccb  mov     [rbp+860h+var_20], rax
0x18001dcd2  mov     rdi, rcx
0x18001dcd5  mov     [rsp+960h+phReportHandle], 0
0x18001dcde  mov     ebx, 8A0h
0x18001dce3  lea     rcx, [rbp+860h+pReportInformation]; void *
0x18001dce7  mov     r8d, ebx; Size
0x18001dcea  xor     edx, edx; Val
0x18001dcec  call    memset_0
0x18001dcf1  xor     edx, edx; Val
0x18001dcf3  lea     rcx, [rsp+960h+var_920]; void *
0x18001dcf8  lea     r8d, [rdx+60h]; Size
0x18001dcfc  call    memset_0
0x18001dd01  mov     rcx, [rdi+0A8h]; hObject
0x18001dd08  lea     r15, aWerFailure; "<WER_Failure>"
0x18001dd0f  lea     rax, [rcx-1]
0x18001dd13  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001dd17  ja      loc_18001DE6B
0x18001dd1d  call    cs:__imp_CloseHandle
0x18001dd23  mov     rcx, cs:pwzEventType; pwzEventType
0x18001dd2a  lea     r9, [rsp+960h+phReportHandle]; phReportHandle
0x18001dd2f  lea     r8, [rbp+860h+pReportInformation]; pReportInformation
0x18001dd33  mov     qword ptr [rdi+0A8h], 0FFFFFFFFFFFFFFFFh
0x18001dd3e  xor     edx, edx; repType
0x18001dd40  mov     [rbp+860h+pReportInformation.dwSize], ebx
0x18001dd43  mov     [rbp+860h+pReportInformation.hProcess], 0
0x18001dd4b  call    cs:__imp_WerReportCreate
0x18001dd51  mov     ebx, eax
0x18001dd53  test    eax, eax
0x18001dd55  js      loc_18001DE5E
0x18001dd5b  mov     rcx, [rsp+960h+phReportHandle]; hReportHandle
0x18001dd60  test    rcx, rcx
0x18001dd63  jz      loc_18001DE5E
0x18001dd69  lea     rsi, pwzValue; "0"
0x18001dd70  xor     edx, edx; dwparamID
0x18001dd72  mov     r9, rsi; pwzValue
0x18001dd75  lea     r8, pwzName; "Parameter0"
0x18001dd7c  call    cs:__imp_WerReportSetParameter
0x18001dd82  mov     ebx, eax
0x18001dd84  test    eax, eax
0x18001dd86  jns     short loc_18001DD98
0x18001dd88  mov     [rsp+960h+var_940], 5B1h
0x18001dd90  mov     r9d, eax
0x18001dd93  jmp     loc_18001DE78
0x18001dd98  mov     rcx, [rsp+960h+phReportHandle]; hReportHandle
0x18001dd9d  lea     r8, aParameter1; "Parameter1"
0x18001dda4  mov     r9, rsi; pwzValue
0x18001dda7  mov     edx, 1; dwparamID
0x18001ddac  call    cs:__imp_WerReportSetParameter
0x18001ddb2  mov     ebx, eax
0x18001ddb4  test    eax, eax
0x18001ddb6  jns     short loc_18001DDC2
0x18001ddb8  mov     [rsp+960h+var_940], 5B2h
0x18001ddc0  jmp     short loc_18001DD90
0x18001ddc2  mov     rcx, [rsp+960h+phReportHandle]; hReportHandle
0x18001ddc7  lea     r8, aParameter2; "Parameter2"
0x18001ddce  mov     r9, rsi; pwzValue
0x18001ddd1  mov     edx, 2; dwparamID
0x18001ddd6  call    cs:__imp_WerReportSetParameter
0x18001dddc  mov     ebx, eax
0x18001ddde  test    eax, eax
0x18001dde0  jns     short loc_18001DDEC
0x18001dde2  mov     [rsp+960h+var_940], 5B3h
0x18001ddea  jmp     short loc_18001DD90
0x18001ddec  mov     rcx, [rsp+960h+phReportHandle]; hReportHandle
0x18001ddf1  lea     rsi, [rdi+0B0h]
0x18001ddf8  mov     r9d, 3; dwFileFlags
0x18001ddfe  mov     rdx, rsi; pwzPath
0x18001de01  lea     r8d, [r9+2]; repFileType
0x18001de05  call    cs:__imp_WerReportAddFile
0x18001de0b  mov     ebx, eax
0x18001de0d  test    eax, eax
0x18001de0f  jns     short loc_18001DE21
0x18001de11  mov     [rsp+960h+var_940], 5BBh
0x18001de19  mov     r9d, eax
0x18001de1c  mov     r8, rsi
0x18001de1f  jmp     short loc_18001DE7B
0x18001de21  mov     rcx, [rsp+960h+phReportHandle]; hReportHandle
0x18001de26  lea     r9, [rsp+960h+pSubmitResult]; pSubmitResult
0x18001de2b  mov     edx, 2; consent
0x18001de30  mov     [rsp+960h+pSubmitResult], 0
0x18001de38  mov     r8d, 2020h; dwFlags
0x18001de3e  call    cs:__imp_WerReportSubmit
0x18001de44  mov     ebx, eax
0x18001de46  test    eax, eax
0x18001de48  js      short loc_18001DE51
0x18001de4a  cmp     [rsp+960h+pSubmitResult], 2
0x18001de4f  jz      short loc_18001DE88
0x18001de51  mov     [rsp+960h+var_940], 5C7h
0x18001de59  jmp     loc_18001DD90
0x18001de5e  mov     [rsp+960h+var_940], 5AAh
0x18001de66  jmp     loc_18001DD90
0x18001de6b  xor     ebx, ebx
0x18001de6d  mov     [rsp+960h+var_940], 59Eh; unsigned int
0x18001de75  xor     r9d, r9d; int
0x18001de78  mov     r8, r15; unsigned __int16 *
0x18001de7b  mov     rdx, rdi; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001de7e  lea     rcx, [rsp+960h+var_920]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001de83  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001de88  mov     rcx, [rsp+960h+phReportHandle]; hReportHandle
0x18001de8d  test    rcx, rcx
0x18001de90  jz      short loc_18001DEBE
0x18001de92  call    cs:__imp_WerReportCloseHandle
0x18001de98  mov     esi, eax
0x18001de9a  test    eax, eax
0x18001de9c  jns     short loc_18001DEB9
0x18001de9e  mov     r9d, eax; int
0x18001dea1  mov     [rsp+960h+var_940], 5D0h; unsigned int
0x18001dea9  mov     r8, r15; unsigned __int16 *
0x18001deac  lea     rcx, [rsp+960h+var_920]; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001deb1  mov     rdx, rdi; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001deb4  call    ?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x18001deb9  test    ebx, ebx
0x18001debb  cmovns  ebx, esi
0x18001debe  mov     eax, ebx
0x18001dec0  mov     rcx, [rbp+860h+var_20]
0x18001dec7  xor     rcx, rsp; StackCookie
0x18001deca  call    __security_check_cookie
0x18001decf  lea     r11, [rsp+960h+var_10]
0x18001ded7  mov     rbx, [r11+28h]
0x18001dedb  mov     rsi, [r11+30h]
0x18001dedf  mov     rsp, r11
0x18001dee2  pop     r15
0x18001dee4  pop     rdi
0x18001dee5  pop     rbp
0x18001dee6  retn
```
