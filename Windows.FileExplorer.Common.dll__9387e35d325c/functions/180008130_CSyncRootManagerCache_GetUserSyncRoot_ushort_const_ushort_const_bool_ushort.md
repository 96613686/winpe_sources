# CSyncRootManagerCache::GetUserSyncRoot(ushort const *,ushort const *,bool,ushort * *)

- ea: `0x180008130`
- end: `0x1800083dd`
- name: `?GetUserSyncRoot@CSyncRootManagerCache@@QEAAJPEBG0_NPEAPEAG@Z`
- size: `685`
- prototype: `int(CSyncRootManagerCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800080e0`
- `0x180064980`

## callees

- `0x180007080`
- `0x1800077c8`
- `0x180008130`
- `0x180009374`
- `0x1800095fc`
- `0x18000bb60`
- `0x180024198`

## import_xrefs

- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18000815c`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18000815c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008359`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008378`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008359`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008378`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800083b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000818c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000818c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800081c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800081c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800081ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008257`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008257`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000827b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000834f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000836e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000827b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000834f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000836e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083a8`

## string_xrefs

- `0x180008316`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180008335`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18000838f`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncRootManagerCache::GetUserSyncRoot(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        bool a4,
        unsigned __int16 **a5)
{
  RTL_SRWLOCK *v7; // rdi
  int v8; // ebx
  RTL_SRWLOCK *v9; // rbx
  PSRWLOCK v10; // rdi
  bool v11; // r14
  char *v12; // r15
  unsigned __int16 **v13; // r13
  const WCHAR **v14; // rcx
  const WCHAR *v15; // rdx
  const WCHAR *v16; // rcx
  int UserSyncRoot; // eax
  unsigned int v19; // r14d
  int UserSid; // eax
  unsigned int v21; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-40h]
  int bIgnoreCasea; // [rsp+20h] [rbp-40h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v25[2]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  bool v27; // [rsp+A0h] [rbp+40h] BYREF
  LPCWCH lpString2; // [rsp+A8h] [rbp+48h]
  bool v29; // [rsp+B8h] [rbp+58h]

  v29 = a4;
  lpString2 = a2;
  if ( LODWORD(this[2].Ptr) == SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER)
    && (BYTE4(this[2].Ptr) & 1) != 0 )
  {
    v7 = this + 3;
  }
  else
  {
    memset(v25, 0, sizeof(v25));
    v7 = this + 3;
    SRWLock = this + 3;
    AcquireSRWLockExclusive(this + 3);
    v8 = CSyncRootManagerCache::_EnsureCachedValues(this, &SRWLock, HIDWORD(this[2].Ptr) | 1u);
    ReleaseSRWLockExclusive(SRWLock);
    CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>::~CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>(v25);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1105,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
      return (unsigned int)v8;
    }
  }
  AcquireSRWLockShared(v7);
  v9 = *(RTL_SRWLOCK **)winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>>::abi_guard::abi_guard(
                          &v27,
                          this);
  v10 = 0;
  SRWLock = 0;
  v25[0] = 0u;
  if ( !a3 )
  {
    *(_QWORD *)&v25[0] = -1;
    *((_QWORD *)&v25[0] + 1) = -1;
    UserSid = TestHook_GetUserSid(0, &SRWLock);
    v21 = UserSid;
    if ( UserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x110E,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)UserSid,
        bIgnoreCase);
      if ( SRWLock )
        LocalFree(SRWLock);
      ReleaseSRWLockShared(v9 + 3);
      return v21;
    }
    v10 = SRWLock;
    a3 = (const unsigned __int16 *)SRWLock;
  }
  v11 = 0;
  v27 = 0;
  v12 = 0;
  v13 = a5;
  while ( v12 < this[5].Ptr )
  {
    if ( v11 )
      goto LABEL_16;
    if ( lpString2 )
    {
      v14 = (const WCHAR **)*((_QWORD *)this[4].Ptr + (_QWORD)v12);
      v15 = v14[1];
      if ( v15 == (const WCHAR *)-1LL )
      {
        if ( *v14 )
        {
          do
            v15 = (const WCHAR *)((char *)v15 + 1);
          while ( (*v14)[(_QWORD)v15] );
          v16 = *v14;
LABEL_13:
          if ( CompareStringOrdinal(v16, (int)v15, lpString2, -1, 1) == 2 )
          {
            UserSyncRoot = CStorageProviderRootsCache::TryGetUserSyncRoot(
                             *((CStorageProviderRootsCache **)this[4].Ptr + (_QWORD)v12),
                             a3,
                             v29,
                             &v27,
                             v13);
            v19 = UserSyncRoot;
            if ( UserSyncRoot < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1117,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)UserSyncRoot,
                bIgnoreCasea);
              if ( v10 )
                LocalFree(v10);
              ReleaseSRWLockShared(v9 + 3);
              return v19;
            }
            v11 = v27;
          }
          goto LABEL_14;
        }
        LODWORD(v15) = 0;
      }
      else
      {
        v16 = *v14;
        if ( v16 )
          goto LABEL_13;
      }
      v16 = &String1;
      goto LABEL_13;
    }
LABEL_14:
    ++v12;
  }
  if ( v11 )
  {
LABEL_16:
    if ( v10 )
      LocalFree(v10);
    ReleaseSRWLockShared(v9 + 3);
    return 0;
  }
  if ( v10 )
    LocalFree(v10);
  ReleaseSRWLockShared(v9 + 3);
  return 2147943568LL;
}

```

## disassembly

```asm
0x180008130  mov     [rsp-38h+arg_10], rbx
0x180008135  mov     [rsp-38h+arg_18], r9b
0x18000813a  mov     [rsp-38h+lpString2], rdx
0x18000813f  push    rbp
0x180008140  push    rsi
0x180008141  push    rdi
0x180008142  push    r12
0x180008144  push    r13
0x180008146  push    r14
0x180008148  push    r15
0x18000814a  mov     rbp, rsp
0x18000814d  sub     rsp, 60h
0x180008151  mov     r12, r8
0x180008154  mov     rsi, rcx
0x180008157  mov     ecx, 39h ; '9'; id
0x18000815c  call    cs:__imp_SHGlobalCounterGetValue
0x180008162  cmp     [rsi+10h], eax
0x180008165  jnz     short loc_180008171
0x180008167  test    byte ptr [rsi+14h], 1
0x18000816b  jnz     loc_1800082D6
0x180008171  xorps   xmm0, xmm0
0x180008174  movdqu  [rbp+var_28], xmm0
0x180008179  xorps   xmm1, xmm1
0x18000817c  movdqu  [rbp+var_18], xmm1
0x180008181  lea     rdi, [rsi+18h]
0x180008185  mov     [rbp+SRWLock], rdi
0x180008189  mov     rcx, rdi; SRWLock
0x18000818c  call    cs:__imp_AcquireSRWLockExclusive
0x180008192  nop
0x180008193  mov     r8d, [rsi+14h]
0x180008197  or      r8d, 1
0x18000819b  lea     rdx, [rbp+SRWLock]
0x18000819f  mov     rcx, rsi
0x1800081a2  call    ?_EnsureCachedValues@CSyncRootManagerCache@@AEAAJAEAVLockCacheAndFreeStale@@W4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValues(LockCacheAndFreeStale &,SPGSP_FLAGS)
0x1800081a7  mov     ebx, eax
0x1800081a9  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800081ad  call    cs:__imp_ReleaseSRWLockExclusive
0x1800081b3  lea     rcx, [rbp+var_28]
0x1800081b7  call    ??1?$CSimplePointerArray@VCStorageProviderRootsCache@@VCTContainer_PolicyNewMem@@V?$CSimpleArrayStandardCompareHelper@PEAVCStorageProviderRootsCache@@@@@@QEAA@XZ; CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>::~CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>(void)
0x1800081bc  test    ebx, ebx
0x1800081be  js      loc_18000830F
0x1800081c4  mov     rcx, rdi; SRWLock
0x1800081c7  call    cs:__imp_AcquireSRWLockShared
0x1800081cd  mov     rdx, rsi
0x1800081d0  lea     rcx, [rbp+arg_0]
0x1800081d4  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$vector@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$allocator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@3@Ucollection_version@23@@winrt@@U?$IIterator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$vector_impl@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$vector@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$allocator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator &)
0x1800081d9  mov     rbx, [rax]
0x1800081dc  xor     r9d, r9d
0x1800081df  mov     edi, r9d
0x1800081e2  mov     [rbp+SRWLock], r9
0x1800081e6  mov     qword ptr [rbp+var_28], r9
0x1800081ea  mov     qword ptr [rbp+var_28+8], r9
0x1800081ee  test    r12, r12
0x1800081f1  jz      loc_1800082DF
0x1800081f7  mov     r14b, r9b
0x1800081fa  mov     [rbp+arg_0], r9b
0x1800081fe  mov     r15, r9
0x180008201  mov     r13, [rbp+arg_20]
0x180008205  cmp     r15, [rsi+28h]
0x180008209  jnb     short loc_18000826A
0x18000820b  test    r14b, r14b
0x18000820e  jnz     short loc_180008273
0x180008210  mov     r8, [rbp+lpString2]; lpString2
0x180008214  test    r8, r8
0x180008217  jz      short loc_180008265
0x180008219  mov     rax, [rsi+20h]
0x18000821d  mov     rcx, [rax+r15*8]
0x180008221  mov     rdx, [rcx+8]
0x180008225  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180008229  jnz     loc_1800083C0
0x18000822f  mov     rax, [rcx]
0x180008232  test    rax, rax
0x180008235  jz      loc_1800083D8
0x18000823b  or      rdx, rdx
0x18000823e  inc     rdx; cchCount1
0x180008241  cmp     [rax+rdx*2], r9w
0x180008246  jnz     short loc_18000823E
0x180008248  mov     rcx, rax; lpString1
0x18000824b  mov     [rsp+60h+bIgnoreCase], 1; bIgnoreCase
0x180008253  or      r9d, 0FFFFFFFFh; cchCount2
0x180008257  call    cs:__imp_CompareStringOrdinal
0x18000825d  cmp     eax, 2
0x180008260  jz      short loc_1800082A5
0x180008262  xor     r9d, r9d
0x180008265  inc     r15
0x180008268  jmp     short loc_180008205
0x18000826a  test    r14b, r14b
0x18000826d  jz      loc_180008366
0x180008273  test    rdi, rdi
0x180008276  jz      short loc_180008281
0x180008278  mov     rcx, rdi; hMem
0x18000827b  call    cs:__imp_LocalFree
0x180008281  lea     rcx, [rbx+18h]; SRWLock
0x180008285  call    cs:__imp_ReleaseSRWLockShared
0x18000828b  xor     eax, eax
0x18000828d  mov     rbx, [rsp+60h+arg_10]
0x180008295  add     rsp, 60h
0x180008299  pop     r15
0x18000829b  pop     r14
0x18000829d  pop     r13
0x18000829f  pop     r12
0x1800082a1  pop     rdi
0x1800082a2  pop     rsi
0x1800082a3  pop     rbp
0x1800082a4  retn
0x1800082a5  mov     rcx, [rsi+20h]
0x1800082a9  mov     qword ptr [rsp+60h+bIgnoreCase], r13; int
0x1800082ae  lea     r9, [rbp+arg_0]; bool *
0x1800082b2  mov     r8b, [rbp+arg_18]; bool
0x1800082b6  mov     rdx, r12; unsigned __int16 *
0x1800082b9  mov     rcx, [rcx+r15*8]; this
0x1800082bd  call    ?TryGetUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG_NAEA_NPEAPEAG@Z; CStorageProviderRootsCache::TryGetUserSyncRoot(ushort const *,bool,bool &,ushort * *)
0x1800082c2  mov     r14d, eax
0x1800082c5  xor     r9d, r9d
0x1800082c8  test    eax, eax
0x1800082ca  js      loc_180008388
0x1800082d0  mov     r14b, [rbp+arg_0]
0x1800082d4  jmp     short loc_180008265
0x1800082d6  lea     rdi, [rsi+18h]
0x1800082da  jmp     loc_1800081C4
0x1800082df  mov     qword ptr [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x1800082e7  mov     qword ptr [rbp+var_28+8], 0FFFFFFFFFFFFFFFFh
0x1800082ef  lea     rdx, [rbp+SRWLock]
0x1800082f3  xor     ecx, ecx
0x1800082f5  call    TestHook_GetUserSid
0x1800082fa  mov     edi, eax
0x1800082fc  xor     r9d, r9d
0x1800082ff  test    eax, eax
0x180008301  js      short loc_18000832E
0x180008303  mov     rdi, [rbp+SRWLock]
0x180008307  mov     r12, rdi
0x18000830a  jmp     loc_1800081F7
0x18000830f  mov     rcx, [rbp+38h]; this
0x180008313  mov     r9d, ebx; char *
0x180008316  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000831d  mov     edx, 1105h; void *
0x180008322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008327  mov     eax, ebx
0x180008329  jmp     loc_18000828D
0x18000832e  mov     rcx, [rbp+38h]; this
0x180008332  mov     r9d, edi; char *
0x180008335  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000833c  mov     edx, 110Eh; void *
0x180008341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008346  mov     rcx, [rbp+SRWLock]; hMem
0x18000834a  test    rcx, rcx
0x18000834d  jz      short loc_180008355
0x18000834f  call    cs:__imp_LocalFree
0x180008355  lea     rcx, [rbx+18h]; SRWLock
0x180008359  call    cs:__imp_ReleaseSRWLockShared
0x18000835f  mov     eax, edi
0x180008361  jmp     loc_18000828D
0x180008366  test    rdi, rdi
0x180008369  jz      short loc_180008374
0x18000836b  mov     rcx, rdi; hMem
0x18000836e  call    cs:__imp_LocalFree
0x180008374  lea     rcx, [rbx+18h]; SRWLock
0x180008378  call    cs:__imp_ReleaseSRWLockShared
0x18000837e  mov     eax, 80070490h
0x180008383  jmp     loc_18000828D
0x180008388  mov     rcx, [rbp+38h]; this
0x18000838c  mov     r9d, r14d; char *
0x18000838f  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180008396  mov     edx, 1117h; void *
0x18000839b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083a0  test    rdi, rdi
0x1800083a3  jz      short loc_1800083AE
0x1800083a5  mov     rcx, rdi; hMem
0x1800083a8  call    cs:__imp_LocalFree
0x1800083ae  lea     rcx, [rbx+18h]; SRWLock
0x1800083b2  call    cs:__imp_ReleaseSRWLockShared
0x1800083b8  mov     eax, r14d
0x1800083bb  jmp     loc_18000828D
0x1800083c0  mov     rcx, [rcx]
0x1800083c3  test    rcx, rcx
0x1800083c6  jnz     loc_18000824B
0x1800083cc  lea     rcx, String1
0x1800083d3  jmp     loc_18000824B
0x1800083d8  mov     rdx, r9
0x1800083db  jmp     short loc_1800083CC
```
