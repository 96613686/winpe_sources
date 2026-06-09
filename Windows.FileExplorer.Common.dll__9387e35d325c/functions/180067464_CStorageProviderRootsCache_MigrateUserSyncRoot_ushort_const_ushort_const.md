# CStorageProviderRootsCache::MigrateUserSyncRoot(ushort const *,ushort const *)

- ea: `0x180067464`
- end: `0x1800676ba`
- name: `?MigrateUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG0@Z`
- size: `598`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, LPCWSTR pszValue, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006770c`

## callees

- `0x180003210`
- `0x18000b9b0`
- `0x18000bc30`
- `0x180019680`
- `0x1800356d8`
- `0x180035848`
- `0x180037780`
- `0x180043c98`
- `0x180067464`

## import_xrefs

- `SHCORE!SHDeleteValueW` at `0x18006757e`
- `SHCORE!SHDeleteValueW` at `0x180067593`
- `SHCORE!SHDeleteValueW` at `0x18006757e`
- `SHCORE!SHDeleteValueW` at `0x180067593`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180067645`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180067645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800675d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800675d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067686`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067555`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067555`

## string_xrefs

- `0x18006765e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderRootsCache::MigrateUserSyncRoot(
        CStorageProviderRootsCache *this,
        LPCWSTR pszValue,
        const unsigned __int16 *a3)
{
  LSTATUS SyncEngineRegPath; // ebx
  unsigned __int64 i; // rdi
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int64 v10; // r8
  int v11; // eax
  bool v12; // sf
  __int64 v13; // rbx
  __int64 v14; // r14
  const unsigned __int16 *v15; // r9
  int updated; // eax
  HKEY v17; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  SyncEngineRegPath = 1;
  for ( i = 0; i < *((_QWORD *)this + 71); ++i )
  {
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         *(_QWORD *)(*((_QWORD *)this + 70) + 8 * i),
                         pszValue,
                         -1) == 2 )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
      v22 = -1;
      v23 = -1;
      SyncEngineRegPath = _AllocString<CTCoAllocPolicy>(v9, v8, a3, &v21);
      if ( SyncEngineRegPath >= 0 )
      {
        SyncEngineRegPath = CStorageProviderRootsCache::_GetSyncEngineRegPath(this, SubKey, v10);
        if ( SyncEngineRegPath >= 0 )
        {
          hkey = 0;
          v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hkey);
          v12 = v11 < 0;
          if ( v11 > 0 )
          {
            v11 = (unsigned __int16)v11 | 0x80070000;
            v12 = v11 < 0;
          }
          if ( v12 )
          {
            SyncEngineRegPath = v11;
          }
          else
          {
            SHDeleteValueW(hkey, L"PendingRedirectionSyncRoots", pszValue);
            SyncEngineRegPath = SHDeleteValueW(hkey, L"UserSyncRoots", pszValue);
            if ( SyncEngineRegPath >= 0 )
            {
              _mm_lfence();
              v13 = *(_QWORD *)(*((_QWORD *)this + 70) + 8 * i);
              v14 = v21;
              v21 = 0;
              v23 = 0;
              v22 = 0;
              if ( *(_QWORD *)v13 )
                CoTaskMemFree(*(LPVOID *)v13);
              *(_QWORD *)v13 = v14;
              *(_QWORD *)(v13 + 16) = -1;
              *(_QWORD *)(v13 + 8) = -1;
              SyncEngineRegPath = SHRegSetString(
                                    hkey,
                                    L"UserSyncRoots",
                                    a3,
                                    *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 70) + 8 * i) + 24LL));
              if ( SyncEngineRegPath >= 0 )
              {
                _mm_lfence();
                v15 = *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 70) + 8 * i) + 48LL);
                if ( v15 )
                  SyncEngineRegPath = SHRegSetString(hkey, L"PendingRedirectionSyncRoots", a3, v15);
              }
              SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
              updated = SetSyncRootManagerRegistryUpdateEvent();
              if ( updated < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xDF5,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                  (const char *)(unsigned int)updated,
                  phkResult);
            }
          }
          v17 = hkey;
          hkey = 0;
          if ( v17 )
            RegCloseKey(v17);
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
      return (unsigned int)SyncEngineRegPath;
    }
  }
  return (unsigned int)SyncEngineRegPath;
}

```

## disassembly

```asm
0x180067464  push    rbp
0x180067466  push    rbx
0x180067467  push    rsi
0x180067468  push    rdi
0x180067469  push    r13
0x18006746b  push    r14
0x18006746d  push    r15
0x18006746f  lea     rbp, [rsp-170h]
0x180067477  sub     rsp, 270h
0x18006747e  mov     rax, cs:__security_cookie
0x180067485  xor     rax, rsp
0x180067488  mov     [rbp+1A0h+var_40], rax
0x18006748f  mov     r15, r8
0x180067492  mov     r14, rdx
0x180067495  mov     rsi, rcx
0x180067498  mov     ebx, 1
0x18006749d  xor     edi, edi
0x18006749f  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800674a3  cmp     rdi, [rsi+238h]
0x1800674aa  jnb     loc_180067697
0x1800674b0  mov     rcx, [rsi+230h]
0x1800674b7  mov     r8, r13
0x1800674ba  mov     rdx, r14
0x1800674bd  mov     rcx, [rcx+rdi*8]
0x1800674c1  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800674c6  cmp     eax, 2
0x1800674c9  jz      short loc_1800674D0
0x1800674cb  add     rdi, rbx
0x1800674ce  jmp     short loc_1800674A3
0x1800674d0  mov     [rsp+2A0h+var_268], 0
0x1800674d9  mov     [rsp+2A0h+var_260], 0
0x1800674e2  mov     [rsp+2A0h+var_258], 0
0x1800674eb  lea     rcx, [rsp+2A0h+var_268]
0x1800674f0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800674f5  mov     [rsp+2A0h+var_260], r13
0x1800674fa  mov     [rsp+2A0h+var_258], r13
0x1800674ff  lea     r9, [rsp+2A0h+var_268]
0x180067504  mov     r8, r15
0x180067507  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18006750c  mov     ebx, eax
0x18006750e  test    eax, eax
0x180067510  js      loc_18006768D
0x180067516  lea     rdx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18006751b  mov     rcx, rsi; this
0x18006751e  call    ?_GetSyncEngineRegPath@CStorageProviderRootsCache@@AEBAJPEAG_K@Z; CStorageProviderRootsCache::_GetSyncEngineRegPath(ushort *,unsigned __int64)
0x180067523  mov     ebx, eax
0x180067525  test    eax, eax
0x180067527  js      loc_18006768D
0x18006752d  mov     [rsp+2A0h+hkey], 0
0x180067536  lea     rax, [rsp+2A0h+hkey]
0x18006753b  mov     qword ptr [rsp+2A0h+phkResult], rax; int
0x180067540  mov     r9d, 2011Fh; samDesired
0x180067546  xor     r8d, r8d; ulOptions
0x180067549  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18006754e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180067555  call    cs:__imp_RegOpenKeyExW
0x18006755b  test    eax, eax
0x18006755d  jle     short loc_180067569
0x18006755f  movzx   eax, ax
0x180067562  or      eax, 80070000h
0x180067567  test    eax, eax
0x180067569  js      loc_180067671
0x18006756f  mov     r8, r14; pszValue
0x180067572  lea     rdx, pszSubKey; "PendingRedirectionSyncRoots"
0x180067579  mov     rcx, [rsp+2A0h+hkey]; hkey
0x18006757e  call    cs:__imp_SHDeleteValueW
0x180067584  mov     r8, r14; pszValue
0x180067587  lea     rdx, aUsersyncroots_0; "UserSyncRoots"
0x18006758e  mov     rcx, [rsp+2A0h+hkey]; hkey
0x180067593  call    cs:__imp_SHDeleteValueW
0x180067599  mov     ebx, eax
0x18006759b  test    eax, eax
0x18006759d  js      loc_180067673
0x1800675a3  lfence
0x1800675a6  mov     rax, [rsi+230h]
0x1800675ad  mov     rbx, [rax+rdi*8]
0x1800675b1  mov     r14, [rsp+2A0h+var_268]
0x1800675b6  mov     [rsp+2A0h+var_268], 0
0x1800675bf  mov     [rsp+2A0h+var_258], 0
0x1800675c8  mov     [rsp+2A0h+var_260], 0
0x1800675d1  mov     rcx, [rbx]; pv
0x1800675d4  test    rcx, rcx
0x1800675d7  jz      short loc_1800675DF
0x1800675d9  call    cs:__imp_CoTaskMemFree
0x1800675df  mov     [rbx], r14
0x1800675e2  mov     [rbx+10h], r13
0x1800675e6  mov     [rbx+8], r13
0x1800675ea  mov     rax, [rsi+230h]
0x1800675f1  mov     r9, [rax+rdi*8]
0x1800675f5  mov     r9, [r9+18h]; unsigned __int16 *
0x1800675f9  mov     r8, r15; unsigned __int16 *
0x1800675fc  lea     rdx, aUsersyncroots_0; "UserSyncRoots"
0x180067603  mov     rcx, [rsp+2A0h+hkey]; HKEY
0x180067608  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18006760d  mov     ebx, eax
0x18006760f  test    eax, eax
0x180067611  js      short loc_180067640
0x180067613  lfence
0x180067616  mov     rax, [rsi+230h]
0x18006761d  mov     rcx, [rax+rdi*8]
0x180067621  mov     r9, [rcx+30h]; unsigned __int16 *
0x180067625  test    r9, r9
0x180067628  jz      short loc_180067640
0x18006762a  mov     r8, r15; unsigned __int16 *
0x18006762d  lea     rdx, pszSubKey; "PendingRedirectionSyncRoots"
0x180067634  mov     rcx, [rsp+2A0h+hkey]; HKEY
0x180067639  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18006763e  mov     ebx, eax
0x180067640  mov     ecx, 39h ; '9'; id
0x180067645  call    cs:__imp_SHGlobalCounterIncrement
0x18006764b  call    ?SetSyncRootManagerRegistryUpdateEvent@@YAJXZ; SetSyncRootManagerRegistryUpdateEvent(void)
0x180067650  mov     rcx, [rbp+1A8h]; this
0x180067657  test    eax, eax
0x180067659  jns     short loc_180067673
0x18006765b  mov     r9d, eax; char *
0x18006765e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180067665  mov     edx, 0DF5h; void *
0x18006766a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006766f  jmp     short loc_180067673
0x180067671  mov     ebx, eax
0x180067673  mov     rcx, [rsp+2A0h+hkey]; hKey
0x180067678  mov     [rsp+2A0h+hkey], 0
0x180067681  test    rcx, rcx
0x180067684  jz      short loc_18006768D
0x180067686  call    cs:__imp_RegCloseKey
0x18006768c  nop
0x18006768d  lea     rcx, [rsp+2A0h+var_268]
0x180067692  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180067697  mov     eax, ebx
0x180067699  mov     rcx, [rbp+1A0h+var_40]
0x1800676a0  xor     rcx, rsp; StackCookie
0x1800676a3  call    __security_check_cookie
0x1800676a8  add     rsp, 270h
0x1800676af  pop     r15
0x1800676b1  pop     r14
0x1800676b3  pop     r13
0x1800676b5  pop     rdi
0x1800676b6  pop     rsi
0x1800676b7  pop     rbx
0x1800676b8  pop     rbp
0x1800676b9  retn
```
