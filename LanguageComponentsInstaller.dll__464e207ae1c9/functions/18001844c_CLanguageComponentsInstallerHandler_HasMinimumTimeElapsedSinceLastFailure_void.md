# CLanguageComponentsInstallerHandler::HasMinimumTimeElapsedSinceLastFailure(void)

- ea: `0x18001844c`
- end: `0x180018554`
- name: `?HasMinimumTimeElapsedSinceLastFailure@CLanguageComponentsInstallerHandler@@AEBA_NXZ`
- size: `264`
- prototype: `bool __fastcall(CLanguageComponentsInstallerHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d0f0`

## callees

- `0x180003520`
- `0x180006380`
- `0x180018234`
- `0x18001844c`
- `0x180018ac4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018512`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018512`

## string_xrefs

- `0x1800184ca`: `LastFailedAttemptTime`

## pseudocode

```c
bool __fastcall CLanguageComponentsInstallerHandler::HasMinimumTimeElapsedSinceLastFailure(
        CLanguageComponentsInstallerHandler *this)
{
  __int64 v2; // rbx
  __int64 RegistryKeyPath; // rax
  LSTATUS ValueW; // ebx
  _BYTE v6[32]; // [rsp+40h] [rbp-48h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-20h] BYREF
  __int64 pvData; // [rsp+70h] [rbp-18h] BYREF

  if ( IsRunningAsLocalSystem() )
  {
    v2 = -2147483646;
    if ( *((_QWORD *)this + 35) )
      v2 = *((_QWORD *)this + 35);
  }
  else
  {
    v2 = -2147483647;
  }
  pvData = 0;
  pcbData = 8;
  RegistryKeyPath = CLanguageComponentsInstallerHandler::GetRegistryKeyPath((__int64)this, (__int64)v6);
  if ( *(_QWORD *)(RegistryKeyPath + 24) > 7u )
    RegistryKeyPath = *(_QWORD *)RegistryKeyPath;
  ValueW = RegGetValueW((HKEY)v2, (LPCWSTR)RegistryKeyPath, L"LastFailedAttemptTime", 0x48u, 0, &pvData, &pcbData);
  std::wstring::~wstring(v6);
  if ( (unsigned int)(ValueW - 2) <= 1 )
    return 1;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  return (unsigned __int64)(*(_QWORD *)&SystemTimeAsFileTime - pvData) >= 0x649534E000LL;
}

```

## disassembly

```asm
0x18001844c  mov     [rsp+arg_8], rbx
0x180018451  push    rdi
0x180018452  sub     rsp, 80h
0x180018459  mov     rax, cs:__security_cookie
0x180018460  xor     rax, rsp
0x180018463  mov     [rsp+88h+var_10], rax
0x180018468  mov     rdi, rcx
0x18001846b  call    ?IsRunningAsLocalSystem@@YA_NXZ; IsRunningAsLocalSystem(void)
0x180018470  test    al, al
0x180018472  jz      short loc_18001848B
0x180018474  mov     rax, [rdi+118h]
0x18001847b  mov     rbx, 0FFFFFFFF80000002h
0x180018482  test    rax, rax
0x180018485  cmovnz  rbx, rax
0x180018489  jmp     short loc_180018492
0x18001848b  mov     rbx, 0FFFFFFFF80000001h
0x180018492  lea     rdx, [rsp+88h+var_48]
0x180018497  mov     [rsp+88h+var_18], 0
0x1800184a0  mov     rcx, rdi
0x1800184a3  mov     [rsp+88h+var_28], 8
0x1800184ab  call    ?GetRegistryKeyPath@CLanguageComponentsInstallerHandler@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CLanguageComponentsInstallerHandler::GetRegistryKeyPath(void)
0x1800184b0  cmp     qword ptr [rax+18h], 7
0x1800184b5  jbe     short loc_1800184BA
0x1800184b7  mov     rax, [rax]
0x1800184ba  lea     rcx, [rsp+88h+var_28]
0x1800184bf  mov     r9d, 48h ; 'H'; dwFlags
0x1800184c5  mov     [rsp+88h+pcbData], rcx; pcbData
0x1800184ca  lea     r8, aLastfailedatte; "LastFailedAttemptTime"
0x1800184d1  lea     rcx, [rsp+88h+var_18]
0x1800184d6  mov     rdx, rax; lpSubKey
0x1800184d9  mov     [rsp+88h+pvData], rcx; pvData
0x1800184de  mov     rcx, rbx; hkey
0x1800184e1  mov     [rsp+88h+pdwType], 0; pdwType
0x1800184ea  call    cs:__imp_RegGetValueW
0x1800184f0  lea     rcx, [rsp+88h+var_48]; void *
0x1800184f5  mov     ebx, eax
0x1800184f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800184fc  lea     eax, [rbx-2]
0x1800184ff  cmp     eax, 1
0x180018502  jbe     short loc_180018534
0x180018504  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018509  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180018512  call    cs:__imp_GetSystemTimeAsFileTime
0x180018518  mov     rax, qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x18001851d  mov     rcx, 649534E000h
0x180018527  sub     rax, [rsp+88h+var_18]
0x18001852c  cmp     rax, rcx
0x18001852f  setnb   al
0x180018532  jmp     short loc_180018536
0x180018534  mov     al, 1
0x180018536  mov     rcx, [rsp+88h+var_10]
0x18001853b  xor     rcx, rsp; StackCookie
0x18001853e  call    __security_check_cookie
0x180018543  mov     rbx, [rsp+88h+arg_8]
0x18001854b  add     rsp, 80h
0x180018552  pop     rdi
0x180018553  retn
```
