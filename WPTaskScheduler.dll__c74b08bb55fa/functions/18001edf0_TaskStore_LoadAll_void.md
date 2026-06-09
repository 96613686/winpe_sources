# TaskStore::LoadAll(void)

- ea: `0x18001edf0`
- end: `0x18001efc1`
- name: `?LoadAll@TaskStore@@QEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(CScheduleMgr **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180018a04`

## callees

- `0x180010208`
- `0x18001e8b8`
- `0x18001edf0`
- `0x18001efc8`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ef64`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ef81`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ef64`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ef81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ee33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ee33`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001eeac`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001eeac`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001ef31`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001ef31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001efb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001efb4`

## string_xrefs

- `0x18001ee25`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Schedules`

## pseudocode

```c
__int64 __fastcall TaskStore::LoadAll(CScheduleMgr **this)
{
  HKEY *phkResult; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // cc
  int v7; // esi
  unsigned __int64 v8; // rax
  void *v9; // rbx
  DWORD i; // r14d
  LSTATUS v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-18h] BYREF
  void *v16; // [rsp+70h] [rbp-10h]
  DWORD cSubKeys; // [rsp+C8h] [rbp+48h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+50h] BYREF
  DWORD cchName; // [rsp+D8h] [rbp+58h] BYREF

  hKey = 0;
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerSchedulesRegPath, 0, 9u, phkResult);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3
    || (cSubKeys = 0,
        cbMaxSubKeyLen = 0,
        ftLastWriteTime = 0,
        v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, &ftLastWriteTime),
        v4 = v3,
        v5 = v3 <= 0,
        v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  else
  {
    v7 = 0;
    if ( cSubKeys )
    {
      v8 = 2LL * (cbMaxSubKeyLen + 1);
      if ( !is_mul_ok(cbMaxSubKeyLen + 1, 2u) )
        v8 = -1;
      v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v9;
      if ( v9 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= cSubKeys )
          {
            operator delete[](v9);
            goto LABEL_24;
          }
          cchName = cbMaxSubKeyLen + 1;
          v11 = RegEnumKeyExW(hKey, i, (LPWSTR)v9, &cchName, 0, 0, 0, &ftLastWriteTime);
          v12 = v11;
          if ( v11 )
            break;
          v13 = TaskStore::LoadGUID(this, &hKey, (const WCHAR *)v9);
          if ( v7 >= 0 )
            v7 = v13;
        }
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        operator delete[](v9);
        if ( hKey )
          RegCloseKey(hKey);
        return v12;
      }
      else
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 2147942414LL;
      }
    }
    else
    {
LABEL_24:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v7;
    }
  }
}

```

## disassembly

```asm
0x18001edf0  push    rbp
0x18001edf2  push    rbx
0x18001edf3  push    rsi
0x18001edf4  push    rdi
0x18001edf5  push    r12
0x18001edf7  push    r14
0x18001edf9  push    r15
0x18001edfb  mov     rbp, rsp
0x18001edfe  sub     rsp, 80h
0x18001ee05  mov     r15, rcx
0x18001ee08  xor     r12d, r12d
0x18001ee0b  mov     [rbp+hKey], r12
0x18001ee0f  lea     rcx, [rbp+hKey]
0x18001ee13  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001ee18  mov     [rsp+80h+phkResult], rax; phkResult
0x18001ee1d  lea     r9d, [r12+9]; samDesired
0x18001ee22  xor     r8d, r8d; ulOptions
0x18001ee25  lea     rdx, ?g_szTaskSchedulerSchedulesRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001ee2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ee33  call    cs:__imp_RegOpenKeyExW
0x18001ee39  mov     ebx, eax
0x18001ee3b  test    eax, eax
0x18001ee3d  jz      short loc_18001EE60
0x18001ee3f  jle     short loc_18001EE4A
0x18001ee41  movzx   ebx, ax
0x18001ee44  or      ebx, 80070000h
0x18001ee4a  mov     rcx, [rbp+hKey]; hKey
0x18001ee4e  test    rcx, rcx
0x18001ee51  jz      short loc_18001EE59
0x18001ee53  call    cs:__imp_RegCloseKey
0x18001ee59  mov     eax, ebx
0x18001ee5b  jmp     loc_18001EF99
0x18001ee60  mov     [rbp+cSubKeys], r12d
0x18001ee64  mov     [rbp+cbMaxSubKeyLen], r12d
0x18001ee68  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], r12
0x18001ee6c  lea     rax, [rbp+ftLastWriteTime]
0x18001ee70  mov     [rsp+80h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001ee75  mov     [rsp+80h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001ee7a  mov     [rsp+80h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001ee7f  mov     [rsp+80h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18001ee84  mov     [rsp+80h+lpcValues], r12; lpcValues
0x18001ee89  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001ee8e  lea     rax, [rbp+cbMaxSubKeyLen]
0x18001ee92  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001ee97  lea     rax, [rbp+cSubKeys]
0x18001ee9b  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18001eea0  xor     r9d, r9d; lpReserved
0x18001eea3  xor     r8d, r8d; lpcchClass
0x18001eea6  xor     edx, edx; lpClass
0x18001eea8  mov     rcx, [rbp+hKey]; hKey
0x18001eeac  call    cs:__imp_RegQueryInfoKeyW
0x18001eeb2  mov     ebx, eax
0x18001eeb4  test    eax, eax
0x18001eeb6  jnz     short loc_18001EE3F
0x18001eeb8  mov     esi, r12d
0x18001eebb  cmp     [rbp+cSubKeys], r12d
0x18001eebf  jz      loc_18001EF88
0x18001eec5  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18001eec8  inc     ecx
0x18001eeca  lea     eax, [rbx+2]
0x18001eecd  mul     rcx
0x18001eed0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001eed7  cmovb   rax, rcx
0x18001eedb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001eee2  mov     rcx, rax; unsigned __int64
0x18001eee5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001eeea  mov     rbx, rax
0x18001eeed  mov     [rbp+var_10], rax
0x18001eef1  test    rax, rax
0x18001eef4  jz      loc_18001EFAB
0x18001eefa  mov     r14d, r12d
0x18001eefd  cmp     r14d, [rbp+cSubKeys]
0x18001ef01  jnb     short loc_18001EF7E
0x18001ef03  mov     eax, [rbp+cbMaxSubKeyLen]
0x18001ef06  inc     eax
0x18001ef08  mov     [rbp+cchName], eax
0x18001ef0b  lea     rax, [rbp+ftLastWriteTime]
0x18001ef0f  mov     [rsp+80h+lpcValues], rax; lpftLastWriteTime
0x18001ef14  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcchClass
0x18001ef19  mov     [rsp+80h+lpcbMaxSubKeyLen], r12; lpClass
0x18001ef1e  mov     [rsp+80h+phkResult], r12; lpReserved
0x18001ef23  lea     r9, [rbp+cchName]; lpcchName
0x18001ef27  mov     r8, rbx; lpName
0x18001ef2a  mov     edx, r14d; dwIndex
0x18001ef2d  mov     rcx, [rbp+hKey]; hKey
0x18001ef31  call    cs:__imp_RegEnumKeyExW
0x18001ef37  mov     edi, eax
0x18001ef39  test    eax, eax
0x18001ef3b  jnz     short loc_18001EF56
0x18001ef3d  mov     r8, rbx
0x18001ef40  lea     rdx, [rbp+hKey]
0x18001ef44  mov     rcx, r15
0x18001ef47  call    ?LoadGUID@TaskStore@@AEAAJAEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@PEBG@Z; TaskStore::LoadGUID(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &,ushort const *)
0x18001ef4c  test    esi, esi
0x18001ef4e  cmovns  esi, eax
0x18001ef51  inc     r14d
0x18001ef54  jmp     short loc_18001EEFD
0x18001ef56  jle     short loc_18001EF61
0x18001ef58  movzx   edi, ax
0x18001ef5b  or      edi, 80070000h
0x18001ef61  mov     rcx, rbx
0x18001ef64  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ef6a  nop
0x18001ef6b  mov     rcx, [rbp+hKey]; hKey
0x18001ef6f  test    rcx, rcx
0x18001ef72  jz      short loc_18001EF7A
0x18001ef74  call    cs:__imp_RegCloseKey
0x18001ef7a  mov     eax, edi
0x18001ef7c  jmp     short loc_18001EF99
0x18001ef7e  mov     rcx, rbx
0x18001ef81  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ef87  nop
0x18001ef88  mov     rcx, [rbp+hKey]; hKey
0x18001ef8c  test    rcx, rcx
0x18001ef8f  jz      short loc_18001EF97
0x18001ef91  call    cs:__imp_RegCloseKey
0x18001ef97  mov     eax, esi
0x18001ef99  add     rsp, 80h
0x18001efa0  pop     r15
0x18001efa2  pop     r14
0x18001efa4  pop     r12
0x18001efa6  pop     rdi
0x18001efa7  pop     rsi
0x18001efa8  pop     rbx
0x18001efa9  pop     rbp
0x18001efaa  retn
0x18001efab  mov     rcx, [rbp+hKey]; hKey
0x18001efaf  test    rcx, rcx
0x18001efb2  jz      short loc_18001EFBA
0x18001efb4  call    cs:__imp_RegCloseKey
0x18001efba  mov     eax, 8007000Eh
0x18001efbf  jmp     short loc_18001EF99
```
