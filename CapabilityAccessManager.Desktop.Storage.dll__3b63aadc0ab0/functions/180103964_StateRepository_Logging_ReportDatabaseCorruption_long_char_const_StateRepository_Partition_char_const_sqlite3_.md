# StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,char const *,sqlite3 *,char const *,unsigned __int64,unsigned __int64)

- ea: `0x180103964`
- end: `0x180103ccf`
- name: `?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@0PEAUsqlite3@@0_K3@Z`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180103cd8`

## callees

- `0x180002658`
- `0x1800038f0`
- `0x1800eabf4`
- `0x1800f7630`
- `0x180103964`
- `0x180106008`
- `0x180106084`
- `0x180106144`
- `0x180109dcc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180103b47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180103b8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180103b47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180103b8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180103ac5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180103b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180103b2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180103ac5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180103b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180103b2a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180103b7d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180103b7d`

## string_xrefs

- `0x180103ad7`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x180103c9e`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x1801039f4`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180103aab`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Logging::ReportDatabaseCorruption(
        int a1,
        const char *a2,
        __int64 a3,
        const char *a4,
        HKEY hKey,
        const char *a6,
        __int64 a7,
        __int64 a8)
{
  int v9; // r15d
  HKEY v10; // r14
  const wchar_t *v11; // rsi
  unsigned __int64 v12; // r12
  unsigned __int16 *v13; // rax
  int PersistedRegKeyPath; // eax
  const wchar_t *v15; // r8
  unsigned int v16; // r9d
  unsigned int v17; // edi
  void *v18; // rcx
  void *v19; // rbx
  const wchar_t *v20; // r8
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  int Value; // eax
  const wchar_t *v24; // r8
  const wchar_t *v25; // r8
  __int64 v27; // r9
  const wchar_t *v28; // rbx
  int Reported; // eax
  unsigned __int64 *v30; // [rsp+28h] [rbp-99h]
  int v31; // [rsp+28h] [rbp-99h]
  void *Block; // [rsp+78h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-41h] BYREF
  unsigned __int64 v34; // [rsp+88h] [rbp-39h] BYREF
  unsigned __int64 v35; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int16 *v36; // [rsp+98h] [rbp-29h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-19h] BYREF
  const char *v39; // [rsp+B0h] [rbp-11h] BYREF
  const char *v40; // [rsp+B8h] [rbp-9h] BYREF
  const char *v41; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+3Fh]
  int v45; // [rsp+118h] [rbp+57h] BYREF

  v9 = a3;
  if ( !(_DWORD)a3 )
    return 0;
  SystemTimeAsFileTime = 0;
  v34 = 0;
  v10 = 0;
  v35 = 0;
  v11 = 0;
  v12 = 0;
  if ( (_DWORD)a3 == 1 )
  {
    v13 = L"Machine";
  }
  else
  {
    if ( (_DWORD)a3 != 2 )
    {
LABEL_31:
      hKey = 0;
      QueryUnbiasedInterruptTime((PULONGLONG)&hKey);
      v10 = hKey;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v11 = (const wchar_t *)(SystemTimeAsFileTime.dwLowDateTime
                            + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32));
      v28 = v11;
      goto LABEL_32;
    }
    v13 = L"Deployment";
  }
  Block = 0;
  v36 = v13;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                          (Common **)&qword_180140490,
                          (const unsigned __int16 **)&v36,
                          a3,
                          (unsigned __int16 **)&Block);
  v17 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x414,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      (int)v30);
    v18 = Block;
LABEL_21:
    operator delete(v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
      (const char *)v17,
      v31);
    return v17;
  }
  hKey = 0;
  v19 = Block;
  v17 = StateRepository::Globals::Registry::Open(&hKey, (struct Common::RegistryKey *)Block, v15, v16);
  if ( v17 + 2147024894 <= 1 )
  {
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    operator delete(v19);
  }
  else
  {
    if ( (v17 & 0x80000000) != 0 )
    {
      v21 = v17;
      v22 = 1056;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)v21,
        (int)v30);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      v18 = v19;
      goto LABEL_21;
    }
    Value = StateRepository::Globals::Registry::ReadValue(
              (StateRepository::Globals::Registry *)&hKey,
              (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedUptime",
              v20,
              (unsigned __int64)&SystemTimeAsFileTime,
              v30);
    v17 = Value;
    if ( Value < 0 )
    {
      v22 = 1057;
LABEL_17:
      v21 = (unsigned int)Value;
      goto LABEL_18;
    }
    Value = StateRepository::Globals::Registry::ReadValue(
              (StateRepository::Globals::Registry *)&hKey,
              (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedWhen",
              v24,
              (unsigned __int64)&v34,
              v30);
    v17 = Value;
    if ( Value < 0 )
    {
      v22 = 1058;
      goto LABEL_17;
    }
    Value = StateRepository::Globals::Registry::ReadValue(
              (StateRepository::Globals::Registry *)&hKey,
              (struct Common::RegistryKey *)L"DatabaseCorruptionLastReported",
              v25,
              (unsigned __int64)&v35,
              v30);
    v17 = Value;
    if ( Value < 0 )
    {
      v22 = 1059;
      goto LABEL_17;
    }
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    operator delete(v19);
    v10 = (HKEY)SystemTimeAsFileTime;
    v11 = (const wchar_t *)v34;
    v12 = v35;
  }
  if ( !v11 )
    goto LABEL_31;
  Block = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&Block);
  v28 = (const wchar_t *)((unsigned int)Block + ((unsigned __int64)HIDWORD(Block) << 32));
  if ( (unsigned __int64)v28 - v12 >= 0x324A9A7000LL )
  {
LABEL_32:
    if ( *(_DWORD *)qword_1801403D8 > 1u
      && (*(_QWORD *)(qword_1801403D8 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(qword_1801403D8 + 24) & 0x400000000000LL) == *(_QWORD *)(qword_1801403D8 + 24) )
    {
      v37 = a8;
      v38 = a7;
      v39 = a6;
      v41 = a2;
      LODWORD(hKey) = a1;
      v36 = (unsigned __int16 *)0x1000000;
      v35 = (unsigned __int64)v11;
      v34 = (unsigned __int64)v10;
      v40 = a4;
      v45 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        qword_1801403D8,
        (__int64)byte_18012A345,
        0x400000000000LL,
        v27,
        (__int64)&hKey,
        &v41,
        (__int64)&v45,
        &v40,
        &v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v34,
        (__int64)&v35,
        (__int64)&v36);
    }
    Reported = StateRepository::Globals::SetDatabaseCorruptionLastReported(v9, (const wchar_t *)v10, v11, v28);
    if ( Reported < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x267,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)(unsigned int)Reported);
  }
  return 0;
}

```

## disassembly

```asm
0x180103964  mov     rax, rsp
0x180103967  mov     [rax+20h], rbx
0x18010396b  mov     [rax+10h], rdx
0x18010396f  mov     [rax+8], ecx
0x180103972  push    rbp
0x180103973  push    rsi
0x180103974  push    rdi
0x180103975  push    r12
0x180103977  push    r13
0x180103979  push    r14
0x18010397b  push    r15
0x18010397d  lea     rbp, [rax-3Fh]
0x180103981  sub     rsp, 0C0h
0x180103988  xor     ebx, ebx
0x18010398a  mov     r13, r9
0x18010398d  mov     r15d, r8d
0x180103990  test    r8d, r8d
0x180103993  jz      loc_180103CB2
0x180103999  mov     edx, r8d
0x18010399c  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1801039a0  mov     [rbp+37h+var_70], rbx
0x1801039a4  mov     r14d, ebx
0x1801039a7  mov     [rbp+37h+var_68], rbx
0x1801039ab  mov     esi, ebx
0x1801039ad  mov     r12d, ebx
0x1801039b0  sub     edx, 1
0x1801039b3  jz      short loc_1801039C7
0x1801039b5  cmp     edx, 1
0x1801039b8  jnz     loc_180103B75
0x1801039be  lea     rax, ?stateRepositoryStatusDeploymentRegistrySubkey@StateRepository@@3QB_WB; "Deployment"
0x1801039c5  jmp     short loc_1801039CE
0x1801039c7  lea     rax, ?stateRepositoryStatusMachineRegistrySubkey@StateRepository@@3QB_WB; "Machine"
0x1801039ce  lea     r9, [rbp+37h+Block]; unsigned __int16 **
0x1801039d2  mov     [rbp+37h+Block], rbx
0x1801039d6  lea     rdx, [rbp+37h+var_60]; unsigned __int16 **
0x1801039da  mov     [rbp+37h+var_60], rax
0x1801039de  lea     rcx, qword_180140490; struct Common::StateSeparationRedirectionMapping *
0x1801039e5  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x1801039ea  mov     edi, eax
0x1801039ec  test    eax, eax
0x1801039ee  jns     short loc_180103A11
0x1801039f0  mov     rcx, [rbp+3Fh]; this
0x1801039f4  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801039fb  mov     r9d, eax; char *
0x1801039fe  mov     edx, 414h; void *
0x180103a03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103a08  mov     rcx, [rbp+37h+Block]
0x180103a0c  jmp     loc_180103ACE
0x180103a11  mov     [rbp+37h+hKey], rbx
0x180103a15  lea     rcx, [rbp+37h+hKey]; phkResult
0x180103a19  mov     rbx, [rbp+37h+Block]
0x180103a1d  mov     rdx, rbx; struct Common::RegistryKey *
0x180103a20  call    ?Open@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WK_N@Z; StateRepository::Globals::Registry::Open(Common::RegistryKey &,wchar_t const *,ulong,bool)
0x180103a25  mov     edi, eax
0x180103a27  add     eax, 7FF8FFFEh
0x180103a2c  cmp     eax, 1
0x180103a2f  jbe     loc_180103B1C
0x180103a35  test    edi, edi
0x180103a37  jns     short loc_180103A43
0x180103a39  mov     r9d, edi
0x180103a3c  mov     edx, 420h
0x180103a41  jmp     short loc_180103AA7
0x180103a43  lea     r9, [rbp+37h+SystemTimeAsFileTime]; unsigned __int64
0x180103a47  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedUptime@StateRepository@@3QB_WB; "DatabaseCorruptionFirstDetectedUptime"
0x180103a4e  lea     rcx, [rbp+37h+hKey]; this
0x180103a52  call    ?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180103a57  mov     edi, eax
0x180103a59  test    eax, eax
0x180103a5b  jns     short loc_180103A64
0x180103a5d  mov     edx, 421h
0x180103a62  jmp     short loc_180103AA4
0x180103a64  lea     r9, [rbp+37h+var_70]; unsigned __int64
0x180103a68  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedWhen@StateRepository@@3QB_WB; "DatabaseCorruptionFirstDetectedWhen"
0x180103a6f  lea     rcx, [rbp+37h+hKey]; this
0x180103a73  call    ?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180103a78  mov     edi, eax
0x180103a7a  test    eax, eax
0x180103a7c  jns     short loc_180103A85
0x180103a7e  mov     edx, 422h
0x180103a83  jmp     short loc_180103AA4
0x180103a85  lea     r9, [rbp+37h+var_68]; unsigned __int64
0x180103a89  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionLastReported@StateRepository@@3QB_WB; "DatabaseCorruptionLastReported"
0x180103a90  lea     rcx, [rbp+37h+hKey]; this
0x180103a94  call    ?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180103a99  mov     edi, eax
0x180103a9b  test    eax, eax
0x180103a9d  jns     short loc_180103AF2
0x180103a9f  mov     edx, 423h; void *
0x180103aa4  mov     r9d, eax; char *
0x180103aa7  mov     rcx, [rbp+3Fh]; this
0x180103aab  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180103ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103ab7  mov     rcx, [rbp+37h+hKey]; hKey
0x180103abb  lea     rax, [rcx-1]
0x180103abf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180103ac3  ja      short loc_180103ACB
0x180103ac5  call    cs:__imp_RegCloseKey
0x180103acb  mov     rcx, rbx; Block
0x180103ace  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180103ad3  mov     rcx, [rbp+3Fh]; this
0x180103ad7  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180103ade  mov     r9d, edi; char *
0x180103ae1  mov     edx, 241h; void *
0x180103ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103aeb  mov     eax, edi
0x180103aed  jmp     loc_180103CB4
0x180103af2  mov     rcx, [rbp+37h+hKey]; hKey
0x180103af6  lea     rax, [rcx-1]
0x180103afa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180103afe  ja      short loc_180103B06
0x180103b00  call    cs:__imp_RegCloseKey
0x180103b06  mov     rcx, rbx; Block
0x180103b09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180103b0e  mov     r14, qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime]
0x180103b12  mov     rsi, [rbp+37h+var_70]
0x180103b16  mov     r12, [rbp+37h+var_68]
0x180103b1a  jmp     short loc_180103B38
0x180103b1c  mov     rcx, [rbp+37h+hKey]; hKey
0x180103b20  lea     rax, [rcx-1]
0x180103b24  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180103b28  ja      short loc_180103B30
0x180103b2a  call    cs:__imp_RegCloseKey
0x180103b30  mov     rcx, rbx; Block
0x180103b33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180103b38  xor     ebx, ebx
0x180103b3a  test    rsi, rsi
0x180103b3d  jz      short loc_180103B75
0x180103b3f  lea     rcx, [rbp+37h+Block]; lpSystemTimeAsFileTime
0x180103b43  mov     [rbp+37h+Block], rbx
0x180103b47  call    cs:__imp_GetSystemTimeAsFileTime
0x180103b4d  mov     eax, dword ptr [rbp+37h+Block]
0x180103b50  mov     rcx, 324A9A7000h
0x180103b5a  mov     ebx, dword ptr [rbp+37h+Block+4]
0x180103b5d  shl     rbx, 20h
0x180103b61  add     rbx, rax
0x180103b64  mov     rax, rbx
0x180103b67  sub     rax, r12
0x180103b6a  cmp     rax, rcx
0x180103b6d  jb      loc_180103CB2
0x180103b73  jmp     short loc_180103BA5
0x180103b75  lea     rcx, [rbp+37h+hKey]; UnbiasedTime
0x180103b79  mov     [rbp+37h+hKey], rbx
0x180103b7d  call    cs:__imp_QueryUnbiasedInterruptTime
0x180103b83  mov     r14, [rbp+37h+hKey]
0x180103b87  lea     rcx, [rbp+37h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180103b8b  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180103b8f  call    cs:__imp_GetSystemTimeAsFileTime
0x180103b95  mov     esi, [rbp+37h+SystemTimeAsFileTime.dwHighDateTime]
0x180103b98  mov     eax, [rbp+37h+SystemTimeAsFileTime.dwLowDateTime]
0x180103b9b  shl     rsi, 20h
0x180103b9f  add     rsi, rax
0x180103ba2  mov     rbx, rsi
0x180103ba5  mov     rcx, cs:qword_1801403D8
0x180103bac  mov     eax, [rcx]
0x180103bae  cmp     eax, 1
0x180103bb1  jbe     loc_180103C85
0x180103bb7  mov     rdx, [rcx+18h]
0x180103bbb  mov     r8, 400000000000h
0x180103bc5  mov     rax, [rcx+10h]
0x180103bc9  test    r8, rax
0x180103bcc  jz      loc_180103C85
0x180103bd2  mov     rax, rdx
0x180103bd5  and     rax, r8
0x180103bd8  cmp     rax, rdx
0x180103bdb  jnz     loc_180103C85
0x180103be1  mov     rax, [rbp+37h+arg_38]
0x180103be5  lea     rdx, byte_18012A345
0x180103bec  mov     [rbp+37h+var_58], rax
0x180103bf0  mov     rax, [rbp+37h+arg_30]
0x180103bf4  mov     [rbp+37h+var_50], rax
0x180103bf8  mov     rax, [rbp+37h+arg_28]
0x180103bfc  mov     [rbp+37h+var_48], rax
0x180103c00  mov     rax, [rbp+37h+arg_8]
0x180103c04  mov     [rbp+37h+var_38], rax
0x180103c08  mov     eax, [rbp+37h+arg_0]
0x180103c0b  mov     dword ptr [rbp+37h+hKey], eax
0x180103c0e  lea     rax, [rbp+37h+var_60]
0x180103c12  mov     [rsp+68h], rax
0x180103c17  lea     rax, [rbp+37h+var_68]
0x180103c1b  mov     [rsp+0F0h+var_90], rax
0x180103c20  lea     rax, [rbp+37h+var_70]
0x180103c24  mov     [rsp+0F0h+var_98], rax
0x180103c29  lea     rax, [rbp+37h+var_58]
0x180103c2d  mov     [rsp+0F0h+var_A0], rax
0x180103c32  lea     rax, [rbp+37h+var_50]
0x180103c36  mov     [rsp+0F0h+var_A8], rax
0x180103c3b  lea     rax, [rbp+37h+var_48]
0x180103c3f  mov     [rsp+0F0h+var_B0], rax
0x180103c44  lea     rax, [rbp+37h+var_40]
0x180103c48  mov     [rsp+0F0h+var_B8], rax
0x180103c4d  lea     rax, [rbp+37h+arg_10]
0x180103c51  mov     [rsp+0F0h+var_C0], rax
0x180103c56  lea     rax, [rbp+37h+var_38]
0x180103c5a  mov     [rsp+0F0h+var_C8], rax
0x180103c5f  lea     rax, [rbp+37h+hKey]
0x180103c63  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180103c68  mov     [rbp+37h+var_60], 1000000h
0x180103c70  mov     [rbp+37h+var_68], rsi
0x180103c74  mov     [rbp+37h+var_70], r14
0x180103c78  mov     [rbp+37h+var_40], r13
0x180103c7c  mov     [rbp+37h+arg_10], r15d
0x180103c80  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@344AEBU?$_tlgWrapperByVal@$07@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180103c85  mov     r9, rbx
0x180103c88  mov     r8, rsi
0x180103c8b  mov     rdx, r14
0x180103c8e  mov     ecx, r15d
0x180103c91  call    ?SetDatabaseCorruptionLastReported@Globals@StateRepository@@YAJW4Partition@2@_K11@Z; StateRepository::Globals::SetDatabaseCorruptionLastReported(StateRepository::Partition,unsigned __int64,unsigned __int64,unsigned __int64)
0x180103c96  test    eax, eax
0x180103c98  jns     short loc_180103CB2
0x180103c9a  mov     rcx, [rbp+3Fh]; this
0x180103c9e  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180103ca5  mov     r9d, eax; char *
0x180103ca8  mov     edx, 267h; void *
0x180103cad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180103cb2  xor     eax, eax
0x180103cb4  mov     rbx, [rsp+0F0h+arg_18]
0x180103cbc  add     rsp, 0C0h
0x180103cc3  pop     r15
0x180103cc5  pop     r14
0x180103cc7  pop     r13
0x180103cc9  pop     r12
0x180103ccb  pop     rdi
0x180103ccc  pop     rsi
0x180103ccd  pop     rbp
0x180103cce  retn
```
