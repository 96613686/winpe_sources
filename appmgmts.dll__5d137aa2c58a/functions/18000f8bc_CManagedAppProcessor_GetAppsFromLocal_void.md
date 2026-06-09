# CManagedAppProcessor::GetAppsFromLocal(void)

- ea: `0x18000f8bc`
- end: `0x18000fdd8`
- name: `?GetAppsFromLocal@CManagedAppProcessor@@AEAAKXZ`
- size: `1308`
- prototype: `__int64 __fastcall(CManagedAppProcessor *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180011ac0`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180002024`
- `0x180004e30`
- `0x180004fc0`
- `0x18000a2cc`
- `0x18000a554`
- `0x18000e834`
- `0x18000f8bc`
- `0x180010ae8`
- `0x180013530`
- `0x18001b1a0`
- `0x18001bbe0`
- `0x18001c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fd32`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fdc2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fd32`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fdc2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f97e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f97e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fbb6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fbb6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000fcb4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000fcb4`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::GetAppsFromLocal(CManagedAppProcessor *this)
{
  int v2; // r13d
  DWORD OrderedLocalAppList; // r14d
  DWORD LastError; // eax
  unsigned int v5; // r12d
  __int64 v6; // rcx
  CAppInfo *v7; // rbx
  struct CAppInfo *v8; // rax
  CAppList *v9; // r10
  int v10; // eax
  DWORD AppInfo; // eax
  int v12; // esi
  CAppInfo *v13; // rax
  __int64 v14; // rsi
  char *v15; // r15
  int v16; // eax
  int *v18; // [rsp+20h] [rbp-E0h]
  int v19[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  CAppInfo *v24; // [rsp+78h] [rbp-88h]
  unsigned __int128 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  int v27; // [rsp+A0h] [rbp-60h]
  int v28; // [rsp+A4h] [rbp-5Ch]
  struct _GUID v29; // [rsp+B0h] [rbp-50h] BYREF
  CAppInfo *v30; // [rsp+C0h] [rbp-40h]
  _OWORD v31[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-18h]
  _BYTE v33[8]; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+F8h] [rbp-8h]

  v25 = 0;
  v24 = (CAppInfo *)&v23;
  v23 = (__int64)&v23;
  v20[1] = 0;
  v21 = 0;
  v22 = 0;
  v20[0] = &CAppList::`vftable';
  v26 = 0;
  v27 = -2147467259;
  v28 = 0;
  v2 = 0;
  v19[0] = 0;
  if ( *((_DWORD *)this + 99) == 1 )
  {
LABEL_72:
    CAppList::~CAppList((CAppList *)v20);
    return 0;
  }
  OrderedLocalAppList = CManagedAppProcessor::GetOrderedLocalAppList(this, (struct CAppList *)v20);
  if ( OrderedLocalAppList )
    goto LABEL_80;
  if ( *((_DWORD *)this + 99) == 1 || !*((_DWORD *)this + 74) || ImpersonateLoggedOnUser(*((HANDLE *)this + 33)) )
  {
    OrderedLocalAppList = 0;
  }
  else
  {
    if ( *(_DWORD *)&gDebugLevel )
    {
      LastError = GetLastError();
      _DebugMsg(2, 0xBC4u, LastError);
    }
    OrderedLocalAppList = GetLastError();
    if ( OrderedLocalAppList )
      goto LABEL_80;
  }
  v5 = 0;
  v6 = v25;
  v7 = v24;
  v25 = __PAIR128__(v25, (unsigned __int64)v24);
  if ( v24 == (CAppInfo *)&v23 )
    v7 = 0;
  if ( !v7 )
  {
LABEL_67:
    *(_QWORD *)&v25 = v6;
    if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
      RevertToSelf();
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBF2u, v5);
    goto LABEL_72;
  }
  while ( 1 )
  {
    v29 = *(struct _GUID *)((char *)v7 + 24);
    v8 = CAppList::Find((CManagedAppProcessor *)((char *)this + 136), &v29);
    if ( v8 )
      *((_DWORD *)v8 + 56) = 1024;
    v29 = *(struct _GUID *)((char *)v7 + 24);
    if ( !CAppList::Find(v9, &v29) )
      break;
    *(_QWORD *)&v25 = *(_QWORD *)(v25 + 8);
LABEL_64:
    v7 = (CAppInfo *)v25;
    if ( (__int64 *)v25 == &v23 || !(_QWORD)v25 )
    {
      v6 = *((_QWORD *)&v25 + 1);
      goto LABEL_67;
    }
  }
  v10 = *((_DWORD *)v7 + 56);
  if ( (v10 & 1) != 0 )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBD2u, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
  }
  else if ( (v10 & 2) != 0 )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBD3u, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
  }
  else if ( (v10 & 0x20) != 0 )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC14u, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
  }
  else if ( (v10 & 0x40) != 0 && *(_DWORD *)&gDebugLevel )
  {
    _DebugMsg(4, 0xC15u, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
  }
  *(_QWORD *)&v25 = *(_QWORD *)(v25 + 8);
  *(_QWORD *)(*(_QWORD *)v7 + 8LL) = *((_QWORD *)v7 + 1);
  **((_QWORD **)v7 + 1) = *(_QWORD *)v7;
  if ( *((_DWORD *)this + 75) )
  {
    if ( (*((_DWORD *)v7 + 56) & 0x202) != 0x202 )
      goto LABEL_54;
  }
  else if ( (*((_DWORD *)v7 + 56) & 0x103) == 0 )
  {
LABEL_54:
    ++v5;
    *((_QWORD *)this + 13) = *((_QWORD *)this + 12);
    v14 = *((_QWORD *)this + 11);
    v15 = (char *)this + 80;
    while ( 1 )
    {
      *((_QWORD *)this + 12) = v14;
      if ( (char *)v14 == v15 )
        v14 = 0;
      if ( !v14 )
        break;
      v16 = CGPOInfoList::Compare(
              (LPCWSTR *)this,
              *(const unsigned __int16 **)(v14 + 48),
              *((const unsigned __int16 **)v7 + 6));
      if ( v16 != -1
        && (v16 == 1 || CompareFileTime((const FILETIME *)(v14 + 172), (const FILETIME *)((char *)v7 + 172)) >= 0) )
      {
        *(_QWORD *)v7 = *(_QWORD *)v14;
        *((_QWORD *)v7 + 1) = v14;
        *(_QWORD *)(*(_QWORD *)v14 + 8LL) = v7;
        *(_QWORD *)v14 = v7;
        goto LABEL_64;
      }
      v14 = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL);
    }
    *((_QWORD *)v7 + 1) = v15;
    *(_QWORD *)v7 = *((_QWORD *)this + 10);
    *(_QWORD *)(*((_QWORD *)this + 10) + 8LL) = v7;
    *((_QWORD *)this + 10) = v7;
    goto LABEL_64;
  }
  memset(v31, 0, sizeof(v31));
  v32 = 0;
  memset_0(v33, 0, 0xD0u);
  LODWORD(v31[0]) = 6;
  *(_OWORD *)((char *)v31 + 8) = *(_OWORD *)((char *)v7 + 24);
  StringToGuid(*((wchar_t **)v7 + 6), (struct _GUID *)((char *)&v31[1] + 8));
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xC0Du, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
  AppInfo = CsGetAppInfo(v31, 0, v33);
  if ( !AppInfo )
  {
    v12 = *((_DWORD *)v7 + 78);
    if ( *(_DWORD *)&gDebugLevel )
    {
      LODWORD(v18) = v34;
      _DebugMsg(4, 0xBCFu, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9), v18);
    }
    CAppInfo::~CAppInfo(v7);
    operator delete(v7);
    v13 = (CAppInfo *)LocalAlloc(0, 0x1C8u);
    v30 = v13;
    if ( v13 )
    {
      v7 = CAppInfo::CAppInfo(v13, this, (struct tagPACKAGEDISPINFO *)v33, 0, v19);
      v2 = v19[0];
    }
    else
    {
      v7 = 0;
    }
    if ( v2 )
    {
      if ( v7 )
        goto LABEL_48;
    }
    else
    {
      if ( v7 )
      {
        CAppInfo::~CAppInfo(v7);
        operator delete(v7);
      }
      v7 = 0;
    }
    OrderedLocalAppList = 14;
LABEL_48:
    ReleasePackageInfo(v33);
    if ( v7 )
      *((_DWORD *)v7 + 78) = v12;
    goto LABEL_53;
  }
  if ( AppInfo == -2147221148 )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xBD5u, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
LABEL_53:
    if ( OrderedLocalAppList )
      goto LABEL_74;
    goto LABEL_54;
  }
  OrderedLocalAppList = AppInfo;
LABEL_74:
  if ( v7 && *(_DWORD *)&gDebugLevel )
  {
    LODWORD(v18) = OrderedLocalAppList;
    _DebugMsg(4, 0xC0Eu, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9), v18);
  }
  if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
    RevertToSelf();
LABEL_80:
  CAppList::~CAppList((CAppList *)v20);
  return OrderedLocalAppList;
}

```

## disassembly

```asm
0x18000f8bc  push    rbp
0x18000f8be  push    rbx
0x18000f8bf  push    rsi
0x18000f8c0  push    rdi
0x18000f8c1  push    r12
0x18000f8c3  push    r13
0x18000f8c5  push    r14
0x18000f8c7  push    r15
0x18000f8c9  lea     rbp, [rsp-0D8h]
0x18000f8d1  sub     rsp, 1D8h
0x18000f8d8  mov     rax, cs:__security_cookie
0x18000f8df  xor     rax, rsp
0x18000f8e2  mov     [rbp+110h+var_50], rax
0x18000f8e9  mov     rdi, rcx
0x18000f8ec  xorps   xmm0, xmm0
0x18000f8ef  movdqa  [rbp+110h+var_190], xmm0
0x18000f8f4  lea     rax, [rsp+210h+var_1A0]
0x18000f8f9  mov     [rsp+210h+var_198], rax
0x18000f8fe  lea     rax, [rsp+210h+var_1A0]
0x18000f903  mov     [rsp+210h+var_1A0], rax
0x18000f908  xor     r15d, r15d
0x18000f90b  mov     [rsp+210h+var_1C8], r15
0x18000f910  movdqa  [rsp+210h+var_1C0], xmm0
0x18000f916  xorps   xmm1, xmm1
0x18000f919  movdqa  [rsp+210h+var_1B0], xmm1
0x18000f91f  lea     rax, ??_7CAppList@@6B@; const CAppList::`vftable'
0x18000f926  mov     [rsp+210h+var_1D0], rax
0x18000f92b  movdqa  [rbp+110h+var_180], xmm0
0x18000f930  mov     [rbp+110h+var_170], 80004005h
0x18000f937  mov     [rbp+110h+var_16C], r15d
0x18000f93b  mov     r13d, r15d
0x18000f93e  mov     [rsp+210h+var_1E0], r15d
0x18000f943  cmp     dword ptr [rcx+18Ch], 1
0x18000f94a  jz      loc_18000FD54
0x18000f950  lea     rdx, [rsp+210h+var_1D0]; struct CAppList *
0x18000f955  call    ?GetOrderedLocalAppList@CManagedAppProcessor@@QEAAKAEAVCAppList@@@Z; CManagedAppProcessor::GetOrderedLocalAppList(CAppList &)
0x18000f95a  mov     r14d, eax
0x18000f95d  test    eax, eax
0x18000f95f  jnz     loc_18000FDC9
0x18000f965  cmp     dword ptr [rdi+18Ch], 1
0x18000f96c  jz      short loc_18000F9BA
0x18000f96e  cmp     [rdi+128h], r15d
0x18000f975  jz      short loc_18000F9BA
0x18000f977  mov     rcx, [rdi+108h]; hToken
0x18000f97e  call    cs:__imp_ImpersonateLoggedOnUser
0x18000f984  test    eax, eax
0x18000f986  jnz     short loc_18000F9BA
0x18000f988  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000f98f  jz      short loc_18000F9A8
0x18000f991  call    cs:__imp_GetLastError
0x18000f997  mov     r8d, eax
0x18000f99a  mov     edx, 0BC4h; unsigned int
0x18000f99f  lea     ecx, [r15+2]; unsigned int
0x18000f9a3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f9a8  call    cs:__imp_GetLastError
0x18000f9ae  mov     r14d, eax
0x18000f9b1  test    eax, eax
0x18000f9b3  jz      short loc_18000F9BD
0x18000f9b5  jmp     loc_18000FDC9
0x18000f9ba  mov     r14d, r15d
0x18000f9bd  mov     r12d, r15d
0x18000f9c0  mov     rcx, qword ptr [rbp+110h+var_190]
0x18000f9c4  mov     qword ptr [rbp+110h+var_190+8], rcx
0x18000f9c8  mov     rbx, [rsp+210h+var_198]
0x18000f9cd  mov     qword ptr [rbp+110h+var_190], rbx
0x18000f9d1  lea     rdx, [rsp+210h+var_1A0]
0x18000f9d6  cmp     rbx, rdx
0x18000f9d9  cmovz   rbx, r15
0x18000f9dd  test    rbx, rbx
0x18000f9e0  jz      loc_18000FD1C
0x18000f9e6  lea     r10, [rdi+20h]
0x18000f9ea  lea     rax, [rdi+88h]
0x18000f9f1  movups  xmm0, xmmword ptr [rbx+18h]
0x18000f9f5  movdqu  xmmword ptr [rbp+110h+var_160.Data1], xmm0
0x18000f9fa  lea     rdx, [rbp+110h+var_160]; struct _GUID
0x18000f9fe  mov     rcx, rax; this
0x18000fa01  call    ?Find@CAppList@@QEAAPEAVCAppInfo@@U_GUID@@@Z; CAppList::Find(_GUID)
0x18000fa06  test    rax, rax
0x18000fa09  jz      short loc_18000FA15
0x18000fa0b  mov     dword ptr [rax+0E0h], 400h
0x18000fa15  movups  xmm0, xmmword ptr [rbx+18h]
0x18000fa19  movdqu  xmmword ptr [rbp+110h+var_160.Data1], xmm0
0x18000fa1e  lea     rdx, [rbp+110h+var_160]; struct _GUID
0x18000fa22  mov     rcx, r10; this
0x18000fa25  call    ?Find@CAppList@@QEAAPEAVCAppInfo@@U_GUID@@@Z; CAppList::Find(_GUID)
0x18000fa2a  test    rax, rax
0x18000fa2d  jz      short loc_18000FA40
0x18000fa2f  mov     rax, qword ptr [rbp+110h+var_190]
0x18000fa33  mov     rcx, [rax+8]
0x18000fa37  mov     qword ptr [rbp+110h+var_190], rcx
0x18000fa3b  jmp     loc_18000FD01
0x18000fa40  mov     eax, [rbx+0E0h]
0x18000fa46  test    al, 1
0x18000fa48  jz      short loc_18000FA5A
0x18000fa4a  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fa51  jz      short loc_18000FAA6
0x18000fa53  mov     edx, 0BD2h
0x18000fa58  jmp     short loc_18000FA94
0x18000fa5a  test    al, 2
0x18000fa5c  jz      short loc_18000FA6E
0x18000fa5e  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fa65  jz      short loc_18000FAA6
0x18000fa67  mov     edx, 0BD3h
0x18000fa6c  jmp     short loc_18000FA94
0x18000fa6e  test    al, 20h
0x18000fa70  jz      short loc_18000FA82
0x18000fa72  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fa79  jz      short loc_18000FAA6
0x18000fa7b  mov     edx, 0C14h
0x18000fa80  jmp     short loc_18000FA94
0x18000fa82  test    al, 40h
0x18000fa84  jz      short loc_18000FAA6
0x18000fa86  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fa8d  jz      short loc_18000FAA6
0x18000fa8f  mov     edx, 0C15h; unsigned int
0x18000fa94  mov     r9, [rbx+48h]
0x18000fa98  mov     r8, [rbx+28h]
0x18000fa9c  mov     ecx, 4; unsigned int
0x18000faa1  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000faa6  mov     rax, qword ptr [rbp+110h+var_190]
0x18000faaa  mov     rcx, [rax+8]
0x18000faae  mov     qword ptr [rbp+110h+var_190], rcx
0x18000fab2  mov     rcx, [rbx]
0x18000fab5  mov     rax, [rbx+8]
0x18000fab9  mov     [rcx+8], rax
0x18000fabd  mov     rcx, [rbx+8]
0x18000fac1  mov     rax, [rbx]
0x18000fac4  mov     [rcx], rax
0x18000fac7  cmp     [rdi+12Ch], r15d
0x18000face  jnz     short loc_18000FAE1
0x18000fad0  test    dword ptr [rbx+0E0h], 103h
0x18000fada  jnz     short loc_18000FAF7
0x18000fadc  jmp     loc_18000FC67
0x18000fae1  mov     eax, [rbx+0E0h]
0x18000fae7  and     eax, 202h
0x18000faec  cmp     eax, 202h
0x18000faf1  jnz     loc_18000FC67
0x18000faf7  xorps   xmm0, xmm0
0x18000fafa  xor     eax, eax
0x18000fafc  movups  [rbp+110h+var_148], xmm0
0x18000fb00  movups  xmmword ptr [rbp+110h+var_138.Data1], xmm0
0x18000fb04  mov     [rbp+110h+var_128], rax
0x18000fb08  xor     edx, edx; Val
0x18000fb0a  mov     r8d, 0D0h; Size
0x18000fb10  lea     rcx, [rbp+110h+var_120]; void *
0x18000fb14  call    memset_0
0x18000fb19  mov     dword ptr [rbp+110h+var_148], 6
0x18000fb20  movups  xmm0, xmmword ptr [rbx+18h]
0x18000fb24  movdqu  [rbp+110h+var_148+8], xmm0
0x18000fb29  lea     rdx, [rbp+110h+var_138.Data4]; struct _GUID *
0x18000fb2d  mov     rcx, [rbx+30h]; String
0x18000fb31  call    ?StringToGuid@@YAXPEAGPEAU_GUID@@@Z; StringToGuid(ushort *,_GUID *)
0x18000fb36  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fb3d  jz      short loc_18000FB56
0x18000fb3f  mov     r9, [rbx+48h]
0x18000fb43  mov     r8, [rbx+28h]
0x18000fb47  mov     edx, 0C0Dh; unsigned int
0x18000fb4c  mov     ecx, 4; unsigned int
0x18000fb51  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000fb56  lea     r8, [rbp+110h+var_120]
0x18000fb5a  xor     edx, edx
0x18000fb5c  lea     rcx, [rbp+110h+var_148]
0x18000fb60  call    CsGetAppInfo
0x18000fb65  test    eax, eax
0x18000fb67  jnz     loc_18000FC33
0x18000fb6d  mov     esi, [rbx+138h]
0x18000fb73  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fb7a  jz      short loc_18000FB9A
0x18000fb7c  mov     eax, [rbp+110h+var_118]
0x18000fb7f  mov     dword ptr [rsp+210h+var_1F0], eax
0x18000fb83  mov     r9, [rbx+48h]
0x18000fb87  mov     r8, [rbx+28h]
0x18000fb8b  mov     edx, 0BCFh; unsigned int
0x18000fb90  mov     ecx, 4; unsigned int
0x18000fb95  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000fb9a  mov     rcx, rbx; this
0x18000fb9d  call    ??1CAppInfo@@QEAA@XZ; CAppInfo::~CAppInfo(void)
0x18000fba2  mov     edx, 1C8h; unsigned __int64
0x18000fba7  mov     rcx, rbx; void *
0x18000fbaa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fbaf  mov     edx, 1C8h; uBytes
0x18000fbb4  xor     ecx, ecx; uFlags
0x18000fbb6  call    cs:__imp_LocalAlloc
0x18000fbbc  mov     [rbp+110h+var_150], rax
0x18000fbc0  test    rax, rax
0x18000fbc3  jz      short loc_18000FBEB
0x18000fbc5  lea     rcx, [rsp+210h+var_1E0]
0x18000fbca  mov     [rsp+210h+var_1F0], rcx; int *
0x18000fbcf  xor     r9d, r9d; int
0x18000fbd2  lea     r8, [rbp+110h+var_120]; struct tagPACKAGEDISPINFO *
0x18000fbd6  mov     rdx, rdi; struct CManagedAppProcessor *
0x18000fbd9  mov     rcx, rax; this
0x18000fbdc  call    ??0CAppInfo@@QEAA@PEAVCManagedAppProcessor@@PEAUtagPACKAGEDISPINFO@@HAEAH@Z; CAppInfo::CAppInfo(CManagedAppProcessor *,tagPACKAGEDISPINFO *,int,int &)
0x18000fbe1  mov     rbx, rax
0x18000fbe4  mov     r13d, [rsp+210h+var_1E0]
0x18000fbe9  jmp     short loc_18000FBEE
0x18000fbeb  mov     rbx, r15
0x18000fbee  test    r13d, r13d
0x18000fbf1  jnz     short loc_18000FC12
0x18000fbf3  test    rbx, rbx
0x18000fbf6  jz      short loc_18000FC0D
0x18000fbf8  mov     rcx, rbx; this
0x18000fbfb  call    ??1CAppInfo@@QEAA@XZ; CAppInfo::~CAppInfo(void)
0x18000fc00  mov     edx, 1C8h; unsigned __int64
0x18000fc05  mov     rcx, rbx; void *
0x18000fc08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc0d  mov     rbx, r15
0x18000fc10  jmp     short loc_18000FC17
0x18000fc12  test    rbx, rbx
0x18000fc15  jnz     short loc_18000FC1D
0x18000fc17  mov     r14d, 0Eh
0x18000fc1d  lea     rcx, [rbp+110h+var_120]; void *
0x18000fc21  call    ReleasePackageInfo
0x18000fc26  test    rbx, rbx
0x18000fc29  jz      short loc_18000FC5E
0x18000fc2b  mov     [rbx+138h], esi
0x18000fc31  jmp     short loc_18000FC5E
0x18000fc33  cmp     eax, 80040164h
0x18000fc38  jnz     loc_18000FD83
0x18000fc3e  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fc45  jz      short loc_18000FC5E
0x18000fc47  mov     r9, [rbx+48h]
0x18000fc4b  mov     r8, [rbx+28h]
0x18000fc4f  mov     edx, 0BD5h; unsigned int
0x18000fc54  mov     ecx, 4; unsigned int
0x18000fc59  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000fc5e  test    r14d, r14d
0x18000fc61  jnz     loc_18000FD86
0x18000fc67  inc     r12d
0x18000fc6a  mov     rax, [rdi+60h]
0x18000fc6e  mov     [rdi+68h], rax
0x18000fc72  mov     rsi, [rdi+58h]
0x18000fc76  lea     r15, [rdi+50h]
0x18000fc7a  mov     [rdi+60h], rsi
0x18000fc7e  xor     eax, eax
0x18000fc80  cmp     rsi, r15
0x18000fc83  cmovz   rsi, rax
0x18000fc87  test    rsi, rsi
0x18000fc8a  jz      short loc_18000FCCD
0x18000fc8c  mov     r8, [rbx+30h]; unsigned __int16 *
0x18000fc90  mov     rdx, [rsi+30h]; unsigned __int16 *
0x18000fc94  mov     rcx, rdi; this
0x18000fc97  call    ?Compare@CGPOInfoList@@QEAAHPEBG0@Z; CGPOInfoList::Compare(ushort const *,ushort const *)
0x18000fc9c  cmp     eax, 0FFFFFFFFh
0x18000fc9f  jz      short loc_18000FCBE
0x18000fca1  cmp     eax, 1
0x18000fca4  jz      short loc_18000FCC8
0x18000fca6  lea     rdx, [rbx+0ACh]; lpFileTime2
0x18000fcad  lea     rcx, [rsi+0ACh]; lpFileTime1
0x18000fcb4  call    cs:__imp_CompareFileTime
0x18000fcba  test    eax, eax
0x18000fcbc  jns     short loc_18000FCC8
0x18000fcbe  mov     rax, [rdi+60h]
0x18000fcc2  mov     rsi, [rax+8]
0x18000fcc6  jmp     short loc_18000FC7A
0x18000fcc8  test    rsi, rsi
0x18000fccb  jnz     short loc_18000FCE6
0x18000fccd  mov     [rbx+8], r15
0x18000fcd1  mov     rax, [rdi+50h]
0x18000fcd5  mov     [rbx], rax
0x18000fcd8  mov     rax, [rdi+50h]
0x18000fcdc  mov     [rax+8], rbx
0x18000fce0  mov     [rdi+50h], rbx
0x18000fce4  jmp     short loc_18000FCFA
0x18000fce6  mov     rax, [rsi]
0x18000fce9  mov     [rbx], rax
0x18000fcec  mov     [rbx+8], rsi
0x18000fcf0  mov     rax, [rsi]
0x18000fcf3  mov     [rax+8], rbx
0x18000fcf7  mov     [rsi], rbx
0x18000fcfa  xor     r15d, r15d
0x18000fcfd  lea     r10, [rdi+20h]
0x18000fd01  mov     rbx, qword ptr [rbp+110h+var_190]
0x18000fd05  lea     rax, [rsp+210h+var_1A0]
0x18000fd0a  cmp     rbx, rax
0x18000fd0d  jz      short loc_18000FD18
0x18000fd0f  test    rbx, rbx
0x18000fd12  jnz     loc_18000F9EA
0x18000fd18  mov     rcx, qword ptr [rbp+110h+var_190+8]
0x18000fd1c  mov     qword ptr [rbp+110h+var_190], rcx
0x18000fd20  cmp     dword ptr [rdi+18Ch], 1
0x18000fd27  jz      short loc_18000FD38
0x18000fd29  cmp     [rdi+128h], r15d
0x18000fd30  jz      short loc_18000FD38
0x18000fd32  call    cs:__imp_RevertToSelf
0x18000fd38  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000fd3f  jz      short loc_18000FD54
0x18000fd41  mov     r8d, r12d
0x18000fd44  mov     edx, 0BF2h; unsigned int
0x18000fd49  mov     ecx, 4; unsigned int
0x18000fd4e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000fd53  nop
0x18000fd54  lea     rcx, [rsp+210h+var_1D0]; this
0x18000fd59  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x18000fd5e  xor     eax, eax
0x18000fd60  mov     rcx, [rbp+110h+var_50]
0x18000fd67  xor     rcx, rsp; StackCookie
0x18000fd6a  call    __security_check_cookie
0x18000fd6f  add     rsp, 1D8h
0x18000fd76  pop     r15
  ... truncated ...
```
