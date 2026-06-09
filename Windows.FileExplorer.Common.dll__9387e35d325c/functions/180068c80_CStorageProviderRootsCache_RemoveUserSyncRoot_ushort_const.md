# CStorageProviderRootsCache::RemoveUserSyncRoot(ushort const *)

- ea: `0x180068c80`
- end: `0x180068e33`
- name: `?RemoveUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG@Z`
- size: `435`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, LPCWSTR pszValue)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800686ec`
- `0x180068e7c`

## callees

- `0x180003210`
- `0x18000c7b8`
- `0x180019680`
- `0x1800353dc`
- `0x180035848`
- `0x180037780`
- `0x1800386fc`
- `0x180043c98`
- `0x180068c80`

## import_xrefs

- `SHCORE!SHDeleteValueW` at `0x180068d47`
- `SHCORE!SHDeleteValueW` at `0x180068d5c`
- `SHCORE!SHDeleteValueW` at `0x180068d47`
- `SHCORE!SHDeleteValueW` at `0x180068d5c`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180068d74`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180068d74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068dff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068dff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068d1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068d1b`

## string_xrefs

- `0x180068d8b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderRootsCache::RemoveUserSyncRoot(CStorageProviderRootsCache *this, LPCWSTR pszValue)
{
  int SyncEngineRegPath; // ebx
  unsigned __int64 i; // rdi
  unsigned __int64 v6; // r8
  LSTATUS v7; // eax
  int v8; // ebx
  int updated; // eax
  CStorageProviderRootsCache *v10; // rcx
  unsigned __int64 v11; // r8
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
          SHDeleteValueW(hkey, L"PendingRedirectionSyncRoots", pszValue);
          v8 = SHDeleteValueW(hkey, L"UserSyncRoots", pszValue);
          if ( v8 >= 0 )
          {
            _mm_lfence();
            SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
            updated = SetSyncRootManagerRegistryUpdateEvent();
            if ( updated < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xDC3,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)updated,
                phkResult);
            CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(
              v10,
              *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 70) + 8 * i) + 24LL),
              0);
            v11 = *((_QWORD *)this + 71);
            if ( i < v11 )
            {
              if ( i != v11 - 1 )
                memmove_0(
                  (void *)(*((_QWORD *)this + 70) + 8 * i),
                  (const void *)(*((_QWORD *)this + 70) + 8 * i + 8),
                  8 * (v11 - i) - 8);
              --*((_QWORD *)this + 71);
              v8 = 0;
            }
            else
            {
              v8 = -2147316575;
            }
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
0x180068c80  mov     [rsp+arg_10], rbx
0x180068c85  push    rbp
0x180068c86  push    rsi
0x180068c87  push    rdi
0x180068c88  sub     rsp, 260h
0x180068c8f  mov     rax, cs:__security_cookie
0x180068c96  xor     rax, rsp
0x180068c99  mov     [rsp+278h+var_28], rax
0x180068ca1  mov     rbp, rdx
0x180068ca4  mov     rsi, rcx
0x180068ca7  mov     ebx, 80070490h
0x180068cac  xor     edi, edi
0x180068cae  cmp     rdi, [rsi+238h]
0x180068cb5  jnb     loc_180068E0E
0x180068cbb  mov     rcx, [rsi+230h]
0x180068cc2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068cc6  mov     rdx, rbp
0x180068cc9  mov     rcx, [rcx+rdi*8]
0x180068ccd  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180068cd2  cmp     eax, 2
0x180068cd5  jz      short loc_180068CDC
0x180068cd7  inc     rdi
0x180068cda  jmp     short loc_180068CAE
0x180068cdc  lea     rdx, [rsp+278h+SubKey]; unsigned __int16 *
0x180068ce1  mov     rcx, rsi; this
0x180068ce4  call    ?_GetSyncEngineRegPath@CStorageProviderRootsCache@@AEBAJPEAG_K@Z; CStorageProviderRootsCache::_GetSyncEngineRegPath(ushort *,unsigned __int64)
0x180068ce9  mov     ebx, eax
0x180068ceb  test    eax, eax
0x180068ced  js      loc_180068E0E
0x180068cf3  lea     rax, [rsp+278h+hkey]
0x180068cf8  mov     [rsp+278h+hkey], 0
0x180068d01  mov     r9d, 2011Fh; samDesired
0x180068d07  mov     qword ptr [rsp+278h+phkResult], rax; int
0x180068d0c  xor     r8d, r8d; ulOptions
0x180068d0f  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x180068d14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068d1b  call    cs:__imp_RegOpenKeyExW
0x180068d21  mov     ebx, eax
0x180068d23  test    eax, eax
0x180068d25  jle     short loc_180068D30
0x180068d27  movzx   ebx, ax
0x180068d2a  or      ebx, 80070000h
0x180068d30  test    ebx, ebx
0x180068d32  js      loc_180068E05
0x180068d38  mov     rcx, [rsp+278h+hkey]; hkey
0x180068d3d  lea     rdx, pszSubKey; "PendingRedirectionSyncRoots"
0x180068d44  mov     r8, rbp; pszValue
0x180068d47  call    cs:__imp_SHDeleteValueW
0x180068d4d  mov     rcx, [rsp+278h+hkey]; hkey
0x180068d52  lea     rdx, aUsersyncroots_0; "UserSyncRoots"
0x180068d59  mov     r8, rbp; pszValue
0x180068d5c  call    cs:__imp_SHDeleteValueW
0x180068d62  mov     ebx, eax
0x180068d64  test    eax, eax
0x180068d66  js      loc_180068DFA
0x180068d6c  lfence
0x180068d6f  mov     ecx, 39h ; '9'; id
0x180068d74  call    cs:__imp_SHGlobalCounterIncrement
0x180068d7a  call    ?SetSyncRootManagerRegistryUpdateEvent@@YAJXZ; SetSyncRootManagerRegistryUpdateEvent(void)
0x180068d7f  test    eax, eax
0x180068d81  jns     short loc_180068D9F
0x180068d83  mov     rcx, [rsp+278h]; this
0x180068d8b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180068d92  mov     r9d, eax; char *
0x180068d95  mov     edx, 0DC3h; void *
0x180068d9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068d9f  mov     rax, [rsi+230h]
0x180068da6  xor     r8d, r8d; unsigned __int16 *
0x180068da9  mov     rdx, [rax+rdi*8]
0x180068dad  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180068db1  call    ?_UpdateStorageProviderIdInExtrinsicPropertyStore@CStorageProviderRootsCache@@AEAAXPEBG0@Z; CStorageProviderRootsCache::_UpdateStorageProviderIdInExtrinsicPropertyStore(ushort const *,ushort const *)
0x180068db6  mov     r8, [rsi+238h]
0x180068dbd  cmp     rdi, r8
0x180068dc0  jb      short loc_180068DC9
0x180068dc2  mov     ebx, 80028CA1h
0x180068dc7  jmp     short loc_180068DFA
0x180068dc9  lea     rax, [r8-1]
0x180068dcd  cmp     rdi, rax
0x180068dd0  jz      short loc_180068DF1
0x180068dd2  mov     rax, [rsi+230h]
0x180068dd9  sub     r8, rdi
0x180068ddc  lea     rcx, [rax+rdi*8]; void *
0x180068de0  lea     rdx, [rcx+8]; Src
0x180068de4  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x180068dec  call    memmove_0
0x180068df1  dec     qword ptr [rsi+238h]
0x180068df8  xor     ebx, ebx
0x180068dfa  mov     rcx, [rsp+278h+hkey]; hKey
0x180068dff  call    cs:__imp_RegCloseKey
0x180068e05  mov     ecx, ebx; int
0x180068e07  call    ?HResultIgnoreNotFound@@YAJJ@Z; HResultIgnoreNotFound(long)
0x180068e0c  mov     ebx, eax
0x180068e0e  mov     eax, ebx
0x180068e10  mov     rcx, [rsp+278h+var_28]
0x180068e18  xor     rcx, rsp; StackCookie
0x180068e1b  call    __security_check_cookie
0x180068e20  mov     rbx, [rsp+278h+arg_10]
0x180068e28  add     rsp, 260h
0x180068e2f  pop     rdi
0x180068e30  pop     rsi
0x180068e31  pop     rbp
0x180068e32  retn
```
