# Windows::Rtl::SystemImplementation::LogProcessesHoldingFile

- ea: `0x180183e0c`
- end: `0x18018439b`
- name: `Windows::Rtl::SystemImplementation::LogProcessesHoldingFile`
- size: `1423`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1801858f0`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x180022940`
- `0x180134b7c`
- `0x180183e0c`
- `0x1801e51c4`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180183e7b`
- `ntdll!NtOpenFile` at `0x180183e7b`
- `ntdll!NtOpenProcess` at `0x180184057`
- `ntdll!NtOpenProcess` at `0x180184057`
- `ntdll!NtQueryInformationProcess` at `0x180184101`
- `ntdll!NtQueryInformationProcess` at `0x180184101`
- `ntdll!NtQueryInformationFile` at `0x180183ee5`
- `ntdll!NtQueryInformationFile` at `0x180183ee5`
- `ntdll!NtClose` at `0x180183e9b`
- `ntdll!NtClose` at `0x180183f05`
- `ntdll!NtClose` at `0x180183fd5`
- `ntdll!NtClose` at `0x180184269`
- `ntdll!NtClose` at `0x1801842f0`
- `ntdll!NtClose` at `0x18018434a`
- `ntdll!NtClose` at `0x18018437b`
- `ntdll!NtClose` at `0x180183e9b`
- `ntdll!NtClose` at `0x180183f05`
- `ntdll!NtClose` at `0x180183fd5`
- `ntdll!NtClose` at `0x180184269`
- `ntdll!NtClose` at `0x1801842f0`
- `ntdll!NtClose` at `0x18018434a`
- `ntdll!NtClose` at `0x18018437b`

## string_xrefs

- `0x1801840b7`: `Failed to open process {0} with status {1}.`
- `0x18018424a`: `Failed to query image path for process {0} with status {1}.`

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
  const wchar_t *v9; // rdx
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
  v9 = &String2;
  if ( v6 )
    v9 = L", ";
  *(_OWORD *)v28 = v20;
  v29 = v21;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
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
0x180183e0c  mov     rax, rsp
0x180183e0f  push    rbp
0x180183e10  push    rdi
0x180183e11  push    r12
0x180183e13  push    r13
0x180183e15  push    r14
0x180183e17  lea     rbp, [rax-498h]
0x180183e1e  sub     rsp, 570h
0x180183e25  mov     [rsp+590h+var_558], 0FFFFFFFFFFFFFFFEh
0x180183e2e  mov     [rax+10h], rbx
0x180183e32  mov     [rax+18h], rsi
0x180183e36  mov     rax, cs:__security_cookie
0x180183e3d  xor     rax, rsp
0x180183e40  mov     [rbp+490h+var_30], rax
0x180183e47  mov     rdi, rcx
0x180183e4a  xor     esi, esi
0x180183e4c  mov     [rbp+490h+FileHandle], rsi
0x180183e50  xorps   xmm0, xmm0
0x180183e53  movups  xmmword ptr [rbp+490h+IoStatusBlock], xmm0
0x180183e57  mov     [rbp+490h+var_508], esi
0x180183e5a  mov     [rsp+590h+OpenOptions], 4020h; OpenOptions
0x180183e62  lea     r14d, [rsi+7]
0x180183e66  mov     [rsp+590h+ShareAccess], r14d; ShareAccess
0x180183e6b  lea     r9, [rbp+490h+IoStatusBlock]; IoStatusBlock
0x180183e6f  mov     r8, rcx; ObjectAttributes
0x180183e72  mov     edx, 100080h; DesiredAccess
0x180183e77  lea     rcx, [rbp+490h+FileHandle]; FileHandle
0x180183e7b  call    cs:__imp_NtOpenFile
0x180183e82  nop     dword ptr [rax+rax+00h]
0x180183e87  mov     ebx, eax
0x180183e89  test    eax, eax
0x180183e8b  jns     short loc_180183EBB
0x180183e8d  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180183e91  lea     rdx, [rcx-1]
0x180183e95  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180183e99  ja      short loc_180183EB4
0x180183e9b  call    cs:__imp_NtClose
0x180183ea2  nop     dword ptr [rax+rax+00h]
0x180183ea7  test    eax, eax
0x180183ea9  jns     short loc_180183EB0
0x180183eab  mov     ecx, r14d
0x180183eae  int     29h; Win8: RtlFailFast(ecx)
0x180183eb0  mov     [rbp+490h+FileHandle], rsi
0x180183eb4  mov     eax, ebx
0x180183eb6  jmp     loc_18018430B
0x180183ebb  mov     ebx, 208h
0x180183ec0  mov     r8d, ebx; Size
0x180183ec3  xor     edx, edx; Val
0x180183ec5  lea     rcx, [rbp+490h+FileInformation]; void *
0x180183ec9  call    memset_0
0x180183ece  mov     [rsp+590h+ShareAccess], 2Fh ; '/'; FileInformationClass
0x180183ed6  mov     r9d, ebx; Length
0x180183ed9  lea     r8, [rbp+490h+FileInformation]; FileInformation
0x180183edd  lea     rdx, [rbp+490h+IoStatusBlock]; IoStatusBlock
0x180183ee1  mov     rcx, [rbp+490h+FileHandle]; FileHandle
0x180183ee5  call    cs:__imp_NtQueryInformationFile
0x180183eec  nop     dword ptr [rax+rax+00h]
0x180183ef1  mov     ebx, eax
0x180183ef3  test    eax, eax
0x180183ef5  jns     short loc_180183F20
0x180183ef7  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180183efb  lea     rdx, [rcx-1]
0x180183eff  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180183f03  ja      short loc_180183F1E
0x180183f05  call    cs:__imp_NtClose
0x180183f0c  nop     dword ptr [rax+rax+00h]
0x180183f11  test    eax, eax
0x180183f13  jns     short loc_180183F1A
0x180183f15  mov     rcx, r14
0x180183f18  int     29h; Win8: RtlFailFast(ecx)
0x180183f1a  mov     [rbp+490h+FileHandle], rsi
0x180183f1e  jmp     short loc_180183EB4
0x180183f20  xorps   xmm0, xmm0
0x180183f23  xor     eax, eax
0x180183f25  movups  [rbp+490h+var_4F8], xmm0
0x180183f29  mov     [rbp+490h+var_4E8], rax
0x180183f2d  mov     rax, [rdi+10h]
0x180183f31  mov     [rbp+490h+var_80], 24h ; '$'
0x180183f3c  mov     [rbp+490h+var_80+8], 26h ; '&'
0x180183f47  lea     rcx, aProcessesHoldi; "Processes holding "
0x180183f4e  mov     [rbp+490h+var_70], rcx
0x180183f55  movd    xmm1, dword ptr [rax]
0x180183f59  punpcklwd xmm1, xmm0
0x180183f5d  punpckldq xmm1, xmm0
0x180183f61  movdqu  [rbp+490h+var_68], xmm1
0x180183f69  mov     rax, [rax+8]
0x180183f6d  mov     [rbp+490h+var_58], rax
0x180183f74  mov     [rbp+490h+var_50], 4
0x180183f7f  mov     [rbp+490h+var_48], 6
0x180183f8a  lea     rax, asc_180321F58; ": "
0x180183f91  mov     [rbp+490h+var_40], rax
0x180183f98  lea     rax, [rbp+490h+var_4F8]
0x180183f9c  mov     [rsp+590h+var_560], rax
0x180183fa1  lea     r8, [rsp+590h+var_560]
0x180183fa6  lea     rdx, [rbp+490h+var_80]
0x180183fad  mov     ecx, 3
0x180183fb2  call    ??$ConcatenateStringsInList@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@$0A@@Rtl@StringUtil@Windows@@YAJ_KQEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::ConcatenateStringsInList<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>,0>(unsigned __int64,_LUNICODE_STRING const * const,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180183fb7  mov     ebx, eax
0x180183fb9  test    eax, eax
0x180183fbb  jns     short loc_180183FF3
0x180183fbd  lea     rcx, [rbp+490h+var_4F8]
0x180183fc1  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180183fc6  nop
0x180183fc7  mov     rcx, [rbp+490h+FileHandle]; Handle
0x180183fcb  lea     rdx, [rcx-1]
0x180183fcf  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180183fd3  ja      short loc_180183FEE
0x180183fd5  call    cs:__imp_NtClose
0x180183fdc  nop     dword ptr [rax+rax+00h]
0x180183fe1  test    eax, eax
0x180183fe3  jns     short loc_180183FEA
0x180183fe5  mov     rcx, r14
0x180183fe8  int     29h; Win8: RtlFailFast(ecx)
0x180183fea  mov     [rbp+490h+FileHandle], rsi
0x180183fee  jmp     loc_180183EB4
0x180183ff3  mov     ebx, esi
0x180183ff5  cmp     [rbp+490h+FileInformation], esi
0x180183ff8  jbe     loc_18018428D
0x180183ffe  lea     r12, ?RtlTraceFormat_PCULONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180184005  lea     r13, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlAutoTrace@PEAU_OBJECT_ATTRIBUTES@@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBQEAU_OBJECT_ATTRIBUTES@@AEBU?$FormatNtStatusWrapper@J@234@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_OBJECT_ATTRIBUTES *,Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_OBJECT_ATTRIBUTES * const &,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018400c  mov     [rsp+590h+ClientId.UniqueThread], rsi
0x180184011  mov     eax, ebx
0x180184013  lea     rdi, [rbp+490h+var_4A8]
0x180184017  lea     rdi, [rdi+rax*8]
0x18018401b  mov     rax, [rdi]
0x18018401e  mov     [rsp+590h+ClientId.UniqueProcess], rax
0x180184023  mov     qword ptr [rsp+590h+ObjectAttributes.Length], 30h ; '0'
0x18018402c  xorps   xmm0, xmm0
0x18018402f  movdqu  xmmword ptr [rsp+590h+ObjectAttributes.RootDirectory], xmm0
0x180184035  mov     qword ptr [rsp+590h+ObjectAttributes.Attributes], rsi
0x18018403a  movdqu  xmmword ptr [rsp+590h+ObjectAttributes.SecurityDescriptor], xmm0
0x180184040  mov     [rbp+490h+ProcessHandle], rsi
0x180184044  lea     r9, [rsp+590h+ClientId]; ClientId
0x180184049  lea     r8, [rsp+590h+ObjectAttributes]; ObjectAttributes
0x18018404e  mov     edx, 1000h; DesiredAccess
0x180184053  lea     rcx, [rbp+490h+ProcessHandle]; ProcessHandle
0x180184057  call    cs:__imp_NtOpenProcess
0x18018405e  nop     dword ptr [rax+rax+00h]
0x180184063  mov     [rbp+490h+var_508], eax
0x180184066  test    eax, eax
0x180184068  jns     short loc_1801840D2
0x18018406a  lea     rax, [rbp+490h+var_508]
0x18018406e  mov     [rsp+590h+var_560], rax; struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *
0x180184073  mov     [rbp+490h+var_80], rsi
0x18018407a  mov     [rbp+490h+var_80+8], r12
0x180184081  mov     [rbp+490h+var_70], rdi
0x180184088  mov     qword ptr [rbp+490h+var_68], rsi
0x18018408f  mov     qword ptr [rbp+490h+var_68+8], r13
0x180184096  lea     rax, [rsp+590h+var_560]
0x18018409b  mov     [rbp+490h+var_58], rax
0x1801840a2  lea     rax, [rbp+490h+var_80]
0x1801840a9  mov     qword ptr [rsp+590h+OpenOptions], rax; unsigned __int64
0x1801840ae  mov     qword ptr [rsp+590h+ShareAccess], 2; char *
0x1801840b7  lea     r9, aFailedToOpenPr; "Failed to open process {0} with status "...
0x1801840be  lea     r8, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1801840c5  xor     ecx, ecx; this
0x1801840c7  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1801840cc  nop
0x1801840cd  jmp     loc_180184260
0x1801840d2  xor     edx, edx; Val
0x1801840d4  mov     r8d, 218h; Size
0x1801840da  lea     rcx, [rbp+490h+ProcessInformation]; void *
0x1801840e1  call    memset_0
0x1801840e6  mov     qword ptr [rsp+590h+ShareAccess], rsi; ReturnLength
0x1801840eb  mov     r9d, 218h; ProcessInformationLength
0x1801840f1  lea     r8, [rbp+490h+ProcessInformation]; ProcessInformation
0x1801840f8  mov     edx, 1Bh; ProcessInformationClass
0x1801840fd  mov     rcx, [rbp+490h+ProcessHandle]; ProcessHandle
0x180184101  call    cs:__imp_NtQueryInformationProcess
0x180184108  nop     dword ptr [rax+rax+00h]
0x18018410d  mov     [rbp+490h+var_508], eax
0x180184110  test    eax, eax
0x180184112  js      loc_1801841FD
0x180184118  xorps   xmm0, xmm0
0x18018411b  xor     eax, eax
0x18018411d  movups  [rbp+490h+var_4E0], xmm0
0x180184121  mov     [rbp+490h+var_4D0], rax
0x180184125  lea     rax, asc_180321FA4; ", "
0x18018412c  lea     rdx, String2
0x180184133  test    ebx, ebx
0x180184135  cmovnz  rdx, rax
0x180184139  movups  xmm0, [rbp+490h+var_4F8]
0x18018413d  movaps  xmmword ptr [rbp+490h+var_80], xmm0
0x180184144  movsd   xmm1, [rbp+490h+var_4E8]
0x180184149  movsd   [rbp+490h+var_70], xmm1
0x180184151  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180184155  inc     rcx
0x180184158  cmp     [rdx+rcx*2], si
0x18018415c  jnz     short loc_180184155
0x18018415e  add     rcx, rcx
0x180184161  lea     rax, [rcx+2]
0x180184165  mov     qword ptr [rbp+490h+var_68], rcx
0x18018416c  mov     qword ptr [rbp+490h+var_68+8], rax
0x180184173  mov     [rbp+490h+var_58], rdx
0x18018417a  movzx   eax, [rbp+490h+ProcessInformation]
0x180184181  mov     [rbp+490h+var_50], rax
0x180184188  movzx   eax, [rbp+490h+var_29E]
0x18018418f  mov     [rbp+490h+var_48], rax
0x180184196  mov     rax, [rbp+490h+var_298]
0x18018419d  mov     [rbp+490h+var_40], rax
0x1801841a4  lea     rax, [rbp+490h+var_4E0]
0x1801841a8  mov     [rsp+590h+var_560], rax
0x1801841ad  lea     r8, [rsp+590h+var_560]
0x1801841b2  lea     rdx, [rbp+490h+var_80]
0x1801841b9  mov     ecx, 3
0x1801841be  call    ??$ConcatenateStringsInList@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@$0A@@Rtl@StringUtil@Windows@@YAJ_KQEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::ConcatenateStringsInList<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>,0>(unsigned __int64,_LUNICODE_STRING const * const,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x1801841c3  mov     edi, eax
0x1801841c5  test    eax, eax
0x1801841c7  js      loc_180184337
0x1801841cd  movups  xmm2, [rbp+490h+var_4F8]
0x1801841d1  movsd   xmm3, [rbp+490h+var_4E8]
0x1801841d6  movups  xmm0, [rbp+490h+var_4E0]
0x1801841da  movups  [rbp+490h+var_4F8], xmm0
0x1801841de  movsd   xmm1, [rbp+490h+var_4D0]
0x1801841e3  movsd   [rbp+490h+var_4E8], xmm1
0x1801841e8  movups  [rbp+490h+var_4E0], xmm2
0x1801841ec  movsd   [rbp+490h+var_4D0], xmm3
0x1801841f1  lea     rcx, [rbp+490h+var_4E0]
0x1801841f5  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801841fa  nop
0x1801841fb  jmp     short loc_180184260
0x1801841fd  lea     rax, [rbp+490h+var_508]
0x180184201  mov     [rsp+590h+var_560], rax; struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *
0x180184206  mov     [rbp+490h+var_80], rsi
0x18018420d  mov     [rbp+490h+var_80+8], r12
0x180184214  mov     [rbp+490h+var_70], rdi
0x18018421b  mov     qword ptr [rbp+490h+var_68], rsi
0x180184222  mov     qword ptr [rbp+490h+var_68+8], r13
0x180184229  lea     rax, [rsp+590h+var_560]
0x18018422e  mov     [rbp+490h+var_58], rax
0x180184235  lea     rax, [rbp+490h+var_80]
0x18018423c  mov     qword ptr [rsp+590h+OpenOptions], rax; unsigned __int64
0x180184241  mov     qword ptr [rsp+590h+ShareAccess], 2; char *
0x18018424a  lea     r9, aFailedToQueryI_1; "Failed to query image path for process "...
0x180184251  lea     r8, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180184258  xor     ecx, ecx; this
0x18018425a  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x18018425f  nop
0x180184260  mov     rcx, [rbp+490h+ProcessHandle]; Handle
0x180184264  test    rcx, rcx
0x180184267  jz      short loc_180184282
0x180184269  call    cs:__imp_NtClose
0x180184270  nop     dword ptr [rax+rax+00h]
0x180184275  test    eax, eax
0x180184277  jns     short loc_18018427E
0x180184279  mov     rcx, r14
0x18018427c  int     29h; Win8: RtlFailFast(ecx)
0x18018427e  mov     [rbp+490h+ProcessHandle], rsi
0x180184282  inc     ebx
0x180184284  cmp     ebx, [rbp+490h+FileInformation]
0x180184287  jb      loc_18018400C
0x18018428d  mov     [rbp+490h+var_80], rsi
0x180184294  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@U_LUNICODE_STRING@@PEB_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEBU_LUNICODE_STRING@@AEBQEB_W@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<_LUNICODE_STRING,wchar_t const *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,_LUNICODE_STRING const &,wchar_t const * const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018429b  mov     [rbp+490h+var_80+8], rax
0x1801842a2  lea     rax, [rbp+490h+var_4F8]
0x1801842a6  mov     [rbp+490h+var_70], rax
0x1801842ad  lea     rax, [rbp+490h+var_80]
0x1801842b4  mov     qword ptr [rsp+590h+OpenOptions], rax; unsigned __int64
0x1801842b9  mov     qword ptr [rsp+590h+ShareAccess], 1; char *
0x1801842c2  lea     r9, a0_2; "{0}"
0x1801842c9  lea     r8, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1801842d0  xor     ecx, ecx; this
0x1801842d2  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1801842d7  nop
0x1801842d8  lea     rcx, [rbp+490h+var_4F8]
0x1801842dc  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801842e1  nop
0x1801842e2  mov     rcx, [rbp+490h+FileHandle]; Handle
0x1801842e6  lea     rax, [rcx-1]
0x1801842ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801842ee  ja      short loc_180184309
0x1801842f0  call    cs:__imp_NtClose
0x1801842f7  nop     dword ptr [rax+rax+00h]
0x1801842fc  test    eax, eax
0x1801842fe  jns     short loc_180184305
0x180184300  mov     rcx, r14
0x180184303  int     29h; Win8: RtlFailFast(ecx)
0x180184305  mov     [rbp+490h+FileHandle], rsi
0x180184309  xor     eax, eax
0x18018430b  mov     rcx, [rbp+490h+var_30]
0x180184312  xor     rcx, rsp; StackCookie
0x180184315  call    __security_check_cookie
0x18018431a  lea     r11, [rsp+590h+var_20]
0x180184322  mov     rbx, [r11+38h]
0x180184326  mov     rsi, [r11+40h]
0x18018432a  mov     rsp, r11
0x18018432d  pop     r14
0x18018432f  pop     r13
0x180184331  pop     r12
0x180184333  pop     rdi
0x180184334  pop     rbp
0x180184335  retn
0x180184337  lea     rcx, [rbp+490h+var_4E0]
0x18018433b  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180184340  nop
0x180184341  mov     rcx, [rbp+490h+ProcessHandle]; Handle
0x180184345  test    rcx, rcx
0x180184348  jz      short loc_180184363
0x18018434a  call    cs:__imp_NtClose
0x180184351  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
