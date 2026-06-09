# CWCTInfoWriter::WriteAuxProcListToFile(void * *,ulong)

- ea: `0x14002ea48`
- end: `0x14002f04d`
- name: `?WriteAuxProcListToFile@CWCTInfoWriter@@AEAAJPEAPEAXK@Z`
- size: `1541`
- prototype: `__int64 __fastcall(CWCTInfoWriter *__hidden this, void **, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14002f70c`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x14000b580`
- `0x140014f14`
- `0x1400166ec`
- `0x14002ea48`
- `0x14002f294`
- `0x14002f32c`
- `0x14002f410`
- `0x14002fb94`
- `0x140034968`
- `0x140034ba0`
- `0x140034da8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14002ec60`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14002ec60`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002eb7b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002eb7b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14002ec40`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14002ec40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWCTInfoWriter::WriteAuxProcListToFile(CWCTInfoWriter *this, void **a2, unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  CUserModeHangReport *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r15
  __int64 v18; // rdx
  __int64 v19; // rcx
  DWORD ProcessId; // esi
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rax
  WCHAR *v24; // rax
  int ProcessPackageFullName; // eax
  __int64 v26; // rdx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v29[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v30[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v31; // [rsp+58h] [rbp-A8h]
  _WORD *v32; // [rsp+60h] [rbp-A0h]
  _WORD v33[8]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v34; // [rsp+78h] [rbp-88h]
  _WORD *v35; // [rsp+80h] [rbp-80h]
  _WORD v36[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ExeName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v34 = v36;
  v35 = v36;
  v36[0] = 0;
  v31 = v33;
  v32 = v33;
  v33[0] = 0;
  v29[0] = v30;
  v29[1] = v30;
  v30[0] = 0;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 0;
  if ( *((_QWORD *)this + 1) == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  if ( !*((_QWORD *)this + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  v12 = CWCTInfoWriter::WriteStartElementToFileWithAttributes(this, L"AUXILIARY_PROCESSES", 0, 0, 1);
  if ( v12 >= 0 )
  {
    v17 = 0;
    if ( a3 )
    {
      while ( 1 )
      {
        if ( !a2[v17] )
          MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v13, v14);
        ProcessId = GetProcessId(a2[v17]);
        if ( !ProcessId )
          MicrosoftTelemetryAssertTriggeredNoArgs(v19, v18, v21, v22);
        v12 = CWCTInfoWriter::WriteStartElementToFileWithAttributes(this, L"AUXILIARY_PROCESS", 0, 0, 1);
        if ( v12 < 0 )
          break;
        v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PID", ProcessId, 0);
        if ( v12 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 52;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        dwSize = 32;
        ExeName[0] = 0;
        v12 = StringCchPrintfW(ExeName, 0x20u, L"triagedump.%04x.dmp", ProcessId);
        if ( v12 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 53;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"FILE", ExeName);
        if ( v12 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 54;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        dwSize = 260;
        ExeName[0] = 0;
        if ( QueryFullProcessImageNameW(a2[v17], 0, ExeName, &dwSize) && dwSize )
        {
          v23 = wcsrchr(ExeName, 0x5Cu);
          if ( v23 )
            v24 = v23 + 1;
          else
            v24 = ExeName;
        }
        else
        {
          v24 = (WCHAR *)L"QUERY_ERROR";
        }
        v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PROCESS_NAME", v24);
        if ( v12 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 55;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(a2[v17]);
        if ( ProcessPackageFullName < 0 )
        {
          if ( ProcessPackageFullName == -2147009196 )
          {
            v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGFULLNAME", L"NO_PACKAGE");
            if ( v12 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v16 = 57;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
          else
          {
            v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGFULLNAME", L"QUERY_ERROR");
            if ( v12 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v16 = 58;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
          v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGRELAPPID", L"NO_PACKAGE");
          if ( v12 < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 61;
              goto LABEL_9;
            }
            goto LABEL_49;
          }
        }
        else
        {
          v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGFULLNAME", v34);
          if ( v12 < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 56;
              goto LABEL_9;
            }
            goto LABEL_49;
          }
          if ( (int)PackageUtility::GetProcessApplicationId(a2[v17]) < 0
            || (int)PackageUtility::ParseApplicationId(v31, v26, v29) < 0 )
          {
            v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGRELAPPID", L"QUERY_ERROR");
            if ( v12 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v16 = 60;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
          else
          {
            v12 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGRELAPPID", v29[0]);
            if ( v12 < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v16 = 59;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
        }
        v12 = CWCTInfoWriter::WriteEndElementToFile(this, L"AUXILIARY_PROCESS", 1);
        if ( v12 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 62;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= a3 )
          goto LABEL_47;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 51;
        goto LABEL_9;
      }
    }
    else
    {
LABEL_47:
      v12 = CWCTInfoWriter::WriteEndElementToFile(this, L"AUXILIARY_PROCESSES", 1);
      if ( v12 >= 0 )
        v12 = 0;
    }
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 50;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids, (unsigned int)v12);
    }
  }
LABEL_49:
  if ( v29[0] != v30 )
    operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  if ( v34 != v36 )
    operator delete(v34, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002ea48  mov     [rsp-8+arg_10], rbx
0x14002ea4d  push    rbp
0x14002ea4e  push    rsi
0x14002ea4f  push    rdi
0x14002ea50  push    r12
0x14002ea52  push    r13
0x14002ea54  push    r14
0x14002ea56  push    r15
0x14002ea58  lea     rbp, [rsp-1C0h]
0x14002ea60  sub     rsp, 2C0h
0x14002ea67  mov     rax, cs:__security_cookie
0x14002ea6e  xor     rax, rsp
0x14002ea71  mov     [rbp+1F0h+var_40], rax
0x14002ea78  mov     r13d, r8d
0x14002ea7b  mov     r12, rdx
0x14002ea7e  mov     rdi, rcx
0x14002ea81  lea     rax, [rbp+1F0h+var_268]
0x14002ea85  mov     [rsp+2F0h+var_278], rax
0x14002ea8a  lea     rax, [rbp+1F0h+var_268]
0x14002ea8e  mov     [rbp+1F0h+var_270], rax
0x14002ea92  xor     eax, eax
0x14002ea94  mov     [rbp+1F0h+var_268], ax
0x14002ea98  lea     rax, [rsp+2F0h+var_288]
0x14002ea9d  mov     [rsp+2F0h+var_298], rax
0x14002eaa2  lea     rax, [rsp+2F0h+var_288]
0x14002eaa7  mov     [rsp+2F0h+var_290], rax
0x14002eaac  xor     eax, eax
0x14002eaae  mov     [rsp+2F0h+var_288], ax
0x14002eab3  lea     rax, [rsp+2F0h+var_2A8]
0x14002eab8  mov     [rsp+2F0h+var_2B8], rax
0x14002eabd  lea     rax, [rsp+2F0h+var_2A8]
0x14002eac2  mov     [rsp+2F0h+var_2B0], rax
0x14002eac7  xor     eax, eax
0x14002eac9  mov     [rsp+2F0h+var_2A8], ax
0x14002eace  xor     edx, edx; Val
0x14002ead0  mov     r8d, 208h; Size
0x14002ead6  lea     rcx, [rbp+1F0h+ExeName]; void *
0x14002eada  call    memset_0
0x14002eadf  mov     [rsp+2F0h+dwSize], 0
0x14002eae7  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14002eaec  jnz     short loc_14002EAF3
0x14002eaee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002eaf3  cmp     qword ptr [rdi+20h], 0
0x14002eaf8  jnz     short loc_14002EAFF
0x14002eafa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002eaff  mov     esi, 1
0x14002eb04  mov     [rsp+2F0h+var_2D0], esi; int
0x14002eb08  xor     r9d, r9d; int
0x14002eb0b  xor     r8d, r8d; struct CWCTInfoWriter::XmlAttribute *
0x14002eb0e  lea     rdx, aAuxiliaryProce_0; "AUXILIARY_PROCESSES"
0x14002eb15  mov     rcx, rdi; this
0x14002eb18  call    ?WriteStartElementToFileWithAttributes@CWCTInfoWriter@@AEAAJPEB_WPEAUXmlAttribute@1@HH@Z; CWCTInfoWriter::WriteStartElementToFileWithAttributes(wchar_t const *,CWCTInfoWriter::XmlAttribute *,int,int)
0x14002eb1d  mov     ebx, eax
0x14002eb1f  test    eax, eax
0x14002eb21  jns     short loc_14002EB5F
0x14002eb23  lea     rcx, WPP_GLOBAL_Control
0x14002eb2a  mov     rax, cs:WPP_GLOBAL_Control
0x14002eb31  cmp     rax, rcx
0x14002eb34  jz      loc_14002EE4F
0x14002eb3a  test    [rax+1Ch], sil
0x14002eb3e  jz      loc_14002EE4F
0x14002eb44  lea     edx, [rsi+31h]
0x14002eb47  mov     r9d, ebx
0x14002eb4a  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002eb51  mov     rcx, [rax+10h]
0x14002eb55  call    WPP_SF_d
0x14002eb5a  jmp     loc_14002EE4F
0x14002eb5f  xor     r15d, r15d
0x14002eb62  test    r13d, r13d
0x14002eb65  jz      loc_14002EE34
0x14002eb6b  cmp     qword ptr [r12+r15*8], 0
0x14002eb70  jnz     short loc_14002EB77
0x14002eb72  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002eb77  mov     rcx, [r12+r15*8]; Process
0x14002eb7b  call    cs:__imp_GetProcessId
0x14002eb82  nop     dword ptr [rax+rax+00h]
0x14002eb87  mov     esi, eax
0x14002eb89  test    eax, eax
0x14002eb8b  jnz     short loc_14002EB92
0x14002eb8d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002eb92  mov     [rsp+2F0h+var_2D0], 1; int
0x14002eb9a  xor     r9d, r9d; int
0x14002eb9d  xor     r8d, r8d; struct CWCTInfoWriter::XmlAttribute *
0x14002eba0  lea     rdx, aAuxiliaryProce; "AUXILIARY_PROCESS"
0x14002eba7  mov     rcx, rdi; this
0x14002ebaa  call    ?WriteStartElementToFileWithAttributes@CWCTInfoWriter@@AEAAJPEB_WPEAUXmlAttribute@1@HH@Z; CWCTInfoWriter::WriteStartElementToFileWithAttributes(wchar_t const *,CWCTInfoWriter::XmlAttribute *,int,int)
0x14002ebaf  mov     ebx, eax
0x14002ebb1  test    eax, eax
0x14002ebb3  js      loc_14002F021
0x14002ebb9  xor     r9d, r9d; unsigned int
0x14002ebbc  mov     r8d, esi; unsigned int
0x14002ebbf  lea     rdx, aPid; "PID"
0x14002ebc6  mov     rcx, rdi; this
0x14002ebc9  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_WKK@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,ulong,ulong)
0x14002ebce  mov     ebx, eax
0x14002ebd0  test    eax, eax
0x14002ebd2  js      loc_14002EFF6
0x14002ebd8  mov     ecx, 20h ; ' '
0x14002ebdd  mov     [rsp+2F0h+dwSize], ecx
0x14002ebe1  xor     eax, eax
0x14002ebe3  mov     [rbp+1F0h+ExeName], ax
0x14002ebe7  mov     r9d, esi
0x14002ebea  lea     r8, aTriagedump04xD; "triagedump.%04x.dmp"
0x14002ebf1  mov     edx, ecx; unsigned __int64
0x14002ebf3  lea     rcx, [rbp+1F0h+ExeName]; wchar_t *
0x14002ebf7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14002ebfc  mov     ebx, eax
0x14002ebfe  test    eax, eax
0x14002ec00  js      loc_14002EFCB
0x14002ec06  lea     r8, [rbp+1F0h+ExeName]; wchar_t *
0x14002ec0a  lea     rdx, aFile; "FILE"
0x14002ec11  mov     rcx, rdi; this
0x14002ec14  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ec19  mov     ebx, eax
0x14002ec1b  test    eax, eax
0x14002ec1d  js      loc_14002EFA0
0x14002ec23  mov     [rsp+2F0h+dwSize], 104h
0x14002ec2b  xor     eax, eax
0x14002ec2d  mov     [rbp+1F0h+ExeName], ax
0x14002ec31  lea     r9, [rsp+2F0h+dwSize]; lpdwSize
0x14002ec36  lea     r8, [rbp+1F0h+ExeName]; lpExeName
0x14002ec3a  xor     edx, edx; dwFlags
0x14002ec3c  mov     rcx, [r12+r15*8]; hProcess
0x14002ec40  call    cs:__imp_QueryFullProcessImageNameW
0x14002ec47  nop     dword ptr [rax+rax+00h]
0x14002ec4c  test    eax, eax
0x14002ec4e  jz      short loc_14002EC7D
0x14002ec50  cmp     [rsp+2F0h+dwSize], 0
0x14002ec55  jbe     short loc_14002EC7D
0x14002ec57  mov     edx, 5Ch ; '\'; Ch
0x14002ec5c  lea     rcx, [rbp+1F0h+ExeName]; Str
0x14002ec60  call    cs:__imp_wcsrchr
0x14002ec67  nop     dword ptr [rax+rax+00h]
0x14002ec6c  test    rax, rax
0x14002ec6f  jz      short loc_14002EC77
0x14002ec71  add     rax, 2
0x14002ec75  jmp     short loc_14002EC84
0x14002ec77  lea     rax, [rbp+1F0h+ExeName]
0x14002ec7b  jmp     short loc_14002EC84
0x14002ec7d  lea     rax, aQueryError; "QUERY_ERROR"
0x14002ec84  mov     r8, rax; wchar_t *
0x14002ec87  lea     rdx, aProcessName; "PROCESS_NAME"
0x14002ec8e  mov     rcx, rdi; this
0x14002ec91  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ec96  mov     ebx, eax
0x14002ec98  test    eax, eax
0x14002ec9a  js      loc_14002EF75
0x14002eca0  lea     rdx, [rsp+2F0h+var_278]
0x14002eca5  mov     rcx, [r12+r15*8]; hProcess
0x14002eca9  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14002ecae  lea     rdx, aPkgfullname; "PKGFULLNAME"
0x14002ecb5  mov     rcx, rdi; this
0x14002ecb8  test    eax, eax
0x14002ecba  js      loc_14002ED8D
0x14002ecc0  mov     r8, [rsp+2F0h+var_278]; wchar_t *
0x14002ecc5  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ecca  mov     ebx, eax
0x14002eccc  test    eax, eax
0x14002ecce  js      loc_14002EEC9
0x14002ecd4  lea     rdx, [rsp+2F0h+var_298]
0x14002ecd9  mov     rcx, [r12+r15*8]; ProcessHandle
0x14002ecdd  call    ?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14002ece2  test    eax, eax
0x14002ece4  js      short loc_14002ED42
0x14002ece6  lea     r8, [rsp+2F0h+var_2B8]
0x14002eceb  mov     rcx, [rsp+2F0h+var_298]
0x14002ecf0  call    ?ParseApplicationId@PackageUtility@@SAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; PackageUtility::ParseApplicationId(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14002ecf5  test    eax, eax
0x14002ecf7  js      short loc_14002ED42
0x14002ecf9  mov     r8, [rsp+2F0h+var_2B8]; wchar_t *
0x14002ecfe  lea     rdx, aPkgrelappid; "PKGRELAPPID"
0x14002ed05  mov     rcx, rdi; this
0x14002ed08  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ed0d  mov     ebx, eax
0x14002ed0f  test    eax, eax
0x14002ed11  jns     loc_14002EE07
0x14002ed17  lea     rcx, WPP_GLOBAL_Control
0x14002ed1e  mov     rax, cs:WPP_GLOBAL_Control
0x14002ed25  cmp     rax, rcx
0x14002ed28  jz      loc_14002EE4F
0x14002ed2e  test    byte ptr [rax+1Ch], 1
0x14002ed32  jz      loc_14002EE4F
0x14002ed38  mov     edx, 3Bh ; ';'
0x14002ed3d  jmp     loc_14002EB47
0x14002ed42  lea     r8, aQueryError; "QUERY_ERROR"
0x14002ed49  lea     rdx, aPkgrelappid; "PKGRELAPPID"
0x14002ed50  mov     rcx, rdi; this
0x14002ed53  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ed58  mov     ebx, eax
0x14002ed5a  test    eax, eax
0x14002ed5c  jns     loc_14002EE07
0x14002ed62  lea     rcx, WPP_GLOBAL_Control
0x14002ed69  mov     rax, cs:WPP_GLOBAL_Control
0x14002ed70  cmp     rax, rcx
0x14002ed73  jz      loc_14002EE4F
0x14002ed79  test    byte ptr [rax+1Ch], 1
0x14002ed7d  jz      loc_14002EE4F
0x14002ed83  mov     edx, 3Ch ; '<'
0x14002ed88  jmp     loc_14002EB47
0x14002ed8d  cmp     eax, 80073D54h
0x14002ed92  jnz     short loc_14002EDD1
0x14002ed94  lea     r8, aNoPackage; "NO_PACKAGE"
0x14002ed9b  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002eda0  mov     ebx, eax
0x14002eda2  test    eax, eax
0x14002eda4  jns     short loc_14002EDE7
0x14002eda6  lea     rcx, WPP_GLOBAL_Control
0x14002edad  mov     rax, cs:WPP_GLOBAL_Control
0x14002edb4  cmp     rax, rcx
0x14002edb7  jz      loc_14002EE4F
0x14002edbd  test    byte ptr [rax+1Ch], 1
0x14002edc1  jz      loc_14002EE4F
0x14002edc7  mov     edx, 39h ; '9'
0x14002edcc  jmp     loc_14002EB47
0x14002edd1  lea     r8, aQueryError; "QUERY_ERROR"
0x14002edd8  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002eddd  mov     ebx, eax
0x14002eddf  test    eax, eax
0x14002ede1  js      loc_14002EF4A
0x14002ede7  lea     r8, aNoPackage; "NO_PACKAGE"
0x14002edee  lea     rdx, aPkgrelappid; "PKGRELAPPID"
0x14002edf5  mov     rcx, rdi; this
0x14002edf8  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002edfd  mov     ebx, eax
0x14002edff  test    eax, eax
0x14002ee01  js      loc_14002EF1F
0x14002ee07  mov     esi, 1
0x14002ee0c  mov     r8d, esi; int
0x14002ee0f  lea     rdx, aAuxiliaryProce; "AUXILIARY_PROCESS"
0x14002ee16  mov     rcx, rdi; this
0x14002ee19  call    ?WriteEndElementToFile@CWCTInfoWriter@@AEAAJPEB_WH@Z; CWCTInfoWriter::WriteEndElementToFile(wchar_t const *,int)
0x14002ee1e  mov     ebx, eax
0x14002ee20  test    eax, eax
0x14002ee22  js      loc_14002EEF4
0x14002ee28  add     r15d, esi
0x14002ee2b  cmp     r15d, r13d
0x14002ee2e  jb      loc_14002EB6B
0x14002ee34  mov     r8d, esi; int
0x14002ee37  lea     rdx, aAuxiliaryProce_0; "AUXILIARY_PROCESSES"
0x14002ee3e  mov     rcx, rdi; this
0x14002ee41  call    ?WriteEndElementToFile@CWCTInfoWriter@@AEAAJPEB_WH@Z; CWCTInfoWriter::WriteEndElementToFile(wchar_t const *,int)
0x14002ee46  mov     ebx, eax
0x14002ee48  xor     eax, eax
0x14002ee4a  test    ebx, ebx
0x14002ee4c  cmovns  ebx, eax
0x14002ee4f  lea     rax, [rsp+2F0h+var_2A8]
0x14002ee54  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002ee5b  mov     rcx, [rsp+2F0h+var_2B8]; void *
0x14002ee60  cmp     rcx, rax
0x14002ee63  jz      short loc_14002EE6E
0x14002ee65  mov     rdx, rdi; struct std::nothrow_t *
0x14002ee68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002ee6d  nop
0x14002ee6e  lea     rax, [rsp+2F0h+var_288]
0x14002ee73  mov     rcx, [rsp+2F0h+var_298]; void *
0x14002ee78  cmp     rcx, rax
0x14002ee7b  jz      short loc_14002EE86
0x14002ee7d  mov     rdx, rdi; struct std::nothrow_t *
0x14002ee80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002ee85  nop
0x14002ee86  lea     rax, [rbp+1F0h+var_268]
0x14002ee8a  mov     rcx, [rsp+2F0h+var_278]; void *
0x14002ee8f  cmp     rcx, rax
0x14002ee92  jz      short loc_14002EE9C
0x14002ee94  mov     rdx, rdi; struct std::nothrow_t *
0x14002ee97  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002ee9c  mov     eax, ebx
0x14002ee9e  mov     rcx, [rbp+1F0h+var_40]
0x14002eea5  xor     rcx, rsp; StackCookie
0x14002eea8  call    __security_check_cookie
0x14002eead  mov     rbx, [rsp+2F0h+arg_10]
0x14002eeb5  add     rsp, 2C0h
0x14002eebc  pop     r15
0x14002eebe  pop     r14
0x14002eec0  pop     r13
0x14002eec2  pop     r12
0x14002eec4  pop     rdi
0x14002eec5  pop     rsi
0x14002eec6  pop     rbp
0x14002eec7  retn
0x14002eec9  lea     rcx, WPP_GLOBAL_Control
0x14002eed0  mov     rax, cs:WPP_GLOBAL_Control
0x14002eed7  cmp     rax, rcx
0x14002eeda  jz      loc_14002EE4F
0x14002eee0  test    byte ptr [rax+1Ch], 1
0x14002eee4  jz      loc_14002EE4F
0x14002eeea  mov     edx, 38h ; '8'
0x14002eeef  jmp     loc_14002EB47
0x14002eef4  lea     rcx, WPP_GLOBAL_Control
0x14002eefb  mov     rax, cs:WPP_GLOBAL_Control
0x14002ef02  cmp     rax, rcx
0x14002ef05  jz      loc_14002EE4F
0x14002ef0b  test    [rax+1Ch], sil
0x14002ef0f  jz      loc_14002EE4F
0x14002ef15  mov     edx, 3Eh ; '>'
0x14002ef1a  jmp     loc_14002EB47
0x14002ef1f  lea     rcx, WPP_GLOBAL_Control
0x14002ef26  mov     rax, cs:WPP_GLOBAL_Control
0x14002ef2d  cmp     rax, rcx
0x14002ef30  jz      loc_14002EE4F
  ... truncated ...
```
