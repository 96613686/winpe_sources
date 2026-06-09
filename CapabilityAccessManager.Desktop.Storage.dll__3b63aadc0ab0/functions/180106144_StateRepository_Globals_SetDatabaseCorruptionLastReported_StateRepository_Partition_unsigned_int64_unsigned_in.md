# StateRepository::Globals::SetDatabaseCorruptionLastReported(StateRepository::Partition,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180106144`
- end: `0x1801063d5`
- name: `?SetDatabaseCorruptionLastReported@Globals@StateRepository@@YAJW4Partition@2@_K11@Z`
- size: `657`
- prototype: `int __high(enum StateRepository::Partition, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180103964`

## callees

- `0x1800038f0`
- `0x1800eabf4`
- `0x1800ec608`
- `0x1800f7630`
- `0x1800fb7b4`
- `0x180102320`
- `0x180106144`
- `0x1801064b4`
- `0x180109dcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801061da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801062cd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801063a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801061da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801062cd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801063a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801061f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801062e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801063ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801061f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801062e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801063ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801062b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010638b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801062b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010638b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180106244`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180106244`

## string_xrefs

- `0x1801061ae`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180106271`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18010628e`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18010630b`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18010633a`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180106369`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180106265`: `CreateSetting: Subkey=%ls`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::SetDatabaseCorruptionLastReported(
        int a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  int v7; // ecx
  unsigned __int16 *v8; // rbx
  __int64 v9; // r8
  int PersistedRegKeyPath; // eax
  unsigned int v11; // edi
  HANDLE v12; // rbx
  wil::details::in1diag3 *v13; // rcx
  void *v15; // rdi
  LSTATUS v16; // eax
  unsigned __int64 v17; // r9
  unsigned int v18; // ebx
  HANDLE v19; // rdi
  int v20; // eax
  unsigned __int64 v21; // r9
  int v22; // eax
  unsigned __int64 v23; // r9
  int v24; // eax
  HANDLE v25; // rbx
  int dwOptions; // [rsp+20h] [rbp-58h]
  int dwOptionsa; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  void *Block; // [rsp+58h] [rbp-20h] BYREF
  HANDLE Token; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v7 = a1 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    v8 = L"Deployment";
  }
  else
  {
    v8 = L"Machine";
  }
  wil::run_as_self_failfast(&Token, a2);
  Block = 0;
  v31 = v8;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                          (Common **)&qword_180140490,
                          (const unsigned __int16 **)&v31,
                          v9,
                          (unsigned __int16 **)&Block);
  v11 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x436,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      dwOptions);
    operator delete(Block);
    v12 = Token;
    if ( Token == (HANDLE)-1LL )
      return v11;
    if ( SetThreadToken(0, Token) )
    {
      if ( v12 )
        CloseHandle(v12);
      return v11;
    }
LABEL_34:
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  }
  v15 = Block;
  hKey = 0;
  v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)Block, 0, 0, 0, 0x2011Fu, 0, &hKey, 0);
  v18 = v16;
  if ( v16 > 0 )
    v18 = (unsigned __int16)v16 | 0x80070000;
  if ( (v18 & 0x80000000) == 0 )
  {
    v20 = StateRepository::Globals::Registry::WriteValue(
            (StateRepository::Globals::Registry *)&hKey,
            (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedUptime",
            a2,
            v17);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43B,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v20);
    v22 = StateRepository::Globals::Registry::WriteValue(
            (StateRepository::Globals::Registry *)&hKey,
            (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedWhen",
            a3,
            v21);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43C,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v22);
    v24 = StateRepository::Globals::Registry::WriteValue(
            (StateRepository::Globals::Registry *)&hKey,
            (struct Common::RegistryKey *)L"DatabaseCorruptionLastReported",
            a4,
            v23);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43D,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v24);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    operator delete(v15);
    v25 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      if ( !SetThreadToken(0, Token) )
        goto LABEL_34;
      if ( v25 )
        CloseHandle(v25);
    }
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x66D,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)v18,
    (int)"CreateSetting: Subkey=%ls",
    (const char *)v15);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x439,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)v18,
    dwOptionsa);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  operator delete(v15);
  v19 = Token;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      goto LABEL_34;
    if ( v19 )
      CloseHandle(v19);
  }
  return v18;
}

```

## disassembly

```asm
0x180106144  push    rbp
0x180106146  push    rbx
0x180106147  push    rsi
0x180106148  push    rdi
0x180106149  push    r14
0x18010614b  push    r15
0x18010614d  mov     rbp, rsp
0x180106150  sub     rsp, 78h
0x180106154  mov     r15, r9
0x180106157  mov     r14, r8
0x18010615a  mov     rsi, rdx
0x18010615d  sub     ecx, 1
0x180106160  jz      short loc_180106174
0x180106162  cmp     ecx, 1
0x180106165  jnz     loc_1801063C0
0x18010616b  lea     rbx, ?stateRepositoryStatusDeploymentRegistrySubkey@StateRepository@@3QB_WB; "Deployment"
0x180106172  jmp     short loc_18010617B
0x180106174  lea     rbx, ?stateRepositoryStatusMachineRegistrySubkey@StateRepository@@3QB_WB; "Machine"
0x18010617b  lea     rcx, [rbp+Token]
0x18010617f  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180106184  lea     r9, [rbp+Block]; unsigned __int16 **
0x180106188  mov     [rbp+Block], 0
0x180106190  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x180106194  mov     [rbp+var_10], rbx
0x180106198  lea     rcx, qword_180140490; struct Common::StateSeparationRedirectionMapping *
0x18010619f  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x1801061a4  mov     edi, eax
0x1801061a6  test    eax, eax
0x1801061a8  jns     short loc_1801061FD
0x1801061aa  mov     rcx, [rbp+30h]; this
0x1801061ae  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801061b5  mov     r9d, eax; char *
0x1801061b8  mov     edx, 436h; void *
0x1801061bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801061c2  mov     rcx, [rbp+Block]; Block
0x1801061c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801061cb  mov     rbx, [rbp+Token]
0x1801061cf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801061d3  jz      short loc_1801061F6
0x1801061d5  mov     rdx, rbx; Token
0x1801061d8  xor     ecx, ecx; Thread
0x1801061da  call    cs:__imp_SetThreadToken
0x1801061e0  test    eax, eax
0x1801061e2  jz      loc_1801063CF
0x1801061e8  test    rbx, rbx
0x1801061eb  jz      short loc_1801061F6
0x1801061ed  mov     rcx, rbx; hObject
0x1801061f0  call    cs:__imp_CloseHandle
0x1801061f6  mov     eax, edi
0x1801061f8  jmp     loc_1801063C2
0x1801061fd  mov     rdi, [rbp+Block]
0x180106201  lea     rax, [rbp+hKey]
0x180106205  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18010620e  xor     r9d, r9d; lpClass
0x180106211  mov     [rsp+78h+phkResult], rax; phkResult
0x180106216  xor     r8d, r8d; Reserved
0x180106219  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180106222  mov     rdx, rdi; lpSubKey
0x180106225  mov     [rsp+78h+samDesired], 2011Fh; samDesired
0x18010622d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180106234  mov     [rsp+78h+dwOptions], 0; int
0x18010623c  mov     [rbp+hKey], 0
0x180106244  call    cs:__imp_RegCreateKeyExW
0x18010624a  mov     ebx, eax
0x18010624c  test    eax, eax
0x18010624e  jle     short loc_180106259
0x180106250  movzx   ebx, ax
0x180106253  or      ebx, 80070000h
0x180106259  test    ebx, ebx
0x18010625b  jns     loc_1801062F0
0x180106261  mov     rcx, [rbp+30h]; this
0x180106265  lea     rax, aCreatesettingS; "CreateSetting: Subkey=%ls"
0x18010626c  mov     qword ptr [rsp+78h+samDesired], rdi; char *
0x180106271  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180106278  mov     r9d, ebx; char *
0x18010627b  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x180106280  mov     edx, 66Dh; void *
0x180106285  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010628a  mov     rcx, [rbp+30h]; this
0x18010628e  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180106295  mov     r9d, ebx; char *
0x180106298  mov     edx, 439h; void *
0x18010629d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801062a2  mov     rcx, [rbp+hKey]; hKey
0x1801062a6  lea     rax, [rcx-1]
0x1801062aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801062ae  ja      short loc_1801062B6
0x1801062b0  call    cs:__imp_RegCloseKey
0x1801062b6  mov     rcx, rdi; Block
0x1801062b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801062be  mov     rdi, [rbp+Token]
0x1801062c2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801062c6  jz      short loc_1801062E9
0x1801062c8  mov     rdx, rdi; Token
0x1801062cb  xor     ecx, ecx; Thread
0x1801062cd  call    cs:__imp_SetThreadToken
0x1801062d3  test    eax, eax
0x1801062d5  jz      loc_1801063CF
0x1801062db  test    rdi, rdi
0x1801062de  jz      short loc_1801062E9
0x1801062e0  mov     rcx, rdi; hObject
0x1801062e3  call    cs:__imp_CloseHandle
0x1801062e9  mov     eax, ebx
0x1801062eb  jmp     loc_1801063C2
0x1801062f0  mov     r8, rsi; wchar_t *
0x1801062f3  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedUptime@StateRepository@@3QB_WB; "DatabaseCorruptionFirstDetectedUptime"
0x1801062fa  lea     rcx, [rbp+hKey]; this
0x1801062fe  call    ?WriteValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_K@Z; StateRepository::Globals::Registry::WriteValue(Common::RegistryKey &,wchar_t const *,unsigned __int64)
0x180106303  test    eax, eax
0x180106305  jns     short loc_18010631F
0x180106307  mov     rcx, [rbp+30h]; this
0x18010630b  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180106312  mov     r9d, eax; char *
0x180106315  mov     edx, 43Bh; void *
0x18010631a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010631f  mov     r8, r14; wchar_t *
0x180106322  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedWhen@StateRepository@@3QB_WB; "DatabaseCorruptionFirstDetectedWhen"
0x180106329  lea     rcx, [rbp+hKey]; this
0x18010632d  call    ?WriteValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_K@Z; StateRepository::Globals::Registry::WriteValue(Common::RegistryKey &,wchar_t const *,unsigned __int64)
0x180106332  test    eax, eax
0x180106334  jns     short loc_18010634E
0x180106336  mov     rcx, [rbp+30h]; this
0x18010633a  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180106341  mov     r9d, eax; char *
0x180106344  mov     edx, 43Ch; void *
0x180106349  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010634e  mov     r8, r15; wchar_t *
0x180106351  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionLastReported@StateRepository@@3QB_WB; "DatabaseCorruptionLastReported"
0x180106358  lea     rcx, [rbp+hKey]; this
0x18010635c  call    ?WriteValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_K@Z; StateRepository::Globals::Registry::WriteValue(Common::RegistryKey &,wchar_t const *,unsigned __int64)
0x180106361  test    eax, eax
0x180106363  jns     short loc_18010637D
0x180106365  mov     rcx, [rbp+30h]; this
0x180106369  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180106370  mov     r9d, eax; char *
0x180106373  mov     edx, 43Dh; void *
0x180106378  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010637d  mov     rcx, [rbp+hKey]; hKey
0x180106381  lea     rax, [rcx-1]
0x180106385  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106389  ja      short loc_180106391
0x18010638b  call    cs:__imp_RegCloseKey
0x180106391  mov     rcx, rdi; Block
0x180106394  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180106399  mov     rbx, [rbp+Token]
0x18010639d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801063a1  jz      short loc_1801063C0
0x1801063a3  mov     rdx, rbx; Token
0x1801063a6  xor     ecx, ecx; Thread
0x1801063a8  call    cs:__imp_SetThreadToken
0x1801063ae  test    eax, eax
0x1801063b0  jz      short loc_1801063CF
0x1801063b2  test    rbx, rbx
0x1801063b5  jz      short loc_1801063C0
0x1801063b7  mov     rcx, rbx; hObject
0x1801063ba  call    cs:__imp_CloseHandle
0x1801063c0  xor     eax, eax
0x1801063c2  add     rsp, 78h
0x1801063c6  pop     r15
0x1801063c8  pop     r14
0x1801063ca  pop     rdi
0x1801063cb  pop     rsi
0x1801063cc  pop     rbx
0x1801063cd  pop     rbp
0x1801063ce  retn
0x1801063cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
