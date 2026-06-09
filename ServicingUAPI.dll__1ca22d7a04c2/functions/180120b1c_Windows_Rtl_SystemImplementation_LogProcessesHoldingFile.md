# Windows::Rtl::SystemImplementation::LogProcessesHoldingFile

- ea: `0x180120b1c`
- end: `0x1801210ab`
- name: `Windows::Rtl::SystemImplementation::LogProcessesHoldingFile`
- size: `1423`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180122600`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x18000e098`
- `0x1800235a0`
- `0x18003104c`
- `0x180120b1c`

## import_xrefs

- `ntdll!NtOpenProcess` at `0x180120d67`
- `ntdll!NtOpenProcess` at `0x180120d67`
- `ntdll!NtQueryInformationProcess` at `0x180120e11`
- `ntdll!NtQueryInformationProcess` at `0x180120e11`
- `ntdll!NtQueryInformationFile` at `0x180120bf5`
- `ntdll!NtQueryInformationFile` at `0x180120bf5`
- `ntdll!NtClose` at `0x180120bab`
- `ntdll!NtClose` at `0x180120c15`
- `ntdll!NtClose` at `0x180120ce5`
- `ntdll!NtClose` at `0x180120f79`
- `ntdll!NtClose` at `0x180121000`
- `ntdll!NtClose` at `0x18012105a`
- `ntdll!NtClose` at `0x18012108b`
- `ntdll!NtClose` at `0x180120bab`
- `ntdll!NtClose` at `0x180120c15`
- `ntdll!NtClose` at `0x180120ce5`
- `ntdll!NtClose` at `0x180120f79`
- `ntdll!NtClose` at `0x180121000`
- `ntdll!NtClose` at `0x18012105a`
- `ntdll!NtClose` at `0x18012108b`
- `ntdll!NtOpenFile` at `0x180120b8b`
- `ntdll!NtOpenFile` at `0x180120b8b`

## string_xrefs

- `0x180120f5a`: `Failed to query image path for process {0} with status {1}.`
- `0x180120dc7`: `Failed to open process {0} with status {1}.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::LogProcessesHoldingFile(POBJECT_ATTRIBUTES ObjectAttributes)
{
  NTSTATUS v2; // ebx
  PUNICODE_STRING ObjectName; // rax
  unsigned int v5; // edx
  int v6; // ebx
  unsigned int v7; // edx
  unsigned int v8; // edx
  int *v9; // rdx
  __int64 v10; // rcx
  int v11; // edi
  __int128 v12; // xmm2
  const wchar_t *v13; // xmm3_8
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v14[2]; // [rsp+38h] [rbp-D0h] BYREF
  _CLIENT_ID ClientId; // [rsp+48h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributesa; // [rsp+58h] [rbp-B0h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-80h] BYREF
  NTSTATUS InformationProcess; // [rsp+90h] [rbp-78h] BYREF
  void *ProcessHandle; // [rsp+98h] [rbp-70h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-68h] BYREF
  const wchar_t *v21; // [rsp+B0h] [rbp-58h]
  __int128 v22; // [rsp+B8h] [rbp-50h] BYREF
  const wchar_t *v23; // [rsp+C8h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-38h] BYREF
  _DWORD FileInformation[132]; // [rsp+E8h] [rbp-20h] BYREF
  _WORD ProcessInformation[4]; // [rsp+2F8h] [rbp+1F0h] BYREF
  const wchar_t *v27; // [rsp+300h] [rbp+1F8h]
  unsigned __int64 v28[2]; // [rsp+518h] [rbp+410h] BYREF
  const wchar_t *v29; // [rsp+528h] [rbp+420h]
  __m128i v30; // [rsp+530h] [rbp+428h]
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **Buffer; // [rsp+540h] [rbp+438h]
  __int64 v32; // [rsp+548h] [rbp+440h]
  __int64 v33; // [rsp+550h] [rbp+448h]
  const wchar_t *v34; // [rsp+558h] [rbp+450h]

  v14[1] = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)-2LL;
  FileHandle = 0;
  IoStatusBlock = 0;
  InformationProcess = 0;
  v2 = NtOpenFile(&FileHandle, 0x100080u, ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
  if ( v2 < 0 )
  {
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(FileHandle) < 0 )
        __fastfail(7u);
      FileHandle = 0;
    }
    return (unsigned int)v2;
  }
  memset_0(FileInformation, 0, 0x208u);
  v2 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x208u, FileProcessIdsUsingFileInformation);
  if ( v2 < 0 )
  {
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(FileHandle) < 0 )
        __fastfail(7u);
      FileHandle = 0;
    }
    return (unsigned int)v2;
  }
  v20 = 0;
  v21 = 0;
  ObjectName = ObjectAttributes->ObjectName;
  v28[0] = 36;
  v28[1] = 38;
  v29 = L"Processes holding ";
  v30 = _mm_unpacklo_epi32(
          _mm_unpacklo_epi16(_mm_cvtsi32_si128(*(_DWORD *)&ObjectName->Length), (__m128i)0LL),
          (__m128i)0LL);
  Buffer = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **)ObjectName->Buffer;
  v32 = 4;
  v33 = 6;
  v34 = L": ";
  v14[0] = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)&v20;
  v2 = Windows::StringUtil::Rtl::ConcatenateStringsInList<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>,0>(
         3,
         v28,
         v14);
  if ( v2 < 0 )
  {
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v20);
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(FileHandle) < 0 )
        __fastfail(7u);
      FileHandle = 0;
    }
    return (unsigned int)v2;
  }
  v6 = 0;
  if ( !FileInformation[0] )
  {
LABEL_35:
    v28[0] = 0;
    v28[1] = (unsigned __int64)`Windows::Tracing::RtlFormatIntoStream<_LUNICODE_STRING,wchar_t const *>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
    v29 = (const wchar_t *)&v20;
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      v5,
      (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"{0}",
      (const char *const)1,
      (unsigned __int64)v28,
      v14[0]);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v20);
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(FileHandle) < 0 )
        __fastfail(7u);
      FileHandle = 0;
    }
    return 0;
  }
  while ( 1 )
  {
    ClientId.UniqueThread = 0;
    ClientId.UniqueProcess = *(HANDLE *)&FileInformation[2 * v6 + 2];
    *(_QWORD *)&ObjectAttributesa.Length = 48;
    memset(&ObjectAttributesa.RootDirectory, 0, 40);
    ProcessHandle = 0;
    InformationProcess = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributesa, &ClientId);
    if ( InformationProcess >= 0 )
      break;
    v28[0] = 0;
    v28[1] = (unsigned __int64)Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG;
    v29 = (const wchar_t *)&FileInformation[2 * v6 + 2];
    v30.m128i_i64[0] = 0;
    v30.m128i_i64[1] = (__int64)`Windows::WCP::Rtl::RtlAutoTrace<_OBJECT_ATTRIBUTES *,Windows::WCP::Rtl::FormatNtStatusWrapper<long>>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
    Buffer = v14;
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      v7,
      (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Failed to open process {0} with status {1}.",
      (const char *const)2,
      (unsigned __int64)v28,
      (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *const)&InformationProcess);
LABEL_30:
    if ( ProcessHandle )
    {
      if ( NtClose(ProcessHandle) < 0 )
        __fastfail(7u);
      ProcessHandle = 0;
    }
    if ( (unsigned int)++v6 >= FileInformation[0] )
      goto LABEL_35;
  }
  memset_0(ProcessInformation, 0, 0x218u);
  InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, ProcessInformation, 0x218u, 0);
  if ( InformationProcess < 0 )
  {
    v28[0] = 0;
    v28[1] = (unsigned __int64)Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG;
    v29 = (const wchar_t *)&FileInformation[2 * v6 + 2];
    v30.m128i_i64[0] = 0;
    v30.m128i_i64[1] = (__int64)`Windows::WCP::Rtl::RtlAutoTrace<_OBJECT_ATTRIBUTES *,Windows::WCP::Rtl::FormatNtStatusWrapper<long>>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
    Buffer = v14;
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      v8,
      (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Failed to query image path for process {0} with status {1}.",
      (const char *const)2,
      (unsigned __int64)v28,
      (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *const)&InformationProcess);
    goto LABEL_30;
  }
  v22 = 0;
  v23 = 0;
  v9 = &dword_1801CAD7C;
  if ( v6 )
    v9 = (int *)L", ";
  *(_OWORD *)v28 = v20;
  v29 = v21;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)v9 + v10) );
  v30.m128i_i64[0] = 2 * v10;
  v30.m128i_i64[1] = 2 * v10 + 2;
  Buffer = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **)v9;
  v32 = ProcessInformation[0];
  v33 = ProcessInformation[1];
  v34 = v27;
  v14[0] = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)&v22;
  v11 = Windows::StringUtil::Rtl::ConcatenateStringsInList<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>,0>(
          3,
          v28,
          v14);
  if ( v11 >= 0 )
  {
    v12 = v20;
    v13 = v21;
    v20 = v22;
    v21 = v23;
    v22 = v12;
    v23 = v13;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v22);
    goto LABEL_30;
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v22);
  if ( ProcessHandle )
  {
    if ( NtClose(ProcessHandle) < 0 )
      __fastfail(7u);
    ProcessHandle = 0;
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v20);
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(FileHandle) < 0 )
      __fastfail(7u);
    FileHandle = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180120b1c  mov     rax, rsp
0x180120b1f  push    rbp
0x180120b20  push    rdi
0x180120b21  push    r12
0x180120b23  push    r13
0x180120b25  push    r14
0x180120b27  lea     rbp, [rax-498h]
0x180120b2e  sub     rsp, 570h
0x180120b35  mov     [rsp+590h+var_558], 0FFFFFFFFFFFFFFFEh
0x180120b3e  mov     [rax+10h], rbx
0x180120b42  mov     [rax+18h], rsi
0x180120b46  mov     rax, cs:__security_cookie
0x180120b4d  xor     rax, rsp
0x180120b50  mov     [rbp+490h+var_30], rax
0x180120b57  mov     rdi, rcx
0x180120b5a  xor     esi, esi
0x180120b5c  mov     [rbp+490h+FileHandle], rsi
0x180120b60  xorps   xmm0, xmm0
0x180120b63  movups  xmmword ptr [rbp+490h+IoStatusBlock], xmm0
0x180120b67  mov     [rbp+490h+var_508], esi
0x180120b6a  mov     [rsp+590h+OpenOptions], 4020h; OpenOptions
0x180120b72  lea     r14d, [rsi+7]
0x180120b76  mov     [rsp+590h+ShareAccess], r14d; ShareAccess
0x180120b7b  lea     r9, [rbp+490h+IoStatusBlock]; IoStatusBlock
0x180120b7f  mov     r8, rcx; ObjectAttributes
0x180120b82  mov     edx, 100080h; DesiredAccess
0x180120b87  lea     rcx, [rbp+490h+FileHandle]; FileHandle
0x180120b8b  call    cs:__imp_NtOpenFile
0x180120b92  nop     dword ptr [rax+rax+00h]
0x180120b97  mov     ebx, eax
0x180120b99  test    eax, eax
0x180120b9b  jns     short loc_180120BCB
0x180120b9d  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180120ba1  lea     rdx, [rcx-1]
0x180120ba5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180120ba9  ja      short loc_180120BC4
0x180120bab  call    cs:__imp_NtClose
0x180120bb2  nop     dword ptr [rax+rax+00h]
0x180120bb7  test    eax, eax
0x180120bb9  jns     short loc_180120BC0
0x180120bbb  mov     ecx, r14d
0x180120bbe  int     29h; Win8: RtlFailFast(ecx)
0x180120bc0  mov     [rbp+490h+FileHandle], rsi
0x180120bc4  mov     eax, ebx
0x180120bc6  jmp     loc_18012101B
0x180120bcb  mov     ebx, 208h
0x180120bd0  mov     r8d, ebx; Size
0x180120bd3  xor     edx, edx; Val
0x180120bd5  lea     rcx, [rbp+490h+FileInformation]; void *
0x180120bd9  call    memset_0
0x180120bde  mov     [rsp+590h+ShareAccess], 2Fh ; '/'; FileInformationClass
0x180120be6  mov     r9d, ebx; Length
0x180120be9  lea     r8, [rbp+490h+FileInformation]; FileInformation
0x180120bed  lea     rdx, [rbp+490h+IoStatusBlock]; IoStatusBlock
0x180120bf1  mov     rcx, [rbp+490h+FileHandle]; FileHandle
0x180120bf5  call    cs:__imp_NtQueryInformationFile
0x180120bfc  nop     dword ptr [rax+rax+00h]
0x180120c01  mov     ebx, eax
0x180120c03  test    eax, eax
0x180120c05  jns     short loc_180120C30
0x180120c07  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180120c0b  lea     rdx, [rcx-1]
0x180120c0f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180120c13  ja      short loc_180120C2E
0x180120c15  call    cs:__imp_NtClose
0x180120c1c  nop     dword ptr [rax+rax+00h]
0x180120c21  test    eax, eax
0x180120c23  jns     short loc_180120C2A
0x180120c25  mov     rcx, r14
0x180120c28  int     29h; Win8: RtlFailFast(ecx)
0x180120c2a  mov     [rbp+490h+FileHandle], rsi
0x180120c2e  jmp     short loc_180120BC4
0x180120c30  xorps   xmm0, xmm0
0x180120c33  xor     eax, eax
0x180120c35  movups  [rbp+490h+var_4F8], xmm0
0x180120c39  mov     [rbp+490h+var_4E8], rax
0x180120c3d  mov     rax, [rdi+10h]
0x180120c41  mov     [rbp+490h+var_80], 24h ; '$'
0x180120c4c  mov     [rbp+490h+var_80+8], 26h ; '&'
0x180120c57  lea     rcx, aProcessesHoldi; "Processes holding "
0x180120c5e  mov     [rbp+490h+var_70], rcx
0x180120c65  movd    xmm1, dword ptr [rax]
0x180120c69  punpcklwd xmm1, xmm0
0x180120c6d  punpckldq xmm1, xmm0
0x180120c71  movdqu  [rbp+490h+var_68], xmm1
0x180120c79  mov     rax, [rax+8]
0x180120c7d  mov     [rbp+490h+var_58], rax
0x180120c84  mov     [rbp+490h+var_50], 4
0x180120c8f  mov     [rbp+490h+var_48], 6
0x180120c9a  lea     rax, asc_1801F2A94; ": "
0x180120ca1  mov     [rbp+490h+var_40], rax
0x180120ca8  lea     rax, [rbp+490h+var_4F8]
0x180120cac  mov     [rsp+590h+var_560], rax
0x180120cb1  lea     r8, [rsp+590h+var_560]
0x180120cb6  lea     rdx, [rbp+490h+var_80]
0x180120cbd  mov     ecx, 3
0x180120cc2  call    ??$ConcatenateStringsInList@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@$0A@@Rtl@StringUtil@Windows@@YAJ_KQEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::ConcatenateStringsInList<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>,0>(unsigned __int64,_LUNICODE_STRING const * const,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180120cc7  mov     ebx, eax
0x180120cc9  test    eax, eax
0x180120ccb  jns     short loc_180120D03
0x180120ccd  lea     rcx, [rbp+490h+var_4F8]
0x180120cd1  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180120cd6  nop
0x180120cd7  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180120cdb  lea     rdx, [rcx-1]
0x180120cdf  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180120ce3  ja      short loc_180120CFE
0x180120ce5  call    cs:__imp_NtClose
0x180120cec  nop     dword ptr [rax+rax+00h]
0x180120cf1  test    eax, eax
0x180120cf3  jns     short loc_180120CFA
0x180120cf5  mov     rcx, r14
0x180120cf8  int     29h; Win8: RtlFailFast(ecx)
0x180120cfa  mov     [rbp+490h+FileHandle], rsi
0x180120cfe  jmp     loc_180120BC4
0x180120d03  mov     ebx, esi
0x180120d05  cmp     [rbp+490h+FileInformation], esi
0x180120d08  jbe     loc_180120F9D
0x180120d0e  lea     r12, ?RtlTraceFormat_PCULONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180120d15  lea     r13, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlAutoTrace@PEAU_OBJECT_ATTRIBUTES@@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBQEAU_OBJECT_ATTRIBUTES@@AEBU?$FormatNtStatusWrapper@J@234@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_OBJECT_ATTRIBUTES *,Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_OBJECT_ATTRIBUTES * const &,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180120d1c  mov     [rsp+590h+ClientId.UniqueThread], rsi
0x180120d21  mov     eax, ebx
0x180120d23  lea     rdi, [rbp+490h+var_4A8]
0x180120d27  lea     rdi, [rdi+rax*8]
0x180120d2b  mov     rax, [rdi]
0x180120d2e  mov     [rsp+590h+ClientId.UniqueProcess], rax
0x180120d33  mov     qword ptr [rsp+590h+ObjectAttributes.Length], 30h ; '0'
0x180120d3c  xorps   xmm0, xmm0
0x180120d3f  movdqu  xmmword ptr [rsp+590h+ObjectAttributes.RootDirectory], xmm0
0x180120d45  mov     qword ptr [rsp+590h+ObjectAttributes.Attributes], rsi
0x180120d4a  movdqu  xmmword ptr [rsp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180120d50  mov     [rbp+490h+ProcessHandle], rsi
0x180120d54  lea     r9, [rsp+590h+ClientId]; ClientId
0x180120d59  lea     r8, [rsp+590h+ObjectAttributes]; ObjectAttributes
0x180120d5e  mov     edx, 1000h; DesiredAccess
0x180120d63  lea     rcx, [rbp+490h+ProcessHandle]; ProcessHandle
0x180120d67  call    cs:__imp_NtOpenProcess
0x180120d6e  nop     dword ptr [rax+rax+00h]
0x180120d73  mov     [rbp+490h+var_508], eax
0x180120d76  test    eax, eax
0x180120d78  jns     short loc_180120DE2
0x180120d7a  lea     rax, [rbp+490h+var_508]
0x180120d7e  mov     [rsp+590h+var_560], rax; struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *
0x180120d83  mov     [rbp+490h+var_80], rsi
0x180120d8a  mov     [rbp+490h+var_80+8], r12
0x180120d91  mov     [rbp+490h+var_70], rdi
0x180120d98  mov     qword ptr [rbp+490h+var_68], rsi
0x180120d9f  mov     qword ptr [rbp+490h+var_68+8], r13
0x180120da6  lea     rax, [rsp+590h+var_560]
0x180120dab  mov     [rbp+490h+var_58], rax
0x180120db2  lea     rax, [rbp+490h+var_80]
0x180120db9  mov     qword ptr [rsp+590h+OpenOptions], rax; unsigned __int64
0x180120dbe  mov     qword ptr [rsp+590h+ShareAccess], 2; char *
0x180120dc7  lea     r9, aFailedToOpenPr; "Failed to open process {0} with status "...
0x180120dce  lea     r8, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180120dd5  xor     ecx, ecx; this
0x180120dd7  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180120ddc  nop
0x180120ddd  jmp     loc_180120F70
0x180120de2  xor     edx, edx; Val
0x180120de4  mov     r8d, 218h; Size
0x180120dea  lea     rcx, [rbp+490h+ProcessInformation]; void *
0x180120df1  call    memset_0
0x180120df6  mov     qword ptr [rsp+590h+ShareAccess], rsi; ReturnLength
0x180120dfb  mov     r9d, 218h; ProcessInformationLength
0x180120e01  lea     r8, [rbp+490h+ProcessInformation]; ProcessInformation
0x180120e08  mov     edx, 1Bh; ProcessInformationClass
0x180120e0d  mov     rcx, [rbp+490h+ProcessHandle]; ProcessHandle
0x180120e11  call    cs:__imp_NtQueryInformationProcess
0x180120e18  nop     dword ptr [rax+rax+00h]
0x180120e1d  mov     [rbp+490h+var_508], eax
0x180120e20  test    eax, eax
0x180120e22  js      loc_180120F0D
0x180120e28  xorps   xmm0, xmm0
0x180120e2b  xor     eax, eax
0x180120e2d  movups  [rbp+490h+var_4E0], xmm0
0x180120e31  mov     [rbp+490h+var_4D0], rax
0x180120e35  lea     rax, asc_1801CCD40; ", "
0x180120e3c  lea     rdx, dword_1801CAD7C
0x180120e43  test    ebx, ebx
0x180120e45  cmovnz  rdx, rax
0x180120e49  movups  xmm0, [rbp+490h+var_4F8]
0x180120e4d  movaps  xmmword ptr [rbp+490h+var_80], xmm0
0x180120e54  movsd   xmm1, [rbp+490h+var_4E8]
0x180120e59  movsd   [rbp+490h+var_70], xmm1
0x180120e61  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180120e65  inc     rcx
0x180120e68  cmp     [rdx+rcx*2], si
0x180120e6c  jnz     short loc_180120E65
0x180120e6e  add     rcx, rcx
0x180120e71  lea     rax, [rcx+2]
0x180120e75  mov     qword ptr [rbp+490h+var_68], rcx
0x180120e7c  mov     qword ptr [rbp+490h+var_68+8], rax
0x180120e83  mov     [rbp+490h+var_58], rdx
0x180120e8a  movzx   eax, [rbp+490h+ProcessInformation]
0x180120e91  mov     [rbp+490h+var_50], rax
0x180120e98  movzx   eax, [rbp+490h+var_29E]
0x180120e9f  mov     [rbp+490h+var_48], rax
0x180120ea6  mov     rax, [rbp+490h+var_298]
0x180120ead  mov     [rbp+490h+var_40], rax
0x180120eb4  lea     rax, [rbp+490h+var_4E0]
0x180120eb8  mov     [rsp+590h+var_560], rax
0x180120ebd  lea     r8, [rsp+590h+var_560]
0x180120ec2  lea     rdx, [rbp+490h+var_80]
0x180120ec9  mov     ecx, 3
0x180120ece  call    ??$ConcatenateStringsInList@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@$0A@@Rtl@StringUtil@Windows@@YAJ_KQEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::ConcatenateStringsInList<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>,0>(unsigned __int64,_LUNICODE_STRING const * const,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180120ed3  mov     edi, eax
0x180120ed5  test    eax, eax
0x180120ed7  js      loc_180121047
0x180120edd  movups  xmm2, [rbp+490h+var_4F8]
0x180120ee1  movsd   xmm3, [rbp+490h+var_4E8]
0x180120ee6  movups  xmm0, [rbp+490h+var_4E0]
0x180120eea  movups  [rbp+490h+var_4F8], xmm0
0x180120eee  movsd   xmm1, [rbp+490h+var_4D0]
0x180120ef3  movsd   [rbp+490h+var_4E8], xmm1
0x180120ef8  movups  [rbp+490h+var_4E0], xmm2
0x180120efc  movsd   [rbp+490h+var_4D0], xmm3
0x180120f01  lea     rcx, [rbp+490h+var_4E0]
0x180120f05  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180120f0a  nop
0x180120f0b  jmp     short loc_180120F70
0x180120f0d  lea     rax, [rbp+490h+var_508]
0x180120f11  mov     [rsp+590h+var_560], rax; struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *
0x180120f16  mov     [rbp+490h+var_80], rsi
0x180120f1d  mov     [rbp+490h+var_80+8], r12
0x180120f24  mov     [rbp+490h+var_70], rdi
0x180120f2b  mov     qword ptr [rbp+490h+var_68], rsi
0x180120f32  mov     qword ptr [rbp+490h+var_68+8], r13
0x180120f39  lea     rax, [rsp+590h+var_560]
0x180120f3e  mov     [rbp+490h+var_58], rax
0x180120f45  lea     rax, [rbp+490h+var_80]
0x180120f4c  mov     qword ptr [rsp+590h+OpenOptions], rax; unsigned __int64
0x180120f51  mov     qword ptr [rsp+590h+ShareAccess], 2; char *
0x180120f5a  lea     r9, aFailedToQueryI_0; "Failed to query image path for process "...
0x180120f61  lea     r8, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180120f68  xor     ecx, ecx; this
0x180120f6a  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180120f6f  nop
0x180120f70  mov     rcx, [rbp+490h+ProcessHandle]; Handle
0x180120f74  test    rcx, rcx
0x180120f77  jz      short loc_180120F92
0x180120f79  call    cs:__imp_NtClose
0x180120f80  nop     dword ptr [rax+rax+00h]
0x180120f85  test    eax, eax
0x180120f87  jns     short loc_180120F8E
0x180120f89  mov     rcx, r14
0x180120f8c  int     29h; Win8: RtlFailFast(ecx)
0x180120f8e  mov     [rbp+490h+ProcessHandle], rsi
0x180120f92  inc     ebx
0x180120f94  cmp     ebx, [rbp+490h+FileInformation]
0x180120f97  jb      loc_180120D1C
0x180120f9d  mov     [rbp+490h+var_80], rsi
0x180120fa4  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@U_LUNICODE_STRING@@PEB_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEBU_LUNICODE_STRING@@AEBQEB_W@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<_LUNICODE_STRING,wchar_t const *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,_LUNICODE_STRING const &,wchar_t const * const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180120fab  mov     [rbp+490h+var_80+8], rax
0x180120fb2  lea     rax, [rbp+490h+var_4F8]
0x180120fb6  mov     [rbp+490h+var_70], rax
0x180120fbd  lea     rax, [rbp+490h+var_80]
0x180120fc4  mov     qword ptr [rsp+590h+OpenOptions], rax; unsigned __int64
0x180120fc9  mov     qword ptr [rsp+590h+ShareAccess], 1; char *
0x180120fd2  lea     r9, a0_2; "{0}"
0x180120fd9  lea     r8, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180120fe0  xor     ecx, ecx; this
0x180120fe2  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180120fe7  nop
0x180120fe8  lea     rcx, [rbp+490h+var_4F8]
0x180120fec  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180120ff1  nop
0x180120ff2  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180120ff6  lea     rax, [rcx-1]
0x180120ffa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180120ffe  ja      short loc_180121019
0x180121000  call    cs:__imp_NtClose
0x180121007  nop     dword ptr [rax+rax+00h]
0x18012100c  test    eax, eax
0x18012100e  jns     short loc_180121015
0x180121010  mov     rcx, r14
0x180121013  int     29h; Win8: RtlFailFast(ecx)
0x180121015  mov     [rbp+490h+FileHandle], rsi
0x180121019  xor     eax, eax
0x18012101b  mov     rcx, [rbp+490h+var_30]
0x180121022  xor     rcx, rsp; StackCookie
0x180121025  call    __security_check_cookie
0x18012102a  lea     r11, [rsp+590h+var_20]
0x180121032  mov     rbx, [r11+38h]
0x180121036  mov     rsi, [r11+40h]
0x18012103a  mov     rsp, r11
0x18012103d  pop     r14
0x18012103f  pop     r13
0x180121041  pop     r12
0x180121043  pop     rdi
0x180121044  pop     rbp
0x180121045  retn
0x180121047  lea     rcx, [rbp+490h+var_4E0]
0x18012104b  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180121050  nop
0x180121051  mov     rcx, [rbp+490h+ProcessHandle]; Handle
0x180121055  test    rcx, rcx
0x180121058  jz      short loc_180121073
0x18012105a  call    cs:__imp_NtClose
0x180121061  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
