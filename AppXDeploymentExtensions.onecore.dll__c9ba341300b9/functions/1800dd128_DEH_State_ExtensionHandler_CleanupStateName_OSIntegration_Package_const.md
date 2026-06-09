# DEH::State::ExtensionHandler::CleanupStateName(OSIntegration::Package const *)

- ea: `0x1800dd128`
- end: `0x1800dd49f`
- name: `?CleanupStateName@ExtensionHandler@State@DEH@@IEAAJPEBVPackage@OSIntegration@@@Z`
- size: `887`
- prototype: `__int64 __fastcall(const char **this, const struct OSIntegration::Package *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800dce30`

## callees

- `0x18001c348`
- `0x18001c3c8`
- `0x18002b7f0`
- `0x1800502f4`
- `0x180054800`
- `0x180070b78`
- `0x180087238`
- `0x1800a8f80`
- `0x1800a8fc8`
- `0x1800b8300`
- `0x1800dd128`
- `0x1800f0700`
- `0x1801295cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800dd3f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800dd3f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800dd43f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800dd43f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dd206`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dd24a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dd2c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dd206`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dd24a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dd2c8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800dd36b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800dd36b`

## string_xrefs

- `0x1800dd215`: `RegOpenKeyEx %ws`
- `0x1800dd259`: `RegOpenKeyEx %ws`
- `0x1800dd2f3`: `RegOpenKeyEx %ws`
- `0x1800dd175`: `DropImpersonation %ws %ws`
- `0x1800dd344`: `DeleteStateNameForUser %ws %ws`
- `0x1800dd1be`: `GetPersistedRegKeyPath`
- `0x1800dd3a1`: `RegDeleteKeyW  %ws %ws`
- `0x1800dd44d`: `RegDeleteTreeW`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DEH::State::ExtensionHandler::CleanupStateName(
        const char **this,
        const struct OSIntegration::Package *a2)
{
  __int64 v4; // rdi
  const char *v5; // rbx
  unsigned int v6; // eax
  int PersistedRegKeyPath; // edi
  WCHAR *v8; // rbx
  unsigned __int64 v9; // rdx
  HKEY *phkResult; // rax
  unsigned int v11; // eax
  int v12; // eax
  HKEY *v13; // rax
  unsigned int v14; // eax
  unsigned __int64 v15; // rdx
  HKEY *v16; // rax
  unsigned int v17; // eax
  DEH::State::ExtensionHandler *v18; // rcx
  int v19; // eax
  __int64 v20; // rbx
  const char *v21; // rdi
  unsigned int v22; // eax
  int v23; // eax
  char v24; // dl
  unsigned int v25; // eax
  unsigned int v26; // eax
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-50h]
  const char *lpcbMaxSubKeyLena; // [rsp+28h] [rbp-50h]
  void *TokenHandle[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  DWORD cSubKeys; // [rsp+C0h] [rbp+48h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+D0h] [rbp+58h] BYREF
  HKEY v35; // [rsp+D8h] [rbp+60h] BYREF

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  TokenHandle[0] = 0;
  v4 = *((_QWORD *)a2 + 31);
  v5 = this[10];
  v6 = Common::AutoNoImpersonateDuringScope::DropImpersonation(TokenHandle);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x4CE,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
    (const char *)v6,
    (__int64)"DropImpersonation %ws %ws",
    v5,
    v4);
  v35 = 0;
  lpSubKey = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                          (const struct Common::StateSeparationRedirectionMapping *)&Common::StateSeparation::AppxRoot,
                          (unsigned __int16 **)&lpSubKey);
  v8 = (WCHAR *)lpSubKey;
  if ( PersistedRegKeyPath >= 0 )
  {
    hKey = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0xF003Fu, phkResult);
    if ( v11 )
    {
      v12 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x4D9,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
              (const char *)v11,
              (unsigned int)"RegOpenKeyEx %ws",
              (const char *)v8);
LABEL_9:
      PersistedRegKeyPath = v12;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_10;
    }
    v13 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v35);
    v14 = RegOpenKeyExW(hKey, L"PackageState", 0, 0xF003Fu, v13);
    if ( v14 )
    {
      v12 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x4DE,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
              (const char *)v14,
              (unsigned int)"RegOpenKeyEx %ws",
              (const char *)L"PackageState");
      goto LABEL_9;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    operator delete(v8, v15);
    cSubKeys = 0;
    lpSubKey = 0;
    v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&lpSubKey);
    v17 = RegOpenKeyExW(v35, (LPCWSTR)this[10], 0, 0xF003Fu, v16);
    if ( v17 == 2 || v17 == 1168 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpSubKey);
    }
    else
    {
      if ( v17 )
      {
        v19 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0x4E8,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
                (const char *)v17,
                (unsigned int)"RegOpenKeyEx %ws",
                this[10]);
LABEL_15:
        PersistedRegKeyPath = v19;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpSubKey);
        goto LABEL_27;
      }
      v20 = *((_QWORD *)a2 + 31);
      v21 = this[10];
      v22 = DEH::State::ExtensionHandler::DeleteStateNameForUser(v18, (HKEY)lpSubKey, a2);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
        (const char *)v22,
        (__int64)"DeleteStateNameForUser %ws %ws",
        v21,
        v20);
      v23 = RegDeleteKeyW((HKEY)lpSubKey, *((LPCWSTR *)a2 + 31));
      if ( v23 >= 0 )
      {
        v24 = 0;
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v24 = 1;
      }
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
        (const char *)(unsigned int)v23,
        v24,
        (bool)"RegDeleteKeyW  %ws %ws",
        this[10],
        *((_QWORD *)a2 + 31));
      v25 = RegQueryInfoKeyW((HKEY)lpSubKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      if ( v25 )
      {
        v19 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0x4F5,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
                (const char *)v25,
                (unsigned int)"RegQueryInfoKey",
                lpcbMaxSubKeyLena);
        goto LABEL_15;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpSubKey);
      if ( !cSubKeys )
      {
        v26 = RegDeleteTreeW(v35, (LPCWSTR)this[10]);
        if ( v26 )
        {
          PersistedRegKeyPath = wil::details::in1diag3::Return_Win32Msg(
                                  retaddr,
                                  (void *)0x4F9,
                                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
                                  (const char *)v26,
                                  (unsigned int)"RegDeleteTreeW",
                                  lpcbMaxSubKeyLena);
          goto LABEL_27;
        }
      }
    }
    PersistedRegKeyPath = 0;
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x4D5,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\state\\state.cpp",
    (const char *)(unsigned int)PersistedRegKeyPath,
    (int)"GetPersistedRegKeyPath",
    lpcbMaxSubKeyLen);
LABEL_10:
  operator delete(v8, v9);
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
  Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)TokenHandle);
  return (unsigned int)PersistedRegKeyPath;
}

```

## disassembly

```asm
0x1800dd128  push    rbp
0x1800dd12a  push    rbx
0x1800dd12b  push    rsi
0x1800dd12c  push    rdi
0x1800dd12d  push    r12
0x1800dd12f  push    r13
0x1800dd131  push    r14
0x1800dd133  push    r15
0x1800dd135  mov     rbp, rsp
0x1800dd138  sub     rsp, 78h
0x1800dd13c  mov     r14, rdx
0x1800dd13f  mov     rsi, rcx
0x1800dd142  xor     r15d, r15d
0x1800dd145  test    rdx, rdx
0x1800dd148  jnz     short loc_1800DD14F
0x1800dd14a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800dd14f  mov     [rbp+TokenHandle], r15
0x1800dd153  mov     rdi, [r14+0F8h]
0x1800dd15a  mov     rbx, [rsi+50h]
0x1800dd15e  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x1800dd162  call    ?DropImpersonation@AutoNoImpersonateDuringScope@Common@@QEAAJXZ; Common::AutoNoImpersonateDuringScope::DropImpersonation(void)
0x1800dd167  mov     rcx, [rbp+40h]; this
0x1800dd16b  mov     [rsp+78h+lpcbMaxClassLen], rdi
0x1800dd170  mov     [rsp+78h+lpcbMaxSubKeyLen], rbx; char *
0x1800dd175  lea     rdx, aDropimpersonat; "DropImpersonation %ws %ws"
0x1800dd17c  mov     [rsp+78h+phkResult], rdx; __int64
0x1800dd181  mov     r9d, eax; char *
0x1800dd184  lea     r12, aOnecoreAdminAp_31; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd18b  mov     r8, r12; unsigned int
0x1800dd18e  mov     edx, 4CEh; void *
0x1800dd193  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800dd198  mov     [rbp+arg_18], r15
0x1800dd19c  mov     [rbp+lpSubKey], r15
0x1800dd1a0  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x1800dd1a4  lea     rcx, ?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x1800dd1ab  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x1800dd1b0  mov     edi, eax
0x1800dd1b2  mov     rbx, [rbp+lpSubKey]
0x1800dd1b6  test    eax, eax
0x1800dd1b8  jns     short loc_1800DD1DF
0x1800dd1ba  mov     rcx, [rbp+40h]; this
0x1800dd1be  lea     rax, aGetpersistedre; "GetPersistedRegKeyPath"
0x1800dd1c5  mov     [rsp+78h+phkResult], rax; int
0x1800dd1ca  mov     r9d, edi; char *
0x1800dd1cd  mov     r8, r12; unsigned int
0x1800dd1d0  mov     edx, 4D5h; void *
0x1800dd1d5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800dd1da  jmp     loc_1800DD285
0x1800dd1df  mov     [rbp+hKey], r15
0x1800dd1e3  lea     rcx, [rbp+hKey]
0x1800dd1e7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800dd1ec  mov     [rsp+78h+phkResult], rax; phkResult
0x1800dd1f1  mov     edi, 0F003Fh
0x1800dd1f6  mov     r9d, edi; samDesired
0x1800dd1f9  xor     r8d, r8d; ulOptions
0x1800dd1fc  mov     rdx, rbx; lpSubKey
0x1800dd1ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dd206  call    cs:__imp_RegOpenKeyExW
0x1800dd20c  test    eax, eax
0x1800dd20e  jz      short loc_1800DD228
0x1800dd210  mov     [rsp+78h+lpcbMaxSubKeyLen], rbx
0x1800dd215  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx %ws"
0x1800dd21c  mov     [rsp+78h+phkResult], rdx
0x1800dd221  mov     edx, 4D9h
0x1800dd226  jmp     short loc_1800DD26A
0x1800dd228  lea     rcx, [rbp+arg_18]
0x1800dd22c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800dd231  mov     [rsp+78h+phkResult], rax; phkResult
0x1800dd236  mov     r9d, edi; samDesired
0x1800dd239  xor     r8d, r8d; ulOptions
0x1800dd23c  lea     r13, aPackagestate; "PackageState"
0x1800dd243  mov     rdx, r13; lpSubKey
0x1800dd246  mov     rcx, [rbp+hKey]; hKey
0x1800dd24a  call    cs:__imp_RegOpenKeyExW
0x1800dd250  test    eax, eax
0x1800dd252  jz      short loc_1800DD292
0x1800dd254  mov     [rsp+78h+lpcbMaxSubKeyLen], r13; char *
0x1800dd259  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx %ws"
0x1800dd260  mov     [rsp+78h+phkResult], rdx; unsigned int
0x1800dd265  mov     edx, 4DEh; void *
0x1800dd26a  mov     r9d, eax; char *
0x1800dd26d  mov     r8, r12; unsigned int
0x1800dd270  mov     rcx, [rbp+40h]; this
0x1800dd274  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800dd279  mov     edi, eax
0x1800dd27b  lea     rcx, [rbp+hKey]
0x1800dd27f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dd284  nop
0x1800dd285  mov     rcx, rbx; void *
0x1800dd288  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dd28d  jmp     loc_1800DD479
0x1800dd292  lea     rcx, [rbp+hKey]
0x1800dd296  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dd29b  nop
0x1800dd29c  mov     rcx, rbx; void *
0x1800dd29f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dd2a4  mov     [rbp+cSubKeys], r15d
0x1800dd2a8  mov     [rbp+lpSubKey], r15
0x1800dd2ac  lea     rcx, [rbp+lpSubKey]
0x1800dd2b0  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800dd2b5  mov     [rsp+78h+phkResult], rax; phkResult
0x1800dd2ba  mov     r9d, edi; samDesired
0x1800dd2bd  xor     r8d, r8d; ulOptions
0x1800dd2c0  mov     rdx, [rsi+50h]; lpSubKey
0x1800dd2c4  mov     rcx, [rbp+arg_18]; hKey
0x1800dd2c8  call    cs:__imp_RegOpenKeyExW
0x1800dd2ce  cmp     eax, 2
0x1800dd2d1  jz      loc_1800DD46D
0x1800dd2d7  cmp     eax, 490h
0x1800dd2dc  jz      loc_1800DD46D
0x1800dd2e2  test    eax, eax
0x1800dd2e4  jz      short loc_1800DD31F
0x1800dd2e6  mov     rcx, [rbp+40h]; this
0x1800dd2ea  mov     rdx, [rsi+50h]
0x1800dd2ee  mov     [rsp+78h+lpcbMaxSubKeyLen], rdx; char *
0x1800dd2f3  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx %ws"
0x1800dd2fa  mov     [rsp+78h+phkResult], rdx; unsigned int
0x1800dd2ff  mov     r9d, eax; char *
0x1800dd302  mov     r8, r12; unsigned int
0x1800dd305  mov     edx, 4E8h; void *
0x1800dd30a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800dd30f  mov     edi, eax
0x1800dd311  lea     rcx, [rbp+lpSubKey]
0x1800dd315  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dd31a  jmp     loc_1800DD479
0x1800dd31f  mov     rbx, [r14+0F8h]
0x1800dd326  mov     rdi, [rsi+50h]
0x1800dd32a  mov     r8, r14; struct OSIntegration::Package *
0x1800dd32d  mov     rdx, [rbp+lpSubKey]; HKEY
0x1800dd331  call    ?DeleteStateNameForUser@ExtensionHandler@State@DEH@@IEAAJQEAUHKEY__@@PEBVPackage@OSIntegration@@@Z; DEH::State::ExtensionHandler::DeleteStateNameForUser(HKEY__ * const,OSIntegration::Package const *)
0x1800dd336  mov     rcx, [rbp+40h]; this
0x1800dd33a  mov     [rsp+78h+lpcbMaxClassLen], rbx
0x1800dd33f  mov     [rsp+78h+lpcbMaxSubKeyLen], rdi; char *
0x1800dd344  lea     rdx, aDeletestatenam; "DeleteStateNameForUser %ws %ws"
0x1800dd34b  mov     [rsp+78h+phkResult], rdx; __int64
0x1800dd350  mov     r9d, eax; char *
0x1800dd353  mov     r8, r12; unsigned int
0x1800dd356  mov     edx, 4EBh; void *
0x1800dd35b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800dd360  mov     rdx, [r14+0F8h]; lpSubKey
0x1800dd367  mov     rcx, [rbp+lpSubKey]; hKey
0x1800dd36b  call    cs:__imp_RegDeleteKeyW
0x1800dd371  mov     r8, [r14+0F8h]
0x1800dd378  mov     r9, [rsi+50h]
0x1800dd37c  test    eax, eax
0x1800dd37e  jns     short loc_1800DD384
0x1800dd380  mov     dl, 1
0x1800dd382  jmp     short loc_1800DD393
0x1800dd384  mov     dl, r15b
0x1800dd387  test    eax, eax
0x1800dd389  jle     short loc_1800DD393
0x1800dd38b  movzx   eax, ax
0x1800dd38e  or      eax, 80070000h
0x1800dd393  mov     rcx, [rbp+40h]; this
0x1800dd397  mov     [rsp+78h+lpcValues], r8
0x1800dd39c  mov     [rsp+78h+lpcbMaxClassLen], r9; char *
0x1800dd3a1  lea     r8, aRegdeletekeywW; "RegDeleteKeyW  %ws %ws"
0x1800dd3a8  mov     [rsp+78h+lpcbMaxSubKeyLen], r8; bool
0x1800dd3ad  mov     byte ptr [rsp+78h+phkResult], dl; char
0x1800dd3b1  mov     r9d, eax; char *
0x1800dd3b4  mov     r8, r12; unsigned int
0x1800dd3b7  mov     edx, 4F1h; void *
0x1800dd3bc  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800dd3c1  mov     [rsp+78h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800dd3c6  mov     [rsp+78h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800dd3cb  mov     [rsp+78h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800dd3d0  mov     [rsp+78h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800dd3d5  mov     [rsp+78h+lpcValues], r15; lpcValues
0x1800dd3da  mov     [rsp+78h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800dd3df  mov     [rsp+78h+lpcbMaxSubKeyLen], r15; char *
0x1800dd3e4  lea     rax, [rbp+cSubKeys]
0x1800dd3e8  mov     [rsp+78h+phkResult], rax; lpcSubKeys
0x1800dd3ed  xor     r9d, r9d; lpReserved
0x1800dd3f0  xor     r8d, r8d; lpcchClass
0x1800dd3f3  xor     edx, edx; lpClass
0x1800dd3f5  mov     rcx, [rbp+lpSubKey]; hKey
0x1800dd3f9  call    cs:__imp_RegQueryInfoKeyW
0x1800dd3ff  test    eax, eax
0x1800dd401  jz      short loc_1800DD428
0x1800dd403  mov     rcx, [rbp+40h]; this
0x1800dd407  lea     rdx, aRegqueryinfoke; "RegQueryInfoKey"
0x1800dd40e  mov     [rsp+78h+phkResult], rdx; unsigned int
0x1800dd413  mov     r9d, eax; char *
0x1800dd416  mov     r8, r12; unsigned int
0x1800dd419  mov     edx, 4F5h; void *
0x1800dd41e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800dd423  jmp     loc_1800DD30F
0x1800dd428  lea     rcx, [rbp+lpSubKey]
0x1800dd42c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dd431  cmp     [rbp+cSubKeys], r15d
0x1800dd435  ja      short loc_1800DD476
0x1800dd437  mov     rdx, [rsi+50h]; lpSubKey
0x1800dd43b  mov     rcx, [rbp+arg_18]; hKey
0x1800dd43f  call    cs:__imp_RegDeleteTreeW
0x1800dd445  test    eax, eax
0x1800dd447  jz      short loc_1800DD476
0x1800dd449  mov     rcx, [rbp+40h]; this
0x1800dd44d  lea     rdx, aRegdeletetreew; "RegDeleteTreeW"
0x1800dd454  mov     [rsp+78h+phkResult], rdx; unsigned int
0x1800dd459  mov     r9d, eax; char *
0x1800dd45c  mov     r8, r12; unsigned int
0x1800dd45f  mov     edx, 4F9h; void *
0x1800dd464  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800dd469  mov     edi, eax
0x1800dd46b  jmp     short loc_1800DD479
0x1800dd46d  lea     rcx, [rbp+lpSubKey]
0x1800dd471  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dd476  mov     edi, r15d
0x1800dd479  lea     rcx, [rbp+arg_18]
0x1800dd47d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dd482  nop
0x1800dd483  lea     rcx, [rbp+TokenHandle]; this
0x1800dd487  call    ??1AutoNoImpersonateDuringScope@Common@@QEAA@XZ; Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope(void)
0x1800dd48c  mov     eax, edi
0x1800dd48e  add     rsp, 78h
0x1800dd492  pop     r15
0x1800dd494  pop     r14
0x1800dd496  pop     r13
0x1800dd498  pop     r12
0x1800dd49a  pop     rdi
0x1800dd49b  pop     rsi
0x1800dd49c  pop     rbx
0x1800dd49d  pop     rbp
0x1800dd49e  retn
```
