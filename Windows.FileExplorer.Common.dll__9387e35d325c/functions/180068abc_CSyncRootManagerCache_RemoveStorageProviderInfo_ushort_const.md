# CSyncRootManagerCache::RemoveStorageProviderInfo(ushort const *)

- ea: `0x180068abc`
- end: `0x180068c77`
- name: `?RemoveStorageProviderInfo@CSyncRootManagerCache@@QEAAJPEBG@Z`
- size: `443`
- prototype: `int(CSyncRootManagerCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180068a80`

## callees

- `0x180003210`
- `0x1800077c8`
- `0x180009374`
- `0x18001be38`
- `0x18001d320`
- `0x1800202c0`
- `0x180021cdc`
- `0x180022608`
- `0x1800386fc`
- `0x180043c98`
- `0x180068abc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068c38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068c38`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180068c52`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180068c52`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180068bc9`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180068bc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068bf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068b8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068b8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180068baf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180068baf`

## string_xrefs

- `0x180068b44`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180068be0`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncRootManagerCache::RemoveStorageProviderInfo(
        struct _RTL_SRWLOCK *this,
        const unsigned __int16 *a2)
{
  signed int v4; // ebx
  void *i; // rsi
  const unsigned __int16 **v6; // rdx
  int SyncRootManagerRegistryLocation; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  int updated; // eax
  _BYTE *Ptr; // r8
  int phkResult; // [rsp+20h] [rbp-58h]
  int phkResulta; // [rsp+20h] [rbp-58h]
  _BYTE v15[72]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF
  LPCWSTR lpSubKey; // [rsp+90h] [rbp+18h] BYREF

  LockCacheAndFreeStale::LockCacheAndFreeStale((LockCacheAndFreeStale *)v15, this + 3);
  v4 = CSyncRootManagerCache::_EnsureCachedValues(this, v15, 0xFFFFFFFFLL);
  if ( v4 >= 0 )
  {
    for ( i = 0; i < this[5].Ptr; i = (char *)i + 1 )
    {
      if ( CStorageProviderRootsCache::IsSameIdentifier(*((CStorageProviderRootsCache **)this[4].Ptr + (_QWORD)i), a2) )
      {
        lpSubKey = 0;
        SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                            (Windows::Internal::SyncRootHelpers *)&lpSubKey,
                                            v6);
        v4 = SyncRootManagerRegistryLocation;
        if ( SyncRootManagerRegistryLocation >= 0 )
        {
          hKey = 0;
          v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
          v4 = v8;
          if ( v8 > 0 )
            v4 = (unsigned __int16)v8 | 0x80070000;
          if ( v4 >= 0 )
          {
            v9 = RegDeleteTreeW(hKey, a2);
            v4 = v9;
            if ( v9 > 0 )
              v4 = (unsigned __int16)v9 | 0x80070000;
            SHGlobalCounterIncrement(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
            updated = SetSyncRootManagerRegistryUpdateEvent();
            if ( updated < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x10EF,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)updated,
                phkResulta);
            RegCloseKey(hKey);
          }
          Ptr = this[5].Ptr;
          if ( i < Ptr )
          {
            if ( i != Ptr - 1 )
              memmove_0(
                (char *)this[4].Ptr + 8 * (_QWORD)i,
                (char *)this[4].Ptr + 8 * (_QWORD)i + 8,
                8 * (Ptr - (_BYTE *)i) - 8);
            --this[5].Ptr;
            if ( !(unsigned int)_o__wcsicmp(a2, this[12].Ptr) )
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &this[12],
                0);
            LODWORD(this[2].Ptr) = SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10E3,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
            (const char *)(unsigned int)SyncRootManagerRegistryLocation,
            phkResult);
        }
        break;
      }
    }
  }
  LockCacheAndFreeStale::~LockCacheAndFreeStale((LockCacheAndFreeStale *)v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180068abc  mov     [rsp+arg_8], rbx
0x180068ac1  push    rbp
0x180068ac2  push    rsi
0x180068ac3  push    rdi
0x180068ac4  sub     rsp, 60h
0x180068ac8  mov     rbp, rdx
0x180068acb  mov     rdi, rcx
0x180068ace  lea     rdx, [rcx+18h]; struct _RTL_SRWLOCK *
0x180068ad2  lea     rcx, [rsp+78h+var_48]; this
0x180068ad7  call    ??0LockCacheAndFreeStale@@QEAA@PEAU_RTL_SRWLOCK@@@Z; LockCacheAndFreeStale::LockCacheAndFreeStale(_RTL_SRWLOCK *)
0x180068adc  nop
0x180068add  or      r8d, 0FFFFFFFFh
0x180068ae1  lea     rdx, [rsp+78h+var_48]
0x180068ae6  mov     rcx, rdi
0x180068ae9  call    ?_EnsureCachedValues@CSyncRootManagerCache@@AEAAJAEAVLockCacheAndFreeStale@@W4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValues(LockCacheAndFreeStale &,SPGSP_FLAGS)
0x180068aee  mov     ebx, eax
0x180068af0  test    eax, eax
0x180068af2  js      loc_180068C5B
0x180068af8  xor     esi, esi
0x180068afa  cmp     rsi, [rdi+28h]
0x180068afe  jnb     loc_180068C5B
0x180068b04  mov     rcx, [rdi+20h]
0x180068b08  mov     rdx, rbp; unsigned __int16 *
0x180068b0b  mov     rcx, [rcx+rsi*8]; this
0x180068b0f  call    ?IsSameIdentifier@CStorageProviderRootsCache@@QEAA_NPEBG@Z; CStorageProviderRootsCache::IsSameIdentifier(ushort const *)
0x180068b14  test    al, al
0x180068b16  jnz     short loc_180068B1D
0x180068b18  inc     rsi
0x180068b1b  jmp     short loc_180068AFA
0x180068b1d  mov     [rsp+78h+lpSubKey], 0
0x180068b29  lea     rcx, [rsp+78h+lpSubKey]; this
0x180068b31  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x180068b36  mov     ebx, eax
0x180068b38  test    eax, eax
0x180068b3a  jns     short loc_180068B5A
0x180068b3c  mov     rcx, [rsp+78h]; this
0x180068b41  mov     r9d, eax; char *
0x180068b44  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180068b4b  mov     edx, 10E3h; void *
0x180068b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068b55  jmp     loc_180068C5B
0x180068b5a  mov     [rsp+78h+hKey], 0
0x180068b66  lea     rax, [rsp+78h+hKey]
0x180068b6e  mov     qword ptr [rsp+78h+phkResult], rax; int
0x180068b73  mov     r9d, 20119h; samDesired
0x180068b79  xor     r8d, r8d; ulOptions
0x180068b7c  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x180068b84  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068b8b  call    cs:__imp_RegOpenKeyExW
0x180068b91  mov     ebx, eax
0x180068b93  test    eax, eax
0x180068b95  jle     short loc_180068BA0
0x180068b97  movzx   ebx, ax
0x180068b9a  or      ebx, 80070000h
0x180068ba0  test    ebx, ebx
0x180068ba2  js      short loc_180068BFF
0x180068ba4  mov     rdx, rbp; lpSubKey
0x180068ba7  mov     rcx, [rsp+78h+hKey]; hKey
0x180068baf  call    cs:__imp_RegDeleteTreeW
0x180068bb5  mov     ebx, eax
0x180068bb7  test    eax, eax
0x180068bb9  jle     short loc_180068BC4
0x180068bbb  movzx   ebx, ax
0x180068bbe  or      ebx, 80070000h
0x180068bc4  mov     ecx, 39h ; '9'; id
0x180068bc9  call    cs:__imp_SHGlobalCounterIncrement
0x180068bcf  call    ?SetSyncRootManagerRegistryUpdateEvent@@YAJXZ; SetSyncRootManagerRegistryUpdateEvent(void)
0x180068bd4  mov     rcx, [rsp+78h]; this
0x180068bd9  test    eax, eax
0x180068bdb  jns     short loc_180068BF1
0x180068bdd  mov     r9d, eax; char *
0x180068be0  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180068be7  mov     edx, 10EFh; void *
0x180068bec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068bf1  mov     rcx, [rsp+78h+hKey]; hKey
0x180068bf9  call    cs:__imp_RegCloseKey
0x180068bff  mov     r8, [rdi+28h]
0x180068c03  cmp     rsi, r8
0x180068c06  jnb     short loc_180068C5B
0x180068c08  lea     rax, [r8-1]
0x180068c0c  cmp     rsi, rax
0x180068c0f  jz      short loc_180068C2D
0x180068c11  mov     rax, [rdi+20h]
0x180068c15  lea     rcx, [rax+rsi*8]; void *
0x180068c19  sub     r8, rsi
0x180068c1c  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x180068c24  lea     rdx, [rcx+8]; Src
0x180068c28  call    memmove_0
0x180068c2d  dec     qword ptr [rdi+28h]
0x180068c31  mov     rdx, [rdi+60h]
0x180068c35  mov     rcx, rbp
0x180068c38  call    cs:__imp__o__wcsicmp
0x180068c3e  test    eax, eax
0x180068c40  jnz     short loc_180068C4D
0x180068c42  xor     edx, edx
0x180068c44  lea     rcx, [rdi+60h]
0x180068c48  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180068c4d  mov     ecx, 39h ; '9'; id
0x180068c52  call    cs:__imp_SHGlobalCounterGetValue
0x180068c58  mov     [rdi+10h], eax
0x180068c5b  lea     rcx, [rsp+78h+var_48]; this
0x180068c60  call    ??1LockCacheAndFreeStale@@QEAA@XZ; LockCacheAndFreeStale::~LockCacheAndFreeStale(void)
0x180068c65  mov     eax, ebx
0x180068c67  mov     rbx, [rsp+78h+arg_8]
0x180068c6f  add     rsp, 60h
0x180068c73  pop     rdi
0x180068c74  pop     rsi
0x180068c75  pop     rbp
0x180068c76  retn
```
