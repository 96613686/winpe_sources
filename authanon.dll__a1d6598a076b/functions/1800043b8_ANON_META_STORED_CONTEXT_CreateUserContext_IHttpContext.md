# ANON_META_STORED_CONTEXT::CreateUserContext(IHttpContext *)

- ea: `0x1800043b8`
- end: `0x180004882`
- name: `?CreateUserContext@ANON_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(ANON_META_STORED_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800049b4`

## callees

- `0x180001d30`
- `0x180002978`
- `0x1800041a4`
- `0x18000421c`
- `0x180004314`
- `0x1800043b8`
- `0x180004c80`
- `0x180004d30`
- `0x180004e6c`
- `0x180004f24`
- `0x180005354`
- `0x180005b46`
- `0x180005b70`
- `0x180006010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004418`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004418`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000442f`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800047f7`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000442f`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800047f7`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x18000444a`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x18000445e`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x18000444a`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x18000445e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000448d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004499`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004813`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000448d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004499`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004813`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180004806`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180004806`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000484a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000484a`
- `iisutil!DecryptMemoryPassword` at `0x180004471`
- `iisutil!DecryptMemoryPassword` at `0x180004471`

## pseudocode

```c
__int64 __fastcall ANON_META_STORED_CONTEXT::CreateUserContext(ANON_META_STORED_CONTEXT *this, struct IHttpContext *a2)
{
  signed int CacheKey; // edi
  unsigned int v5; // edi
  const unsigned __int16 *Str; // rbx
  const unsigned __int16 *v7; // rax
  int v8; // esi
  __int64 (__fastcall *v9)(struct IHttpServer *, _QWORD, _BYTE *, struct IHttpTokenEntry **); // rbx
  TOKEN_ENTRY *v10; // rax
  TOKEN_ENTRY *v11; // rax
  struct IHttpTokenEntry *v12; // rbx
  void (__fastcall *v13)(struct IHttpServer *, __int64, _BYTE *, struct IHttpTokenEntry **, __int64); // rbx
  __int64 v14; // rax
  _QWORD *v15; // rax
  struct IHttpTokenEntry *v16; // rcx
  __int64 v17; // rax
  struct sockaddr *v18; // r14
  char *v19; // rsi
  unsigned int v20; // edi
  const unsigned __int16 *v21; // rbx
  const unsigned __int16 *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  struct IHttpTraceContext *v25; // rax
  const struct _GUID *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  struct IHttpTraceContext *v29; // rax
  const struct _GUID *v30; // rdx
  __int64 CB; // rbx
  unsigned __int16 *i; // rax
  unsigned __int16 *v34; // [rsp+20h] [rbp-E0h]
  struct IHttpTokenEntry *v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  void *v37; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v39[128]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v40[32]; // [rsp+110h] [rbp+10h] BYREF

  v35 = 0;
  TOKEN_KEY::TOKEN_KEY((TOKEN_KEY *)v39);
  CacheKey = 0;
  memset_0(v40, 0, sizeof(v40));
  STRU::STRU((STRU *)v38, v40, 0x20u);
  v37 = 0;
  v36 = 0;
  if ( STRU::IsEmpty((ANON_META_STORED_CONTEXT *)((char *)this + 16)) )
    goto LABEL_22;
  if ( STRU::EqualsNoCase((ANON_META_STORED_CONTEXT *)((char *)this + 16), L"IUSR")
    || STRU::EqualsNoCase((ANON_META_STORED_CONTEXT *)((char *)this + 16), L"NT Authority\\IUSR") )
  {
    if ( (**(unsigned int (__fastcall ***)(struct IHttpServer *))s_pGlobalInfo)(s_pGlobalInfo) )
      goto LABEL_22;
    CacheKey = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(*(_QWORD *)s_pGlobalInfo + 160LL))(
                 s_pGlobalInfo,
                 &v36);
    if ( CacheKey < 0 )
      goto LABEL_37;
    CacheKey = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v36 + 48LL))(v36, 0, &v37);
    if ( CacheKey < 0 )
      goto LABEL_37;
    if ( !v37 )
      goto LABEL_37;
    CacheKey = TOKEN_KEY::CreateCacheKey((TOKEN_KEY *)v39, L"IUSR", L"IUSR", 3u);
    if ( CacheKey < 0 )
      goto LABEL_37;
    v8 = 1;
  }
  else
  {
    CacheKey = DecryptMemoryPassword((ANON_META_STORED_CONTEXT *)((char *)this + 72), (struct STRU *)v38);
    if ( CacheKey < 0 )
      goto LABEL_37;
    v5 = *((_DWORD *)this + 32);
    Str = STRU::QueryStr((STRU *)v38);
    v7 = STRU::QueryStr((ANON_META_STORED_CONTEXT *)((char *)this + 16));
    CacheKey = TOKEN_KEY::CreateCacheKey((TOKEN_KEY *)v39, v7, Str, v5);
    if ( CacheKey < 0 )
      goto LABEL_37;
    v8 = 0;
  }
  v9 = *(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, _BYTE *, struct IHttpTokenEntry **))(*(_QWORD *)s_pGlobalInfo
                                                                                                  + 80LL);
  v34 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  CacheKey = v9(s_pGlobalInfo, 0, v39, &v35);
  if ( CacheKey < 0 || !v35 )
  {
    if ( v8 )
    {
      v10 = (TOKEN_ENTRY *)operator new(0x108u);
      if ( !v10 || (v11 = TOKEN_ENTRY::TOKEN_ENTRY(v10), (v12 = v11) == 0) )
      {
LABEL_36:
        CacheKey = -2147024888;
        goto LABEL_37;
      }
      CacheKey = TOKEN_ENTRY::Create(v11, v37, L"IUSR", L"IUSR", 3u, 0);
      if ( CacheKey < 0 )
      {
        (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_37;
      }
      v35 = v12;
    }
    else
    {
      v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v18 = *(struct sockaddr **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17) + 104);
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
      v19 = (char *)s_pAnonAuthProvider;
      v20 = *((_DWORD *)this + 32);
      v21 = STRU::QueryStr((STRU *)v38);
      v22 = STRU::QueryStr((ANON_META_STORED_CONTEXT *)((char *)this + 16));
      CacheKey = IIS_LOGON_PROVIDER::IISLogonUser((IIS_LOGON_PROVIDER *)(v19 + 16), v22, v21, v20, v34, v18, &v35);
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
      if ( CacheKey < 0 )
      {
        if ( CacheKey == -2147022989 || CacheKey == -2147023566 )
        {
          v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
          if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v27, v28, 2) )
          {
            v29 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
            IISAuthenticationEvents::AUTH_ANON_PASSWD_CHANGE_NEEDED::RaiseEvent(v29, v30);
          }
        }
        else
        {
          v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
          if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v23, v24, 2) )
          {
            v25 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
            IISAuthenticationEvents::AUTH_INVALID_ANON_ACCOUNT::RaiseEvent(v25, v26, CacheKey);
          }
        }
        *((_DWORD *)this + 3) = 0;
        CacheKey = 0;
        goto LABEL_37;
      }
    }
    v13 = *(void (__fastcall **)(struct IHttpServer *, __int64, _BYTE *, struct IHttpTokenEntry **, __int64))(*(_QWORD *)s_pGlobalInfo + 80LL);
    v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v13(s_pGlobalInfo, 1, v39, &v35, v14);
  }
LABEL_22:
  v15 = operator new(0x18u);
  if ( v15 )
  {
    v16 = v35;
    *v15 = &ANON_USER_CONTEXT::`vftable';
    v15[2] = v16;
    *((_DWORD *)v15 + 2) = 1;
  }
  else
  {
    v15 = 0;
  }
  *((_QWORD *)this + 17) = v15;
  if ( !v15 )
  {
    if ( v35 )
    {
      (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
    }
    goto LABEL_36;
  }
LABEL_37:
  if ( !STRU::IsEmpty((STRU *)v38) )
  {
    CB = STRU::QueryCB((STRU *)v38);
    for ( i = STRU::QueryStr((STRU *)v38); CB; --CB )
    {
      *(_BYTE *)i = 0;
      i = (unsigned __int16 *)((char *)i + 1);
    }
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
    v36 = 0;
  }
  STRU::~STRU((STRU *)v38);
  TOKEN_KEY::~TOKEN_KEY((TOKEN_KEY *)v39);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x1800043b8  mov     [rsp-8+arg_10], rbx
0x1800043bd  push    rbp
0x1800043be  push    rsi
0x1800043bf  push    rdi
0x1800043c0  push    r12
0x1800043c2  push    r13
0x1800043c4  push    r14
0x1800043c6  push    r15
0x1800043c8  lea     rbp, [rsp-60h]
0x1800043cd  sub     rsp, 160h
0x1800043d4  mov     rax, cs:__security_cookie
0x1800043db  xor     rax, rsp
0x1800043de  mov     [rbp+90h+var_40], rax
0x1800043e2  mov     r13, rcx
0x1800043e5  xor     r14d, r14d
0x1800043e8  lea     rcx, [rbp+90h+var_100]; this
0x1800043ec  mov     [rsp+190h+var_150], r14
0x1800043f1  mov     r15, rdx
0x1800043f4  call    ??0TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::TOKEN_KEY(void)
0x1800043f9  xor     edx, edx; Val
0x1800043fb  lea     r8d, [r14+40h]; Size
0x1800043ff  lea     rcx, [rbp+90h+var_80]; void *
0x180004403  mov     edi, r14d
0x180004406  call    memset_0
0x18000440b  lea     r8d, [r14+20h]
0x18000440f  lea     rdx, [rbp+90h+var_80]
0x180004413  lea     rcx, [rsp+190h+var_138]
0x180004418  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000441e  lea     r12, [r13+10h]
0x180004422  mov     [rsp+190h+var_140], r14
0x180004427  mov     rcx, r12
0x18000442a  mov     [rsp+190h+var_148], r14
0x18000442f  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180004435  test    al, al
0x180004437  jnz     loc_18000465B
0x18000443d  lea     rbx, aIusr; "IUSR"
0x180004444  mov     rcx, r12
0x180004447  mov     rdx, rbx
0x18000444a  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x180004450  test    al, al
0x180004452  jnz     short loc_1800044C3
0x180004454  lea     rdx, aNtAuthorityIus; "NT Authority\\IUSR"
0x18000445b  mov     rcx, r12
0x18000445e  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x180004464  test    al, al
0x180004466  jnz     short loc_1800044C3
0x180004468  lea     rcx, [r13+48h]
0x18000446c  lea     rdx, [rsp+190h+var_138]
0x180004471  call    cs:__imp_?DecryptMemoryPassword@@YAJPEAVSTRU@@0@Z; DecryptMemoryPassword(STRU *,STRU *)
0x180004477  mov     edi, eax
0x180004479  test    eax, eax
0x18000447b  js      loc_1800047F2
0x180004481  mov     edi, [r13+80h]
0x180004488  lea     rcx, [rsp+190h+var_138]
0x18000448d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004493  mov     rcx, r12
0x180004496  mov     rbx, rax
0x180004499  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000449f  mov     r9d, edi; unsigned int
0x1800044a2  lea     rcx, [rbp+90h+var_100]; this
0x1800044a6  mov     rdx, rax; unsigned __int16 *
0x1800044a9  mov     r8, rbx; unsigned __int16 *
0x1800044ac  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x1800044b1  mov     edi, eax
0x1800044b3  test    eax, eax
0x1800044b5  js      loc_1800047F2
0x1800044bb  mov     esi, r14d
0x1800044be  jmp     loc_180004553
0x1800044c3  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800044ca  mov     rax, [rcx]
0x1800044cd  mov     rax, [rax]
0x1800044d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d5  test    eax, eax
0x1800044d7  jnz     loc_18000465B
0x1800044dd  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800044e4  lea     rdx, [rsp+190h+var_148]
0x1800044e9  mov     rax, [rcx]
0x1800044ec  mov     rax, [rax+0A0h]
0x1800044f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f8  mov     edi, eax
0x1800044fa  test    eax, eax
0x1800044fc  js      loc_1800047F2
0x180004502  mov     rcx, [rsp+190h+var_148]
0x180004507  lea     r8, [rsp+190h+var_140]
0x18000450c  xor     edx, edx
0x18000450e  mov     rax, [rcx]
0x180004511  mov     rax, [rax+30h]
0x180004515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000451a  mov     edi, eax
0x18000451c  test    eax, eax
0x18000451e  js      loc_1800047F2
0x180004524  cmp     [rsp+190h+var_140], r14
0x180004529  jz      loc_1800047F2
0x18000452f  mov     r9d, 3; unsigned int
0x180004535  lea     rcx, [rbp+90h+var_100]; this
0x180004539  mov     r8, rbx; unsigned __int16 *
0x18000453c  mov     rdx, rbx; unsigned __int16 *
0x18000453f  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180004544  mov     edi, eax
0x180004546  test    eax, eax
0x180004548  js      loc_1800047F2
0x18000454e  mov     esi, 1
0x180004553  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000455a  mov     rcx, [rax]
0x18000455d  mov     rbx, [rcx+50h]
0x180004561  mov     rcx, [r15]
0x180004564  mov     rax, [rcx+110h]
0x18000456b  mov     rcx, r15
0x18000456e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004573  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000457a  lea     r9, [rsp+190h+var_150]
0x18000457f  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x180004584  lea     r8, [rbp+90h+var_100]
0x180004588  mov     rax, rbx
0x18000458b  xor     edx, edx
0x18000458d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004592  mov     edi, eax
0x180004594  test    eax, eax
0x180004596  js      short loc_1800045A3
0x180004598  cmp     [rsp+190h+var_150], r14
0x18000459d  jnz     loc_18000465B
0x1800045a3  test    esi, esi
0x1800045a5  jz      loc_18000468D
0x1800045ab  mov     ecx, 108h; Size
0x1800045b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045b5  test    rax, rax
0x1800045b8  jz      loc_1800047ED
0x1800045be  mov     rcx, rax; this
0x1800045c1  call    ??0TOKEN_ENTRY@@QEAA@XZ; TOKEN_ENTRY::TOKEN_ENTRY(void)
0x1800045c6  mov     rbx, rax
0x1800045c9  test    rax, rax
0x1800045cc  jz      loc_1800047ED
0x1800045d2  mov     rdx, [rsp+190h+var_140]; void *
0x1800045d7  lea     r9, aIusr; "IUSR"
0x1800045de  mov     dword ptr [rsp+190h+var_168], r14d; int
0x1800045e3  lea     r8, aIusr; "IUSR"
0x1800045ea  mov     rcx, rax; this
0x1800045ed  mov     dword ptr [rsp+190h+var_170], 3; unsigned int
0x1800045f5  call    ?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z; TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)
0x1800045fa  mov     edi, eax
0x1800045fc  test    eax, eax
0x1800045fe  jns     short loc_180004614
0x180004600  mov     rax, [rbx]
0x180004603  mov     rcx, rbx
0x180004606  mov     rax, [rax+10h]
0x18000460a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000460f  jmp     loc_1800047F2
0x180004614  mov     [rsp+190h+var_150], rbx
0x180004619  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004620  mov     rcx, [rax]
0x180004623  mov     rbx, [rcx+50h]
0x180004627  mov     rcx, [r15]
0x18000462a  mov     rax, [rcx+110h]
0x180004631  mov     rcx, r15
0x180004634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004639  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004640  lea     r9, [rsp+190h+var_150]
0x180004645  mov     [rsp+190h+var_170], rax
0x18000464a  lea     r8, [rbp+90h+var_100]
0x18000464e  mov     rax, rbx
0x180004651  mov     edx, 1
0x180004656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000465b  mov     ecx, 18h; Size
0x180004660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004665  test    rax, rax
0x180004668  jz      loc_1800047C3
0x18000466e  mov     rcx, [rsp+190h+var_150]
0x180004673  lea     rdx, ??_7ANON_USER_CONTEXT@@6B@; const ANON_USER_CONTEXT::`vftable'
0x18000467a  mov     [rax], rdx
0x18000467d  mov     [rax+10h], rcx
0x180004681  mov     dword ptr [rax+8], 1
0x180004688  jmp     loc_1800047C6
0x18000468d  mov     rax, [r15]
0x180004690  mov     rcx, r15
0x180004693  mov     rax, [rax+18h]
0x180004697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469c  mov     rdx, rax
0x18000469f  mov     rcx, [rax]
0x1800046a2  mov     rax, [rcx+8]
0x1800046a6  mov     rcx, rdx
0x1800046a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ae  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800046b5  mov     r14, [rax+68h]
0x1800046b9  mov     rax, [rcx]
0x1800046bc  mov     rax, [rax+18h]
0x1800046c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c5  mov     rsi, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x1800046cc  lea     rcx, [rsp+190h+var_138]
0x1800046d1  mov     edi, [r13+80h]
0x1800046d8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800046de  mov     rcx, r12
0x1800046e1  mov     rbx, rax
0x1800046e4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800046ea  lea     rcx, [rsp+190h+var_150]
0x1800046ef  mov     r9d, edi; unsigned int
0x1800046f2  mov     [rsp+190h+var_160], rcx; struct IHttpTokenEntry **
0x1800046f7  mov     r8, rbx; unsigned __int16 *
0x1800046fa  lea     rcx, [rsi+10h]; this
0x1800046fe  mov     [rsp+190h+var_168], r14; struct sockaddr *
0x180004703  mov     rdx, rax; unsigned __int16 *
0x180004706  call    ?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z; IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)
0x18000470b  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004712  mov     edi, eax
0x180004714  mov     rax, [rcx]
0x180004717  mov     rax, [rax+20h]
0x18000471b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004720  xor     r14d, r14d
0x180004723  test    edi, edi
0x180004725  jns     loc_180004619
0x18000472b  cmp     edi, 80070773h
0x180004731  jz      short loc_18000477C
0x180004733  cmp     edi, 80070532h
0x180004739  jz      short loc_18000477C
0x18000473b  mov     rax, [r15]
0x18000473e  mov     rcx, r15
0x180004741  mov     rax, [rax+110h]
0x180004748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000474d  lea     r8d, [r14+2]
0x180004751  mov     rcx, rax
0x180004754  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180004759  test    eax, eax
0x18000475b  jz      short loc_1800047BA
0x18000475d  mov     rax, [r15]
0x180004760  mov     rcx, r15
0x180004763  mov     rax, [rax+110h]
0x18000476a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476f  mov     rcx, rax; struct IHttpTraceContext *
0x180004772  mov     r8d, edi; unsigned int
0x180004775  call    ?RaiseEvent@AUTH_INVALID_ANON_ACCOUNT@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISAuthenticationEvents::AUTH_INVALID_ANON_ACCOUNT::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x18000477a  jmp     short loc_1800047BA
0x18000477c  mov     rax, [r15]
0x18000477f  mov     rcx, r15
0x180004782  mov     rax, [rax+110h]
0x180004789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478e  mov     r8d, 2
0x180004794  mov     rcx, rax
0x180004797  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000479c  test    eax, eax
0x18000479e  jz      short loc_1800047BA
0x1800047a0  mov     rax, [r15]
0x1800047a3  mov     rcx, r15
0x1800047a6  mov     rax, [rax+110h]
0x1800047ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b2  mov     rcx, rax; struct IHttpTraceContext *
0x1800047b5  call    ?RaiseEvent@AUTH_ANON_PASSWD_CHANGE_NEEDED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISAuthenticationEvents::AUTH_ANON_PASSWD_CHANGE_NEEDED::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x1800047ba  mov     [r13+0Ch], r14d
0x1800047be  mov     edi, r14d
0x1800047c1  jmp     short loc_1800047F2
0x1800047c3  mov     rax, r14
0x1800047c6  mov     [r13+88h], rax
0x1800047cd  test    rax, rax
0x1800047d0  jnz     short loc_1800047F2
0x1800047d2  mov     rcx, [rsp+190h+var_150]
0x1800047d7  test    rcx, rcx
0x1800047da  jz      short loc_1800047ED
0x1800047dc  mov     rax, [rcx]
0x1800047df  mov     rax, [rax+10h]
0x1800047e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e8  mov     [rsp+190h+var_150], r14
0x1800047ed  mov     edi, 80070008h
0x1800047f2  lea     rcx, [rsp+190h+var_138]
0x1800047f7  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800047fd  test    al, al
0x1800047ff  jnz     short loc_18000482A
0x180004801  lea     rcx, [rsp+190h+var_138]
0x180004806  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18000480c  lea     rcx, [rsp+190h+var_138]
0x180004811  mov     ebx, eax
0x180004813  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004819  test    rbx, rbx
0x18000481c  jz      short loc_18000482A
0x18000481e  mov     [rax], r14b
0x180004821  inc     rax
0x180004824  sub     rbx, 1
0x180004828  jnz     short loc_18000481E
0x18000482a  mov     rcx, [rsp+190h+var_148]
0x18000482f  test    rcx, rcx
0x180004832  jz      short loc_180004845
0x180004834  mov     rax, [rcx]
0x180004837  mov     rax, [rax+8]
0x18000483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004840  mov     [rsp+190h+var_148], r14
0x180004845  lea     rcx, [rsp+190h+var_138]
0x18000484a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004850  lea     rcx, [rbp+90h+var_100]; this
0x180004854  call    ??1TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::~TOKEN_KEY(void)
0x180004859  mov     eax, edi
0x18000485b  mov     rcx, [rbp+90h+var_40]
0x18000485f  xor     rcx, rsp; StackCookie
0x180004862  call    __security_check_cookie
0x180004867  mov     rbx, [rsp+190h+arg_10]
0x18000486f  add     rsp, 160h
0x180004876  pop     r15
0x180004878  pop     r14
0x18000487a  pop     r13
0x18000487c  pop     r12
0x18000487e  pop     rdi
0x18000487f  pop     rsi
0x180004880  pop     rbp
0x180004881  retn
  ... truncated ...
```
