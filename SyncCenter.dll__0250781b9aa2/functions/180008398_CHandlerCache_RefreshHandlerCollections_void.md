# CHandlerCache::_RefreshHandlerCollections(void *)

- ea: `0x180008398`
- end: `0x18000857c`
- name: `?_RefreshHandlerCollections@CHandlerCache@@AEAAXPEAX@Z`
- size: `484`
- prototype: `void __fastcall(CHandlerCache *__hidden this, HANDLE hEvent)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002130`
- `0x180015ec0`

## callees

- `0x1800041d0`
- `0x180004a60`
- `0x180005d30`
- `0x180008398`
- `0x180008584`
- `0x180008688`
- `0x180009d1c`
- `0x18000a714`
- `0x180015790`
- `0x180051dd4`
- `0x180051e8c`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008550`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008550`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000848b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000848b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084ca`
- `ADVAPI32!RegEnumKeyW` at `0x1800084bb`
- `ADVAPI32!RegEnumKeyW` at `0x1800084bb`

## pseudocode

```c
void __fastcall CHandlerCache::_RefreshHandlerCollections(CHandlerCache *this, HANDLE hEvent)
{
  __int64 (__fastcall *v2)(__int64); // rax
  bool v4; // r15
  struct _DSA *v6; // rbx
  HKEY v7; // rcx
  DWORD v8; // esi
  DWORD i; // edx
  HDSA v10; // rbx
  int j; // esi
  int v12; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HDSA hdsa; // [rsp+38h] [rbp-C8h] BYREF
  GUID pclsid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = (__int64 (__fastcall *)(__int64))qword_180070208;
  hKey = 0;
  v4 = hEvent != 0;
  if ( qword_180070208 == -1 )
  {
    GetProcFromComCtl32(&qword_180070208, 320);
    v2 = (__int64 (__fastcall *)(__int64))qword_180070208;
  }
  if ( v2 )
  {
    hdsa = (HDSA)v2(16);
    v6 = hdsa;
    if ( hdsa )
    {
      if ( (int)StringCchPrintfW(
                  sz,
                  0x104u,
                  L"%ws\\%ws",
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr",
                  L"HandlerCollections") >= 0 )
        CSettingsBase::OpenKey(HKEY_LOCAL_MACHINE, sz, &hKey);
      v7 = hKey;
      if ( hKey )
      {
        v8 = 0;
        for ( i = 0; !RegEnumKeyW(v7, i, sz, 0x104u); i = v8 )
        {
          pclsid = 0;
          if ( !CLSIDFromString(sz, &pclsid) )
            DSA_InsertItem(v6, 0x7FFFFFFF, &pclsid);
          v7 = hKey;
          ++v8;
        }
        RegCloseKey(hKey);
      }
      _InterlockedExchange((volatile __int32 *)this + 24, 0);
      _InterlockedIncrement((volatile signed __int32 *)this + 99);
      CHandlerCache::_MarkHandlerCollectionsToBePurged((LPCRITICAL_SECTION)this, &hdsa);
      v10 = hdsa;
      for ( j = 0; ; ++j )
      {
        v12 = v10 ? *(_DWORD *)v10 : 0;
        if ( j >= v12 )
          break;
        pclsid = 0;
        if ( DSA_GetItem(v10, j, &pclsid) )
          CHandlerCache::_RefreshHandlerCollection((LPCRITICAL_SECTION)this, &pclsid, v4);
      }
      CDSA_Base<unsigned short [64]>::Destroy(&hdsa);
      CHandlerCache::Release(this);
      CHandlerCache::_UpdateAggregateStatus(this);
    }
  }
  if ( hEvent )
    SetEvent(hEvent);
}

```

## disassembly

```asm
0x180008398  mov     [rsp-8+arg_10], rbx
0x18000839d  push    rbp
0x18000839e  push    rsi
0x18000839f  push    rdi
0x1800083a0  push    r14
0x1800083a2  push    r15
0x1800083a4  lea     rbp, [rsp-170h]
0x1800083ac  sub     rsp, 270h
0x1800083b3  mov     rax, cs:__security_cookie
0x1800083ba  xor     rax, rsp
0x1800083bd  mov     [rbp+190h+var_30], rax
0x1800083c4  mov     rax, cs:qword_180070208
0x1800083cb  test    rdx, rdx
0x1800083ce  mov     r14, rdx
0x1800083d1  mov     [rsp+290h+hKey], 0
0x1800083da  setnz   r15b
0x1800083de  mov     rdi, rcx
0x1800083e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800083e5  jnz     short loc_1800083FF
0x1800083e7  mov     edx, 140h
0x1800083ec  lea     rcx, qword_180070208
0x1800083f3  call    _GetProcFromComCtl32
0x1800083f8  mov     rax, cs:qword_180070208
0x1800083ff  test    rax, rax
0x180008402  jz      loc_180008548
0x180008408  mov     edx, 8
0x18000840d  lea     ecx, [rdx+8]
0x180008410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008415  mov     [rsp+290h+hdsa], rax
0x18000841a  mov     rbx, rax
0x18000841d  test    rax, rax
0x180008420  jz      loc_180008548
0x180008426  lea     rax, ?s_szHandlerCollections_regkey@CSettingsBase@@1QBGB; "HandlerCollections"
0x18000842d  mov     edx, 104h; unsigned __int64
0x180008432  lea     r9, ?s_szToplevel_regkey@CSettingsBase@@1QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008439  mov     [rsp+290h+var_270], rax
0x18000843e  lea     r8, aWsWs; "%ws\\%ws"
0x180008445  lea     rcx, [rsp+290h+sz]; unsigned __int16 *
0x18000844a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000844f  test    eax, eax
0x180008451  js      short loc_180008469
0x180008453  lea     r8, [rsp+290h+hKey]; HKEY *
0x180008458  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18000845f  lea     rdx, [rsp+290h+sz]; unsigned __int16 *
0x180008464  call    ?OpenKey@CSettingsBase@@KAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSettingsBase::OpenKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180008469  mov     rcx, [rsp+290h+hKey]
0x18000846e  test    rcx, rcx
0x180008471  jz      short loc_1800084D0
0x180008473  xor     esi, esi
0x180008475  xor     edx, edx
0x180008477  jmp     short loc_1800084B0
0x180008479  xorps   xmm0, xmm0
0x18000847c  lea     rdx, [rsp+290h+pclsid]; pclsid
0x180008481  lea     rcx, [rsp+290h+sz]; lpsz
0x180008486  movups  xmmword ptr [rsp+290h+pclsid.Data1], xmm0
0x18000848b  call    cs:__imp_CLSIDFromString
0x180008491  test    eax, eax
0x180008493  jnz     short loc_1800084A7
0x180008495  lea     r8, [rsp+290h+pclsid]; pitem
0x18000849a  mov     edx, 7FFFFFFFh; i
0x18000849f  mov     rcx, rbx; hdsa
0x1800084a2  call    DSA_InsertItem
0x1800084a7  mov     rcx, [rsp+290h+hKey]; hKey
0x1800084ac  inc     esi
0x1800084ae  mov     edx, esi; dwIndex
0x1800084b0  mov     r9d, 104h; cchName
0x1800084b6  lea     r8, [rsp+290h+sz]; lpName
0x1800084bb  call    cs:__imp_RegEnumKeyW
0x1800084c1  test    eax, eax
0x1800084c3  jz      short loc_180008479
0x1800084c5  mov     rcx, [rsp+290h+hKey]; hKey
0x1800084ca  call    cs:__imp_RegCloseKey
0x1800084d0  xor     eax, eax
0x1800084d2  xchg    eax, [rdi+60h]
0x1800084d5  lock inc dword ptr [rdi+18Ch]
0x1800084dc  lea     rdx, [rsp+290h+hdsa]
0x1800084e1  mov     rcx, rdi; lpCriticalSection
0x1800084e4  call    ?_MarkHandlerCollectionsToBePurged@CHandlerCache@@AEAAXAEBV?$CDSA@U_GUID@@@@@Z; CHandlerCache::_MarkHandlerCollectionsToBePurged(CDSA<_GUID> const &)
0x1800084e9  mov     rbx, [rsp+290h+hdsa]
0x1800084ee  xor     esi, esi
0x1800084f0  test    rbx, rbx
0x1800084f3  jz      short loc_1800084F9
0x1800084f5  mov     eax, [rbx]
0x1800084f7  jmp     short loc_1800084FB
0x1800084f9  xor     eax, eax
0x1800084fb  cmp     esi, eax
0x1800084fd  jge     short loc_18000852E
0x1800084ff  xorps   xmm0, xmm0
0x180008502  lea     r8, [rsp+290h+pclsid]; pitem
0x180008507  mov     edx, esi; i
0x180008509  mov     rcx, rbx; hdsa
0x18000850c  movups  xmmword ptr [rsp+290h+pclsid.Data1], xmm0
0x180008511  call    DSA_GetItem
0x180008516  test    eax, eax
0x180008518  jz      short loc_18000852A
0x18000851a  mov     r8b, r15b; bool
0x18000851d  lea     rdx, [rsp+290h+pclsid]; struct _GUID *
0x180008522  mov     rcx, rdi; lpCriticalSection
0x180008525  call    ?_RefreshHandlerCollection@CHandlerCache@@AEAAJAEBU_GUID@@_N@Z; CHandlerCache::_RefreshHandlerCollection(_GUID const &,bool)
0x18000852a  inc     esi
0x18000852c  jmp     short loc_1800084F0
0x18000852e  lea     rcx, [rsp+290h+hdsa]
0x180008533  call    ?Destroy@?$CDSA_Base@$$BY0EA@G@@QEAAHXZ; CDSA_Base<ushort [64]>::Destroy(void)
0x180008538  mov     rcx, rdi; this
0x18000853b  call    ?Release@CHandlerCache@@QEAAJXZ; CHandlerCache::Release(void)
0x180008540  mov     rcx, rdi; this
0x180008543  call    ?_UpdateAggregateStatus@CHandlerCache@@AEAAXXZ; CHandlerCache::_UpdateAggregateStatus(void)
0x180008548  test    r14, r14
0x18000854b  jz      short loc_180008556
0x18000854d  mov     rcx, r14; hEvent
0x180008550  call    cs:__imp_SetEvent
0x180008556  mov     rcx, [rbp+190h+var_30]
0x18000855d  xor     rcx, rsp; StackCookie
0x180008560  call    __security_check_cookie
0x180008565  mov     rbx, [rsp+290h+arg_10]
0x18000856d  add     rsp, 270h
0x180008574  pop     r15
0x180008576  pop     r14
0x180008578  pop     rdi
0x180008579  pop     rsi
0x18000857a  pop     rbp
0x18000857b  retn
```
