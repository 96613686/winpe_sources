# CVersionManagerServer::Initialize(void)

- ea: `0x1800f62e0`
- end: `0x1800f6620`
- name: `?Initialize@CVersionManagerServer@@QEAAJXZ`
- size: `832`
- prototype: `__int64 __fastcall(CVersionManagerServer *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800f5bc0`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x1800723b0`
- `0x18007c7ec`
- `0x1800f6208`
- `0x1800f62e0`
- `0x1800f846c`
- `0x1800f912c`
- `0x1800f94a4`
- `0x1800fcf2c`
- `0x18010c584`
- `0x18010c93c`
- `0x18010e438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f630f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f631f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f632f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f633f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f630f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f631f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f632f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f633f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f64e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f64f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f64fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6504`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f64e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f64f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f64fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6504`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800f62f9`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800f62f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f6601`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f6601`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::Initialize(CVersionManagerServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  unsigned int v3; // edx
  int RegistrySettings; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r8d
  CFileInfoCache *v7; // rax
  CByteHashTable *v8; // rax
  unsigned int v9; // r8d
  char v10; // si
  unsigned int v11; // edx
  CByteHashTable *v12; // rax
  unsigned int v13; // r8d
  void *v14; // rcx
  void *v15; // rcx
  CFileInfoCache *v16; // rcx
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v19; // [rsp+20h] [rbp-58h]
  unsigned int v20; // [rsp+20h] [rbp-58h]
  unsigned int (*v21)(const unsigned __int8 *, unsigned int, unsigned int); // [rsp+28h] [rbp-50h]
  unsigned int (*v22)(const unsigned __int8 *, unsigned int, unsigned int); // [rsp+28h] [rbp-50h]
  int v23; // [rsp+80h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1888);
  *((_DWORD *)this + 499) = GetUserGeoID(0x10u);
  InitializeCriticalSection(v2);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1848));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1784));
  RegistrySettings = CVersionManagerServer::_ReadRegistrySettings(this);
  if ( RegistrySettings < 0 )
    goto LABEL_24;
  RegistrySettings = MutexUtils::CMutex::Create(
                       (CVersionManagerServer *)((char *)this + 2032),
                       L"Local\\VERMGMTBlockListFileMutex",
                       v5);
  if ( RegistrySettings < 0 )
    goto LABEL_24;
  if ( *((_BYTE *)this + 25) )
  {
    RegistrySettings = MutexUtils::CMutex::Create(
                         (CVersionManagerServer *)((char *)this + 2056),
                         L"Local\\VERMGMTAuditMutex",
                         v6);
    if ( RegistrySettings < 0 )
      goto LABEL_24;
  }
  v7 = (CFileInfoCache *)operator new(0x38u);
  if ( v7 )
  {
    *(_WORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 211) = v7;
  if ( v7 )
  {
    RegistrySettings = CFileInfoCache::Initialize(v7, *((_BYTE *)this + 25));
    if ( RegistrySettings < 0 )
      goto LABEL_24;
    v8 = (CByteHashTable *)operator new(0x28u);
    if ( v8 )
    {
      *((_QWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = 0;
      *((_QWORD *)v8 + 3) = 0;
    }
    else
    {
      v8 = 0;
    }
    *((_QWORD *)this + 246) = v8;
    if ( v8 )
    {
      RegistrySettings = CByteHashTable::Create(v8, v3, v9, 2u, v19, v21);
      if ( RegistrySettings < 0 )
        goto LABEL_24;
      v10 = 0;
      RegistrySettings = CVersionManagerServer::_InitializeDomainWhitelist(this);
      if ( RegistrySettings >= 0 )
      {
        v12 = (CByteHashTable *)operator new(0x28u);
        if ( v12 )
        {
          *((_QWORD *)v12 + 4) = 0;
          *((_QWORD *)v12 + 1) = 0;
          *((_QWORD *)v12 + 2) = 0;
          *(_QWORD *)v12 = 0;
          *((_QWORD *)v12 + 3) = 0;
        }
        else
        {
          v12 = 0;
        }
        *((_QWORD *)this + 247) = v12;
        if ( !v12 )
        {
LABEL_21:
          RegistrySettings = -2147024882;
          goto LABEL_22;
        }
        RegistrySettings = CByteHashTable::Create(v12, v11, v13, 2u, v20, v22);
        if ( RegistrySettings >= 0 )
        {
          v10 = 1;
          RegistrySettings = CSharedMem::_InitInternal(
                               (CVersionManagerServer *)((char *)this + 2008),
                               L"Local\\VERMGMTSharedMemory",
                               4u,
                               0,
                               0);
          if ( RegistrySettings >= 0 )
          {
            v23 = 1;
            RegistrySettings = GetBOOL(SettingStore::IEVALUE_urlmon_ExtVerDownloadVersionList, &v23);
            if ( RegistrySettings >= 0 )
            {
              if ( !v23 || (RegistrySettings = CVersionManagerServer::_StartDownloadTimer(this), RegistrySettings >= 0) )
              {
                *((_DWORD *)this + 428) = 3;
                *((_QWORD *)this + 215) = 0;
                *((_QWORD *)this + 216) = 0;
                *((_QWORD *)this + 217) = 0;
                *((_QWORD *)this + 218) = 0;
                *((_QWORD *)this + 219) = 0;
                *((_QWORD *)this + 220) = 0;
                *((_DWORD *)this + 442) = 0;
                *((_DWORD *)this + 444) = 72;
                *((_BYTE *)this + 1704) = 1;
                *((_DWORD *)this + 443) = 2;
                ThreadpoolWork = CreateThreadpoolWork(
                                   CVersionManagerServer::s_TelemetryWorkCallback,
                                   this,
                                   (PTP_CALLBACK_ENVIRON)((char *)this + 1712));
                *((_QWORD *)this + 212) = ThreadpoolWork;
                if ( ThreadpoolWork )
                {
                  *((_BYTE *)this + 24) = 1;
                  return (unsigned int)RegistrySettings;
                }
                goto LABEL_21;
              }
            }
          }
        }
      }
LABEL_22:
      CByteHashTable::_RemoveCallback(*((CByteHashTable **)this + 246), v11, 0, 0);
      if ( v10 )
        CByteHashTable::_RemoveCallback(*((CByteHashTable **)this + 247), v3, 0, 0);
      goto LABEL_24;
    }
  }
  RegistrySettings = -2147024882;
LABEL_24:
  v14 = (void *)*((_QWORD *)this + 247);
  if ( v14 )
    operator delete(v14);
  v15 = (void *)*((_QWORD *)this + 246);
  *((_QWORD *)this + 247) = 0;
  if ( v15 )
    operator delete(v15);
  v16 = (CFileInfoCache *)*((_QWORD *)this + 211);
  *((_QWORD *)this + 246) = 0;
  if ( v16 )
    CFileInfoCache::`scalar deleting destructor'(v16, v3);
  *((_QWORD *)this + 211) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1888));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1848));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1784));
  if ( *((_BYTE *)this + 1704) )
    *((_BYTE *)this + 1704) = 0;
  return (unsigned int)RegistrySettings;
}

```

## disassembly

```asm
0x1800f62e0  push    rbx
0x1800f62e2  push    rbp
0x1800f62e3  push    rsi
0x1800f62e4  push    rdi
0x1800f62e5  push    r12
0x1800f62e7  push    r13
0x1800f62e9  push    r14
0x1800f62eb  push    r15
0x1800f62ed  sub     rsp, 38h
0x1800f62f1  mov     rdi, rcx
0x1800f62f4  mov     ecx, 10h; GeoClass
0x1800f62f9  call    cs:__imp_GetUserGeoID
0x1800f62ff  lea     rbp, [rdi+760h]
0x1800f6306  mov     [rdi+7CCh], eax
0x1800f630c  mov     rcx, rbp; lpCriticalSection
0x1800f630f  call    cs:__imp_InitializeCriticalSection
0x1800f6315  lea     r14, [rdi+738h]
0x1800f631c  mov     rcx, r14; lpCriticalSection
0x1800f631f  call    cs:__imp_InitializeCriticalSection
0x1800f6325  lea     r15, [rdi+788h]
0x1800f632c  mov     rcx, r15; lpCriticalSection
0x1800f632f  call    cs:__imp_InitializeCriticalSection
0x1800f6335  lea     r12, [rdi+6F8h]
0x1800f633c  mov     rcx, r12; lpCriticalSection
0x1800f633f  call    cs:__imp_InitializeCriticalSection
0x1800f6345  mov     rcx, rdi; this
0x1800f6348  call    ?_ReadRegistrySettings@CVersionManagerServer@@AEAAJXZ; CVersionManagerServer::_ReadRegistrySettings(void)
0x1800f634d  xor     r13d, r13d
0x1800f6350  mov     ebx, eax
0x1800f6352  test    eax, eax
0x1800f6354  js      loc_1800F649E
0x1800f635a  lea     rcx, [rdi+7F0h]; this
0x1800f6361  lea     rdx, aLocalVermgmtbl; "Local\\VERMGMTBlockListFileMutex"
0x1800f6368  call    ?Create@CMutex@MutexUtils@@QEAAJPEBGK@Z; MutexUtils::CMutex::Create(ushort const *,ulong)
0x1800f636d  mov     ebx, eax
0x1800f636f  test    eax, eax
0x1800f6371  js      loc_1800F649E
0x1800f6377  cmp     [rdi+19h], r13b
0x1800f637b  jz      short loc_1800F639A
0x1800f637d  lea     rcx, [rdi+808h]; this
0x1800f6384  lea     rdx, aLocalVermgmtau; "Local\\VERMGMTAuditMutex"
0x1800f638b  call    ?Create@CMutex@MutexUtils@@QEAAJPEBGK@Z; MutexUtils::CMutex::Create(ushort const *,ulong)
0x1800f6390  mov     ebx, eax
0x1800f6392  test    eax, eax
0x1800f6394  js      loc_1800F649E
0x1800f639a  mov     ecx, 38h ; '8'; Size
0x1800f639f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f63a4  test    rax, rax
0x1800f63a7  jz      short loc_1800F63B3
0x1800f63a9  mov     [rax], r13w
0x1800f63ad  mov     [rax+8], r13
0x1800f63b1  jmp     short loc_1800F63B6
0x1800f63b3  mov     rax, r13
0x1800f63b6  mov     [rdi+698h], rax
0x1800f63bd  test    rax, rax
0x1800f63c0  jnz     short loc_1800F63CC
0x1800f63c2  mov     ebx, 8007000Eh
0x1800f63c7  jmp     loc_1800F649E
0x1800f63cc  mov     dl, [rdi+19h]; bool
0x1800f63cf  mov     rcx, rax; this
0x1800f63d2  call    ?Initialize@CFileInfoCache@@QEAAJ_N@Z; CFileInfoCache::Initialize(bool)
0x1800f63d7  mov     ebx, eax
0x1800f63d9  test    eax, eax
0x1800f63db  js      loc_1800F649E
0x1800f63e1  mov     ecx, 28h ; '('; Size
0x1800f63e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f63eb  test    rax, rax
0x1800f63ee  jz      short loc_1800F6405
0x1800f63f0  mov     [rax+20h], r13
0x1800f63f4  mov     [rax+8], r13
0x1800f63f8  mov     [rax+10h], r13
0x1800f63fc  mov     [rax], r13
0x1800f63ff  mov     [rax+18h], r13
0x1800f6403  jmp     short loc_1800F6408
0x1800f6405  mov     rax, r13
0x1800f6408  mov     [rdi+7B0h], rax
0x1800f640f  test    rax, rax
0x1800f6412  jz      short loc_1800F63C2
0x1800f6414  mov     r9d, 2; unsigned int
0x1800f641a  mov     rcx, rax; this
0x1800f641d  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x1800f6422  mov     ebx, eax
0x1800f6424  test    eax, eax
0x1800f6426  js      short loc_1800F649E
0x1800f6428  mov     rcx, rdi; this
0x1800f642b  mov     sil, r13b
0x1800f642e  call    ?_InitializeDomainWhitelist@CVersionManagerServer@@AEAAJXZ; CVersionManagerServer::_InitializeDomainWhitelist(void)
0x1800f6433  mov     ebx, eax
0x1800f6435  test    eax, eax
0x1800f6437  js      short loc_1800F6475
0x1800f6439  mov     ecx, 28h ; '('; Size
0x1800f643e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f6443  test    rax, rax
0x1800f6446  jz      short loc_1800F645D
0x1800f6448  mov     [rax+20h], r13
0x1800f644c  mov     [rax+8], r13
0x1800f6450  mov     [rax+10h], r13
0x1800f6454  mov     [rax], r13
0x1800f6457  mov     [rax+18h], r13
0x1800f645b  jmp     short loc_1800F6460
0x1800f645d  mov     rax, r13
0x1800f6460  mov     [rdi+7B8h], rax
0x1800f6467  test    rax, rax
0x1800f646a  jnz     loc_1800F652D
0x1800f6470  mov     ebx, 8007000Eh
0x1800f6475  mov     rcx, [rdi+7B0h]; this
0x1800f647c  xor     r9d, r9d; void *
0x1800f647f  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x1800f6482  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1800f6487  test    sil, sil
0x1800f648a  jz      short loc_1800F649E
0x1800f648c  mov     rcx, [rdi+7B8h]; this
0x1800f6493  xor     r9d, r9d; void *
0x1800f6496  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x1800f6499  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1800f649e  mov     rcx, [rdi+7B8h]; void *
0x1800f64a5  test    rcx, rcx
0x1800f64a8  jz      short loc_1800F64AF
0x1800f64aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f64af  mov     rcx, [rdi+7B0h]; void *
0x1800f64b6  mov     [rdi+7B8h], r13
0x1800f64bd  test    rcx, rcx
0x1800f64c0  jz      short loc_1800F64C7
0x1800f64c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f64c7  mov     rcx, [rdi+698h]; this
0x1800f64ce  mov     [rdi+7B0h], r13
0x1800f64d5  test    rcx, rcx
0x1800f64d8  jz      short loc_1800F64DF
0x1800f64da  call    ??_GCFileInfoCache@@QEAAPEAXI@Z; CFileInfoCache::`scalar deleting destructor'(uint)
0x1800f64df  mov     rcx, rbp; lpCriticalSection
0x1800f64e2  mov     [rdi+698h], r13
0x1800f64e9  call    cs:__imp_DeleteCriticalSection
0x1800f64ef  mov     rcx, r14; lpCriticalSection
0x1800f64f2  call    cs:__imp_DeleteCriticalSection
0x1800f64f8  mov     rcx, r15; lpCriticalSection
0x1800f64fb  call    cs:__imp_DeleteCriticalSection
0x1800f6501  mov     rcx, r12; lpCriticalSection
0x1800f6504  call    cs:__imp_DeleteCriticalSection
0x1800f650a  cmp     [rdi+6A8h], r13b
0x1800f6511  jz      short loc_1800F651A
0x1800f6513  mov     [rdi+6A8h], r13b
0x1800f651a  mov     eax, ebx
0x1800f651c  add     rsp, 38h
0x1800f6520  pop     r15
0x1800f6522  pop     r14
0x1800f6524  pop     r13
0x1800f6526  pop     r12
0x1800f6528  pop     rdi
0x1800f6529  pop     rsi
0x1800f652a  pop     rbp
0x1800f652b  pop     rbx
0x1800f652c  retn
0x1800f652d  mov     r9d, 2; unsigned int
0x1800f6533  mov     rcx, rax; this
0x1800f6536  call    ?Create@CByteHashTable@@QEAAJIIIIP6AIPEBEII@Z@Z; CByteHashTable::Create(uint,uint,uint,uint,uint (*)(uchar const *,uint,uint))
0x1800f653b  mov     ebx, eax
0x1800f653d  test    eax, eax
0x1800f653f  js      loc_1800F6475
0x1800f6545  mov     esi, 1
0x1800f654a  mov     [rsp+78h+var_58], r13d; unsigned int
0x1800f654f  lea     rcx, [rdi+7D8h]; this
0x1800f6556  xor     r9d, r9d; int
0x1800f6559  lea     rdx, aLocalVermgmtsh; "Local\\VERMGMTSharedMemory"
0x1800f6560  lea     r8d, [rsi+3]; unsigned int
0x1800f6564  call    ?_InitInternal@CSharedMem@@AEAAJPEBGKHK@Z; CSharedMem::_InitInternal(ushort const *,ulong,int,ulong)
0x1800f6569  mov     ebx, eax
0x1800f656b  test    eax, eax
0x1800f656d  js      loc_1800F6475
0x1800f6573  mov     rcx, cs:?IEVALUE_urlmon_ExtVerDownloadVersionList@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_urlmon_ExtVerDownloadVersionList
0x1800f657a  lea     rdx, [rsp+78h+arg_0]
0x1800f6582  mov     [rsp+78h+arg_0], esi
0x1800f6589  call    GetBOOL
0x1800f658e  mov     ebx, eax
0x1800f6590  test    eax, eax
0x1800f6592  js      loc_1800F6475
0x1800f6598  cmp     [rsp+78h+arg_0], r13d
0x1800f65a0  jz      short loc_1800F65B4
0x1800f65a2  mov     rcx, rdi; pv
0x1800f65a5  call    ?_StartDownloadTimer@CVersionManagerServer@@AEAAJXZ; CVersionManagerServer::_StartDownloadTimer(void)
0x1800f65aa  mov     ebx, eax
0x1800f65ac  test    eax, eax
0x1800f65ae  js      loc_1800F6475
0x1800f65b4  lea     r8, [rdi+6B0h]; pcbe
0x1800f65bb  mov     rdx, rdi; pv
0x1800f65be  mov     dword ptr [r8], 3
0x1800f65c5  lea     rcx, ?s_TelemetryWorkCallback@CVersionManagerServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f65cc  mov     [r8+8], r13
0x1800f65d0  mov     [r8+10h], r13
0x1800f65d4  mov     [r8+18h], r13
0x1800f65d8  mov     [r8+20h], r13
0x1800f65dc  mov     [r8+28h], r13
0x1800f65e0  mov     [r8+30h], r13
0x1800f65e4  mov     [r8+38h], r13d
0x1800f65e8  mov     dword ptr [r8+40h], 48h ; 'H'
0x1800f65f0  mov     [rdi+6A8h], sil
0x1800f65f7  mov     dword ptr [rdi+6ECh], 2
0x1800f6601  call    cs:__imp_CreateThreadpoolWork
0x1800f6607  mov     [rdi+6A0h], rax
0x1800f660e  test    rax, rax
0x1800f6611  jz      loc_1800F6470
0x1800f6617  mov     [rdi+18h], sil
0x1800f661b  jmp     loc_1800F651A
```
