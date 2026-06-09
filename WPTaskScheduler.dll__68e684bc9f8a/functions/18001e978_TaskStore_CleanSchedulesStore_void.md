# TaskStore::CleanSchedulesStore(void)

- ea: `0x18001e978`
- end: `0x18001ebca`
- name: `?CleanSchedulesStore@TaskStore@@QEAAJXZ`
- size: `594`
- prototype: `__int64 __fastcall(TaskStore *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180018a04`

## callees

- `0x180010208`
- `0x18001e8b8`
- `0x18001e978`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eb4c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eb81`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eb4c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eb81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e9b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eae9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e9b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eb18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eb18`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001ea33`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001ea33`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001eab9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001eab9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e9d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ebb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e9d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ebb5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001eb29`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001eb29`

## string_xrefs

- `0x18001e9a8`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Schedules`

## pseudocode

```c
__int64 __fastcall TaskStore::CleanSchedulesStore(TaskStore *this)
{
  HKEY *phkResult; // rax
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  char v6; // si
  size_t v7; // rax
  void *v8; // rbx
  DWORD i; // r14d
  LSTATUS v10; // eax
  unsigned int v11; // edi
  HKEY *v12; // rax
  LSTATUS v13; // eax
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  HKEY v15; // [rsp+68h] [rbp-10h] BYREF
  TaskStore *cSubKeys; // [rsp+B0h] [rbp+38h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B8h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+C0h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp+50h] BYREF

  cSubKeys = this;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerSchedulesRegPath, 0, 9u, phkResult);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
  {
LABEL_2:
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  else
  {
    v6 = 1;
    do
    {
LABEL_8:
      if ( !v6 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
      LODWORD(cSubKeys) = 0;
      cbMaxSubKeyLen = 0;
      v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v3 = v2;
      v4 = v2 <= 0;
      if ( v2 )
        goto LABEL_2;
      v6 = 0;
    }
    while ( !(_DWORD)cSubKeys );
    v7 = 2LL * (cbMaxSubKeyLen + 1);
    if ( !is_mul_ok(cbMaxSubKeyLen + 1, 2u) )
      v7 = -1;
    v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      for ( i = 0; ; ++i )
      {
        if ( v6 || i >= (unsigned int)cSubKeys )
        {
          operator delete[](v8);
          goto LABEL_8;
        }
        cchName = cbMaxSubKeyLen + 1;
        v10 = RegEnumKeyExW(hKey, i, (LPWSTR)v8, &cchName, 0, 0, 0, 0);
        v11 = v10;
        if ( v10 )
          break;
        v15 = 0;
        v12 = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&v15);
        v13 = RegOpenKeyExW(hKey, (LPCWSTR)v8, 0, 1u, v12);
        v11 = v13;
        if ( v13 )
        {
          if ( v13 > 0 )
            v11 = (unsigned __int16)v13 | 0x80070000;
          if ( v15 )
            RegCloseKey(v15);
          goto LABEL_31;
        }
        cbData = 0;
        if ( RegQueryValueExW(v15, L"Schedule", 0, 0, 0, &cbData) )
        {
          RegDeleteKeyW(hKey, (LPCWSTR)v8);
          v6 = 1;
        }
        if ( v15 )
          RegCloseKey(v15);
      }
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
LABEL_31:
      operator delete[](v8);
      if ( hKey )
        RegCloseKey(hKey);
      return v11;
    }
    else
    {
      if ( hKey )
        RegCloseKey(hKey);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x18001e978  mov     [rsp-30h+cSubKeys], rcx
0x18001e97d  push    rbp
0x18001e97e  push    rbx
0x18001e97f  push    rsi
0x18001e980  push    rdi
0x18001e981  push    r14
0x18001e983  push    r15
0x18001e985  mov     rbp, rsp
0x18001e988  sub     rsp, 78h
0x18001e98c  xor     r15d, r15d
0x18001e98f  lea     rcx, [rbp+hKey]
0x18001e993  mov     [rbp+hKey], r15
0x18001e997  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001e99c  lea     r9d, [r15+9]; samDesired
0x18001e9a0  mov     [rsp+78h+phkResult], rax; phkResult
0x18001e9a5  xor     r8d, r8d; ulOptions
0x18001e9a8  lea     rdx, ?g_szTaskSchedulerSchedulesRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001e9af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e9b6  call    cs:__imp_RegOpenKeyExW
0x18001e9bc  mov     ebx, eax
0x18001e9be  test    eax, eax
0x18001e9c0  jz      short loc_18001E9E3
0x18001e9c2  jle     short loc_18001E9CD
0x18001e9c4  movzx   ebx, ax
0x18001e9c7  or      ebx, 80070000h
0x18001e9cd  mov     rcx, [rbp+hKey]; hKey
0x18001e9d1  test    rcx, rcx
0x18001e9d4  jz      short loc_18001E9DC
0x18001e9d6  call    cs:__imp_RegCloseKey
0x18001e9dc  mov     eax, ebx
0x18001e9de  jmp     loc_18001EBBD
0x18001e9e3  mov     sil, 1
0x18001e9e6  mov     rcx, [rbp+hKey]; hKey
0x18001e9ea  test    sil, sil
0x18001e9ed  jz      loc_18001EBB0
0x18001e9f3  mov     [rsp+78h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001e9f8  lea     rax, [rbp+cbMaxSubKeyLen]
0x18001e9fc  mov     [rsp+78h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001ea01  xor     r9d, r9d; lpReserved
0x18001ea04  mov     [rsp+78h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001ea09  xor     r8d, r8d; lpcchClass
0x18001ea0c  mov     [rsp+78h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001ea11  xor     edx, edx; lpClass
0x18001ea13  mov     [rsp+78h+lpcValues], r15; lpcValues
0x18001ea18  mov     [rsp+78h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001ea1d  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001ea22  lea     rax, [rbp+cSubKeys]
0x18001ea26  mov     [rsp+78h+phkResult], rax; lpcSubKeys
0x18001ea2b  mov     dword ptr [rbp+cSubKeys], r15d
0x18001ea2f  mov     [rbp+cbMaxSubKeyLen], r15d
0x18001ea33  call    cs:__imp_RegQueryInfoKeyW
0x18001ea39  mov     ebx, eax
0x18001ea3b  test    eax, eax
0x18001ea3d  jnz     short loc_18001E9C2
0x18001ea3f  mov     sil, r15b
0x18001ea42  cmp     dword ptr [rbp+cSubKeys], r15d
0x18001ea46  jz      short loc_18001E9E6
0x18001ea48  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18001ea4b  lea     eax, [rbx+2]
0x18001ea4e  inc     ecx
0x18001ea50  mul     rcx
0x18001ea53  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ea5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ea61  cmovb   rax, rcx
0x18001ea65  mov     rcx, rax; unsigned __int64
0x18001ea68  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ea6d  mov     rbx, rax
0x18001ea70  test    rax, rax
0x18001ea73  jz      loc_18001EB9A
0x18001ea79  mov     r14d, r15d
0x18001ea7c  test    sil, sil
0x18001ea7f  jnz     loc_18001EB49
0x18001ea85  cmp     r14d, dword ptr [rbp+cSubKeys]
0x18001ea89  jnb     loc_18001EB49
0x18001ea8f  mov     eax, [rbp+cbMaxSubKeyLen]
0x18001ea92  lea     r9, [rbp+cchName]; lpcchName
0x18001ea96  mov     rcx, [rbp+hKey]; hKey
0x18001ea9a  inc     eax
0x18001ea9c  mov     [rsp+78h+lpcValues], r15; lpftLastWriteTime
0x18001eaa1  mov     r8, rbx; lpName
0x18001eaa4  mov     [rsp+78h+lpcbMaxClassLen], r15; lpcchClass
0x18001eaa9  mov     edx, r14d; dwIndex
0x18001eaac  mov     [rsp+78h+lpcbMaxSubKeyLen], r15; lpClass
0x18001eab1  mov     [rbp+cchName], eax
0x18001eab4  mov     [rsp+78h+phkResult], r15; lpReserved
0x18001eab9  call    cs:__imp_RegEnumKeyExW
0x18001eabf  mov     edi, eax
0x18001eac1  test    eax, eax
0x18001eac3  jnz     loc_18001EB73
0x18001eac9  lea     rcx, [rbp+var_10]
0x18001eacd  mov     [rbp+var_10], r15
0x18001ead1  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001ead6  mov     rcx, [rbp+hKey]; hKey
0x18001eada  lea     r9d, [rdi+1]; samDesired
0x18001eade  xor     r8d, r8d; ulOptions
0x18001eae1  mov     [rsp+78h+phkResult], rax; phkResult
0x18001eae6  mov     rdx, rbx; lpSubKey
0x18001eae9  call    cs:__imp_RegOpenKeyExW
0x18001eaef  mov     edi, eax
0x18001eaf1  test    eax, eax
0x18001eaf3  jnz     short loc_18001EB57
0x18001eaf5  mov     rcx, [rbp+var_10]; hKey
0x18001eaf9  lea     rax, [rbp+cbData]
0x18001eafd  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x18001eb02  lea     rdx, aSchedule; "Schedule"
0x18001eb09  xor     r9d, r9d; lpType
0x18001eb0c  mov     [rsp+78h+phkResult], r15; lpData
0x18001eb11  xor     r8d, r8d; lpReserved
0x18001eb14  mov     [rbp+cbData], r15d
0x18001eb18  call    cs:__imp_RegQueryValueExW
0x18001eb1e  test    eax, eax
0x18001eb20  jz      short loc_18001EB32
0x18001eb22  mov     rcx, [rbp+hKey]; hKey
0x18001eb26  mov     rdx, rbx; lpSubKey
0x18001eb29  call    cs:__imp_RegDeleteKeyW
0x18001eb2f  mov     sil, 1
0x18001eb32  mov     rcx, [rbp+var_10]; hKey
0x18001eb36  test    rcx, rcx
0x18001eb39  jz      short loc_18001EB41
0x18001eb3b  call    cs:__imp_RegCloseKey
0x18001eb41  inc     r14d
0x18001eb44  jmp     loc_18001EA7C
0x18001eb49  mov     rcx, rbx
0x18001eb4c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001eb52  jmp     loc_18001E9E6
0x18001eb57  jle     short loc_18001EB62
0x18001eb59  movzx   edi, ax
0x18001eb5c  or      edi, 80070000h
0x18001eb62  mov     rcx, [rbp+var_10]; hKey
0x18001eb66  test    rcx, rcx
0x18001eb69  jz      short loc_18001EB7E
0x18001eb6b  call    cs:__imp_RegCloseKey
0x18001eb71  jmp     short loc_18001EB7E
0x18001eb73  jle     short loc_18001EB7E
0x18001eb75  movzx   edi, ax
0x18001eb78  or      edi, 80070000h
0x18001eb7e  mov     rcx, rbx
0x18001eb81  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001eb87  mov     rcx, [rbp+hKey]; hKey
0x18001eb8b  test    rcx, rcx
0x18001eb8e  jz      short loc_18001EB96
0x18001eb90  call    cs:__imp_RegCloseKey
0x18001eb96  mov     eax, edi
0x18001eb98  jmp     short loc_18001EBBD
0x18001eb9a  mov     rcx, [rbp+hKey]; hKey
0x18001eb9e  test    rcx, rcx
0x18001eba1  jz      short loc_18001EBA9
0x18001eba3  call    cs:__imp_RegCloseKey
0x18001eba9  mov     eax, 8007000Eh
0x18001ebae  jmp     short loc_18001EBBD
0x18001ebb0  test    rcx, rcx
0x18001ebb3  jz      short loc_18001EBBB
0x18001ebb5  call    cs:__imp_RegCloseKey
0x18001ebbb  xor     eax, eax
0x18001ebbd  add     rsp, 78h
0x18001ebc1  pop     r15
0x18001ebc3  pop     r14
0x18001ebc5  pop     rdi
0x18001ebc6  pop     rsi
0x18001ebc7  pop     rbx
0x18001ebc8  pop     rbp
0x18001ebc9  retn
```
