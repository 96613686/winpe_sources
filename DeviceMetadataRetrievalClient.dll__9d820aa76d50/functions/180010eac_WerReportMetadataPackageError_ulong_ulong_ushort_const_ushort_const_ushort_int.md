# WerReportMetadataPackageError(ulong,ulong,ushort const *,ushort const *,ushort *,int)

- ea: `0x180010eac`
- end: `0x180011281`
- name: `?WerReportMetadataPackageError@@YAXKKPEBG0PEAGH@Z`
- size: `981`
- prototype: `void(unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006714`

## callees

- `0x180002f2c`
- `0x180004dec`
- `0x18000bf9c`
- `0x180010eac`
- `0x1800135cc`
- `0x1800136c6`
- `0x180013700`

## import_xrefs

- `wer!WerReportSetParameter` at `0x1800110d4`
- `wer!WerReportSetParameter` at `0x18001111b`
- `wer!WerReportSetParameter` at `0x180011169`
- `wer!WerReportSetParameter` at `0x18001118b`
- `wer!WerReportSetParameter` at `0x1800111ad`
- `wer!WerReportSetParameter` at `0x1800110d4`
- `wer!WerReportSetParameter` at `0x18001111b`
- `wer!WerReportSetParameter` at `0x180011169`
- `wer!WerReportSetParameter` at `0x18001118b`
- `wer!WerReportSetParameter` at `0x1800111ad`
- `wer!WerReportAddFile` at `0x180011147`
- `wer!WerReportAddFile` at `0x180011147`
- `wer!WerReportCreate` at `0x18001108e`
- `wer!WerReportCreate` at `0x18001108e`
- `wer!WerReportSubmit` at `0x1800111c9`
- `wer!WerReportSubmit` at `0x1800111c9`
- `wer!WerReportCloseHandle` at `0x180011258`
- `wer!WerReportCloseHandle` at `0x180011258`

## string_xrefs

- `0x180010fe3`: `%windir%\system32\dmrc.dll`
- `0x18001102f`: `Windows detected a new device metadata package for a device attached to your computer, but the metadata package is corrupted or has errors. Each device manufacturer typically includes the metadata package on a CD that comes with the device or as a download from its website.`

## pseudocode

```c
void __fastcall WerReportMetadataPackageError(
        unsigned int a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  HRESULT v9; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r11
  __int64 v16; // r10
  __int64 v17; // rcx
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  WCHAR *wzFriendlyEventName; // rax
  WCHAR *v21; // rcx
  __int64 v22; // rcx
  const wchar_t *v23; // rdx
  WCHAR *wzApplicationName; // rax
  WCHAR *v25; // rcx
  __int64 v26; // rcx
  const wchar_t *v27; // r8
  __int64 v28; // rdx
  WCHAR *wzApplicationPath; // rax
  WCHAR *v30; // rcx
  const wchar_t *v31; // rcx
  __int64 v32; // rdx
  WCHAR *wzDescription; // rax
  WCHAR *v34; // rcx
  _QWORD *v35; // rcx
  __int64 v36; // rcx
  const wchar_t *v37; // r9
  HREPORT phReportHandle; // [rsp+30h] [rbp-D0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+38h] [rbp-C8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pwzValue[12]; // [rsp+8E0h] [rbp+7E0h] BYREF

  phReportHandle = 0;
  v9 = 0;
  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  pSubmitResult = 0;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  v15 = 2147483646;
  pReportInformation.dwSize = 2208;
  v16 = 128;
  pReportInformation.hProcess = 0;
  v17 = 2147483646;
  pReportInformation.hwndParent = 0;
  v18 = 128;
  v19 = L"Device Metadata Package Error";
  wzFriendlyEventName = pReportInformation.wzFriendlyEventName;
  do
  {
    if ( !v17 )
      break;
    if ( !*v19 )
      break;
    *wzFriendlyEventName++ = *v19++;
    --v17;
    --v18;
  }
  while ( v18 );
  v21 = wzFriendlyEventName - 1;
  if ( v18 )
    v21 = wzFriendlyEventName;
  *v21 = 0;
  if ( !v18 )
    goto LABEL_48;
  v22 = 2147483646;
  v23 = L"Device Metadata Retrieval Client";
  wzApplicationName = pReportInformation.wzApplicationName;
  do
  {
    if ( !v22 )
      break;
    if ( !*v23 )
      break;
    *wzApplicationName++ = *v23++;
    --v22;
    --v16;
  }
  while ( v16 );
  v25 = wzApplicationName - 1;
  if ( v16 )
    v25 = wzApplicationName;
  *v25 = 0;
  if ( !v16 )
    goto LABEL_48;
  v26 = 2147483646;
  v27 = L"%windir%\\system32\\dmrc.dll";
  v28 = 260;
  wzApplicationPath = pReportInformation.wzApplicationPath;
  do
  {
    if ( !v26 )
      break;
    if ( !*v27 )
      break;
    *wzApplicationPath++ = *v27++;
    --v26;
    --v28;
  }
  while ( v28 );
  v30 = wzApplicationPath - 1;
  if ( v28 )
    v30 = wzApplicationPath;
  *v30 = 0;
  if ( !v28 )
    goto LABEL_48;
  v31 = L"Windows detected a new device metadata package for a device attached to your computer, but the metadata package "
         "is corrupted or has errors. Each device manufacturer typically includes the metadata package on a CD that comes"
         " with the device or as a download from its website.";
  v32 = 512;
  wzDescription = pReportInformation.wzDescription;
  do
  {
    if ( !v15 )
      break;
    if ( !*v31 )
      break;
    *wzDescription++ = *v31++;
    --v15;
    --v32;
  }
  while ( v32 );
  v34 = wzDescription - 1;
  if ( v32 )
    v34 = wzDescription;
  *v34 = 0;
  if ( !v32 )
    goto LABEL_48;
  v9 = WerReportCreate(L"DMRCDeviceMetadataPackageFailure", WerReportNonCritical, &pReportInformation, &phReportHandle);
  if ( v9 )
    goto LABEL_48;
  if ( (int)StringCchPrintfW(pwzValue, 0xBu, L"0x%08x", a1) < 0 )
    goto LABEL_48;
  v9 = WerReportSetParameter(phReportHandle, 0, L"Error Code", pwzValue);
  if ( v9 )
    goto LABEL_48;
  if ( (int)StringCchPrintfW(pwzValue, 0xBu, L"0x%08x", a2) < 0 )
    goto LABEL_48;
  v9 = WerReportSetParameter(phReportHandle, v9 + 1, L"Win32 Error Code", pwzValue);
  if ( v9 )
    goto LABEL_48;
  v9 = WerReportAddFile(phReportHandle, a4, WerFileTypeOther, (a6 != 0) + 2);
  if ( v9 )
    goto LABEL_48;
  v9 = WerReportSetParameter(phReportHandle, 2u, L"Source", a5);
  if ( v9 )
    goto LABEL_48;
  v9 = WerReportSetParameter(phReportHandle, 3u, L"Package name", a3);
  if ( v9 )
    goto LABEL_48;
  v9 = WerReportSetParameter(phReportHandle, 4u, L"Version", L"1.0");
  if ( v9 )
    goto LABEL_48;
  v9 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0, &pSubmitResult);
  if ( v9 )
    goto LABEL_48;
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_54;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_2faca7f1b9023131caad1ec5563abb37_Traceguids,
      (unsigned int)pSubmitResult);
LABEL_48:
    v35 = WPP_GLOBAL_Control;
  }
  if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 8) != 0 )
  {
    v36 = v35[2];
    v37 = L"successfully";
    if ( v9 )
      v37 = L"unsucessfully";
    WPP_SF_SD(v36, 11, (unsigned int)&WPP_2faca7f1b9023131caad1ec5563abb37_Traceguids, (_DWORD)v37, v9);
  }
LABEL_54:
  if ( phReportHandle )
    WerReportCloseHandle(phReportHandle);
}

```

## disassembly

```asm
0x180010eac  push    rbp
0x180010eae  push    rbx
0x180010eaf  push    rsi
0x180010eb0  push    rdi
0x180010eb1  push    r12
0x180010eb3  push    r13
0x180010eb5  push    r14
0x180010eb7  push    r15
0x180010eb9  lea     rbp, [rsp-808h]
0x180010ec1  sub     rsp, 908h
0x180010ec8  mov     rax, cs:__security_cookie
0x180010ecf  xor     rax, rsp
0x180010ed2  mov     [rbp+840h+var_48], rax
0x180010ed9  mov     rsi, [rbp+840h+arg_20]
0x180010ee0  mov     r15, r8
0x180010ee3  mov     r12d, edx
0x180010ee6  mov     r14d, ecx
0x180010ee9  xor     r13d, r13d
0x180010eec  lea     rcx, [rsp+940h+pReportInformation]; void *
0x180010ef1  xor     edx, edx; Val
0x180010ef3  mov     [rsp+940h+phReportHandle], r13
0x180010ef8  mov     r8d, 8A0h; Size
0x180010efe  mov     ebx, r13d
0x180010f01  mov     rdi, r9
0x180010f04  call    memset_0
0x180010f09  mov     [rsp+940h+pSubmitResult], r13d
0x180010f0e  test    r15, r15
0x180010f11  jnz     short loc_180010F18
0x180010f13  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010f18  test    rdi, rdi
0x180010f1b  jnz     short loc_180010F22
0x180010f1d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010f22  test    rsi, rsi
0x180010f25  jnz     short loc_180010F2C
0x180010f27  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010f2c  mov     r11d, 7FFFFFFEh
0x180010f32  mov     [rsp+940h+pReportInformation.dwSize], 8A0h
0x180010f3a  mov     r10d, 80h
0x180010f40  mov     [rsp+940h+pReportInformation.hProcess], r13
0x180010f45  mov     ecx, r11d
0x180010f48  mov     [rbp+840h+pReportInformation.hwndParent], r13
0x180010f4f  mov     edx, r10d
0x180010f52  lea     r8, aDeviceMetadata; "Device Metadata Package Error"
0x180010f59  lea     rax, [rbp+840h+pReportInformation.wzFriendlyEventName]
0x180010f5d  test    rcx, rcx
0x180010f60  jz      short loc_180010F81
0x180010f62  movzx   r9d, word ptr [r8]
0x180010f66  test    r9w, r9w
0x180010f6a  jz      short loc_180010F81
0x180010f6c  mov     [rax], r9w
0x180010f70  add     r8, 2
0x180010f74  add     rax, 2
0x180010f78  dec     rcx
0x180010f7b  sub     rdx, 1
0x180010f7f  jnz     short loc_180010F5D
0x180010f81  test    rdx, rdx
0x180010f84  lea     rcx, [rax-2]
0x180010f88  cmovnz  rcx, rax
0x180010f8c  mov     [rcx], r13w
0x180010f90  jz      loc_180011208
0x180010f96  mov     rcx, r11
0x180010f99  lea     rdx, aDeviceMetadata_0; "Device Metadata Retrieval Client"
0x180010fa0  lea     rax, [rbp+840h+pReportInformation.wzApplicationName]
0x180010fa7  test    rcx, rcx
0x180010faa  jz      short loc_180010FCB
0x180010fac  movzx   r8d, word ptr [rdx]
0x180010fb0  test    r8w, r8w
0x180010fb4  jz      short loc_180010FCB
0x180010fb6  mov     [rax], r8w
0x180010fba  add     rdx, 2
0x180010fbe  add     rax, 2
0x180010fc2  dec     rcx
0x180010fc5  sub     r10, 1
0x180010fc9  jnz     short loc_180010FA7
0x180010fcb  test    r10, r10
0x180010fce  lea     rcx, [rax-2]
0x180010fd2  cmovnz  rcx, rax
0x180010fd6  mov     [rcx], r13w
0x180010fda  jz      loc_180011208
0x180010fe0  mov     rcx, r11
0x180010fe3  lea     r8, aWindirSystem32; "%windir%\\system32\\dmrc.dll"
0x180010fea  mov     edx, 104h
0x180010fef  lea     rax, [rbp+840h+pReportInformation.wzApplicationPath]
0x180010ff6  test    rcx, rcx
0x180010ff9  jz      short loc_18001101A
0x180010ffb  movzx   r9d, word ptr [r8]
0x180010fff  test    r9w, r9w
0x180011003  jz      short loc_18001101A
0x180011005  mov     [rax], r9w
0x180011009  add     r8, 2
0x18001100d  add     rax, 2
0x180011011  dec     rcx
0x180011014  sub     rdx, 1
0x180011018  jnz     short loc_180010FF6
0x18001101a  test    rdx, rdx
0x18001101d  lea     rcx, [rax-2]
0x180011021  cmovnz  rcx, rax
0x180011025  mov     [rcx], r13w
0x180011029  jz      loc_180011208
0x18001102f  lea     rcx, aWindowsDetecte; "Windows detected a new device metadata "...
0x180011036  mov     edx, 200h
0x18001103b  lea     rax, [rbp+840h+pReportInformation.wzDescription]
0x180011042  test    r11, r11
0x180011045  jz      short loc_180011066
0x180011047  movzx   r8d, word ptr [rcx]
0x18001104b  test    r8w, r8w
0x18001104f  jz      short loc_180011066
0x180011051  mov     [rax], r8w
0x180011055  add     rcx, 2
0x180011059  add     rax, 2
0x18001105d  dec     r11
0x180011060  sub     rdx, 1
0x180011064  jnz     short loc_180011042
0x180011066  test    rdx, rdx
0x180011069  lea     rcx, [rax-2]
0x18001106d  cmovnz  rcx, rax
0x180011071  mov     [rcx], r13w
0x180011075  jz      loc_180011208
0x18001107b  lea     r9, [rsp+940h+phReportHandle]; phReportHandle
0x180011080  xor     edx, edx; repType
0x180011082  lea     r8, [rsp+940h+pReportInformation]; pReportInformation
0x180011087  lea     rcx, pwzEventType; "DMRCDeviceMetadataPackageFailure"
0x18001108e  call    cs:__imp_WerReportCreate
0x180011094  mov     ebx, eax
0x180011096  test    eax, eax
0x180011098  jnz     loc_180011208
0x18001109e  mov     r9d, r14d
0x1800110a1  lea     r8, a0x08x; "0x%08x"
0x1800110a8  lea     edx, [rax+0Bh]; unsigned __int64
0x1800110ab  lea     rcx, [rbp+840h+pwzValue]; unsigned __int16 *
0x1800110b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800110b7  test    eax, eax
0x1800110b9  js      loc_180011208
0x1800110bf  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x1800110c4  lea     r9, [rbp+840h+pwzValue]; pwzValue
0x1800110cb  lea     r8, pwzName; "Error Code"
0x1800110d2  xor     edx, edx; dwparamID
0x1800110d4  call    cs:__imp_WerReportSetParameter
0x1800110da  mov     ebx, eax
0x1800110dc  test    eax, eax
0x1800110de  jnz     loc_180011208
0x1800110e4  mov     r9d, r12d
0x1800110e7  lea     r8, a0x08x; "0x%08x"
0x1800110ee  lea     edx, [rax+0Bh]; unsigned __int64
0x1800110f1  lea     rcx, [rbp+840h+pwzValue]; unsigned __int16 *
0x1800110f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800110fd  test    eax, eax
0x1800110ff  js      loc_180011208
0x180011105  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18001110a  lea     r9, [rbp+840h+pwzValue]; pwzValue
0x180011111  lea     r8, aWin32ErrorCode; "Win32 Error Code"
0x180011118  lea     edx, [rbx+1]; dwparamID
0x18001111b  call    cs:__imp_WerReportSetParameter
0x180011121  mov     ebx, eax
0x180011123  test    eax, eax
0x180011125  jnz     loc_180011208
0x18001112b  neg     [rbp+840h+arg_28]
0x180011131  lea     r8d, [rax+5]; repFileType
0x180011135  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18001113a  mov     rdx, rdi; pwzPath
0x18001113d  sbb     r9d, r9d
0x180011140  neg     r9d
0x180011143  add     r9d, 2; dwFileFlags
0x180011147  call    cs:__imp_WerReportAddFile
0x18001114d  mov     ebx, eax
0x18001114f  test    eax, eax
0x180011151  jnz     loc_180011208
0x180011157  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18001115c  lea     r8, aSource; "Source"
0x180011163  mov     r9, rsi; pwzValue
0x180011166  lea     edx, [rax+2]; dwparamID
0x180011169  call    cs:__imp_WerReportSetParameter
0x18001116f  mov     ebx, eax
0x180011171  test    eax, eax
0x180011173  jnz     loc_180011208
0x180011179  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18001117e  lea     r8, aPackageName; "Package name"
0x180011185  mov     r9, r15; pwzValue
0x180011188  lea     edx, [rax+3]; dwparamID
0x18001118b  call    cs:__imp_WerReportSetParameter
0x180011191  mov     ebx, eax
0x180011193  test    eax, eax
0x180011195  jnz     short loc_180011208
0x180011197  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18001119c  lea     r9, pwzValue; "1.0"
0x1800111a3  lea     r8, aVersion; "Version"
0x1800111aa  lea     edx, [rax+4]; dwparamID
0x1800111ad  call    cs:__imp_WerReportSetParameter
0x1800111b3  mov     ebx, eax
0x1800111b5  test    eax, eax
0x1800111b7  jnz     short loc_180011208
0x1800111b9  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x1800111be  lea     r9, [rsp+940h+pSubmitResult]; pSubmitResult
0x1800111c3  xor     r8d, r8d; dwFlags
0x1800111c6  lea     edx, [rax+1]; consent
0x1800111c9  call    cs:__imp_WerReportSubmit
0x1800111cf  mov     ebx, eax
0x1800111d1  test    eax, eax
0x1800111d3  jnz     short loc_180011208
0x1800111d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111dc  lea     rdi, WPP_GLOBAL_Control
0x1800111e3  cmp     rcx, rdi
0x1800111e6  jz      short loc_18001124E
0x1800111e8  test    byte ptr [rcx+1Ch], 8
0x1800111ec  jz      short loc_180011216
0x1800111ee  mov     r9d, [rsp+940h+pSubmitResult]
0x1800111f3  lea     edx, [rax+0Ah]
0x1800111f6  mov     rcx, [rcx+10h]
0x1800111fa  lea     r8, WPP_2faca7f1b9023131caad1ec5563abb37_Traceguids
0x180011201  call    WPP_SF_d
0x180011206  jmp     short loc_18001120F
0x180011208  lea     rdi, WPP_GLOBAL_Control
0x18001120f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011216  cmp     rcx, rdi
0x180011219  jz      short loc_18001124E
0x18001121b  test    byte ptr [rcx+1Ch], 8
0x18001121f  jz      short loc_18001124E
0x180011221  mov     rcx, [rcx+10h]
0x180011225  lea     rax, aUnsucessfully; "unsucessfully"
0x18001122c  test    ebx, ebx
0x18001122e  mov     [rsp+940h+var_920], ebx
0x180011232  lea     r9, aSuccessfully; "successfully"
0x180011239  mov     edx, 0Bh
0x18001123e  cmovnz  r9, rax
0x180011242  lea     r8, WPP_2faca7f1b9023131caad1ec5563abb37_Traceguids
0x180011249  call    WPP_SF_SD
0x18001124e  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x180011253  test    rcx, rcx
0x180011256  jz      short loc_18001125E
0x180011258  call    cs:__imp_WerReportCloseHandle
0x18001125e  mov     rcx, [rbp+840h+var_48]
0x180011265  xor     rcx, rsp; StackCookie
0x180011268  call    __security_check_cookie
0x18001126d  add     rsp, 908h
0x180011274  pop     r15
0x180011276  pop     r14
0x180011278  pop     r13
0x18001127a  pop     r12
0x18001127c  pop     rdi
0x18001127d  pop     rsi
0x18001127e  pop     rbx
0x18001127f  pop     rbp
0x180011280  retn
```
