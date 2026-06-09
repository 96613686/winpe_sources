# CWCTInfoWriter::WriteAuxProcListToFile(void * *,ulong)

- ea: `0x14002cc4c`
- end: `0x14002d23e`
- name: `?WriteAuxProcListToFile@CWCTInfoWriter@@AEAAJPEAPEAXK@Z`
- size: `1522`
- prototype: `__int64 __fastcall(CWCTInfoWriter *__hidden this, void **, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14002d8f4`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x14000b540`
- `0x140014474`
- `0x140015b40`
- `0x14002cc4c`
- `0x14002d484`
- `0x14002d51c`
- `0x14002d5fc`
- `0x14002dd7c`
- `0x140032628`
- `0x140032850`
- `0x140032a48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14002ce58`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14002ce58`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002cd7f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002cd7f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14002ce3e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14002ce3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWCTInfoWriter::WriteAuxProcListToFile(CWCTInfoWriter *this, void **a2, unsigned int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // ebx
  CUserModeHangReport *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rcx
  DWORD ProcessId; // esi
  wchar_t *v14; // rax
  WCHAR *v15; // rax
  int ProcessPackageFullName; // eax
  __int64 v17; // rdx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v21[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v22; // [rsp+58h] [rbp-A8h]
  _WORD *v23; // [rsp+60h] [rbp-A0h]
  _WORD v24[8]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v25; // [rsp+78h] [rbp-88h]
  _WORD *v26; // [rsp+80h] [rbp-80h]
  _WORD v27[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ExeName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v25 = v27;
  v26 = v27;
  v27[0] = 0;
  v22 = v24;
  v23 = v24;
  v24[0] = 0;
  v20[0] = v21;
  v20[1] = v21;
  v21[0] = 0;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 0;
  if ( *((_QWORD *)this + 1) == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_QWORD *)this + 4) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v8 = CWCTInfoWriter::WriteStartElementToFileWithAttributes(this, L"AUXILIARY_PROCESSES", 0, 0, 1);
  if ( v8 >= 0 )
  {
    v11 = 0;
    if ( a3 )
    {
      while ( 1 )
      {
        if ( !a2[v11] )
          MicrosoftTelemetryAssertTriggeredNoArgs(v7);
        ProcessId = GetProcessId(a2[v11]);
        if ( !ProcessId )
          MicrosoftTelemetryAssertTriggeredNoArgs(v12);
        v8 = CWCTInfoWriter::WriteStartElementToFileWithAttributes(this, L"AUXILIARY_PROCESS", 0, 0, 1);
        if ( v8 < 0 )
          break;
        v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PID", ProcessId, 0);
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 52;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        dwSize = 32;
        ExeName[0] = 0;
        v8 = StringCchPrintfW(ExeName, 0x20u, L"triagedump.%04x.dmp", ProcessId);
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 53;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"FILE", ExeName);
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 54;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        dwSize = 260;
        ExeName[0] = 0;
        if ( QueryFullProcessImageNameW(a2[v11], 0, ExeName, &dwSize) && dwSize )
        {
          v14 = wcsrchr(ExeName, 0x5Cu);
          if ( v14 )
            v15 = v14 + 1;
          else
            v15 = ExeName;
        }
        else
        {
          v15 = (WCHAR *)L"QUERY_ERROR";
        }
        v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PROCESS_NAME", v15);
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 55;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(a2[v11]);
        if ( ProcessPackageFullName < 0 )
        {
          if ( ProcessPackageFullName == -2147009196 )
          {
            v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGFULLNAME", L"NO_PACKAGE");
            if ( v8 < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v10 = 57;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
          else
          {
            v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGFULLNAME", L"QUERY_ERROR");
            if ( v8 < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v10 = 58;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
          v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGRELAPPID", L"NO_PACKAGE");
          if ( v8 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 61;
              goto LABEL_9;
            }
            goto LABEL_49;
          }
        }
        else
        {
          v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGFULLNAME", v25);
          if ( v8 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 56;
              goto LABEL_9;
            }
            goto LABEL_49;
          }
          if ( (int)PackageUtility::GetProcessApplicationId(a2[v11]) < 0
            || (int)PackageUtility::ParseApplicationId(v22, v17, v20) < 0 )
          {
            v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGRELAPPID", L"QUERY_ERROR");
            if ( v8 < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v10 = 60;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
          else
          {
            v8 = CWCTInfoWriter::WriteElementWithContentToFile(this, L"PKGRELAPPID", v20[0]);
            if ( v8 < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v10 = 59;
                goto LABEL_9;
              }
              goto LABEL_49;
            }
          }
        }
        v8 = CWCTInfoWriter::WriteEndElementToFile(this, L"AUXILIARY_PROCESS", 1);
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 62;
            goto LABEL_9;
          }
          goto LABEL_49;
        }
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= a3 )
          goto LABEL_47;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 51;
        goto LABEL_9;
      }
    }
    else
    {
LABEL_47:
      v8 = CWCTInfoWriter::WriteEndElementToFile(this, L"AUXILIARY_PROCESSES", 1);
      if ( v8 >= 0 )
        v8 = 0;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 50;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids, (unsigned int)v8);
    }
  }
LABEL_49:
  if ( v20[0] != v21 )
    operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v22 != v24 )
    operator delete(v22, (const struct std::nothrow_t *)&std::nothrow);
  if ( v25 != v27 )
    operator delete(v25, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002cc4c  mov     [rsp-8+arg_10], rbx
0x14002cc51  push    rbp
0x14002cc52  push    rsi
0x14002cc53  push    rdi
0x14002cc54  push    r12
0x14002cc56  push    r13
0x14002cc58  push    r14
0x14002cc5a  push    r15
0x14002cc5c  lea     rbp, [rsp-1C0h]
0x14002cc64  sub     rsp, 2C0h
0x14002cc6b  mov     rax, cs:__security_cookie
0x14002cc72  xor     rax, rsp
0x14002cc75  mov     [rbp+1F0h+var_40], rax
0x14002cc7c  mov     r13d, r8d
0x14002cc7f  mov     r12, rdx
0x14002cc82  mov     rdi, rcx
0x14002cc85  lea     rax, [rbp+1F0h+var_268]
0x14002cc89  mov     [rsp+2F0h+var_278], rax
0x14002cc8e  lea     rax, [rbp+1F0h+var_268]
0x14002cc92  mov     [rbp+1F0h+var_270], rax
0x14002cc96  xor     eax, eax
0x14002cc98  mov     [rbp+1F0h+var_268], ax
0x14002cc9c  lea     rax, [rsp+2F0h+var_288]
0x14002cca1  mov     [rsp+2F0h+var_298], rax
0x14002cca6  lea     rax, [rsp+2F0h+var_288]
0x14002ccab  mov     [rsp+2F0h+var_290], rax
0x14002ccb0  xor     eax, eax
0x14002ccb2  mov     [rsp+2F0h+var_288], ax
0x14002ccb7  lea     rax, [rsp+2F0h+var_2A8]
0x14002ccbc  mov     [rsp+2F0h+var_2B8], rax
0x14002ccc1  lea     rax, [rsp+2F0h+var_2A8]
0x14002ccc6  mov     [rsp+2F0h+var_2B0], rax
0x14002cccb  xor     eax, eax
0x14002cccd  mov     [rsp+2F0h+var_2A8], ax
0x14002ccd2  xor     edx, edx; Val
0x14002ccd4  mov     r8d, 208h; Size
0x14002ccda  lea     rcx, [rbp+1F0h+ExeName]; void *
0x14002ccde  call    memset_0
0x14002cce3  mov     [rsp+2F0h+dwSize], 0
0x14002cceb  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14002ccf0  jnz     short loc_14002CCF7
0x14002ccf2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002ccf7  cmp     qword ptr [rdi+20h], 0
0x14002ccfc  jnz     short loc_14002CD03
0x14002ccfe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002cd03  mov     esi, 1
0x14002cd08  mov     [rsp+2F0h+var_2D0], esi; int
0x14002cd0c  xor     r9d, r9d; int
0x14002cd0f  xor     r8d, r8d; struct CWCTInfoWriter::XmlAttribute *
0x14002cd12  lea     rdx, aAuxiliaryProce_0; "AUXILIARY_PROCESSES"
0x14002cd19  mov     rcx, rdi; this
0x14002cd1c  call    ?WriteStartElementToFileWithAttributes@CWCTInfoWriter@@AEAAJPEB_WPEAUXmlAttribute@1@HH@Z; CWCTInfoWriter::WriteStartElementToFileWithAttributes(wchar_t const *,CWCTInfoWriter::XmlAttribute *,int,int)
0x14002cd21  mov     ebx, eax
0x14002cd23  test    eax, eax
0x14002cd25  jns     short loc_14002CD63
0x14002cd27  lea     rcx, WPP_GLOBAL_Control
0x14002cd2e  mov     rax, cs:WPP_GLOBAL_Control
0x14002cd35  cmp     rax, rcx
0x14002cd38  jz      loc_14002D041
0x14002cd3e  test    [rax+1Ch], sil
0x14002cd42  jz      loc_14002D041
0x14002cd48  lea     edx, [rsi+31h]
0x14002cd4b  mov     r9d, ebx
0x14002cd4e  lea     r8, WPP_717fe7b68fda31d0249477bcdbbfd81e_Traceguids
0x14002cd55  mov     rcx, [rax+10h]
0x14002cd59  call    WPP_SF_d
0x14002cd5e  jmp     loc_14002D041
0x14002cd63  xor     r15d, r15d
0x14002cd66  test    r13d, r13d
0x14002cd69  jz      loc_14002D026
0x14002cd6f  cmp     qword ptr [r12+r15*8], 0
0x14002cd74  jnz     short loc_14002CD7B
0x14002cd76  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002cd7b  mov     rcx, [r12+r15*8]; Process
0x14002cd7f  call    cs:__imp_GetProcessId
0x14002cd85  mov     esi, eax
0x14002cd87  test    eax, eax
0x14002cd89  jnz     short loc_14002CD90
0x14002cd8b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002cd90  mov     [rsp+2F0h+var_2D0], 1; int
0x14002cd98  xor     r9d, r9d; int
0x14002cd9b  xor     r8d, r8d; struct CWCTInfoWriter::XmlAttribute *
0x14002cd9e  lea     rdx, aAuxiliaryProce; "AUXILIARY_PROCESS"
0x14002cda5  mov     rcx, rdi; this
0x14002cda8  call    ?WriteStartElementToFileWithAttributes@CWCTInfoWriter@@AEAAJPEB_WPEAUXmlAttribute@1@HH@Z; CWCTInfoWriter::WriteStartElementToFileWithAttributes(wchar_t const *,CWCTInfoWriter::XmlAttribute *,int,int)
0x14002cdad  mov     ebx, eax
0x14002cdaf  test    eax, eax
0x14002cdb1  js      loc_14002D212
0x14002cdb7  xor     r9d, r9d; unsigned int
0x14002cdba  mov     r8d, esi; unsigned int
0x14002cdbd  lea     rdx, aPid; "PID"
0x14002cdc4  mov     rcx, rdi; this
0x14002cdc7  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_WKK@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,ulong,ulong)
0x14002cdcc  mov     ebx, eax
0x14002cdce  test    eax, eax
0x14002cdd0  js      loc_14002D1E7
0x14002cdd6  mov     ecx, 20h ; ' '
0x14002cddb  mov     [rsp+2F0h+dwSize], ecx
0x14002cddf  xor     eax, eax
0x14002cde1  mov     [rbp+1F0h+ExeName], ax
0x14002cde5  mov     r9d, esi
0x14002cde8  lea     r8, aTriagedump04xD; "triagedump.%04x.dmp"
0x14002cdef  mov     edx, ecx; unsigned __int64
0x14002cdf1  lea     rcx, [rbp+1F0h+ExeName]; wchar_t *
0x14002cdf5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14002cdfa  mov     ebx, eax
0x14002cdfc  test    eax, eax
0x14002cdfe  js      loc_14002D1BC
0x14002ce04  lea     r8, [rbp+1F0h+ExeName]; wchar_t *
0x14002ce08  lea     rdx, aFile; "FILE"
0x14002ce0f  mov     rcx, rdi; this
0x14002ce12  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ce17  mov     ebx, eax
0x14002ce19  test    eax, eax
0x14002ce1b  js      loc_14002D191
0x14002ce21  mov     [rsp+2F0h+dwSize], 104h
0x14002ce29  xor     eax, eax
0x14002ce2b  mov     [rbp+1F0h+ExeName], ax
0x14002ce2f  lea     r9, [rsp+2F0h+dwSize]; lpdwSize
0x14002ce34  lea     r8, [rbp+1F0h+ExeName]; lpExeName
0x14002ce38  xor     edx, edx; dwFlags
0x14002ce3a  mov     rcx, [r12+r15*8]; hProcess
0x14002ce3e  call    cs:__imp_QueryFullProcessImageNameW
0x14002ce44  test    eax, eax
0x14002ce46  jz      short loc_14002CE6F
0x14002ce48  cmp     [rsp+2F0h+dwSize], 0
0x14002ce4d  jbe     short loc_14002CE6F
0x14002ce4f  mov     edx, 5Ch ; '\'; Ch
0x14002ce54  lea     rcx, [rbp+1F0h+ExeName]; Str
0x14002ce58  call    cs:__imp_wcsrchr
0x14002ce5e  test    rax, rax
0x14002ce61  jz      short loc_14002CE69
0x14002ce63  add     rax, 2
0x14002ce67  jmp     short loc_14002CE76
0x14002ce69  lea     rax, [rbp+1F0h+ExeName]
0x14002ce6d  jmp     short loc_14002CE76
0x14002ce6f  lea     rax, aQueryError; "QUERY_ERROR"
0x14002ce76  mov     r8, rax; wchar_t *
0x14002ce79  lea     rdx, aProcessName; "PROCESS_NAME"
0x14002ce80  mov     rcx, rdi; this
0x14002ce83  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ce88  mov     ebx, eax
0x14002ce8a  test    eax, eax
0x14002ce8c  js      loc_14002D166
0x14002ce92  lea     rdx, [rsp+2F0h+var_278]
0x14002ce97  mov     rcx, [r12+r15*8]; hProcess
0x14002ce9b  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14002cea0  lea     rdx, aPkgfullname; "PKGFULLNAME"
0x14002cea7  mov     rcx, rdi; this
0x14002ceaa  test    eax, eax
0x14002ceac  js      loc_14002CF7F
0x14002ceb2  mov     r8, [rsp+2F0h+var_278]; wchar_t *
0x14002ceb7  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002cebc  mov     ebx, eax
0x14002cebe  test    eax, eax
0x14002cec0  js      loc_14002D0BA
0x14002cec6  lea     rdx, [rsp+2F0h+var_298]
0x14002cecb  mov     rcx, [r12+r15*8]; ProcessHandle
0x14002cecf  call    ?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14002ced4  test    eax, eax
0x14002ced6  js      short loc_14002CF34
0x14002ced8  lea     r8, [rsp+2F0h+var_2B8]
0x14002cedd  mov     rcx, [rsp+2F0h+var_298]
0x14002cee2  call    ?ParseApplicationId@PackageUtility@@SAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; PackageUtility::ParseApplicationId(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14002cee7  test    eax, eax
0x14002cee9  js      short loc_14002CF34
0x14002ceeb  mov     r8, [rsp+2F0h+var_2B8]; wchar_t *
0x14002cef0  lea     rdx, aPkgrelappid; "PKGRELAPPID"
0x14002cef7  mov     rcx, rdi; this
0x14002cefa  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002ceff  mov     ebx, eax
0x14002cf01  test    eax, eax
0x14002cf03  jns     loc_14002CFF9
0x14002cf09  lea     rcx, WPP_GLOBAL_Control
0x14002cf10  mov     rax, cs:WPP_GLOBAL_Control
0x14002cf17  cmp     rax, rcx
0x14002cf1a  jz      loc_14002D041
0x14002cf20  test    byte ptr [rax+1Ch], 1
0x14002cf24  jz      loc_14002D041
0x14002cf2a  mov     edx, 3Bh ; ';'
0x14002cf2f  jmp     loc_14002CD4B
0x14002cf34  lea     r8, aQueryError; "QUERY_ERROR"
0x14002cf3b  lea     rdx, aPkgrelappid; "PKGRELAPPID"
0x14002cf42  mov     rcx, rdi; this
0x14002cf45  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002cf4a  mov     ebx, eax
0x14002cf4c  test    eax, eax
0x14002cf4e  jns     loc_14002CFF9
0x14002cf54  lea     rcx, WPP_GLOBAL_Control
0x14002cf5b  mov     rax, cs:WPP_GLOBAL_Control
0x14002cf62  cmp     rax, rcx
0x14002cf65  jz      loc_14002D041
0x14002cf6b  test    byte ptr [rax+1Ch], 1
0x14002cf6f  jz      loc_14002D041
0x14002cf75  mov     edx, 3Ch ; '<'
0x14002cf7a  jmp     loc_14002CD4B
0x14002cf7f  cmp     eax, 80073D54h
0x14002cf84  jnz     short loc_14002CFC3
0x14002cf86  lea     r8, aNoPackage; "NO_PACKAGE"
0x14002cf8d  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002cf92  mov     ebx, eax
0x14002cf94  test    eax, eax
0x14002cf96  jns     short loc_14002CFD9
0x14002cf98  lea     rcx, WPP_GLOBAL_Control
0x14002cf9f  mov     rax, cs:WPP_GLOBAL_Control
0x14002cfa6  cmp     rax, rcx
0x14002cfa9  jz      loc_14002D041
0x14002cfaf  test    byte ptr [rax+1Ch], 1
0x14002cfb3  jz      loc_14002D041
0x14002cfb9  mov     edx, 39h ; '9'
0x14002cfbe  jmp     loc_14002CD4B
0x14002cfc3  lea     r8, aQueryError; "QUERY_ERROR"
0x14002cfca  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002cfcf  mov     ebx, eax
0x14002cfd1  test    eax, eax
0x14002cfd3  js      loc_14002D13B
0x14002cfd9  lea     r8, aNoPackage; "NO_PACKAGE"
0x14002cfe0  lea     rdx, aPkgrelappid; "PKGRELAPPID"
0x14002cfe7  mov     rcx, rdi; this
0x14002cfea  call    ?WriteElementWithContentToFile@CWCTInfoWriter@@AEAAJPEB_W0@Z; CWCTInfoWriter::WriteElementWithContentToFile(wchar_t const *,wchar_t const *)
0x14002cfef  mov     ebx, eax
0x14002cff1  test    eax, eax
0x14002cff3  js      loc_14002D110
0x14002cff9  mov     esi, 1
0x14002cffe  mov     r8d, esi; int
0x14002d001  lea     rdx, aAuxiliaryProce; "AUXILIARY_PROCESS"
0x14002d008  mov     rcx, rdi; this
0x14002d00b  call    ?WriteEndElementToFile@CWCTInfoWriter@@AEAAJPEB_WH@Z; CWCTInfoWriter::WriteEndElementToFile(wchar_t const *,int)
0x14002d010  mov     ebx, eax
0x14002d012  test    eax, eax
0x14002d014  js      loc_14002D0E5
0x14002d01a  add     r15d, esi
0x14002d01d  cmp     r15d, r13d
0x14002d020  jb      loc_14002CD6F
0x14002d026  mov     r8d, esi; int
0x14002d029  lea     rdx, aAuxiliaryProce_0; "AUXILIARY_PROCESSES"
0x14002d030  mov     rcx, rdi; this
0x14002d033  call    ?WriteEndElementToFile@CWCTInfoWriter@@AEAAJPEB_WH@Z; CWCTInfoWriter::WriteEndElementToFile(wchar_t const *,int)
0x14002d038  mov     ebx, eax
0x14002d03a  xor     eax, eax
0x14002d03c  test    ebx, ebx
0x14002d03e  cmovns  ebx, eax
0x14002d041  lea     rax, [rsp+2F0h+var_2A8]
0x14002d046  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002d04d  mov     rcx, [rsp+2F0h+var_2B8]; void *
0x14002d052  cmp     rcx, rax
0x14002d055  jz      short loc_14002D060
0x14002d057  mov     rdx, rdi; struct std::nothrow_t *
0x14002d05a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d05f  nop
0x14002d060  lea     rax, [rsp+2F0h+var_288]
0x14002d065  mov     rcx, [rsp+2F0h+var_298]; void *
0x14002d06a  cmp     rcx, rax
0x14002d06d  jz      short loc_14002D078
0x14002d06f  mov     rdx, rdi; struct std::nothrow_t *
0x14002d072  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d077  nop
0x14002d078  lea     rax, [rbp+1F0h+var_268]
0x14002d07c  mov     rcx, [rsp+2F0h+var_278]; void *
0x14002d081  cmp     rcx, rax
0x14002d084  jz      short loc_14002D08E
0x14002d086  mov     rdx, rdi; struct std::nothrow_t *
0x14002d089  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002d08e  mov     eax, ebx
0x14002d090  mov     rcx, [rbp+1F0h+var_40]
0x14002d097  xor     rcx, rsp; StackCookie
0x14002d09a  call    __security_check_cookie
0x14002d09f  mov     rbx, [rsp+2F0h+arg_10]
0x14002d0a7  add     rsp, 2C0h
0x14002d0ae  pop     r15
0x14002d0b0  pop     r14
0x14002d0b2  pop     r13
0x14002d0b4  pop     r12
0x14002d0b6  pop     rdi
0x14002d0b7  pop     rsi
0x14002d0b8  pop     rbp
0x14002d0b9  retn
0x14002d0ba  lea     rcx, WPP_GLOBAL_Control
0x14002d0c1  mov     rax, cs:WPP_GLOBAL_Control
0x14002d0c8  cmp     rax, rcx
0x14002d0cb  jz      loc_14002D041
0x14002d0d1  test    byte ptr [rax+1Ch], 1
0x14002d0d5  jz      loc_14002D041
0x14002d0db  mov     edx, 38h ; '8'
0x14002d0e0  jmp     loc_14002CD4B
0x14002d0e5  lea     rcx, WPP_GLOBAL_Control
0x14002d0ec  mov     rax, cs:WPP_GLOBAL_Control
0x14002d0f3  cmp     rax, rcx
0x14002d0f6  jz      loc_14002D041
0x14002d0fc  test    [rax+1Ch], sil
0x14002d100  jz      loc_14002D041
0x14002d106  mov     edx, 3Eh ; '>'
0x14002d10b  jmp     loc_14002CD4B
0x14002d110  lea     rcx, WPP_GLOBAL_Control
0x14002d117  mov     rax, cs:WPP_GLOBAL_Control
0x14002d11e  cmp     rax, rcx
0x14002d121  jz      loc_14002D041
0x14002d127  test    byte ptr [rax+1Ch], 1
0x14002d12b  jz      loc_14002D041
0x14002d131  mov     edx, 3Dh ; '='
  ... truncated ...
```
