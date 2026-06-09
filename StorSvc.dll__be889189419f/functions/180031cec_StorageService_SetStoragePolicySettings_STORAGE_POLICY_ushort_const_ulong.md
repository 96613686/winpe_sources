# StorageService::SetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong)

- ea: `0x180031cec`
- end: `0x18003203a`
- name: `?SetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGK@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64, int, const WCHAR *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003037c`
- `0x1800379c0`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180012ce0`
- `0x180019d4c`
- `0x180019db4`
- `0x18001dcf4`
- `0x180030ab0`
- `0x180031cec`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003200c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003200c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031e9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031e9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031eb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031eb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031f6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031f6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031db8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031db8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180031f03`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180031f03`
- `RPCRT4!RpcRevertToSelf` at `0x180031f19`
- `RPCRT4!RpcRevertToSelf` at `0x180031f19`
- `RPCRT4!RpcImpersonateClient` at `0x180031ec2`
- `RPCRT4!RpcImpersonateClient` at `0x180031ec2`

## string_xrefs

- `0x180031d49`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031d85`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031df6`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031e28`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031e74`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031f89`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall StorageService::SetStoragePolicySettings(__int64 a1, int a2, const WCHAR *a3, int a4)
{
  __int64 v5; // r14
  int v6; // edi
  int v7; // eax
  int v8; // eax
  HANDLE CurrentThread; // rax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  signed int LastError; // eax
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  int Data; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v20[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v5 = a2;
  Data = a4;
  Microsoft::WRL::Wrappers::CriticalSection::Lock(qword_1800C11A8, &lpCriticalSection);
  if ( (unsigned int)v5 >= 0xC )
  {
    v6 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x8000FFFFLL,
      lpData);
LABEL_31:
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    return (unsigned int)v6;
  }
  if ( BYTE4(qword_18008E530[3 * v5 + 1]) )
  {
    v6 = -2147018887;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x80071779LL,
      lpData);
    goto LABEL_31;
  }
  hKey = 0;
  v7 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"StoragePolicy", &hKey);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v7,
      lpData);
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_31;
  }
  if ( !BYTE4(qword_18008E530[3 * v5]) && a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x80070057LL,
      lpData);
    goto LABEL_30;
  }
  v8 = StringCchPrintfW(ValueName, 0x104u, L"%02d", (unsigned int)(1 << v5));
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v8,
      lpData);
    goto LABEL_30;
  }
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_29;
  }
  v6 = RpcImpersonateClient(0);
  if ( v6 < 0 )
    goto LABEL_29;
  v10 = RegSetKeyValueW(hKey, a3, ValueName, 4u, &Data, 4u);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  RpcRevertToSelf();
  if ( v6 < 0 )
  {
LABEL_29:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_30;
  }
  if ( (_DWORD)v5 == 1 && Data )
  {
    *(_DWORD *)v20 = 1;
    v11 = RegSetValueExW(hKey, L"CloudfilePolicyConsent", 0, 4u, v20, 4u);
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v6,
        lpDataa);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_30;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( lpCriticalSection )
  {
    LeaveCriticalSection(lpCriticalSection);
    lpCriticalSection = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180031cec  push    rbp
0x180031cee  push    rbx
0x180031cef  push    rsi
0x180031cf0  push    rdi
0x180031cf1  push    r12
0x180031cf3  push    r14
0x180031cf5  push    r15
0x180031cf7  lea     rbp, [rsp-180h]
0x180031cff  sub     rsp, 280h
0x180031d06  mov     rax, cs:__security_cookie
0x180031d0d  xor     rax, rsp
0x180031d10  mov     [rbp+1B0h+var_40], rax
0x180031d17  mov     r15, r8
0x180031d1a  movsxd  r14, edx
0x180031d1d  mov     [rsp+2B0h+Data], r9d
0x180031d22  lea     rdx, [rsp+2B0h+lpCriticalSection]
0x180031d27  lea     rcx, qword_1800C11A8
0x180031d2e  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x180031d33  nop
0x180031d34  cmp     r14d, 0Ch
0x180031d38  jb      short loc_180031D62
0x180031d3a  mov     rcx, [rbp+1B8h]; this
0x180031d41  mov     edi, 8000FFFFh
0x180031d46  mov     r9d, edi; char *
0x180031d49  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031d50  mov     edx, 0DCh; void *
0x180031d55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d5a  nop
0x180031d5b  xor     ebx, ebx
0x180031d5d  jmp     loc_180032002
0x180031d62  lea     rsi, [r14+r14*2]
0x180031d66  lea     r12, qword_18008E530
0x180031d6d  xor     ebx, ebx
0x180031d6f  cmp     [r12+rsi*8+0Ch], bl
0x180031d74  jz      short loc_180031D9B
0x180031d76  mov     rcx, [rbp+1B8h]; this
0x180031d7d  mov     edi, 80071779h
0x180031d82  mov     r9d, edi; char *
0x180031d85  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031d8c  mov     edx, 0DDh; void *
0x180031d91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d96  jmp     loc_180032002
0x180031d9b  mov     [rsp+2B0h+hKey], rbx
0x180031da0  mov     rdi, [rsp+2B0h+hKey]
0x180031da5  test    rdi, rdi
0x180031da8  jz      short loc_180031DC9
0x180031daa  lea     rcx, [rsp+2B0h+var_260]; this
0x180031daf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180031db4  nop
0x180031db5  mov     rcx, rdi; hKey
0x180031db8  call    cs:__imp_RegCloseKey
0x180031dbe  nop
0x180031dbf  lea     rcx, [rsp+2B0h+var_260]; this
0x180031dc4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180031dc9  mov     [rsp+2B0h+hKey], rbx
0x180031dce  lea     r8, [rsp+2B0h+hKey]; phkResult
0x180031dd3  lea     rdx, aStoragepolicy; "StoragePolicy"
0x180031dda  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031de1  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180031de6  mov     edi, eax
0x180031de8  test    eax, eax
0x180031dea  jns     short loc_180031E0D
0x180031dec  mov     rcx, [rbp+1B8h]; this
0x180031df3  mov     r9d, eax; char *
0x180031df6  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031dfd  mov     edx, 0E3h; void *
0x180031e02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031e07  nop
0x180031e08  jmp     loc_180031FF7
0x180031e0d  cmp     [r12+rsi*8+4], bl
0x180031e12  jnz     short loc_180031E3F
0x180031e14  test    r15, r15
0x180031e17  jz      short loc_180031E3F
0x180031e19  mov     rcx, [rbp+1B8h]; this
0x180031e20  mov     edi, 80070057h
0x180031e25  mov     r9d, edi; char *
0x180031e28  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031e2f  mov     edx, 0E8h; void *
0x180031e34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031e39  nop
0x180031e3a  jmp     loc_180031FF7
0x180031e3f  mov     ecx, r14d
0x180031e42  mov     r12d, 1
0x180031e48  mov     r9d, r12d
0x180031e4b  shl     r9d, cl
0x180031e4e  lea     r8, a02d; "%02d"
0x180031e55  mov     edx, 104h; unsigned __int64
0x180031e5a  lea     rcx, [rsp+2B0h+ValueName]; unsigned __int16 *
0x180031e5f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031e64  mov     edi, eax
0x180031e66  test    eax, eax
0x180031e68  jns     short loc_180031E8B
0x180031e6a  mov     rcx, [rbp+1B8h]; this
0x180031e71  mov     r9d, eax; char *
0x180031e74  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031e7b  mov     edx, 0EAh; void *
0x180031e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031e85  nop
0x180031e86  jmp     loc_180031FF7
0x180031e8b  mov     [rsp+2B0h+TokenHandle], rbx
0x180031e90  xor     edx, edx
0x180031e92  lea     rcx, [rsp+2B0h+TokenHandle]
0x180031e97  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180031e9c  call    cs:__imp_GetCurrentThread
0x180031ea2  lea     r9, [rsp+2B0h+TokenHandle]; TokenHandle
0x180031ea7  mov     r8d, r12d; OpenAsSelf
0x180031eaa  mov     edx, 0Ch; DesiredAccess
0x180031eaf  mov     rcx, rax; ThreadHandle
0x180031eb2  call    cs:__imp_OpenThreadToken
0x180031eb8  test    eax, eax
0x180031eba  jnz     loc_180031FD7
0x180031ec0  xor     ecx, ecx; BindingHandle
0x180031ec2  call    cs:__imp_RpcImpersonateClient
0x180031ec8  mov     edi, eax
0x180031eca  test    eax, eax
0x180031ecc  jns     short loc_180031EDE
0x180031ece  lea     rcx, [rsp+2B0h+TokenHandle]
0x180031ed3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031ed8  nop
0x180031ed9  jmp     loc_180031FF7
0x180031ede  mov     [rsp+2B0h+cbData], 4; cbData
0x180031ee6  lea     rax, [rsp+2B0h+Data]
0x180031eeb  mov     [rsp+2B0h+lpData], rax; lpData
0x180031ef0  mov     r9d, 4; dwType
0x180031ef6  lea     r8, [rsp+2B0h+ValueName]; lpValueName
0x180031efb  mov     rdx, r15; lpSubKey
0x180031efe  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180031f03  call    cs:__imp_RegSetKeyValueW
0x180031f09  mov     edi, eax
0x180031f0b  mov     esi, 80070000h
0x180031f10  test    eax, eax
0x180031f12  jle     short loc_180031F19
0x180031f14  movzx   edi, ax
0x180031f17  or      edi, esi
0x180031f19  call    cs:__imp_RpcRevertToSelf
0x180031f1f  test    edi, edi
0x180031f21  jns     short loc_180031F33
0x180031f23  lea     rcx, [rsp+2B0h+TokenHandle]
0x180031f28  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031f2d  nop
0x180031f2e  jmp     loc_180031FF7
0x180031f33  cmp     r14d, r12d
0x180031f36  jnz     short loc_180031FA8
0x180031f38  cmp     [rsp+2B0h+Data], ebx
0x180031f3c  jz      short loc_180031FA8
0x180031f3e  mov     dword ptr [rsp+2B0h+var_260], r12d
0x180031f43  mov     [rsp+2B0h+cbData], 4; cbData
0x180031f4b  lea     rax, [rsp+2B0h+var_260]
0x180031f50  mov     [rsp+2B0h+lpData], rax; int
0x180031f55  mov     r9d, 4; dwType
0x180031f5b  xor     r8d, r8d; Reserved
0x180031f5e  lea     rdx, aCloudfilepolic; "CloudfilePolicyConsent"
0x180031f65  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180031f6a  call    cs:__imp_RegSetValueExW
0x180031f70  mov     edi, eax
0x180031f72  test    eax, eax
0x180031f74  jle     short loc_180031F7B
0x180031f76  movzx   edi, ax
0x180031f79  or      edi, esi
0x180031f7b  test    edi, edi
0x180031f7d  jns     short loc_180031FA8
0x180031f7f  mov     rcx, [rbp+1B8h]; this
0x180031f86  mov     r9d, edi; char *
0x180031f89  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031f90  mov     edx, 10Fh; void *
0x180031f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031f9a  nop
0x180031f9b  lea     rcx, [rsp+2B0h+TokenHandle]
0x180031fa0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031fa5  nop
0x180031fa6  jmp     short loc_180031FF7
0x180031fa8  lea     rcx, [rsp+2B0h+TokenHandle]
0x180031fad  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031fb2  nop
0x180031fb3  lea     rcx, [rsp+2B0h+hKey]
0x180031fb8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031fbd  nop
0x180031fbe  mov     rcx, [rsp+2B0h+lpCriticalSection]; lpCriticalSection
0x180031fc3  test    rcx, rcx
0x180031fc6  jz      short loc_180031FD3
0x180031fc8  call    cs:__imp_LeaveCriticalSection
0x180031fce  mov     [rsp+2B0h+lpCriticalSection], rbx
0x180031fd3  xor     eax, eax
0x180031fd5  jmp     short loc_180032019
0x180031fd7  call    cs:__imp_GetLastError
0x180031fdd  mov     edi, eax
0x180031fdf  test    eax, eax
0x180031fe1  jle     short loc_180031FEC
0x180031fe3  movzx   edi, ax
0x180031fe6  or      edi, 80070000h
0x180031fec  lea     rcx, [rsp+2B0h+TokenHandle]
0x180031ff1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031ff6  nop
0x180031ff7  lea     rcx, [rsp+2B0h+hKey]
0x180031ffc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180032001  nop
0x180032002  mov     rcx, [rsp+2B0h+lpCriticalSection]; lpCriticalSection
0x180032007  test    rcx, rcx
0x18003200a  jz      short loc_180032017
0x18003200c  call    cs:__imp_LeaveCriticalSection
0x180032012  mov     [rsp+2B0h+lpCriticalSection], rbx
0x180032017  mov     eax, edi
0x180032019  mov     rcx, [rbp+1B0h+var_40]
0x180032020  xor     rcx, rsp; StackCookie
0x180032023  call    __security_check_cookie
0x180032028  add     rsp, 280h
0x18003202f  pop     r15
0x180032031  pop     r14
0x180032033  pop     r12
0x180032035  pop     rdi
0x180032036  pop     rsi
0x180032037  pop     rbx
0x180032038  pop     rbp
0x180032039  retn
```
