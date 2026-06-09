# CBaseConfigCache::GetConfigCache(IRequestContext *,ErrorLogging,CBaseConfigCache * (*)(void),FastLock *,AutoRelease<CBaseConfigCache::CConfigCacheMap> &,int)

- ea: `0x18006d680`
- end: `0x18006d8a9`
- name: `?GetConfigCache@CBaseConfigCache@@KAPEAV1@PEAVIRequestContext@@W4ErrorLogging@@P6APEAV1@XZPEAVFastLock@@AEAV?$AutoRelease@VCConfigCacheMap@CBaseConfigCache@@@@H@Z`
- size: `553`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800fa490`
- `0x1801a1300`

## callees

- `0x180008920`
- `0x18000fc50`
- `0x180010030`
- `0x180064250`
- `0x18006b0f0`
- `0x18006bdf0`
- `0x18006c1a0`
- `0x18006d680`
- `0x18006e2c0`
- `0x1800c12b0`
- `0x1800da140`
- `0x180112380`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d886`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006d7aa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006d84b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006d7aa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006d84b`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18006d73d`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18006d73d`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18006d825`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18006d825`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006d792`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006d833`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006d792`
- `miutils!RtlReleaseFastLockExclusive` at `0x18006d833`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006d728`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006d728`

## string_xrefs

- `0x18006d6d8`: `onecore\admin\wmi\wmx\config\cbaseconfigcache.cpp`
- `0x18006d6e7`: `GetSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CBaseConfigCache *__fastcall CBaseConfigCache::GetConfigCache(
        struct IRequestContext *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        int a6)
{
  void *Sid; // rax
  void (__fastcall *v11)(struct IRequestContext *, __int64, const wchar_t *, _QWORD, const wchar_t *, int); // rbx
  DWORD LastError; // eax
  CBaseConfigCache *Existing; // rbx
  LPWSTR v15; // rcx
  LPWSTR v16; // rcx
  void (__fastcall *v17)(struct IRequestContext *, _QWORD); // rbx
  DWORD v18; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-20h] BYREF
  CBaseConfigCache *v20; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_8bd3cce8cb123278e51b7ba80b282f9d_Traceguids);
  Sid = CSecurity::GetSid();
  v21[0] = Sid;
  if ( !Sid )
  {
    v11 = *(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD, const wchar_t *, int))(*(_QWORD *)a1 + 88LL);
    LastError = GetLastError();
    v11(a1, 1077134181, L"GetSid", LastError, L"onecore\\admin\\wmi\\wmx\\config\\cbaseconfigcache.cpp", 76);
LABEL_4:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(v21);
    return 0;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v17 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL);
    v18 = GetLastError();
    v17(a1, v18);
    AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>((void **)&StringSid);
    goto LABEL_4;
  }
  v21[1] = a4;
  if ( !(unsigned int)RtlTryAcquireFastLockExclusive(a4) )
    RtlQueueAcquireFastLockExclusive(a4);
  if ( (unsigned int)CBaseConfigCache::InitMap(a1, a5) )
  {
    Existing = (CBaseConfigCache *)CBaseConfigCache::FindExisting(*a5, StringSid, a2);
    v20 = Existing;
    if ( !Existing )
    {
      Existing = (CBaseConfigCache *)CBaseConfigCache::CreateNew(a1, *a5, a3, a2, a6);
      AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
      v20 = Existing;
      if ( Existing )
      {
        if ( !CBaseConfigCache::AddToMap(Existing, a1, (struct AutoLocalFree *)&StringSid) )
        {
          CBaseConfigCache::Shutdown(Existing);
          AutoRelease<CServiceConfigCache>::operator=(&v20, 0);
          Existing = v20;
        }
      }
    }
    v20 = 0;
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v20);
    RtlReleaseFastLockExclusive(a4);
    v15 = StringSid;
    StringSid = 0;
    if ( v15 )
      LocalFree(v15);
  }
  else
  {
    RtlReleaseFastLockExclusive(a4);
    v16 = StringSid;
    StringSid = 0;
    if ( v16 )
      LocalFree(v16);
    Existing = 0;
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(v21);
  return Existing;
}

```

## disassembly

```asm
0x18006d680  push    rbp
0x18006d682  push    rbx
0x18006d683  push    rsi
0x18006d684  push    rdi
0x18006d685  push    r12
0x18006d687  push    r14
0x18006d689  push    r15
0x18006d68b  mov     rbp, rsp
0x18006d68e  sub     rsp, 60h
0x18006d692  mov     rdi, r9
0x18006d695  mov     r12, r8
0x18006d698  mov     r15d, edx
0x18006d69b  mov     rsi, rcx
0x18006d69e  lea     rax, WPP_GLOBAL_Control
0x18006d6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d6ac  cmp     rcx, rax
0x18006d6af  jnz     loc_18006D858
0x18006d6b5  call    ?GetSid@CSecurity@@SAPEAXXZ; CSecurity::GetSid(void)
0x18006d6ba  mov     [rbp+var_10], rax
0x18006d6be  test    rax, rax
0x18006d6c1  jnz     short loc_18006D719
0x18006d6c3  mov     rax, [rsi]
0x18006d6c6  mov     rbx, [rax+58h]
0x18006d6ca  call    cs:__imp_GetLastError
0x18006d6d0  mov     [rsp+60h+var_38], 4Ch ; 'L'
0x18006d6d8  lea     rcx, aOnecoreAdminWm_55; "onecore\\admin\\wmi\\wmx\\config\\cbase"...
0x18006d6df  mov     [rsp+60h+var_40], rcx
0x18006d6e4  mov     r9d, eax
0x18006d6e7  lea     r8, aGetsid; "GetSid"
0x18006d6ee  mov     edx, 4033C365h
0x18006d6f3  mov     rcx, rsi
0x18006d6f6  mov     rax, rbx
0x18006d6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6fe  nop
0x18006d6ff  lea     rcx, [rbp+var_10]
0x18006d703  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18006d708  xor     eax, eax
0x18006d70a  add     rsp, 60h
0x18006d70e  pop     r15
0x18006d710  pop     r14
0x18006d712  pop     r12
0x18006d714  pop     rdi
0x18006d715  pop     rsi
0x18006d716  pop     rbx
0x18006d717  pop     rbp
0x18006d718  retn
0x18006d719  mov     [rbp+StringSid], 0
0x18006d721  lea     rdx, [rbp+StringSid]; StringSid
0x18006d725  mov     rcx, rax; Sid
0x18006d728  call    cs:__imp_ConvertSidToStringSidW
0x18006d72e  test    eax, eax
0x18006d730  jz      loc_18006D87F
0x18006d736  mov     [rbp+var_8], rdi
0x18006d73a  mov     rcx, rdi
0x18006d73d  call    cs:__imp_RtlTryAcquireFastLockExclusive
0x18006d743  test    eax, eax
0x18006d745  jz      loc_18006D822
0x18006d74b  mov     r14, [rbp+arg_20]
0x18006d74f  mov     rdx, r14
0x18006d752  mov     rcx, rsi
0x18006d755  call    ?InitMap@CBaseConfigCache@@CAHPEAVIRequestContext@@AEAV?$AutoRelease@VCConfigCacheMap@CBaseConfigCache@@@@@Z; CBaseConfigCache::InitMap(IRequestContext *,AutoRelease<CBaseConfigCache::CConfigCacheMap> &)
0x18006d75a  test    eax, eax
0x18006d75c  jz      loc_18006D830
0x18006d762  mov     r8d, r15d
0x18006d765  mov     rdx, [rbp+StringSid]
0x18006d769  mov     rcx, [r14]
0x18006d76c  call    ?FindExisting@CBaseConfigCache@@CAPEAV1@PEAVCConfigCacheMap@1@PEBGW4ErrorLogging@@@Z; CBaseConfigCache::FindExisting(CBaseConfigCache::CConfigCacheMap *,ushort const *,ErrorLogging)
0x18006d771  mov     rbx, rax
0x18006d774  mov     [rbp+var_18], rax
0x18006d778  test    rax, rax
0x18006d77b  jz      short loc_18006D7C2
0x18006d77d  mov     [rbp+var_18], 0
0x18006d785  lea     rcx, [rbp+var_18]
0x18006d789  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18006d78e  nop
0x18006d78f  mov     rcx, rdi
0x18006d792  call    cs:__imp_RtlReleaseFastLockExclusive
0x18006d798  nop
0x18006d799  mov     rcx, [rbp+StringSid]; hMem
0x18006d79d  mov     [rbp+StringSid], 0
0x18006d7a5  test    rcx, rcx
0x18006d7a8  jz      short loc_18006D7B1
0x18006d7aa  call    cs:__imp_LocalFree
0x18006d7b0  nop
0x18006d7b1  lea     rcx, [rbp+var_10]
0x18006d7b5  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18006d7ba  mov     rax, rbx
0x18006d7bd  jmp     loc_18006D70A
0x18006d7c2  mov     eax, [rbp+arg_28]
0x18006d7c5  mov     dword ptr [rsp+60h+var_40], eax
0x18006d7c9  mov     r9d, r15d
0x18006d7cc  mov     r8, r12
0x18006d7cf  mov     rdx, [r14]
0x18006d7d2  mov     rcx, rsi
0x18006d7d5  call    ?CreateNew@CBaseConfigCache@@CAPEAV1@PEAVIRequestContext@@PEAVCConfigCacheMap@1@P6APEAV1@XZW4ErrorLogging@@H@Z; CBaseConfigCache::CreateNew(IRequestContext *,CBaseConfigCache::CConfigCacheMap *,CBaseConfigCache * (*)(void),ErrorLogging,int)
0x18006d7da  mov     rbx, rax
0x18006d7dd  lea     rcx, [rbp+var_18]
0x18006d7e1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18006d7e6  mov     [rbp+var_18], rbx
0x18006d7ea  test    rbx, rbx
0x18006d7ed  jz      short loc_18006D77D
0x18006d7ef  lea     r8, [rbp+StringSid]; struct AutoLocalFree *
0x18006d7f3  mov     rdx, rsi; struct IRequestContext *
0x18006d7f6  mov     rcx, rbx; this
0x18006d7f9  call    ?AddToMap@CBaseConfigCache@@AEAAHPEAVIRequestContext@@AEAVAutoLocalFree@@@Z; CBaseConfigCache::AddToMap(IRequestContext *,AutoLocalFree &)
0x18006d7fe  test    eax, eax
0x18006d800  jnz     loc_18006D77D
0x18006d806  mov     rcx, rbx; this
0x18006d809  call    ?Shutdown@CBaseConfigCache@@IEAAXXZ; CBaseConfigCache::Shutdown(void)
0x18006d80e  xor     edx, edx
0x18006d810  lea     rcx, [rbp+var_18]
0x18006d814  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x18006d819  mov     rbx, [rbp+var_18]
0x18006d81d  jmp     loc_18006D77D
0x18006d822  mov     rcx, rdi
0x18006d825  call    cs:__imp_RtlQueueAcquireFastLockExclusive
0x18006d82b  jmp     loc_18006D74B
0x18006d830  mov     rcx, rdi
0x18006d833  call    cs:__imp_RtlReleaseFastLockExclusive
0x18006d839  nop
0x18006d83a  mov     rcx, [rbp+StringSid]; hMem
0x18006d83e  mov     [rbp+StringSid], 0
0x18006d846  test    rcx, rcx
0x18006d849  jz      short loc_18006D851
0x18006d84b  call    cs:__imp_LocalFree
0x18006d851  xor     ebx, ebx
0x18006d853  jmp     loc_18006D7B1
0x18006d858  test    dword ptr [rcx+1Ch], 200000h
0x18006d85f  jz      loc_18006D6B5
0x18006d865  mov     edx, 0Ch
0x18006d86a  lea     r8, WPP_8bd3cce8cb123278e51b7ba80b282f9d_Traceguids
0x18006d871  mov     rcx, [rcx+10h]
0x18006d875  call    WPP_SF_
0x18006d87a  jmp     loc_18006D6B5
0x18006d87f  mov     rax, [rsi]
0x18006d882  mov     rbx, [rax+48h]
0x18006d886  call    cs:__imp_GetLastError
0x18006d88c  mov     edx, eax
0x18006d88e  mov     rcx, rsi
0x18006d891  mov     rax, rbx
0x18006d894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d899  nop
0x18006d89a  lea     rcx, [rbp+StringSid]; void *
0x18006d89e  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18006d8a3  jmp     loc_18006D6FF
```
