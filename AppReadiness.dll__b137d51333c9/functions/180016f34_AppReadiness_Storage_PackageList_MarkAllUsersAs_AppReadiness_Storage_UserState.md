# AppReadiness::Storage::PackageList::MarkAllUsersAs(AppReadiness::Storage::UserState)

- ea: `0x180016f34`
- end: `0x1800170c0`
- name: `?MarkAllUsersAs@PackageList@Storage@AppReadiness@@SAXW4UserState@23@@Z`
- size: `396`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026c10`

## callees

- `0x18000aac0`
- `0x180016f34`
- `0x1800170d0`
- `0x1800178d0`
- `0x180018b20`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016f5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016f5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001707e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001707e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800170a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800170a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017088`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001704b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001704b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016fc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016fc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016fb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016fb1`

## string_xrefs

- `0x180016ffd`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x180017009`: `AppReadiness::Storage::PackageList::MarkAllUsersAs`
- `0x180017010`: `SHRegSetDWORD(s_machineRootKey.Get(), key.c_str(), c_UserStateValueName, static_cast<DWORD>(state))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int AppReadiness::Storage::PackageList::MarkAllUsersAs()
{
  HANDLE v0; // rdi
  DWORD v1; // esi
  LPCWSTR i; // rbx
  const WCHAR *v3; // rcx
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  const WCHAR *v6; // rdx
  int result; // eax
  int LastError; // eax
  LPCWSTR StringSid[3]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-30h] BYREF
  PSID Sid; // [rsp+98h] [rbp+10h] BYREF

  AppReadiness::Storage::PackageList::InitRegistry();
  v0 = hSemaphore;
  v1 = WaitForSingleObjectEx(hSemaphore, 0xFFFFFFFF, 0);
  AppReadiness::Storage::PackageList::GetSubkeys(StringSid, hKey);
  for ( i = StringSid[0]; i != StringSid[1]; i += 16 )
  {
    Sid = 0;
    if ( *((_QWORD *)i + 3) <= 7u )
      v3 = i;
    else
      v3 = *(const WCHAR **)i;
    if ( ConvertStringSidToSidW(v3, &Sid) )
    {
      LocalFree(Sid);
      if ( *((_QWORD *)i + 3) <= 7u )
        v4 = i;
      else
        v4 = *(const unsigned __int16 **)i;
      v5 = SHRegSetDWORD(hKey, v4, L"UserState", 2u);
      if ( v5 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v5,
          "SHRegSetDWORD(s_machineRootKey.Get(), key.c_str(), c_UserStateValueName, static_cast<DWORD>(state))",
          "AppReadiness::Storage::PackageList::MarkAllUsersAs",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
          394);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    else
    {
      if ( *((_QWORD *)i + 3) <= 7u )
        v6 = i;
      else
        v6 = *(const WCHAR **)i;
      RegDeleteTreeW(hKey, v6);
    }
  }
  result = std::vector<std::wstring>::_Tidy(StringSid);
  if ( v0 )
  {
    if ( (v1 & 0xFFFFFF7F) == 0 )
    {
      result = ReleaseSemaphore(v0, 1, 0);
      if ( !result )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RaiseException(LastError, 1u, 0, 0);
        __debugbreak();
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016f34  mov     [rsp+arg_0], rbx
0x180016f39  mov     [rsp+arg_10], rsi
0x180016f3e  push    rdi
0x180016f3f  sub     rsp, 80h
0x180016f46  call    ?InitRegistry@PackageList@Storage@AppReadiness@@CAXXZ; AppReadiness::Storage::PackageList::InitRegistry(void)
0x180016f4b  mov     rdi, cs:hSemaphore
0x180016f52  xor     r8d, r8d; bAlertable
0x180016f55  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016f58  mov     rcx, rdi; hHandle
0x180016f5b  call    cs:__imp_WaitForSingleObjectEx
0x180016f61  mov     esi, eax
0x180016f63  mov     [rsp+88h+var_58], eax
0x180016f67  mov     [rsp+88h+var_50], rdi
0x180016f6c  mov     rdx, cs:hKey
0x180016f73  lea     rcx, [rsp+88h+StringSid]
0x180016f78  call    ?GetSubkeys@PackageList@Storage@AppReadiness@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; AppReadiness::Storage::PackageList::GetSubkeys(HKEY__ *,ushort const *)
0x180016f7d  nop
0x180016f7e  mov     rbx, [rsp+88h+StringSid]
0x180016f83  cmp     rbx, [rsp+88h+var_40]
0x180016f88  jz      loc_18001705A
0x180016f8e  mov     [rsp+88h+Sid], 0
0x180016f9a  cmp     qword ptr [rbx+18h], 7
0x180016f9f  jbe     short loc_180016FA6
0x180016fa1  mov     rcx, [rbx]
0x180016fa4  jmp     short loc_180016FA9
0x180016fa6  mov     rcx, rbx; StringSid
0x180016fa9  lea     rdx, [rsp+88h+Sid]; Sid
0x180016fb1  call    cs:__imp_ConvertStringSidToSidW
0x180016fb7  test    eax, eax
0x180016fb9  jz      short loc_180017035
0x180016fbb  mov     rcx, [rsp+88h+Sid]; hMem
0x180016fc3  call    cs:__imp_LocalFree
0x180016fc9  cmp     qword ptr [rbx+18h], 7
0x180016fce  jbe     short loc_180016FD5
0x180016fd0  mov     rdx, [rbx]
0x180016fd3  jmp     short loc_180016FD8
0x180016fd5  mov     rdx, rbx; unsigned __int16 *
0x180016fd8  mov     r9d, 2; unsigned int
0x180016fde  lea     r8, aUserstate; "UserState"
0x180016fe5  mov     rcx, cs:hKey; hKey
0x180016fec  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180016ff1  test    eax, eax
0x180016ff3  jns     short loc_180017051
0x180016ff5  mov     [rsp+88h+var_60], 18Ah; int
0x180016ffd  lea     rcx, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017004  mov     [rsp+88h+var_68], rcx; char *
0x180017009  lea     r9, aAppreadinessSt_1; "AppReadiness::Storage::PackageList::Mar"...
0x180017010  lea     r8, aShregsetdwordS; "SHRegSetDWORD(s_machineRootKey.Get(), k"...
0x180017017  mov     edx, eax; int
0x180017019  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001701e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017023  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001702a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001702f  call    _CxxThrowException_0
0x180017035  cmp     qword ptr [rbx+18h], 7
0x18001703a  jbe     short loc_180017041
0x18001703c  mov     rdx, [rbx]
0x18001703f  jmp     short loc_180017044
0x180017041  mov     rdx, rbx; lpSubKey
0x180017044  mov     rcx, cs:hKey; hKey
0x18001704b  call    cs:__imp_RegDeleteTreeW
0x180017051  add     rbx, 20h ; ' '
0x180017055  jmp     loc_180016F83
0x18001705a  lea     rcx, [rsp+88h+StringSid]
0x18001705f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180017064  nop
0x180017065  test    rdi, rdi
0x180017068  jz      short loc_1800170AB
0x18001706a  test    esi, 0FFFFFF7Fh
0x180017070  jnz     short loc_1800170AB
0x180017072  xor     r8d, r8d; lpPreviousCount
0x180017075  lea     ebx, [r8+1]
0x180017079  mov     edx, ebx; lReleaseCount
0x18001707b  mov     rcx, rdi; hSemaphore
0x18001707e  call    cs:__imp_ReleaseSemaphore
0x180017084  test    eax, eax
0x180017086  jnz     short loc_1800170AB
0x180017088  call    cs:__imp_GetLastError
0x18001708e  test    eax, eax
0x180017090  jle     short loc_18001709A
0x180017092  movzx   eax, ax
0x180017095  or      eax, 80070000h
0x18001709a  xor     r9d, r9d; lpArguments
0x18001709d  xor     r8d, r8d; nNumberOfArguments
0x1800170a0  mov     edx, ebx; dwExceptionFlags
0x1800170a2  mov     ecx, eax; dwExceptionCode
0x1800170a4  call    cs:__imp_RaiseException
0x1800170aa  int     3; Trap to Debugger
0x1800170ab  lea     r11, [rsp+88h+var_8]
0x1800170b3  mov     rbx, [r11+10h]
0x1800170b7  mov     rsi, [r11+20h]
0x1800170bb  mov     rsp, r11
0x1800170be  pop     rdi
0x1800170bf  retn
```
