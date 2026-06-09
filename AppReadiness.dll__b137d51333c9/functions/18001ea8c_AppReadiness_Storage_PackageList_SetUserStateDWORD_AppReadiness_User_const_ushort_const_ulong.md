# AppReadiness::Storage::PackageList::SetUserStateDWORD(AppReadiness::User const *,ushort const *,ulong)

- ea: `0x18001ea8c`
- end: `0x18001ebe7`
- name: `?SetUserStateDWORD@PackageList@Storage@AppReadiness@@CAXPEBVUser@3@PEBGK@Z`
- size: `347`
- prototype: `static void(const struct AppReadiness::User *, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010afc`
- `0x180026ab0`
- `0x180064f80`
- `0x180066630`

## callees

- `0x180009d60`
- `0x180009f50`
- `0x18001ea8c`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001eac2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001eac2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001eb6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001eb6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001eb92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ebd4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001eb92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ebd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001eafd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001eafd`

## string_xrefs

- `0x18001eb1d`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18001eb29`: `AppReadiness::Storage::PackageList::SetUserStateDWORD`
- `0x18001eb30`: `SHRegSetDWORD(userKey.Get(), nullptr, valueName, value)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Storage::PackageList::SetUserStateDWORD(
        const struct AppReadiness::User *a1,
        const unsigned __int16 *a2,
        int a3)
{
  HANDLE v5; // rsi
  DWORD v6; // ebp
  int v7; // eax
  bool v8; // sf
  int LastError; // eax
  int v10; // eax
  void **v11; // [rsp+30h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-70h]
  DWORD v13; // [rsp+40h] [rbp-68h]
  HANDLE v14; // [rsp+48h] [rbp-60h]
  _BYTE pExceptionObject[88]; // [rsp+50h] [rbp-58h] BYREF
  int Data; // [rsp+C0h] [rbp+18h] BYREF

  AppReadiness::Storage::PackageList::OpenUserMachineRoot(&v11, (__int64)a1, 2u);
  v5 = hSemaphore;
  v6 = WaitForSingleObjectEx(hSemaphore, 0xFFFFFFFF, 0);
  v13 = v6;
  v14 = v5;
  Data = a3;
  v7 = RegSetValueExW(hKey, a2, 0, 4u, (const BYTE *)&Data, 4u);
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = v7 < 0;
  }
  if ( v8 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v7,
      "SHRegSetDWORD(userKey.Get(), nullptr, valueName, value)",
      "AppReadiness::Storage::PackageList::SetUserStateDWORD",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
      417);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( v5 && (v6 & 0xFFFFFF7F) == 0 && !ReleaseSemaphore(v5, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
  }
  v11 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  if ( hKey
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v11) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    RaiseException(v10, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18001ea8c  push    rbx
0x18001ea8e  push    rbp
0x18001ea8f  push    rsi
0x18001ea90  push    rdi
0x18001ea91  sub     rsp, 88h
0x18001ea98  mov     ebx, r8d
0x18001ea9b  mov     rdi, rdx
0x18001ea9e  mov     r8d, 2
0x18001eaa4  mov     rdx, rcx
0x18001eaa7  lea     rcx, [rsp+0A8h+var_78]
0x18001eaac  call    ?OpenUserMachineRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserMachineRoot(AppReadiness::User const *,ulong)
0x18001eab1  nop
0x18001eab2  mov     rsi, cs:hSemaphore
0x18001eab9  xor     r8d, r8d; bAlertable
0x18001eabc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001eabf  mov     rcx, rsi; hHandle
0x18001eac2  call    cs:__imp_WaitForSingleObjectEx
0x18001eac8  mov     ebp, eax
0x18001eaca  mov     [rsp+0A8h+var_68], eax
0x18001eace  mov     [rsp+0A8h+var_60], rsi
0x18001ead3  mov     [rsp+0A8h+Data], ebx
0x18001eada  mov     r9d, 4; dwType
0x18001eae0  mov     [rsp+0A8h+cbData], r9d; cbData
0x18001eae5  lea     rax, [rsp+0A8h+Data]
0x18001eaed  mov     [rsp+0A8h+lpData], rax; lpData
0x18001eaf2  xor     r8d, r8d; Reserved
0x18001eaf5  mov     rdx, rdi; lpValueName
0x18001eaf8  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001eafd  call    cs:__imp_RegSetValueExW
0x18001eb03  mov     edi, 80070000h
0x18001eb08  test    eax, eax
0x18001eb0a  jle     short loc_18001EB13
0x18001eb0c  movzx   eax, ax
0x18001eb0f  or      eax, edi
0x18001eb11  test    eax, eax
0x18001eb13  jns     short loc_18001EB55
0x18001eb15  mov     [rsp+0A8h+cbData], 1A1h; int
0x18001eb1d  lea     rcx, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001eb24  mov     [rsp+0A8h+lpData], rcx; char *
0x18001eb29  lea     r9, aAppreadinessSt_9; "AppReadiness::Storage::PackageList::Set"...
0x18001eb30  lea     r8, aShregsetdwordU; "SHRegSetDWORD(userKey.Get(), nullptr, v"...
0x18001eb37  mov     edx, eax; int
0x18001eb39  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18001eb3e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18001eb43  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001eb4a  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18001eb4f  call    _CxxThrowException_0
0x18001eb55  mov     ebx, 1
0x18001eb5a  test    rsi, rsi
0x18001eb5d  jz      short loc_18001EB99
0x18001eb5f  test    ebp, 0FFFFFF7Fh
0x18001eb65  jnz     short loc_18001EB99
0x18001eb67  xor     r8d, r8d; lpPreviousCount
0x18001eb6a  mov     edx, ebx; lReleaseCount
0x18001eb6c  mov     rcx, rsi; hSemaphore
0x18001eb6f  call    cs:__imp_ReleaseSemaphore
0x18001eb75  test    eax, eax
0x18001eb77  jnz     short loc_18001EB99
0x18001eb79  call    cs:__imp_GetLastError
0x18001eb7f  test    eax, eax
0x18001eb81  jle     short loc_18001EB88
0x18001eb83  movzx   eax, ax
0x18001eb86  or      eax, edi
0x18001eb88  xor     r9d, r9d; lpArguments
0x18001eb8b  xor     r8d, r8d; nNumberOfArguments
0x18001eb8e  mov     edx, ebx; dwExceptionFlags
0x18001eb90  mov     ecx, eax; dwExceptionCode
0x18001eb92  call    cs:__imp_RaiseException
0x18001eb98  nop
0x18001eb99  lea     rax, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18001eba0  mov     [rsp+0A8h+var_78], rax
0x18001eba5  cmp     [rsp+0A8h+hKey], 0
0x18001ebab  jz      short loc_18001EBDB
0x18001ebad  lea     rcx, [rsp+0A8h+var_78]
0x18001ebb2  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x18001ebb7  test    al, al
0x18001ebb9  jnz     short loc_18001EBDB
0x18001ebbb  call    cs:__imp_GetLastError
0x18001ebc1  test    eax, eax
0x18001ebc3  jle     short loc_18001EBCA
0x18001ebc5  movzx   eax, ax
0x18001ebc8  or      eax, edi
0x18001ebca  xor     r9d, r9d; lpArguments
0x18001ebcd  xor     r8d, r8d; nNumberOfArguments
0x18001ebd0  mov     edx, ebx; dwExceptionFlags
0x18001ebd2  mov     ecx, eax; dwExceptionCode
0x18001ebd4  call    cs:__imp_RaiseException
0x18001ebda  int     3; Trap to Debugger
0x18001ebdb  add     rsp, 88h
0x18001ebe2  pop     rdi
0x18001ebe3  pop     rsi
0x18001ebe4  pop     rbp
0x18001ebe5  pop     rbx
0x18001ebe6  retn
```
