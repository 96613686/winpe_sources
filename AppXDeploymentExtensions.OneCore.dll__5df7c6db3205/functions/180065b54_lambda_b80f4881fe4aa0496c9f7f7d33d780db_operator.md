# _lambda_b80f4881fe4aa0496c9f7f7d33d780db_::operator()

- ea: `0x180065b54`
- end: `0x180065ee2`
- name: `_lambda_b80f4881fe4aa0496c9f7f7d33d780db_::operator()`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180065880`

## callees

- `0x18000e6e0`
- `0x18004bac8`
- `0x18005ded4`
- `0x180065b54`
- `0x180065ee8`
- `0x180065ff8`
- `0x18006601c`
- `0x18006cb78`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a2854`
- `0x1800baaac`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f20d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065ca8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065d8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065e09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065d8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065e09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065da0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065da0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180065c0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180065c0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065c72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065d27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065c72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065d27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c3f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180065d5a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180065d5a`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180065dca`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180065dca`

## string_xrefs

- `0x180065bf4`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180065cc7`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180065d6b`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180065e53`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`
- `0x180065e8d`: `onecore\admin\appmodel\osim\src\deh\appx\common\shellrefresh.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_b80f4881fe4aa0496c9f7f7d33d780db_::operator()(PHKEY *a1, __int64 a2)
{
  Common::Deployment *v3; // rcx
  struct Common::StringBuffer *v4; // r8
  unsigned int v5; // ebx
  int ShellRefreshRegistryLocation; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  WCHAR *v11; // rbx
  HANDLE EventW; // rax
  const char *v13; // r9
  char *v14; // rdi
  unsigned int LastError; // eax
  int i; // eax
  int v17; // eax
  unsigned int v18; // esi
  unsigned int v19; // eax
  char *v20; // rdx
  unsigned __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  DWORD Type; // [rsp+30h] [rbp-50h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-4Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  DWORD lpcbData; // [rsp+40h] [rbp-40h] BYREF
  BYTE v29[4]; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD cbData; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-30h] BYREF
  int v32; // [rsp+60h] [rbp-20h]
  HANDLE hObject[2]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_OWORD *)lpSubKey = 0;
  v32 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = -1;
  cbData = 4;
  *(_DWORD *)v29 = -1;
  lpcbData = 4;
  hObject[0] = 0;
  McGenEventRegister_EventRegister(
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
    a2,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context);
  if ( !(unsigned __int8)IsSHChangeNotifyPresent() )
  {
    v5 = 0;
LABEL_42:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hObject);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return v5;
  }
  ShellRefreshRegistryLocation = Common::Deployment::GetShellRefreshRegistryLocation(v3, (int)lpSubKey, v4);
  v5 = ShellRefreshRegistryLocation;
  if ( ShellRefreshRegistryLocation < 0 )
  {
    v7 = (unsigned int)ShellRefreshRegistryLocation;
    v8 = 98;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
      (const char *)v7,
      phkResult);
    goto LABEL_42;
  }
  v9 = RegOpenCurrentUser(0xF003Fu, *a1);
  if ( v9 )
  {
    v10 = 104;
LABEL_40:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
                  (const char *)v9,
                  phkResult);
    goto LABEL_41;
  }
  v11 = (WCHAR *)lpSubKey[1];
  v9 = RegOpenKeyExW(**a1, lpSubKey[1], 0, 0xF003Fu, &hKey);
  if ( v9 )
  {
    v10 = 113;
    goto LABEL_40;
  }
  v9 = RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData);
  if ( v9 )
  {
    v10 = 123;
    goto LABEL_40;
  }
  if ( Type != 4 )
  {
    v5 = -2147024883;
    v7 = 2147942413LL;
    v8 = 124;
    goto LABEL_5;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    hObject,
    EventW);
  v14 = (char *)hObject[0];
  if ( !hObject[0] )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
                  v13);
LABEL_41:
    v5 = LastError;
    goto LABEL_42;
  }
  for ( i = 0; ; i = 1 )
  {
    v17 = PumpWindowsMessagesUntilTimeout(i != 0 ? 15000 : 10000, v14);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
        (const char *)(unsigned int)v17,
        phkResult);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hObject);
      Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
      return v18;
    }
    lpcbData = 4;
    v9 = RegQueryValueExW(hKey, 0, 0, &Type, v29, &lpcbData);
    if ( v9 )
    {
      v10 = 164;
      goto LABEL_40;
    }
    if ( Type != 4 )
    {
      v5 = -2147024883;
      v7 = 2147942413LL;
      v8 = 165;
      goto LABEL_5;
    }
    if ( *(_DWORD *)v29 == *(_DWORD *)Data )
      break;
    *(_DWORD *)Data = *(_DWORD *)v29;
  }
  v19 = RegDeleteKeyW(**a1, v11);
  if ( v19 )
  {
    v18 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xB8,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\shellrefresh.cpp",
            (const char *)v19,
            phkResult);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    v20 = (char *)hKey - 1;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    if ( v11 )
      operator delete(v11, (unsigned __int64)v20);
    return v18;
  }
  SHChangeNotify(0x8000000, 0, 0, 0);
  if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
      ShellRefreshSuccess,
      v22,
      1,
      hObject);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( v11 )
    operator delete(v11, v21);
  return 0;
}

```

## disassembly

```asm
0x180065b54  mov     [rsp-18h+arg_8], rbx
0x180065b59  mov     [rsp-18h+arg_10], rsi
0x180065b5e  push    rbp
0x180065b5f  push    rdi
0x180065b60  push    r14
0x180065b62  mov     rbp, rsp
0x180065b65  sub     rsp, 80h
0x180065b6c  mov     rax, cs:__security_cookie
0x180065b73  xor     rax, rsp
0x180065b76  mov     [rbp+var_8], rax
0x180065b7a  mov     r14, rcx
0x180065b7d  xor     eax, eax
0x180065b7f  xorps   xmm0, xmm0
0x180065b82  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180065b86  mov     [rbp+var_20], eax
0x180065b89  mov     [rbp+hKey], rax
0x180065b8d  mov     [rbp+Type], eax
0x180065b90  or      eax, 0FFFFFFFFh
0x180065b93  mov     dword ptr [rbp+Data], eax
0x180065b96  mov     [rbp+cbData], 4
0x180065b9d  mov     dword ptr [rbp+var_3C], eax
0x180065ba0  mov     [rbp+var_40], 4
0x180065ba7  mov     [rbp+hObject], 0
0x180065baf  lea     r9, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x180065bb6  lea     r8, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x180065bbd  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID
0x180065bc4  call    McGenEventRegister_EventRegister
0x180065bc9  call    IsSHChangeNotifyPresent
0x180065bce  test    al, al
0x180065bd0  jnz     short loc_180065BD9
0x180065bd2  xor     ebx, ebx
0x180065bd4  jmp     loc_180065E65
0x180065bd9  lea     rdx, [rbp+lpSubKey]; int
0x180065bdd  call    ?GetShellRefreshRegistryLocation@Deployment@Common@@YAJHPEAVStringBuffer@2@@Z; Common::Deployment::GetShellRefreshRegistryLocation(int,Common::StringBuffer *)
0x180065be2  mov     ebx, eax
0x180065be4  test    eax, eax
0x180065be6  jns     short loc_180065C05
0x180065be8  mov     r9d, eax; char *
0x180065beb  mov     edx, 62h ; 'b'; void *
0x180065bf0  mov     rcx, [rbp+18h]; this
0x180065bf4  lea     r8, aOnecoreAdminAp_166; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180065bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065c00  jmp     loc_180065E65
0x180065c05  mov     rdx, [r14]; phkResult
0x180065c08  mov     ebx, 0F003Fh
0x180065c0d  mov     ecx, ebx; samDesired
0x180065c0f  call    cs:__imp_RegOpenCurrentUser
0x180065c15  test    eax, eax
0x180065c17  jz      short loc_180065C23
0x180065c19  mov     edx, 68h ; 'h'
0x180065c1e  jmp     loc_180065E50
0x180065c23  mov     rcx, [r14]
0x180065c26  lea     rax, [rbp+hKey]
0x180065c2a  mov     [rsp+80h+phkResult], rax; phkResult
0x180065c2f  mov     r9d, ebx; samDesired
0x180065c32  xor     r8d, r8d; ulOptions
0x180065c35  mov     rbx, [rbp+lpSubKey+8]
0x180065c39  mov     rdx, rbx; lpSubKey
0x180065c3c  mov     rcx, [rcx]; hKey
0x180065c3f  call    cs:__imp_RegOpenKeyExW
0x180065c45  test    eax, eax
0x180065c47  jz      short loc_180065C53
0x180065c49  mov     edx, 71h ; 'q'
0x180065c4e  jmp     loc_180065E50
0x180065c53  lea     rax, [rbp+cbData]
0x180065c57  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180065c5c  lea     rax, [rbp+Data]
0x180065c60  mov     [rsp+80h+phkResult], rax; int
0x180065c65  lea     r9, [rbp+Type]; lpType
0x180065c69  xor     r8d, r8d; lpReserved
0x180065c6c  xor     edx, edx; lpValueName
0x180065c6e  mov     rcx, [rbp+hKey]; hKey
0x180065c72  call    cs:__imp_RegQueryValueExW
0x180065c78  test    eax, eax
0x180065c7a  jz      short loc_180065C86
0x180065c7c  mov     edx, 7Bh ; '{'
0x180065c81  jmp     loc_180065E50
0x180065c86  cmp     [rbp+Type], 4
0x180065c8a  jz      short loc_180065C9E
0x180065c8c  mov     ebx, 8007000Dh
0x180065c91  mov     r9d, ebx
0x180065c94  mov     edx, 7Ch ; '|'
0x180065c99  jmp     loc_180065BF0
0x180065c9e  xor     r9d, r9d; lpName
0x180065ca1  xor     r8d, r8d; bInitialState
0x180065ca4  xor     edx, edx; bManualReset
0x180065ca6  xor     ecx, ecx; lpEventAttributes
0x180065ca8  call    cs:__imp_CreateEventW
0x180065cae  mov     rdx, rax
0x180065cb1  lea     rcx, [rbp+hObject]
0x180065cb5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180065cba  mov     rdi, [rbp+hObject]
0x180065cbe  test    rdi, rdi
0x180065cc1  jnz     short loc_180065CDD
0x180065cc3  mov     rcx, [rbp+18h]; this
0x180065cc7  lea     r8, aOnecoreAdminAp_166; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180065cce  mov     edx, 81h; void *
0x180065cd3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180065cd8  jmp     loc_180065E63
0x180065cdd  xor     eax, eax
0x180065cdf  neg     eax
0x180065ce1  sbb     ecx, ecx
0x180065ce3  and     ecx, 1388h
0x180065ce9  add     ecx, 2710h; unsigned int
0x180065cef  mov     rdx, rdi; void *
0x180065cf2  call    ?PumpWindowsMessagesUntilTimeout@@YAJKPEAX@Z; PumpWindowsMessagesUntilTimeout(ulong,void *)
0x180065cf7  mov     esi, eax
0x180065cf9  test    eax, eax
0x180065cfb  js      loc_180065E86
0x180065d01  mov     [rbp+var_40], 4
0x180065d08  lea     rax, [rbp+var_40]
0x180065d0c  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180065d11  lea     rax, [rbp+var_3C]
0x180065d15  mov     [rsp+80h+phkResult], rax; unsigned int
0x180065d1a  lea     r9, [rbp+Type]; lpType
0x180065d1e  xor     r8d, r8d; lpReserved
0x180065d21  xor     edx, edx; lpValueName
0x180065d23  mov     rcx, [rbp+hKey]; hKey
0x180065d27  call    cs:__imp_RegQueryValueExW
0x180065d2d  test    eax, eax
0x180065d2f  jnz     loc_180065E4B
0x180065d35  cmp     [rbp+Type], 4
0x180065d39  jnz     loc_180065E39
0x180065d3f  mov     eax, dword ptr [rbp+var_3C]
0x180065d42  cmp     eax, dword ptr [rbp+Data]
0x180065d45  jz      short loc_180065D51
0x180065d47  mov     dword ptr [rbp+Data], eax
0x180065d4a  mov     eax, 1
0x180065d4f  jmp     short loc_180065CDF
0x180065d51  mov     rcx, [r14]
0x180065d54  mov     rdx, rbx; lpSubKey
0x180065d57  mov     rcx, [rcx]; hKey
0x180065d5a  call    cs:__imp_RegDeleteKeyW
0x180065d60  test    eax, eax
0x180065d62  jz      short loc_180065DBD
0x180065d64  mov     rcx, [rbp+18h]; this
0x180065d68  mov     r9d, eax; char *
0x180065d6b  lea     r8, aOnecoreAdminAp_166; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180065d72  mov     edx, 0B8h; void *
0x180065d77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180065d7c  mov     esi, eax
0x180065d7e  lea     rdx, [rdi-1]
0x180065d82  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180065d86  ja      short loc_180065D92
0x180065d88  mov     rcx, rdi; hObject
0x180065d8b  call    cs:__imp_CloseHandle
0x180065d91  nop
0x180065d92  mov     rcx, [rbp+hKey]; hKey
0x180065d96  lea     rdx, [rcx-1]
0x180065d9a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180065d9e  ja      short loc_180065DA7
0x180065da0  call    cs:__imp_RegCloseKey
0x180065da6  nop
0x180065da7  test    rbx, rbx
0x180065daa  jz      loc_180065EBC
0x180065db0  mov     rcx, rbx; void *
0x180065db3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180065db8  jmp     loc_180065EBC
0x180065dbd  xor     r9d, r9d; dwItem2
0x180065dc0  xor     r8d, r8d; dwItem1
0x180065dc3  xor     edx, edx; uFlags
0x180065dc5  mov     ecx, 8000000h; wEventId
0x180065dca  call    cs:__imp_SHChangeNotify
0x180065dd0  test    cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 8
0x180065dd7  jz      short loc_180065DFC
0x180065dd9  lea     rax, [rbp+hObject]
0x180065ddd  mov     [rsp+80h+phkResult], rax
0x180065de2  mov     r9d, 1
0x180065de8  lea     rdx, ShellRefreshSuccess
0x180065def  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x180065df6  call    McGenEventWrite_EventWriteTransfer
0x180065dfb  nop
0x180065dfc  lea     rax, [rdi-1]
0x180065e00  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180065e04  ja      short loc_180065E10
0x180065e06  mov     rcx, rdi; hObject
0x180065e09  call    cs:__imp_CloseHandle
0x180065e0f  nop
0x180065e10  mov     rcx, [rbp+hKey]; hKey
0x180065e14  lea     rax, [rcx-1]
0x180065e18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180065e1c  ja      short loc_180065E25
0x180065e1e  call    cs:__imp_RegCloseKey
0x180065e24  nop
0x180065e25  test    rbx, rbx
0x180065e28  jz      short loc_180065E32
0x180065e2a  mov     rcx, rbx; void *
0x180065e2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180065e32  xor     eax, eax
0x180065e34  jmp     loc_180065EBE
0x180065e39  mov     ebx, 8007000Dh
0x180065e3e  mov     r9d, ebx
0x180065e41  mov     edx, 0A5h
0x180065e46  jmp     loc_180065BF0
0x180065e4b  mov     edx, 0A4h; void *
0x180065e50  mov     r9d, eax; char *
0x180065e53  lea     r8, aOnecoreAdminAp_166; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180065e5a  mov     rcx, [rbp+18h]; this
0x180065e5e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180065e63  mov     ebx, eax
0x180065e65  lea     rcx, [rbp+hObject]
0x180065e69  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180065e6e  nop
0x180065e6f  lea     rcx, [rbp+hKey]; this
0x180065e73  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180065e78  nop
0x180065e79  lea     rcx, [rbp+lpSubKey]; this
0x180065e7d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180065e82  mov     eax, ebx
0x180065e84  jmp     short loc_180065EBE
0x180065e86  mov     rcx, [rbp+18h]; this
0x180065e8a  mov     r9d, esi; char *
0x180065e8d  lea     r8, aOnecoreAdminAp_166; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180065e94  mov     edx, 99h; void *
0x180065e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065e9e  nop
0x180065e9f  lea     rcx, [rbp+hObject]
0x180065ea3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180065ea8  nop
0x180065ea9  lea     rcx, [rbp+hKey]; this
0x180065ead  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180065eb2  nop
0x180065eb3  lea     rcx, [rbp+lpSubKey]; this
0x180065eb7  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180065ebc  mov     eax, esi
0x180065ebe  mov     rcx, [rbp+var_8]
0x180065ec2  xor     rcx, rsp; StackCookie
0x180065ec5  call    __security_check_cookie
0x180065eca  lea     r11, [rsp+80h+var_s0]
0x180065ed2  mov     rbx, [r11+28h]
0x180065ed6  mov     rsi, [r11+30h]
0x180065eda  mov     rsp, r11
0x180065edd  pop     r14
0x180065edf  pop     rdi
0x180065ee0  pop     rbp
0x180065ee1  retn
```
