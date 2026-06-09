# CStorageProviderRootsCache::SetPendingRedirectionUserSyncRoot(ushort const *,ushort const *)

- ea: `0x180069b78`
- end: `0x180069d54`
- name: `?SetPendingRedirectionUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG0@Z`
- size: `476`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069dac`

## callees

- `0x180003210`
- `0x18000b9b0`
- `0x18000bc30`
- `0x180019680`
- `0x1800356d8`
- `0x180035848`
- `0x180037780`
- `0x180043c98`
- `0x180069b78`

## import_xrefs

- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180069cab`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180069cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069d09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069c69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069c69`

## string_xrefs

- `0x180069cc4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderRootsCache::SetPendingRedirectionUserSyncRoot(
        CStorageProviderRootsCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  signed int SyncEngineRegPath; // ebx
  unsigned __int64 i; // rdi
  unsigned __int64 v10; // r8
  LSTATUS v11; // eax
  int updated; // eax
  _QWORD *v13; // rdi
  __int64 v14; // rsi
  void *v15; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v19 = 0;
  v20 = 0;
  v21 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
  v20 = -1;
  v21 = -1;
  SyncEngineRegPath = _AllocString<CTCoAllocPolicy>(v7, v6, a3, &v19);
  if ( SyncEngineRegPath >= 0 )
  {
    SyncEngineRegPath = -2147023728;
    for ( i = 0; i < *((_QWORD *)this + 71); ++i )
    {
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           *(_QWORD *)(*((_QWORD *)this + 70) + 8 * i),
                           a2,
                           -1) == 2 )
      {
        SyncEngineRegPath = CStorageProviderRootsCache::_GetSyncEngineRegPath(this, SubKey, v10);
        if ( SyncEngineRegPath >= 0 )
        {
          hKey = 0;
          v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
          SyncEngineRegPath = v11;
          if ( v11 > 0 )
            SyncEngineRegPath = (unsigned __int16)v11 | 0x80070000;
          if ( SyncEngineRegPath >= 0 )
          {
            SyncEngineRegPath = SHRegSetString(hKey, L"PendingRedirectionSyncRoots", a2, a3);
            if ( SyncEngineRegPath >= 0 )
            {
              _mm_lfence();
              SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
              updated = SetSyncRootManagerRegistryUpdateEvent();
              if ( updated < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xD9E,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                  (const char *)(unsigned int)updated,
                  phkResult);
              v13 = *(_QWORD **)(*((_QWORD *)this + 70) + 8 * i);
              v14 = v19;
              v19 = 0;
              v21 = 0;
              v20 = 0;
              v15 = (void *)v13[6];
              if ( v15 )
                CoTaskMemFree(v15);
              v13[6] = v14;
              v13[8] = -1;
              v13[7] = -1;
            }
            RegCloseKey(hKey);
          }
        }
        break;
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
  return (unsigned int)SyncEngineRegPath;
}

```

## disassembly

```asm
0x180069b78  push    rbp
0x180069b7a  push    rbx
0x180069b7b  push    rsi
0x180069b7c  push    rdi
0x180069b7d  push    r13
0x180069b7f  push    r14
0x180069b81  push    r15
0x180069b83  lea     rbp, [rsp-170h]
0x180069b8b  sub     rsp, 270h
0x180069b92  mov     rax, cs:__security_cookie
0x180069b99  xor     rax, rsp
0x180069b9c  mov     [rbp+1A0h+var_40], rax
0x180069ba3  mov     r15, r8
0x180069ba6  mov     r14, rdx
0x180069ba9  mov     rsi, rcx
0x180069bac  mov     [rsp+2A0h+var_268], 0
0x180069bb5  mov     [rsp+2A0h+var_260], 0
0x180069bbe  mov     [rsp+2A0h+var_258], 0
0x180069bc7  lea     rcx, [rsp+2A0h+var_268]
0x180069bcc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180069bd1  or      r13, 0FFFFFFFFFFFFFFFFh
0x180069bd5  mov     [rsp+2A0h+var_260], r13
0x180069bda  mov     [rsp+2A0h+var_258], r13
0x180069bdf  lea     r9, [rsp+2A0h+var_268]
0x180069be4  mov     r8, r15
0x180069be7  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180069bec  mov     ebx, eax
0x180069bee  test    eax, eax
0x180069bf0  js      loc_180069D27
0x180069bf6  mov     ebx, 80070490h
0x180069bfb  xor     edi, edi
0x180069bfd  cmp     rdi, [rsi+238h]
0x180069c04  jnb     loc_180069D27
0x180069c0a  mov     rcx, [rsi+230h]
0x180069c11  mov     r8, r13
0x180069c14  mov     rdx, r14
0x180069c17  mov     rcx, [rcx+rdi*8]
0x180069c1b  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180069c20  cmp     eax, 2
0x180069c23  jz      short loc_180069C2A
0x180069c25  inc     rdi
0x180069c28  jmp     short loc_180069BFD
0x180069c2a  lea     rdx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180069c2f  mov     rcx, rsi; this
0x180069c32  call    ?_GetSyncEngineRegPath@CStorageProviderRootsCache@@AEBAJPEAG_K@Z; CStorageProviderRootsCache::_GetSyncEngineRegPath(ushort *,unsigned __int64)
0x180069c37  mov     ebx, eax
0x180069c39  test    eax, eax
0x180069c3b  js      loc_180069D27
0x180069c41  mov     [rsp+2A0h+hKey], 0
0x180069c4a  lea     rax, [rsp+2A0h+hKey]
0x180069c4f  mov     qword ptr [rsp+2A0h+phkResult], rax; int
0x180069c54  mov     r9d, 2011Fh; samDesired
0x180069c5a  xor     r8d, r8d; ulOptions
0x180069c5d  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180069c62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069c69  call    cs:__imp_RegOpenKeyExW
0x180069c6f  mov     ebx, eax
0x180069c71  test    eax, eax
0x180069c73  jle     short loc_180069C7E
0x180069c75  movzx   ebx, ax
0x180069c78  or      ebx, 80070000h
0x180069c7e  test    ebx, ebx
0x180069c80  js      loc_180069D27
0x180069c86  mov     r9, r15; unsigned __int16 *
0x180069c89  mov     r8, r14; unsigned __int16 *
0x180069c8c  lea     rdx, pszSubKey; "PendingRedirectionSyncRoots"
0x180069c93  mov     rcx, [rsp+2A0h+hKey]; HKEY
0x180069c98  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180069c9d  mov     ebx, eax
0x180069c9f  test    eax, eax
0x180069ca1  js      short loc_180069D1B
0x180069ca3  lfence
0x180069ca6  mov     ecx, 39h ; '9'; id
0x180069cab  call    cs:__imp_SHGlobalCounterIncrement
0x180069cb1  call    ?SetSyncRootManagerRegistryUpdateEvent@@YAJXZ; SetSyncRootManagerRegistryUpdateEvent(void)
0x180069cb6  mov     rcx, [rbp+1A8h]; this
0x180069cbd  test    eax, eax
0x180069cbf  jns     short loc_180069CD5
0x180069cc1  mov     r9d, eax; char *
0x180069cc4  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180069ccb  mov     edx, 0D9Eh; void *
0x180069cd0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180069cd5  mov     rax, [rsi+230h]
0x180069cdc  mov     rdi, [rax+rdi*8]
0x180069ce0  mov     rsi, [rsp+2A0h+var_268]
0x180069ce5  mov     [rsp+2A0h+var_268], 0
0x180069cee  mov     [rsp+2A0h+var_258], 0
0x180069cf7  mov     [rsp+2A0h+var_260], 0
0x180069d00  mov     rcx, [rdi+30h]; pv
0x180069d04  test    rcx, rcx
0x180069d07  jz      short loc_180069D0F
0x180069d09  call    cs:__imp_CoTaskMemFree
0x180069d0f  mov     [rdi+30h], rsi
0x180069d13  mov     [rdi+40h], r13
0x180069d17  mov     [rdi+38h], r13
0x180069d1b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180069d20  call    cs:__imp_RegCloseKey
0x180069d26  nop
0x180069d27  lea     rcx, [rsp+2A0h+var_268]
0x180069d2c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180069d31  mov     eax, ebx
0x180069d33  mov     rcx, [rbp+1A0h+var_40]
0x180069d3a  xor     rcx, rsp; StackCookie
0x180069d3d  call    __security_check_cookie
0x180069d42  add     rsp, 270h
0x180069d49  pop     r15
0x180069d4b  pop     r14
0x180069d4d  pop     r13
0x180069d4f  pop     rdi
0x180069d50  pop     rsi
0x180069d51  pop     rbx
0x180069d52  pop     rbp
0x180069d53  retn
```
