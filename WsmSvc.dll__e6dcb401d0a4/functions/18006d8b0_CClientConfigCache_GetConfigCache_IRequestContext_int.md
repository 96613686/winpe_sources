# CClientConfigCache::GetConfigCache(IRequestContext *,int)

- ea: `0x18006d8b0`
- end: `0x18006db4f`
- name: `?GetConfigCache@CClientConfigCache@@SAPEAV1@PEAVIRequestContext@@H@Z`
- size: `671`
- prototype: `struct CClientConfigCache *__fastcall(struct IRequestContext *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014134`
- `0x18006db58`

## callees

- `0x180008920`
- `0x18000fc50`
- `0x180010030`
- `0x180064250`
- `0x18006b0f0`
- `0x18006bdf0`
- `0x18006c1a0`
- `0x18006d8b0`
- `0x18006e2c0`
- `0x1800c12b0`
- `0x1800da140`
- `0x180112380`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006db10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006db10`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006da15`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006dab6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006da15`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006dab6`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18006d9a1`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18006d9a1`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18006da8c`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18006da8c`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006d9fd`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006da9a`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006d9fd`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006da9a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006d985`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006d985`

## string_xrefs

- `0x18006d914`: `onecore\admin\wmi\wmx\config\cbaseconfigcache.cpp`
- `0x18006d923`: `GetSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct CClientConfigCache *__fastcall CClientConfigCache::GetConfigCache(struct IRequestContext *a1, int a2)
{
  PVOID *v4; // rcx
  void *Sid; // rax
  void (__fastcall *v6)(struct IRequestContext *, __int64, const wchar_t *, _QWORD, const wchar_t *, int); // rbx
  DWORD LastError; // eax
  CBaseConfigCache *Existing; // rbx
  LPWSTR v10; // rcx
  LPWSTR v11; // rcx
  void (__fastcall *v12)(struct IRequestContext *, _QWORD); // rbx
  DWORD v13; // eax
  _QWORD v14[2]; // [rsp+40h] [rbp-10h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp+40h] BYREF
  CBaseConfigCache *v16; // [rsp+98h] [rbp+48h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1e1842acf310370d2787f779e68f4b62_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200000) != 0 )
      WPP_SF_(v4[2], 12, &WPP_8bd3cce8cb123278e51b7ba80b282f9d_Traceguids);
  }
  Sid = CSecurity::GetSid();
  v14[0] = Sid;
  if ( !Sid )
  {
    v6 = *(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD, const wchar_t *, int))(*(_QWORD *)a1 + 88LL);
    LastError = GetLastError();
    v6(a1, 1077134181, L"GetSid", LastError, L"onecore\\admin\\wmi\\wmx\\config\\cbaseconfigcache.cpp", 76);
LABEL_7:
    Existing = 0;
    goto LABEL_8;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v12 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL);
    v13 = GetLastError();
    v12(a1, v13);
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>((void **)&StringSid);
    goto LABEL_7;
  }
  v14[1] = &CClientConfigCache::s_mapLock;
  if ( !(unsigned int)RtlTryAcquireFastLockExclusive(&CClientConfigCache::s_mapLock) )
    RtlQueueAcquireFastLockExclusive(&CClientConfigCache::s_mapLock);
  if ( !(unsigned int)CBaseConfigCache::InitMap(a1, &CClientConfigCache::s_cacheMap) )
  {
    RtlReleaseFastLockExclusive(&CClientConfigCache::s_mapLock);
    v11 = StringSid;
    StringSid = 0;
    if ( v11 )
      LocalFree(v11);
    goto LABEL_7;
  }
  Existing = (CBaseConfigCache *)CBaseConfigCache::FindExisting(CClientConfigCache::s_cacheMap, StringSid, 2);
  v16 = Existing;
  if ( !Existing )
  {
    Existing = (CBaseConfigCache *)CBaseConfigCache::CreateNew(
                                     a1,
                                     CClientConfigCache::s_cacheMap,
                                     CClientConfigCache::AllocCache,
                                     2,
                                     a2);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v16);
    v16 = Existing;
    if ( Existing )
    {
      if ( !CBaseConfigCache::AddToMap(Existing, a1, (struct AutoLocalFree *)&StringSid) )
      {
        CBaseConfigCache::Shutdown(Existing);
        AutoRelease<CServiceConfigCache>::operator=(&v16, 0);
        Existing = v16;
      }
    }
  }
  v16 = 0;
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v16);
  RtlReleaseFastLockExclusive(&CClientConfigCache::s_mapLock);
  v10 = StringSid;
  StringSid = 0;
  if ( v10 )
    LocalFree(v10);
LABEL_8:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(v14);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1e1842acf310370d2787f779e68f4b62_Traceguids, Existing);
  return Existing;
}

```

## disassembly

```asm
0x18006d8b0  mov     [rsp-28h+arg_0], rbx
0x18006d8b5  push    rbp
0x18006d8b6  push    rsi
0x18006d8b7  push    rdi
0x18006d8b8  push    r13
0x18006d8ba  push    r15
0x18006d8bc  mov     rbp, rsp
0x18006d8bf  sub     rsp, 50h
0x18006d8c3  mov     esi, edx
0x18006d8c5  mov     rdi, rcx
0x18006d8c8  lea     r13, WPP_GLOBAL_Control
0x18006d8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d8d6  cmp     rcx, r13
0x18006d8d9  jz      short loc_18006D8F1
0x18006d8db  test    dword ptr [rcx+1Ch], 200000h
0x18006d8e2  jnz     loc_18006DAC1
0x18006d8e8  cmp     rcx, r13
0x18006d8eb  jnz     loc_18006DAE2
0x18006d8f1  call    ?GetSid@CSecurity@@SAPEAXXZ; CSecurity::GetSid(void)
0x18006d8f6  mov     [rbp+var_10], rax
0x18006d8fa  test    rax, rax
0x18006d8fd  jnz     short loc_18006D976
0x18006d8ff  mov     rax, [rdi]
0x18006d902  mov     rbx, [rax+58h]
0x18006d906  call    cs:__imp_GetLastError
0x18006d90c  mov     [rsp+50h+var_28], 4Ch ; 'L'
0x18006d914  lea     rcx, aOnecoreAdminWm_55; "onecore\\admin\\wmi\\wmx\\config\\cbase"...
0x18006d91b  mov     [rsp+50h+var_30], rcx
0x18006d920  mov     r9d, eax
0x18006d923  lea     r8, aGetsid; "GetSid"
0x18006d92a  mov     edx, 4033C365h
0x18006d92f  mov     rcx, rdi
0x18006d932  mov     rax, rbx
0x18006d935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d93a  nop
0x18006d93b  xor     ebx, ebx
0x18006d93d  lea     rcx, [rbp+var_10]
0x18006d941  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18006d946  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d94d  cmp     rcx, r13
0x18006d950  jz      short loc_18006D95F
0x18006d952  test    dword ptr [rcx+1Ch], 200000h
0x18006d959  jnz     loc_18006DB32
0x18006d95f  mov     rax, rbx
0x18006d962  mov     rbx, [rsp+50h+arg_0]
0x18006d96a  add     rsp, 50h
0x18006d96e  pop     r15
0x18006d970  pop     r13
0x18006d972  pop     rdi
0x18006d973  pop     rsi
0x18006d974  pop     rbp
0x18006d975  retn
0x18006d976  mov     [rbp+StringSid], 0
0x18006d97e  lea     rdx, [rbp+StringSid]; StringSid
0x18006d982  mov     rcx, rax; Sid
0x18006d985  call    cs:__imp_ConvertSidToStringSidW
0x18006d98b  test    eax, eax
0x18006d98d  jz      loc_18006DB09
0x18006d993  lea     r15, ?s_mapLock@CClientConfigCache@@0VFastLock@@A; FastLock CClientConfigCache::s_mapLock
0x18006d99a  mov     [rbp+var_8], r15
0x18006d99e  mov     rcx, r15
0x18006d9a1  call    cs:__imp_RtlTryAcquireFastLockExclusive
0x18006d9a7  test    eax, eax
0x18006d9a9  jz      loc_18006DA89
0x18006d9af  lea     rdx, ?s_cacheMap@CClientConfigCache@@0V?$AutoRelease@VCConfigCacheMap@CBaseConfigCache@@@@A; AutoRelease<CBaseConfigCache::CConfigCacheMap> CClientConfigCache::s_cacheMap
0x18006d9b6  mov     rcx, rdi
0x18006d9b9  call    ?InitMap@CBaseConfigCache@@CAHPEAVIRequestContext@@AEAV?$AutoRelease@VCConfigCacheMap@CBaseConfigCache@@@@@Z; CBaseConfigCache::InitMap(IRequestContext *,AutoRelease<CBaseConfigCache::CConfigCacheMap> &)
0x18006d9be  test    eax, eax
0x18006d9c0  jz      loc_18006DA97
0x18006d9c6  mov     r8d, 2
0x18006d9cc  mov     rdx, [rbp+StringSid]
0x18006d9d0  mov     rcx, cs:?s_cacheMap@CClientConfigCache@@0V?$AutoRelease@VCConfigCacheMap@CBaseConfigCache@@@@A; AutoRelease<CBaseConfigCache::CConfigCacheMap> CClientConfigCache::s_cacheMap
0x18006d9d7  call    ?FindExisting@CBaseConfigCache@@CAPEAV1@PEAVCConfigCacheMap@1@PEBGW4ErrorLogging@@@Z; CBaseConfigCache::FindExisting(CBaseConfigCache::CConfigCacheMap *,ushort const *,ErrorLogging)
0x18006d9dc  mov     rbx, rax
0x18006d9df  mov     [rbp+arg_18], rax
0x18006d9e3  test    rax, rax
0x18006d9e6  jz      short loc_18006DA21
0x18006d9e8  mov     [rbp+arg_18], 0
0x18006d9f0  lea     rcx, [rbp+arg_18]
0x18006d9f4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18006d9f9  nop
0x18006d9fa  mov     rcx, r15
0x18006d9fd  call    cs:__imp_RtlReleaseFastLockExclusive
0x18006da03  nop
0x18006da04  mov     rcx, [rbp+StringSid]; hMem
0x18006da08  mov     [rbp+StringSid], 0
0x18006da10  test    rcx, rcx
0x18006da13  jz      short loc_18006DA1C
0x18006da15  call    cs:__imp_LocalFree
0x18006da1b  nop
0x18006da1c  jmp     loc_18006D93D
0x18006da21  mov     dword ptr [rsp+50h+var_30], esi
0x18006da25  mov     r9d, 2
0x18006da2b  lea     r8, ?AllocCache@CClientConfigCache@@CAPEAVCBaseConfigCache@@XZ; CClientConfigCache::AllocCache(void)
0x18006da32  mov     rdx, cs:?s_cacheMap@CClientConfigCache@@0V?$AutoRelease@VCConfigCacheMap@CBaseConfigCache@@@@A; AutoRelease<CBaseConfigCache::CConfigCacheMap> CClientConfigCache::s_cacheMap
0x18006da39  mov     rcx, rdi
0x18006da3c  call    ?CreateNew@CBaseConfigCache@@CAPEAV1@PEAVIRequestContext@@PEAVCConfigCacheMap@1@P6APEAV1@XZW4ErrorLogging@@H@Z; CBaseConfigCache::CreateNew(IRequestContext *,CBaseConfigCache::CConfigCacheMap *,CBaseConfigCache * (*)(void),ErrorLogging,int)
0x18006da41  mov     rbx, rax
0x18006da44  lea     rcx, [rbp+arg_18]
0x18006da48  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18006da4d  mov     [rbp+arg_18], rbx
0x18006da51  test    rbx, rbx
0x18006da54  jz      short loc_18006D9E8
0x18006da56  lea     r8, [rbp+StringSid]; struct AutoLocalFree *
0x18006da5a  mov     rdx, rdi; struct IRequestContext *
0x18006da5d  mov     rcx, rbx; this
0x18006da60  call    ?AddToMap@CBaseConfigCache@@AEAAHPEAVIRequestContext@@AEAVAutoLocalFree@@@Z; CBaseConfigCache::AddToMap(IRequestContext *,AutoLocalFree &)
0x18006da65  test    eax, eax
0x18006da67  jnz     loc_18006D9E8
0x18006da6d  mov     rcx, rbx; this
0x18006da70  call    ?Shutdown@CBaseConfigCache@@IEAAXXZ; CBaseConfigCache::Shutdown(void)
0x18006da75  xor     edx, edx
0x18006da77  lea     rcx, [rbp+arg_18]
0x18006da7b  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x18006da80  mov     rbx, [rbp+arg_18]
0x18006da84  jmp     loc_18006D9E8
0x18006da89  mov     rcx, r15
0x18006da8c  call    cs:__imp_RtlQueueAcquireFastLockExclusive
0x18006da92  jmp     loc_18006D9AF
0x18006da97  mov     rcx, r15
0x18006da9a  call    cs:__imp_RtlReleaseFastLockExclusive
0x18006daa0  nop
0x18006daa1  mov     rcx, [rbp+StringSid]; hMem
0x18006daa5  mov     [rbp+StringSid], 0
0x18006daad  test    rcx, rcx
0x18006dab0  jz      loc_18006D93B
0x18006dab6  call    cs:__imp_LocalFree
0x18006dabc  jmp     loc_18006D93B
0x18006dac1  mov     edx, 0Bh
0x18006dac6  lea     r8, WPP_1e1842acf310370d2787f779e68f4b62_Traceguids
0x18006dacd  mov     rcx, [rcx+10h]
0x18006dad1  call    WPP_SF_
0x18006dad6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dadd  jmp     loc_18006D8E8
0x18006dae2  test    dword ptr [rcx+1Ch], 200000h
0x18006dae9  jz      loc_18006D8F1
0x18006daef  mov     edx, 0Ch
0x18006daf4  lea     r8, WPP_8bd3cce8cb123278e51b7ba80b282f9d_Traceguids
0x18006dafb  mov     rcx, [rcx+10h]
0x18006daff  call    WPP_SF_
0x18006db04  jmp     loc_18006D8F1
0x18006db09  mov     rax, [rdi]
0x18006db0c  mov     rbx, [rax+48h]
0x18006db10  call    cs:__imp_GetLastError
0x18006db16  mov     edx, eax
0x18006db18  mov     rcx, rdi
0x18006db1b  mov     rax, rbx
0x18006db1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db23  nop
0x18006db24  lea     rcx, [rbp+StringSid]; void *
0x18006db28  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18006db2d  jmp     loc_18006D93B
0x18006db32  mov     edx, 0Ch
0x18006db37  mov     r9, rbx
0x18006db3a  lea     r8, WPP_1e1842acf310370d2787f779e68f4b62_Traceguids
0x18006db41  mov     rcx, [rcx+10h]
0x18006db45  call    WPP_SF_q
0x18006db4a  jmp     loc_18006D95F
```
