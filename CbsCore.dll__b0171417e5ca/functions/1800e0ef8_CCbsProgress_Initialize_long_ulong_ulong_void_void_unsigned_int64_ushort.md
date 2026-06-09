# CCbsProgress::Initialize(long (*)(ulong,ulong,void *),void *,unsigned __int64,ushort *)

- ea: `0x1800e0ef8`
- end: `0x1800e127c`
- name: `?Initialize@CCbsProgress@@QEAAJP6AJKKPEAX@Z0_KPEAG@Z`
- size: `900`
- prototype: `__int64 __usercall@<rax>(CCbsProgress *__hidden this@<rcx>, int (*)(unsigned int, unsigned int, void *)@<rdx>, void *@<r8>, unsigned __int64@<r9>, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800fcb34`
- `0x18017a2e0`
- `0x1802b14fc`

## callees

- `0x1800150c0`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800e0ef8`
- `0x1800eb920`
- `0x18013d508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e104d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e110b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e104d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e110b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e112a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e11e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e112a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e11e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e11c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e11c7`

## string_xrefs

- `0x1800e1205`: `Failed to create progress thread.`
- `0x1800e108f`: `Failed to create done event.`
- `0x1800e1149`: `Failed to create done event.`

## pseudocode

```c
int __fastcall CCbsProgress::Initialize(
        CCbsProgress *this,
        int (*a2)(unsigned int, unsigned int, void *),
        void *a3,
        unsigned __int64 a4,
        unsigned __int16 *a5)
{
  __int64 v7; // rdx
  unsigned __int64 i; // rbx
  int v10; // eax
  int v11; // esi
  HANDLE EventW; // rax
  signed int LastError; // ebx
  unsigned int v14; // eax
  __int64 v15; // rdx
  HANDLE v16; // rax
  unsigned int v17; // eax
  HANDLE Thread; // rax
  unsigned int v19; // eax
  unsigned int dwCreationFlags; // [rsp+20h] [rbp-38h]
  unsigned int v21[2]; // [rsp+30h] [rbp-28h] BYREF
  int v22; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  if ( !a3 )
  {
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No progress callback context specified");
      *(_QWORD *)v21 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v7 = 234;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsprogresstracker.cpp",
      (const char *)0x80070057LL,
      dwCreationFlags);
    return -2147024809;
  }
  if ( !a5 )
  {
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No phase percentage values specified");
      *(_QWORD *)v21 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v7 = 236;
    goto LABEL_5;
  }
  *((_QWORD *)this + 14) = a3;
  *((_QWORD *)this + 13) = CCbsProgressExecutionCommunicationCallback;
  for ( i = 0; i < a4; ++i )
  {
    v10 = CCbsArrayBase<unsigned short,CCbsArray<unsigned short>>::Add((char *)this + 120, &a5[i]);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsprogresstracker.cpp",
        (const char *)(unsigned int)v10,
        dwCreationFlags);
      return v11;
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership((char *)this + 48, EventW);
  if ( *((_QWORD *)this + 6) )
  {
    v16 = CreateEventW(0, 0, 0, 0);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership((char *)this + 56, v16);
    if ( *((_QWORD *)this + 7) )
    {
      Thread = CreateThread(0, 0, CCbsProgress::ProgressThreadProc, this, 0, 0);
      Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership((char *)this + 40, Thread);
      if ( !*((_QWORD *)this + 5) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create progress thread.");
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
          else
            v19 = LastError;
          v22 = v19;
          *(_QWORD *)v21 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v21);
        }
        if ( LastError )
        {
          v15 = 253;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v15,
                   (unsigned int)"onecore\\base\\cbs\\core\\cbsprogresstracker.cpp",
                   (const char *)(unsigned int)LastError,
                   dwCreationFlags);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create done event.");
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
        else
          v17 = LastError;
        v22 = v17;
        *(_QWORD *)v21 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v21);
      }
      if ( LastError )
      {
        v15 = 250;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v15,
                 (unsigned int)"onecore\\base\\cbs\\core\\cbsprogresstracker.cpp",
                 (const char *)(unsigned int)LastError,
                 dwCreationFlags);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create done event.");
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      v22 = v14;
      *(_QWORD *)v21 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v21);
    }
    if ( LastError )
    {
      v15 = 247;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsprogresstracker.cpp",
               (const char *)(unsigned int)LastError,
               dwCreationFlags);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800e0ef8  push    rbp
0x1800e0efa  push    rbx
0x1800e0efb  push    rsi
0x1800e0efc  push    rdi
0x1800e0efd  push    r14
0x1800e0eff  push    r15
0x1800e0f01  mov     rbp, rsp
0x1800e0f04  sub     rsp, 58h
0x1800e0f08  mov     rax, cs:__security_cookie
0x1800e0f0f  xor     rax, rsp
0x1800e0f12  mov     [rbp+var_18], rax
0x1800e0f16  mov     r15, r9
0x1800e0f19  mov     rdi, rcx
0x1800e0f1c  test    r8, r8
0x1800e0f1f  jnz     short loc_1800E0F92
0x1800e0f21  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e0f28  mov     ebx, 80070057h
0x1800e0f2d  mov     [rbp+var_20], ebx
0x1800e0f30  test    rcx, rcx
0x1800e0f33  jz      short loc_1800E0F73
0x1800e0f35  lea     edi, [r8+3]
0x1800e0f39  xor     edx, edx
0x1800e0f3b  mov     r8d, edi
0x1800e0f3e  lea     r9, aNoProgressCall; "No progress callback context specified"
0x1800e0f45  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e0f4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e0f51  lea     rax, [rbp+var_20]
0x1800e0f55  mov     qword ptr [rbp+var_28], rax
0x1800e0f59  lea     r9, asc_1802EE7AC; ": {}"
0x1800e0f60  lea     rax, [rbp+var_28]
0x1800e0f64  mov     r8d, edi
0x1800e0f67  mov     dl, 1
0x1800e0f69  mov     qword ptr [rsp+58h+dwCreationFlags], rax; int
0x1800e0f6e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e0f73  mov     edx, 0EAh; void *
0x1800e0f78  mov     rcx, [rbp+30h]; this
0x1800e0f7c  lea     r8, aOnecoreBaseCbs_103; "onecore\\base\\cbs\\core\\cbsprogresstr"...
0x1800e0f83  mov     r9d, ebx; char *
0x1800e0f86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0f8b  mov     eax, ebx
0x1800e0f8d  jmp     loc_1800E1262
0x1800e0f92  mov     r14, [rbp+arg_20]
0x1800e0f96  test    r14, r14
0x1800e0f99  jnz     short loc_1800E0FF4
0x1800e0f9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e0fa2  mov     ebx, 80070057h
0x1800e0fa7  mov     [rbp+var_20], ebx
0x1800e0faa  test    rcx, rcx
0x1800e0fad  jz      short loc_1800E0FED
0x1800e0faf  lea     edi, [r14+3]
0x1800e0fb3  xor     edx, edx
0x1800e0fb5  mov     r8d, edi
0x1800e0fb8  lea     r9, aNoPhasePercent; "No phase percentage values specified"
0x1800e0fbf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e0fc4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e0fcb  lea     rax, [rbp+var_20]
0x1800e0fcf  mov     qword ptr [rbp+var_28], rax
0x1800e0fd3  lea     r9, asc_1802EE7AC; ": {}"
0x1800e0fda  lea     rax, [rbp+var_28]
0x1800e0fde  mov     r8d, edi
0x1800e0fe1  mov     dl, 1
0x1800e0fe3  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800e0fe8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e0fed  mov     edx, 0ECh
0x1800e0ff2  jmp     short loc_1800E0F78
0x1800e0ff4  lea     rax, ?CCbsProgressExecutionCommunicationCallback@@YAJKKPEAX@Z; CCbsProgressExecutionCommunicationCallback(ulong,ulong,void *)
0x1800e0ffb  mov     [rcx+70h], r8
0x1800e0fff  mov     [rcx+68h], rax
0x1800e1003  xor     ebx, ebx
0x1800e1005  cmp     rbx, r15
0x1800e1008  jnb     short loc_1800E1041
0x1800e100a  lea     rdx, [r14+rbx*2]
0x1800e100e  lea     rcx, [rdi+78h]
0x1800e1012  call    ?Add@?$CCbsArrayBase@GV?$CCbsArray@G@@@@QEAAJAEBG@Z; CCbsArrayBase<ushort,CCbsArray<ushort>>::Add(ushort const &)
0x1800e1017  mov     esi, eax
0x1800e1019  test    eax, eax
0x1800e101b  js      short loc_1800E1022
0x1800e101d  inc     rbx
0x1800e1020  jmp     short loc_1800E1005
0x1800e1022  mov     rcx, [rbp+30h]; this
0x1800e1026  lea     r8, aOnecoreBaseCbs_103; "onecore\\base\\cbs\\core\\cbsprogresstr"...
0x1800e102d  mov     r9d, esi; char *
0x1800e1030  mov     edx, 0F3h; void *
0x1800e1035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e103a  mov     eax, esi
0x1800e103c  jmp     loc_1800E1262
0x1800e1041  xor     r9d, r9d; lpName
0x1800e1044  xor     r8d, r8d; bInitialState
0x1800e1047  xor     ecx, ecx; lpEventAttributes
0x1800e1049  lea     edx, [r9+1]; bManualReset
0x1800e104d  call    cs:__imp_CreateEventW
0x1800e1054  nop     dword ptr [rax+rax+00h]
0x1800e1059  mov     rdx, rax
0x1800e105c  lea     rcx, [rdi+30h]
0x1800e1060  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800e1065  cmp     qword ptr [rdi+30h], 0
0x1800e106a  jnz     loc_1800E1101
0x1800e1070  call    cs:__imp_GetLastError
0x1800e1077  nop     dword ptr [rax+rax+00h]
0x1800e107c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e1083  mov     ebx, eax
0x1800e1085  test    rcx, rcx
0x1800e1088  jz      short loc_1800E10DC
0x1800e108a  mov     edi, 3
0x1800e108f  lea     r9, aFailedToCreate_87; "Failed to create done event."
0x1800e1096  mov     r8d, edi
0x1800e1099  xor     edx, edx
0x1800e109b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e10a0  test    ebx, ebx
0x1800e10a2  jg      short loc_1800E10A8
0x1800e10a4  mov     eax, ebx
0x1800e10a6  jmp     short loc_1800E10B0
0x1800e10a8  movzx   eax, bx
0x1800e10ab  or      eax, 80070000h
0x1800e10b0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e10b7  lea     r9, a0; ": {0}"
0x1800e10be  mov     [rbp+var_20], eax
0x1800e10c1  mov     r8d, edi
0x1800e10c4  lea     rax, [rbp+var_20]
0x1800e10c8  mov     dl, 1
0x1800e10ca  mov     qword ptr [rbp+var_28], rax
0x1800e10ce  lea     rax, [rbp+var_28]
0x1800e10d2  mov     qword ptr [rsp+58h+dwCreationFlags], rax; unsigned int
0x1800e10d7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e10dc  test    ebx, ebx
0x1800e10de  jz      loc_1800E1260
0x1800e10e4  mov     edx, 0F7h; void *
0x1800e10e9  mov     rcx, [rbp+30h]; this
0x1800e10ed  lea     r8, aOnecoreBaseCbs_103; "onecore\\base\\cbs\\core\\cbsprogresstr"...
0x1800e10f4  mov     r9d, ebx; char *
0x1800e10f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e10fc  jmp     loc_1800E1262
0x1800e1101  xor     r9d, r9d; lpName
0x1800e1104  xor     r8d, r8d; bInitialState
0x1800e1107  xor     edx, edx; bManualReset
0x1800e1109  xor     ecx, ecx; lpEventAttributes
0x1800e110b  call    cs:__imp_CreateEventW
0x1800e1112  nop     dword ptr [rax+rax+00h]
0x1800e1117  mov     rdx, rax
0x1800e111a  lea     rcx, [rdi+38h]
0x1800e111e  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800e1123  cmp     qword ptr [rdi+38h], 0
0x1800e1128  jnz     short loc_1800E11A8
0x1800e112a  call    cs:__imp_GetLastError
0x1800e1131  nop     dword ptr [rax+rax+00h]
0x1800e1136  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e113d  mov     ebx, eax
0x1800e113f  test    rcx, rcx
0x1800e1142  jz      short loc_1800E1196
0x1800e1144  mov     edi, 3
0x1800e1149  lea     r9, aFailedToCreate_87; "Failed to create done event."
0x1800e1150  mov     r8d, edi
0x1800e1153  xor     edx, edx
0x1800e1155  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e115a  test    ebx, ebx
0x1800e115c  jg      short loc_1800E1162
0x1800e115e  mov     eax, ebx
0x1800e1160  jmp     short loc_1800E116A
0x1800e1162  movzx   eax, bx
0x1800e1165  or      eax, 80070000h
0x1800e116a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e1171  lea     r9, a0; ": {0}"
0x1800e1178  mov     [rbp+var_20], eax
0x1800e117b  mov     r8d, edi
0x1800e117e  lea     rax, [rbp+var_20]
0x1800e1182  mov     dl, 1
0x1800e1184  mov     qword ptr [rbp+var_28], rax
0x1800e1188  lea     rax, [rbp+var_28]
0x1800e118c  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800e1191  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e1196  test    ebx, ebx
0x1800e1198  jz      loc_1800E1260
0x1800e119e  mov     edx, 0FAh
0x1800e11a3  jmp     loc_1800E10E9
0x1800e11a8  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1800e11b1  lea     r8, ?ProgressThreadProc@CCbsProgress@@CAKPEAX@Z; lpStartAddress
0x1800e11b8  mov     r9, rdi; lpParameter
0x1800e11bb  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800e11c3  xor     edx, edx; dwStackSize
0x1800e11c5  xor     ecx, ecx; lpThreadAttributes
0x1800e11c7  call    cs:__imp_CreateThread
0x1800e11ce  nop     dword ptr [rax+rax+00h]
0x1800e11d3  mov     rdx, rax
0x1800e11d6  lea     rcx, [rdi+28h]
0x1800e11da  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800e11df  cmp     qword ptr [rdi+28h], 0
0x1800e11e4  jnz     short loc_1800E1260
0x1800e11e6  call    cs:__imp_GetLastError
0x1800e11ed  nop     dword ptr [rax+rax+00h]
0x1800e11f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e11f9  mov     ebx, eax
0x1800e11fb  test    rcx, rcx
0x1800e11fe  jz      short loc_1800E1252
0x1800e1200  mov     edi, 3
0x1800e1205  lea     r9, aFailedToCreate_52; "Failed to create progress thread."
0x1800e120c  mov     r8d, edi
0x1800e120f  xor     edx, edx
0x1800e1211  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e1216  test    ebx, ebx
0x1800e1218  jg      short loc_1800E121E
0x1800e121a  mov     eax, ebx
0x1800e121c  jmp     short loc_1800E1226
0x1800e121e  movzx   eax, bx
0x1800e1221  or      eax, 80070000h
0x1800e1226  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e122d  lea     r9, a0; ": {0}"
0x1800e1234  mov     [rbp+var_20], eax
0x1800e1237  mov     r8d, edi
0x1800e123a  lea     rax, [rbp+var_20]
0x1800e123e  mov     dl, 1
0x1800e1240  mov     qword ptr [rbp+var_28], rax
0x1800e1244  lea     rax, [rbp+var_28]
0x1800e1248  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800e124d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e1252  test    ebx, ebx
0x1800e1254  jz      short loc_1800E1260
0x1800e1256  mov     edx, 0FDh
0x1800e125b  jmp     loc_1800E10E9
0x1800e1260  xor     eax, eax
0x1800e1262  mov     rcx, [rbp+var_18]
0x1800e1266  xor     rcx, rsp; StackCookie
0x1800e1269  call    __security_check_cookie
0x1800e126e  add     rsp, 58h
0x1800e1272  pop     r15
0x1800e1274  pop     r14
0x1800e1276  pop     rdi
0x1800e1277  pop     rsi
0x1800e1278  pop     rbx
0x1800e1279  pop     rbp
0x1800e127a  retn
```
