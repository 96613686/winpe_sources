# AppReadiness::Storage::PackageList::WritePackageTaskResult(AppReadiness::User *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,long)

- ea: `0x18000a2c8`
- end: `0x18000a454`
- name: `?WritePackageTaskResult@PackageList@Storage@AppReadiness@@SAXPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1J@Z`
- size: `396`
- prototype: `void **__fastcall(__int64, const WCHAR *, const WCHAR *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003ad0`
- `0x180027e50`
- `0x1800294d0`
- `0x180063170`
- `0x18006c900`

## callees

- `0x180009d60`
- `0x180009e10`
- `0x18000a2c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a30d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a30d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a3ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000a3ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a412`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a435`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a412`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a3ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a3ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a39e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a39e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a376`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a376`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall AppReadiness::Storage::PackageList::WritePackageTaskResult(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        int a4)
{
  HANDLE v7; // r14
  DWORD v8; // r12d
  HKEY v9; // rdi
  HKEY v10; // rcx
  void **result; // rax
  int v12; // eax
  int LastError; // eax
  void **v14; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h]
  HKEY phkResult; // [rsp+A8h] [rbp+48h] BYREF
  int Data; // [rsp+B8h] [rbp+58h] BYREF

  AppReadiness::Storage::PackageList::OpenUserQueueRoot(&v14, a1, 0x20006u);
  v7 = hSemaphore;
  v8 = WaitForSingleObjectEx(hSemaphore, 0xFFFFFFFF, 0);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v9 = hKey;
  Data = a4;
  phkResult = 0;
  if ( a2 && *a2 )
  {
    if ( RegCreateKeyExW(hKey, a2, 0, 0, 0, 2u, 0, &phkResult, 0) )
      goto LABEL_12;
    v10 = phkResult;
  }
  else
  {
    v10 = hKey;
    phkResult = hKey;
  }
  RegSetValueExW(v10, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( phkResult != v9 )
    RegCloseKey(phkResult);
LABEL_12:
  if ( v7 && (v8 & 0xFFFFFF7F) == 0 && !ReleaseSemaphore(v7, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  result = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  v14 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  if ( hKey )
  {
    result = (void **)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v14);
    if ( !(_BYTE)result )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      RaiseException(v12, 1u, 0, 0);
      __debugbreak();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a2c8  mov     [rsp-38h+arg_0], rbx
0x18000a2cd  push    rbp
0x18000a2ce  push    rsi
0x18000a2cf  push    rdi
0x18000a2d0  push    r12
0x18000a2d2  push    r13
0x18000a2d4  push    r14
0x18000a2d6  push    r15
0x18000a2d8  mov     rbp, rsp
0x18000a2db  sub     rsp, 60h
0x18000a2df  mov     rbx, rdx
0x18000a2e2  mov     rsi, r8
0x18000a2e5  mov     rdx, rcx
0x18000a2e8  mov     r8d, 20006h
0x18000a2ee  lea     rcx, [rbp+var_10]
0x18000a2f2  mov     r15d, r9d
0x18000a2f5  xor     r13d, r13d
0x18000a2f8  call    ?OpenUserQueueRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserQueueRoot(AppReadiness::User const *,ulong)
0x18000a2fd  mov     r14, cs:hSemaphore
0x18000a304  xor     r8d, r8d; bAlertable
0x18000a307  mov     rcx, r14; hHandle
0x18000a30a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a30d  call    cs:__imp_WaitForSingleObjectEx
0x18000a313  cmp     qword ptr [rsi+18h], 7
0x18000a318  mov     r12d, eax
0x18000a31b  jbe     short loc_18000A320
0x18000a31d  mov     rsi, [rsi]
0x18000a320  cmp     qword ptr [rbx+18h], 7
0x18000a325  jbe     short loc_18000A32A
0x18000a327  mov     rbx, [rbx]
0x18000a32a  mov     rdi, [rbp+hKey]
0x18000a32e  mov     [rbp+Data], r15d
0x18000a332  mov     [rbp+arg_8], r13
0x18000a336  test    rbx, rbx
0x18000a339  jnz     short loc_18000A344
0x18000a33b  mov     rcx, rdi
0x18000a33e  mov     [rbp+arg_8], rcx
0x18000a342  jmp     short loc_18000A384
0x18000a344  cmp     [rbx], r13w
0x18000a348  jz      short loc_18000A33B
0x18000a34a  mov     [rsp+60h+lpdwDisposition], r13; lpdwDisposition
0x18000a34f  lea     rax, [rbp+arg_8]
0x18000a353  mov     [rsp+60h+phkResult], rax; phkResult
0x18000a358  xor     r9d, r9d; lpClass
0x18000a35b  mov     [rsp+60h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18000a360  xor     r8d, r8d; Reserved
0x18000a363  mov     [rsp+60h+samDesired], 2; samDesired
0x18000a36b  mov     rdx, rbx; lpSubKey
0x18000a36e  mov     rcx, rdi; hKey
0x18000a371  mov     [rsp+60h+dwOptions], r13d; dwOptions
0x18000a376  call    cs:__imp_RegCreateKeyExW
0x18000a37c  test    eax, eax
0x18000a37e  jnz     short loc_18000A3B3
0x18000a380  mov     rcx, [rbp+arg_8]; hKey
0x18000a384  mov     r9d, 4; dwType
0x18000a38a  lea     rax, [rbp+Data]
0x18000a38e  mov     [rsp+60h+samDesired], r9d; cbData
0x18000a393  xor     r8d, r8d; Reserved
0x18000a396  mov     rdx, rsi; lpValueName
0x18000a399  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18000a39e  call    cs:__imp_RegSetValueExW
0x18000a3a4  mov     rcx, [rbp+arg_8]; hKey
0x18000a3a8  cmp     rcx, rdi
0x18000a3ab  jz      short loc_18000A3B3
0x18000a3ad  call    cs:__imp_RegCloseKey
0x18000a3b3  mov     ebx, 1
0x18000a3b8  test    r14, r14
0x18000a3bb  jz      short loc_18000A3D8
0x18000a3bd  test    r12d, 0FFFFFF7Fh
0x18000a3c4  jnz     short loc_18000A3D8
0x18000a3c6  xor     r8d, r8d; lpPreviousCount
0x18000a3c9  mov     edx, ebx; lReleaseCount
0x18000a3cb  mov     rcx, r14; hSemaphore
0x18000a3ce  call    cs:__imp_ReleaseSemaphore
0x18000a3d4  test    eax, eax
0x18000a3d6  jz      short loc_18000A419
0x18000a3d8  lea     rax, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18000a3df  mov     [rbp+var_10], rax
0x18000a3e3  cmp     [rbp+hKey], r13
0x18000a3e7  jz      short loc_18000A43C
0x18000a3e9  lea     rcx, [rbp+var_10]
0x18000a3ed  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x18000a3f2  test    al, al
0x18000a3f4  jnz     short loc_18000A43C
0x18000a3f6  call    cs:__imp_GetLastError
0x18000a3fc  test    eax, eax
0x18000a3fe  jle     short loc_18000A408
0x18000a400  movzx   eax, ax
0x18000a403  or      eax, 80070000h
0x18000a408  xor     r9d, r9d; lpArguments
0x18000a40b  xor     r8d, r8d; nNumberOfArguments
0x18000a40e  mov     edx, ebx; dwExceptionFlags
0x18000a410  mov     ecx, eax; dwExceptionCode
0x18000a412  call    cs:__imp_RaiseException
0x18000a418  int     3; Trap to Debugger
0x18000a419  call    cs:__imp_GetLastError
0x18000a41f  test    eax, eax
0x18000a421  jle     short loc_18000A42B
0x18000a423  movzx   eax, ax
0x18000a426  or      eax, 80070000h
0x18000a42b  xor     r9d, r9d; lpArguments
0x18000a42e  xor     r8d, r8d; nNumberOfArguments
0x18000a431  mov     edx, ebx; dwExceptionFlags
0x18000a433  mov     ecx, eax; dwExceptionCode
0x18000a435  call    cs:__imp_RaiseException
0x18000a43b  int     3; Trap to Debugger
0x18000a43c  mov     rbx, [rsp+60h+arg_0]
0x18000a444  add     rsp, 60h
0x18000a448  pop     r15
0x18000a44a  pop     r14
0x18000a44c  pop     r13
0x18000a44e  pop     r12
0x18000a450  pop     rdi
0x18000a451  pop     rsi
0x18000a452  pop     rbp
0x18000a453  retn
```
