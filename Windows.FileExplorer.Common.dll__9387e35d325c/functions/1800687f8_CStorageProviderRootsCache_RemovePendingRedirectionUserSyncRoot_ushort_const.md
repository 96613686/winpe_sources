# CStorageProviderRootsCache::RemovePendingRedirectionUserSyncRoot(ushort const *)

- ea: `0x1800687f8`
- end: `0x180068944`
- name: `?RemovePendingRedirectionUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG@Z`
- size: `332`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, LPCWSTR pszValue)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006898c`

## callees

- `0x180003210`
- `0x18000b9b0`
- `0x18000c7b8`
- `0x180019680`
- `0x180035848`
- `0x180037780`
- `0x180043c98`
- `0x1800687f8`

## import_xrefs

- `SHCORE!SHDeleteValueW` at `0x1800688bb`
- `SHCORE!SHDeleteValueW` at `0x1800688bb`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x1800688cc`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x1800688cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068910`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068910`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068893`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068893`

## string_xrefs

- `0x1800688e3`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderRootsCache::RemovePendingRedirectionUserSyncRoot(
        CStorageProviderRootsCache *this,
        LPCWSTR pszValue)
{
  int SyncEngineRegPath; // ebx
  unsigned __int64 i; // rdi
  unsigned __int64 v6; // r8
  LSTATUS v7; // eax
  int v8; // ebx
  int updated; // eax
  int phkResult; // [rsp+20h] [rbp-258h]
  HKEY hkey; // [rsp+30h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  SyncEngineRegPath = -2147023728;
  for ( i = 0; i < *((_QWORD *)this + 71); ++i )
  {
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         *(_QWORD *)(*((_QWORD *)this + 70) + 8 * i),
                         pszValue,
                         -1) == 2 )
    {
      SyncEngineRegPath = CStorageProviderRootsCache::_GetSyncEngineRegPath(this, SubKey, v6);
      if ( SyncEngineRegPath >= 0 )
      {
        hkey = 0;
        v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hkey);
        v8 = v7;
        if ( v7 > 0 )
          v8 = (unsigned __int16)v7 | 0x80070000;
        if ( v8 >= 0 )
        {
          v8 = SHDeleteValueW(hkey, L"PendingRedirectionSyncRoots", pszValue);
          if ( v8 >= 0 )
          {
            SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
            updated = SetSyncRootManagerRegistryUpdateEvent();
            if ( updated < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xE16,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)updated,
                phkResult);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(*(_QWORD *)(*((_QWORD *)this + 70) + 8 * i) + 48LL);
          }
          RegCloseKey(hkey);
        }
        return (unsigned int)HResultIgnoreNotFound(v8);
      }
      return (unsigned int)SyncEngineRegPath;
    }
  }
  return (unsigned int)SyncEngineRegPath;
}

```

## disassembly

```asm
0x1800687f8  mov     [rsp+arg_10], rbx
0x1800687fd  push    rbp
0x1800687fe  push    rsi
0x1800687ff  push    rdi
0x180068800  sub     rsp, 260h
0x180068807  mov     rax, cs:__security_cookie
0x18006880e  xor     rax, rsp
0x180068811  mov     [rsp+278h+var_28], rax
0x180068819  mov     rbp, rdx
0x18006881c  mov     rsi, rcx
0x18006881f  mov     ebx, 80070490h
0x180068824  xor     edi, edi
0x180068826  cmp     rdi, [rsi+238h]
0x18006882d  jnb     loc_18006891F
0x180068833  mov     rcx, [rsi+230h]
0x18006883a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006883e  mov     rdx, rbp
0x180068841  mov     rcx, [rcx+rdi*8]
0x180068845  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x18006884a  cmp     eax, 2
0x18006884d  jz      short loc_180068854
0x18006884f  inc     rdi
0x180068852  jmp     short loc_180068826
0x180068854  lea     rdx, [rsp+278h+SubKey]; unsigned __int16 *
0x180068859  mov     rcx, rsi; this
0x18006885c  call    ?_GetSyncEngineRegPath@CStorageProviderRootsCache@@AEBAJPEAG_K@Z; CStorageProviderRootsCache::_GetSyncEngineRegPath(ushort *,unsigned __int64)
0x180068861  mov     ebx, eax
0x180068863  test    eax, eax
0x180068865  js      loc_18006891F
0x18006886b  lea     rax, [rsp+278h+hkey]
0x180068870  mov     [rsp+278h+hkey], 0
0x180068879  mov     r9d, 2011Fh; samDesired
0x18006887f  mov     qword ptr [rsp+278h+phkResult], rax; int
0x180068884  xor     r8d, r8d; ulOptions
0x180068887  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18006888c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068893  call    cs:__imp_RegOpenKeyExW
0x180068899  mov     ebx, eax
0x18006889b  test    eax, eax
0x18006889d  jle     short loc_1800688A8
0x18006889f  movzx   ebx, ax
0x1800688a2  or      ebx, 80070000h
0x1800688a8  test    ebx, ebx
0x1800688aa  js      short loc_180068916
0x1800688ac  mov     rcx, [rsp+278h+hkey]; hkey
0x1800688b1  lea     rdx, pszSubKey; "PendingRedirectionSyncRoots"
0x1800688b8  mov     r8, rbp; pszValue
0x1800688bb  call    cs:__imp_SHDeleteValueW
0x1800688c1  mov     ebx, eax
0x1800688c3  test    eax, eax
0x1800688c5  js      short loc_18006890B
0x1800688c7  mov     ecx, 39h ; '9'; id
0x1800688cc  call    cs:__imp_SHGlobalCounterIncrement
0x1800688d2  call    ?SetSyncRootManagerRegistryUpdateEvent@@YAJXZ; SetSyncRootManagerRegistryUpdateEvent(void)
0x1800688d7  test    eax, eax
0x1800688d9  jns     short loc_1800688F7
0x1800688db  mov     rcx, [rsp+278h]; this
0x1800688e3  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800688ea  mov     r9d, eax; char *
0x1800688ed  mov     edx, 0E16h; void *
0x1800688f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800688f7  mov     rax, [rsi+230h]
0x1800688fe  mov     rcx, [rax+rdi*8]
0x180068902  add     rcx, 30h ; '0'
0x180068906  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006890b  mov     rcx, [rsp+278h+hkey]; hKey
0x180068910  call    cs:__imp_RegCloseKey
0x180068916  mov     ecx, ebx; int
0x180068918  call    ?HResultIgnoreNotFound@@YAJJ@Z; HResultIgnoreNotFound(long)
0x18006891d  mov     ebx, eax
0x18006891f  mov     eax, ebx
0x180068921  mov     rcx, [rsp+278h+var_28]
0x180068929  xor     rcx, rsp; StackCookie
0x18006892c  call    __security_check_cookie
0x180068931  mov     rbx, [rsp+278h+arg_10]
0x180068939  add     rsp, 260h
0x180068940  pop     rdi
0x180068941  pop     rsi
0x180068942  pop     rbp
0x180068943  retn
```
