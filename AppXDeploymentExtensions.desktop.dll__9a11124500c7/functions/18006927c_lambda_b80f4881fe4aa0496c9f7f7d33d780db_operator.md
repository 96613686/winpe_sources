# _lambda_b80f4881fe4aa0496c9f7f7d33d780db_::operator()

- ea: `0x18006927c`
- end: `0x18006965d`
- name: `_lambda_b80f4881fe4aa0496c9f7f7d33d780db_::operator()`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d7b30`

## callees

- `0x18000669c`
- `0x18001adb4`
- `0x18001f678`
- `0x18002c258`
- `0x18002d2e0`
- `0x1800529ec`
- `0x18006927c`
- `0x180069eb4`
- `0x18007b024`
- `0x180089784`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800affe4`
- `0x1800d795c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069459`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069459`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180069372`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180069372`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800693ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800693ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069428`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800694ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069428`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800694ec`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180069525`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180069525`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18006954c`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18006954c`

## string_xrefs

- `0x18006932d`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180069389`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x1800693cf`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x18006948c`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x1800695b9`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180069603`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_b80f4881fe4aa0496c9f7f7d33d780db_::operator()(PHKEY *a1, __int64 a2)
{
  __int64 v3; // rcx
  struct Common::StringBuffer *v4; // r8
  int ShellRefreshRegistryLocation; // eax
  unsigned int v7; // ebx
  const struct std::nothrow_t *v8; // rdx
  WCHAR *v9; // rcx
  unsigned int v10; // eax
  WCHAR *v11; // rdi
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned int LastError; // eax
  __int64 v15; // rdx
  const char *v16; // r9
  void *v17; // rbx
  int i; // eax
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const struct std::nothrow_t *v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+30h] [rbp-50h] BYREF
  void *v28; // [rsp+38h] [rbp-48h] BYREF
  DWORD Type; // [rsp+40h] [rbp-40h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD lpcbData; // [rsp+48h] [rbp-38h] BYREF
  BYTE v32[4]; // [rsp+4Ch] [rbp-34h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+58h] [rbp-28h] BYREF
  int v35; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_OWORD *)lpSubKey = 0;
  v35 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = -1;
  cbData = 4;
  *(_DWORD *)v32 = -1;
  lpcbData = 4;
  v28 = 0;
  McGenEventRegister_EventRegister(
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
    a2,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context);
  if ( !(unsigned __int8)IsSHChangeNotifyPresent(v3) )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    return 0;
  }
  ShellRefreshRegistryLocation = Common::Deployment::GetShellRefreshRegistryLocation(0, (int)lpSubKey, v4);
  v7 = ShellRefreshRegistryLocation;
  if ( ShellRefreshRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
      (const char *)(unsigned int)ShellRefreshRegistryLocation,
      phkResult);
    goto LABEL_6;
  }
  v10 = RegOpenCurrentUser(0xF003Fu, *a1);
  if ( v10 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x68,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
           (const char *)v10,
           phkResult);
LABEL_6:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    v9 = (WCHAR *)lpSubKey[1];
    if ( !lpSubKey[1] )
      return v7;
LABEL_7:
    operator delete(v9, v8);
    return v7;
  }
  v11 = (WCHAR *)lpSubKey[1];
  v12 = RegOpenKeyExW(**a1, lpSubKey[1], 0, 0xF003Fu, &hKey);
  if ( v12 )
  {
    v13 = 113;
LABEL_13:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
                  (const char *)v12,
                  phkResulta);
LABEL_14:
    v7 = LastError;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    if ( !v11 )
      return v7;
    v9 = v11;
    goto LABEL_7;
  }
  v12 = RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData);
  if ( v12 )
  {
    v13 = 123;
    goto LABEL_13;
  }
  if ( Type == 4 )
  {
    lpSubKey[0] = (LPCWSTR)CreateEventW(0, 0, 0, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v28,
      lpSubKey);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(lpSubKey);
    v17 = v28;
    if ( v28 )
    {
      for ( i = 0; ; i = 1 )
      {
        v19 = PumpWindowsMessagesUntilTimeout(i != 0 ? 15000 : 10000, v17);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
            (const char *)(unsigned int)v19,
            phkResulta);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
          Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
          if ( v11 )
            operator delete(v11, v24);
          return v20;
        }
        lpcbData = 4;
        v12 = RegQueryValueExW(hKey, 0, 0, &Type, v32, &lpcbData);
        if ( v12 )
        {
          v13 = 164;
          goto LABEL_13;
        }
        if ( Type != 4 )
        {
          v15 = 165;
          goto LABEL_35;
        }
        if ( *(_DWORD *)v32 == *(_DWORD *)Data )
          break;
        *(_DWORD *)Data = *(_DWORD *)v32;
      }
      v12 = RegDeleteKeyW(**a1, v11);
      if ( v12 )
      {
        v13 = 184;
        goto LABEL_13;
      }
      SHChangeNotify(0x8000000, 0, 0, 0);
      if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 8) != 0 )
        McGenEventWrite_EventWriteTransfer(&APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context, ShellRefreshSuccess, v21, 1);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
      Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
      if ( v11 )
        operator delete(v11, v22);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
                  v16);
    goto LABEL_14;
  }
  v15 = 124;
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
    (const char *)0x8007000DLL,
    phkResulta);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
  if ( v11 )
    operator delete(v11, v23);
  return 2147942413LL;
}

```

## disassembly

```asm
0x18006927c  mov     [rsp-18h+arg_8], rbx
0x180069281  mov     [rsp-18h+arg_10], rsi
0x180069286  push    rbp
0x180069287  push    rdi
0x180069288  push    r14
0x18006928a  mov     rbp, rsp
0x18006928d  sub     rsp, 80h
0x180069294  mov     rax, cs:__security_cookie
0x18006929b  xor     rax, rsp
0x18006929e  mov     [rbp+var_10], rax
0x1800692a2  mov     r14, rcx
0x1800692a5  xor     eax, eax
0x1800692a7  xorps   xmm0, xmm0
0x1800692aa  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x1800692ae  mov     [rbp+var_18], eax
0x1800692b1  mov     [rbp+hKey], rax
0x1800692b5  mov     [rbp+Type], eax
0x1800692b8  or      eax, 0FFFFFFFFh
0x1800692bb  mov     dword ptr [rbp+Data], eax
0x1800692be  mov     [rbp+cbData], 4
0x1800692c5  mov     dword ptr [rbp+var_34], eax
0x1800692c8  mov     [rbp+var_38], 4
0x1800692cf  mov     [rbp+var_48], 0
0x1800692d7  lea     r9, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x1800692de  lea     r8, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x1800692e5  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID
0x1800692ec  call    McGenEventRegister_EventRegister
0x1800692f1  call    IsSHChangeNotifyPresent
0x1800692f6  test    al, al
0x1800692f8  jnz     short loc_180069315
0x1800692fa  lea     rcx, [rbp+var_48]
0x1800692fe  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180069303  nop
0x180069304  lea     rcx, [rbp+hKey]; this
0x180069308  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18006930d  nop
0x18006930e  xor     eax, eax
0x180069310  jmp     loc_180069638
0x180069315  lea     rdx, [rbp+lpSubKey]; int
0x180069319  xor     ecx, ecx; this
0x18006931b  call    ?GetShellRefreshRegistryLocation@Deployment@Common@@YAJHPEAVStringBuffer@2@@Z; Common::Deployment::GetShellRefreshRegistryLocation(int,Common::StringBuffer *)
0x180069320  mov     ebx, eax
0x180069322  test    eax, eax
0x180069324  jns     short loc_180069368
0x180069326  mov     rcx, [rbp+18h]; this
0x18006932a  mov     r9d, eax; char *
0x18006932d  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069334  mov     edx, 62h ; 'b'; void *
0x180069339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006933e  nop
0x18006933f  lea     rcx, [rbp+var_48]
0x180069343  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180069348  nop
0x180069349  lea     rcx, [rbp+hKey]; this
0x18006934d  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180069352  nop
0x180069353  mov     rcx, [rbp+lpSubKey+8]; void *
0x180069357  test    rcx, rcx
0x18006935a  jz      short loc_180069361
0x18006935c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069361  mov     eax, ebx
0x180069363  jmp     loc_180069638
0x180069368  mov     rdx, [r14]; phkResult
0x18006936b  mov     ebx, 0F003Fh
0x180069370  mov     ecx, ebx; samDesired
0x180069372  call    cs:__imp_RegOpenCurrentUser
0x180069379  nop     dword ptr [rax+rax+00h]
0x18006937e  test    eax, eax
0x180069380  jz      short loc_18006939E
0x180069382  mov     rcx, [rbp+18h]; this
0x180069386  mov     r9d, eax; char *
0x180069389  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069390  mov     edx, 68h ; 'h'; void *
0x180069395  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006939a  mov     ebx, eax
0x18006939c  jmp     short loc_18006933F
0x18006939e  mov     rdi, [rbp+lpSubKey+8]
0x1800693a2  mov     rcx, [r14]
0x1800693a5  lea     rax, [rbp+hKey]
0x1800693a9  mov     [rsp+80h+phkResult], rax; unsigned int
0x1800693ae  mov     r9d, ebx; samDesired
0x1800693b1  xor     r8d, r8d; ulOptions
0x1800693b4  mov     rdx, rdi; lpSubKey
0x1800693b7  mov     rcx, [rcx]; hKey
0x1800693ba  call    cs:__imp_RegOpenKeyExW
0x1800693c1  nop     dword ptr [rax+rax+00h]
0x1800693c6  test    eax, eax
0x1800693c8  jz      short loc_180069409
0x1800693ca  mov     edx, 71h ; 'q'; void *
0x1800693cf  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800693d6  mov     r9d, eax; char *
0x1800693d9  mov     rcx, [rbp+18h]; this
0x1800693dd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800693e2  mov     ebx, eax
0x1800693e4  lea     rcx, [rbp+var_48]
0x1800693e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800693ed  nop
0x1800693ee  lea     rcx, [rbp+hKey]; this
0x1800693f2  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800693f7  nop
0x1800693f8  test    rdi, rdi
0x1800693fb  jz      loc_180069361
0x180069401  mov     rcx, rdi
0x180069404  jmp     loc_18006935C
0x180069409  lea     rax, [rbp+cbData]
0x18006940d  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180069412  lea     rax, [rbp+Data]
0x180069416  mov     [rsp+80h+phkResult], rax; int
0x18006941b  lea     r9, [rbp+Type]; lpType
0x18006941f  xor     r8d, r8d; lpReserved
0x180069422  xor     edx, edx; lpValueName
0x180069424  mov     rcx, [rbp+hKey]; hKey
0x180069428  call    cs:__imp_RegQueryValueExW
0x18006942f  nop     dword ptr [rax+rax+00h]
0x180069434  test    eax, eax
0x180069436  jz      short loc_18006943F
0x180069438  mov     edx, 7Bh ; '{'
0x18006943d  jmp     short loc_1800693CF
0x18006943f  cmp     [rbp+Type], 4
0x180069443  jz      short loc_18006944F
0x180069445  mov     edx, 7Ch ; '|'
0x18006944a  jmp     loc_1800695B3
0x18006944f  xor     r9d, r9d; lpName
0x180069452  xor     r8d, r8d; bInitialState
0x180069455  xor     edx, edx; bManualReset
0x180069457  xor     ecx, ecx; lpEventAttributes
0x180069459  call    cs:__imp_CreateEventW
0x180069460  nop     dword ptr [rax+rax+00h]
0x180069465  mov     [rbp+lpSubKey], rax
0x180069469  lea     rdx, [rbp+lpSubKey]
0x18006946d  lea     rcx, [rbp+var_48]
0x180069471  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180069476  lea     rcx, [rbp+lpSubKey]
0x18006947a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006947f  mov     rbx, [rbp+var_48]
0x180069483  test    rbx, rbx
0x180069486  jnz     short loc_1800694A2
0x180069488  mov     rcx, [rbp+18h]; this
0x18006948c  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069493  mov     edx, 81h; void *
0x180069498  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006949d  jmp     loc_1800693E2
0x1800694a2  xor     eax, eax
0x1800694a4  neg     eax
0x1800694a6  sbb     ecx, ecx
0x1800694a8  and     ecx, 1388h
0x1800694ae  add     ecx, 2710h; unsigned int
0x1800694b4  mov     rdx, rbx; void *
0x1800694b7  call    ?PumpWindowsMessagesUntilTimeout@@YAJKPEAX@Z; PumpWindowsMessagesUntilTimeout(ulong,void *)
0x1800694bc  mov     esi, eax
0x1800694be  test    eax, eax
0x1800694c0  js      loc_1800695FC
0x1800694c6  mov     [rbp+var_38], 4
0x1800694cd  lea     rax, [rbp+var_38]
0x1800694d1  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800694d6  lea     rax, [rbp+var_34]
0x1800694da  mov     [rsp+80h+phkResult], rax; int
0x1800694df  lea     r9, [rbp+Type]; lpType
0x1800694e3  xor     r8d, r8d; lpReserved
0x1800694e6  xor     edx, edx; lpValueName
0x1800694e8  mov     rcx, [rbp+hKey]; hKey
0x1800694ec  call    cs:__imp_RegQueryValueExW
0x1800694f3  nop     dword ptr [rax+rax+00h]
0x1800694f8  test    eax, eax
0x1800694fa  jnz     loc_1800695F2
0x180069500  cmp     [rbp+Type], 4
0x180069504  jnz     loc_1800695AE
0x18006950a  mov     eax, dword ptr [rbp+var_34]
0x18006950d  cmp     eax, dword ptr [rbp+Data]
0x180069510  jz      short loc_18006951C
0x180069512  mov     dword ptr [rbp+Data], eax
0x180069515  mov     eax, 1
0x18006951a  jmp     short loc_1800694A4
0x18006951c  mov     rcx, [r14]
0x18006951f  mov     rdx, rdi; lpSubKey
0x180069522  mov     rcx, [rcx]; hKey
0x180069525  call    cs:__imp_RegDeleteKeyW
0x18006952c  nop     dword ptr [rax+rax+00h]
0x180069531  test    eax, eax
0x180069533  jz      short loc_18006953F
0x180069535  mov     edx, 0B8h
0x18006953a  jmp     loc_1800693CF
0x18006953f  xor     r9d, r9d; dwItem2
0x180069542  xor     r8d, r8d; dwItem1
0x180069545  xor     edx, edx; uFlags
0x180069547  mov     ecx, 8000000h; wEventId
0x18006954c  call    cs:__imp_SHChangeNotify
0x180069553  nop     dword ptr [rax+rax+00h]
0x180069558  test    cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 8
0x18006955f  jz      short loc_180069584
0x180069561  lea     rax, [rbp+lpSubKey]
0x180069565  mov     [rsp+80h+phkResult], rax
0x18006956a  mov     r9d, 1
0x180069570  lea     rdx, ShellRefreshSuccess
0x180069577  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18006957e  call    McGenEventWrite_EventWriteTransfer
0x180069583  nop
0x180069584  lea     rcx, [rbp+var_48]
0x180069588  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006958d  nop
0x18006958e  lea     rcx, [rbp+hKey]; this
0x180069592  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180069597  nop
0x180069598  test    rdi, rdi
0x18006959b  jz      loc_18006930E
0x1800695a1  mov     rcx, rdi; void *
0x1800695a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800695a9  jmp     loc_18006930E
0x1800695ae  mov     edx, 0A5h; void *
0x1800695b3  mov     r9d, 8007000Dh; char *
0x1800695b9  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800695c0  mov     rcx, [rbp+18h]; this
0x1800695c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800695c9  nop
0x1800695ca  lea     rcx, [rbp+var_48]
0x1800695ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800695d3  nop
0x1800695d4  lea     rcx, [rbp+hKey]; this
0x1800695d8  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800695dd  nop
0x1800695de  test    rdi, rdi
0x1800695e1  jz      short loc_1800695EB
0x1800695e3  mov     rcx, rdi; void *
0x1800695e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800695eb  mov     eax, 8007000Dh
0x1800695f0  jmp     short loc_180069638
0x1800695f2  mov     edx, 0A4h
0x1800695f7  jmp     loc_1800693CF
0x1800695fc  mov     rcx, [rbp+18h]; this
0x180069600  mov     r9d, esi; char *
0x180069603  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006960a  mov     edx, 99h; void *
0x18006960f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069614  nop
0x180069615  lea     rcx, [rbp+var_48]
0x180069619  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006961e  nop
0x18006961f  lea     rcx, [rbp+hKey]; this
0x180069623  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180069628  nop
0x180069629  test    rdi, rdi
0x18006962c  jz      short loc_180069636
0x18006962e  mov     rcx, rdi; void *
0x180069631  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069636  mov     eax, esi
0x180069638  mov     rcx, [rbp+var_10]
0x18006963c  xor     rcx, rsp; StackCookie
0x18006963f  call    __security_check_cookie
0x180069644  lea     r11, [rsp+80h+var_s0]
0x18006964c  mov     rbx, [r11+28h]
0x180069650  mov     rsi, [r11+30h]
0x180069654  mov     rsp, r11
0x180069657  pop     r14
0x180069659  pop     rdi
0x18006965a  pop     rbp
0x18006965b  retn
```
