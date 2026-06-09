# Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader,std::allocator<Pal::HttpHeader>>> const &)

- ea: `0x180037350`
- end: `0x180037787`
- name: `?sendRequestAsUser@NetworkRequestInternalWinHttp@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z`
- size: `1079`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037790`

## callees

- `0x18000d090`
- `0x18000d49c`
- `0x180011d90`
- `0x1800126c4`
- `0x180012720`
- `0x180016548`
- `0x180016770`
- `0x18001b9e0`
- `0x18001d0bc`
- `0x18001d0e4`
- `0x18001d12c`
- `0x1800247cc`
- `0x180033758`
- `0x180033fcc`
- `0x1800363b8`
- `0x180036484`
- `0x180036560`
- `0x180036898`
- `0x180037350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800374c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800374c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037721`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800375f2`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800375f2`
- `WINHTTP!WinHttpConnect` at `0x180037402`
- `WINHTTP!WinHttpConnect` at `0x180037402`
- `WINHTTP!WinHttpOpenRequest` at `0x18003746f`
- `WINHTTP!WinHttpOpenRequest` at `0x18003746f`
- `WINHTTP!WinHttpSetOption` at `0x180037643`
- `WINHTTP!WinHttpSetOption` at `0x18003766c`
- `WINHTTP!WinHttpSetOption` at `0x180037643`
- `WINHTTP!WinHttpSetOption` at `0x18003766c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18003768d`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18003768d`
- `WINHTTP!WinHttpOpen` at `0x1800373d7`
- `WINHTTP!WinHttpOpen` at `0x1800373d7`
- `WINHTTP!WinHttpSendRequest` at `0x180037717`
- `WINHTTP!WinHttpSendRequest` at `0x180037717`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(DWORD_PTR dwContext, __int64 a2, __int64 **a3)
{
  __int64 v6; // rdx
  const WCHAR *v7; // rax
  HINTERNET v8; // rax
  const WCHAR *v9; // rax
  HINTERNET v10; // r10
  HINTERNET v11; // rax
  DWORD LastError; // ebx
  const WCHAR *v13; // rax
  DWORD v14; // r9d
  HINTERNET v15; // r10
  HINTERNET v16; // rbx
  char *v17; // rdi
  HINTERNET *v18; // rsi
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 *v24; // rax
  __int64 v25; // r15
  __int64 i; // rbx
  __int64 v27; // rax
  const WCHAR *v28; // rax
  DWORD *j; // rbx
  const WCHAR *v30; // rax
  DWORD v31; // r8d
  DWORD v32; // r9d
  LPVOID v33; // r10
  _WORD v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v37[8]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v38; // [rsp+50h] [rbp-B0h]
  _DWORD v39[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v40; // [rsp+64h] [rbp-9Ch] BYREF
  _QWORD v41[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v42[8]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v43; // [rsp+80h] [rbp-80h]
  _BYTE v44[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v45[40]; // [rsp+A8h] [rbp-58h] BYREF
  int v46; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v47; // [rsp+D8h] [rbp-28h]
  _BYTE v48[544]; // [rsp+E0h] [rbp-20h] BYREF

  std::wstring::wstring(v45);
  std::wstring::assign(dwContext + 312, *(_QWORD *)(v6 + 24), *(unsigned int *)(v6 + 32));
  std::wstring::assign(v45, *(_QWORD *)(a2 + 72), *(unsigned int *)(a2 + 80));
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(dwContext + 256);
  v8 = WinHttpOpen(v7, 4u, 0, 0, 0x10000000u);
  *(_QWORD *)(dwContext + 152) = v8;
  if ( !v8
    || (v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(dwContext + 312),
        v11 = WinHttpConnect(v10, v9, *(_WORD *)(a2 + 36), 0),
        (*(_QWORD *)(dwContext + 160) = v11) == 0) )
  {
    LastError = GetLastError();
    goto LABEL_30;
  }
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
  v16 = WinHttpOpenRequest(v15, off_18009C610[*(int *)(dwContext + 288)], v13, 0, 0, 0, v14);
  v17 = (char *)operator new(0x18u);
  *(_OWORD *)v17 = 0;
  *((_DWORD *)v17 + 2) = 1;
  *((_DWORD *)v17 + 3) = 1;
  *(_QWORD *)v17 = &std::_Ref_count_obj2<Pal::WinHttpHandle>::`vftable';
  v18 = (HINTERNET *)(v17 + 16);
  *((_QWORD *)v17 + 2) = v16;
  v41[0] = v17 + 16;
  v41[1] = v17;
  EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 168));
  std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
    v37,
    dwContext + 208);
  v19 = (__int64 *)std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
                     v42,
                     v41);
  v20 = *v19;
  *v19 = *v21;
  *v21 = v20;
  v22 = v19[1];
  v19[1] = v21[1];
  v21[1] = v22;
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  LeaveCriticalSection((LPCRITICAL_SECTION)(dwContext + 168));
  if ( !*v18 )
    goto LABEL_7;
  if ( *a3 )
  {
    Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(&v46);
    v35[0] = 0;
    Core::InlineVector<unsigned short,256>::ensureSpaceFor(&v46, v47 + 1);
    v23 = ++v47;
    if ( v46 )
      std::vector<unsigned short>::emplace_back<unsigned short>(v48, v35);
    else
      *(_WORD *)Core::InlineVector<unsigned short,32>::getAt(&v46, v23 - 1) = 0;
    v24 = *a3;
    v25 = (*a3)[1];
    for ( i = *v24; i != v25; i += 64 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 32);
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
      Core::BasicInlineString<unsigned short,256>::formatInto(&v46, L"%ls: %ls", v27);
      v28 = (const WCHAR *)Core::InlineVector<unsigned short,20>::data(&v46);
      WinHttpAddRequestHeaders(*v18, v28, 0xFFFFFFFF, 0x20000000u);
    }
    Core::InlineVector<unsigned short,51>::~InlineVector<unsigned short,51>(&v46);
  }
  v39[0] = 3;
  v39[1] = 6;
  v39[2] = 5;
  for ( j = v39; j != (DWORD *)&v40; ++j )
  {
    if ( !WinHttpSetOption(*v18, *j, &c_networkTimeout, 4u) )
      goto LABEL_7;
  }
  Buffer = 1;
  if ( !WinHttpSetOption(*v18, 0x76u, &Buffer, 4u)
    || WinHttpSetStatusCallback(*v18, Pal::NetworkRequestInternalWinHttp::winHttpStatusCallback, 0x97E0C00u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
LABEL_7:
    LastError = GetLastError();
LABEL_8:
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
    goto LABEL_30;
  }
  std::wstring::wstring(v44, L"Host: ");
  std::wstring::append(v44, dwContext + 312);
  std::wstring::append(v44, L"\r\n");
  v30 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
  if ( !WinHttpSendRequest(*v18, v30, v31, v33, v32, v32, dwContext) )
  {
    LastError = GetLastError();
    std::wstring::_Tidy_deallocate(v44);
    goto LABEL_8;
  }
  std::wstring::_Tidy_deallocate(v44);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
  LastError = 0;
LABEL_30:
  std::wstring::_Tidy_deallocate(v45);
  return LastError;
}

```

## disassembly

```asm
0x180037350  push    rbp
0x180037352  push    rbx
0x180037353  push    rsi
0x180037354  push    rdi
0x180037355  push    r12
0x180037357  push    r14
0x180037359  push    r15
0x18003735b  lea     rbp, [rsp-210h]
0x180037363  sub     rsp, 310h
0x18003736a  mov     rax, cs:__security_cookie
0x180037371  xor     rax, rsp
0x180037374  mov     [rbp+240h+var_40], rax
0x18003737b  mov     r15, r8
0x18003737e  mov     rbx, rdx
0x180037381  mov     r14, rcx
0x180037384  lea     rcx, [rbp+240h+var_298]
0x180037388  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003738d  nop
0x18003738e  lea     r12, [r14+138h]
0x180037395  mov     r8d, [rdx+20h]
0x180037399  mov     rdx, [rdx+18h]
0x18003739d  mov     rcx, r12
0x1800373a0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800373a5  mov     r8d, [rbx+50h]
0x1800373a9  mov     rdx, [rbx+48h]
0x1800373ad  lea     rcx, [rbp+240h+var_298]
0x1800373b1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800373b6  lea     rcx, [r14+100h]
0x1800373bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800373c2  mov     [rsp+340h+dwFlags], 10000000h; dwFlags
0x1800373ca  xor     r9d, r9d; pszProxyBypassW
0x1800373cd  xor     r8d, r8d; pszProxyW
0x1800373d0  lea     edx, [r9+4]; dwAccessType
0x1800373d4  mov     rcx, rax; pszAgentW
0x1800373d7  call    cs:__imp_WinHttpOpen
0x1800373dd  mov     r10, rax
0x1800373e0  mov     [r14+98h], rax
0x1800373e7  test    rax, rax
0x1800373ea  jz      short loc_180037417
0x1800373ec  mov     rcx, r12
0x1800373ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800373f4  xor     r9d, r9d; dwReserved
0x1800373f7  movzx   r8d, word ptr [rbx+24h]; nServerPort
0x1800373fc  mov     rdx, rax; pswzServerName
0x1800373ff  mov     rcx, r10; hSession
0x180037402  call    cs:__imp_WinHttpConnect
0x180037408  mov     r10, rax
0x18003740b  mov     [r14+0A0h], rax
0x180037412  test    rax, rax
0x180037415  jnz     short loc_180037424
0x180037417  call    cs:__imp_GetLastError
0x18003741d  mov     ebx, eax
0x18003741f  jmp     loc_18003775B
0x180037424  xor     eax, eax
0x180037426  mov     r9d, 800000h
0x18003742c  cmp     dword ptr [rbx+14h], 2
0x180037430  cmovnz  r9d, eax
0x180037434  lea     rcx, [rbp+240h+var_298]
0x180037438  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003743d  mov     r8, rax; pwszObjectName
0x180037440  movsxd  rdx, dword ptr [r14+120h]
0x180037447  lea     rax, off_18009C610; "GET"
0x18003744e  mov     [rsp+340h+var_310], r9d; dwFlags
0x180037453  mov     [rsp+340h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18003745c  mov     qword ptr [rsp+340h+dwFlags], 0; pwszReferrer
0x180037465  xor     r9d, r9d; pwszVersion
0x180037468  mov     rdx, [rax+rdx*8]; pwszVerb
0x18003746c  mov     rcx, r10; hConnect
0x18003746f  call    cs:__imp_WinHttpOpenRequest
0x180037475  mov     rbx, rax
0x180037478  mov     ecx, 18h; Size
0x18003747d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037482  mov     rdi, rax
0x180037485  mov     [rsp+340h+var_2D8], rax
0x18003748a  xorps   xmm0, xmm0
0x18003748d  movups  xmmword ptr [rax], xmm0
0x180037490  mov     dword ptr [rax+8], 1
0x180037497  mov     dword ptr [rax+0Ch], 1
0x18003749e  lea     rax, ??_7?$_Ref_count_obj2@VWinHttpHandle@Pal@@@std@@6B@; const std::_Ref_count_obj2<Pal::WinHttpHandle>::`vftable'
0x1800374a5  mov     [rdi], rax
0x1800374a8  lea     rsi, [rdi+10h]
0x1800374ac  mov     [rsi], rbx
0x1800374af  mov     [rsp+340h+var_2D8], rsi
0x1800374b4  mov     [rsp+340h+var_2D0], rdi
0x1800374b9  lea     rbx, [r14+0A8h]
0x1800374c0  mov     rcx, rbx; lpCriticalSection
0x1800374c3  call    cs:__imp_EnterCriticalSection
0x1800374c9  lea     r9, [rbx+28h]
0x1800374cd  mov     rdx, r9
0x1800374d0  lea     rcx, [rsp+340h+var_2F8]
0x1800374d5  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800374da  lea     rdx, [rsp+340h+var_2D8]
0x1800374df  lea     rcx, [rsp+340h+var_2C8]
0x1800374e4  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800374e9  mov     rdx, [rax]
0x1800374ec  mov     rcx, [r9]
0x1800374ef  mov     [rax], rcx
0x1800374f2  mov     [r9], rdx
0x1800374f5  mov     r8, [rax+8]
0x1800374f9  mov     rdx, [r9+8]
0x1800374fd  mov     [rax+8], rdx
0x180037501  mov     [r9+8], r8
0x180037505  mov     rcx, [rbp+240h+var_2C0]; this
0x180037509  test    rcx, rcx
0x18003750c  jz      short loc_180037513
0x18003750e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037513  mov     rcx, rbx; lpCriticalSection
0x180037516  call    cs:__imp_LeaveCriticalSection
0x18003751c  nop
0x18003751d  cmp     qword ptr [rsi], 0
0x180037521  jnz     short loc_180037548
0x180037523  call    cs:__imp_GetLastError
0x180037529  mov     ebx, eax
0x18003752b  mov     rcx, [rsp+340h+var_2F0]; this
0x180037530  test    rcx, rcx
0x180037533  jz      short loc_18003753B
0x180037535  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003753a  nop
0x18003753b  mov     rcx, rdi; this
0x18003753e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037543  jmp     loc_18003775B
0x180037548  cmp     qword ptr [r15], 0
0x18003754c  jz      loc_18003760A
0x180037552  lea     rcx, [rbp+240h+var_270]
0x180037556  call    ??0?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@QEAA@XZ; Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(void)
0x18003755b  nop
0x18003755c  xor     eax, eax
0x18003755e  mov     [rsp+340h+var_300], ax
0x180037563  mov     rdx, [rbp+240h+var_268]
0x180037567  inc     rdx
0x18003756a  lea     rcx, [rbp+240h+var_270]
0x18003756e  call    ?ensureSpaceFor@?$InlineVector@G$0BAA@@Core@@AEAAX_K@Z; Core::InlineVector<ushort,256>::ensureSpaceFor(unsigned __int64)
0x180037573  mov     rdx, [rbp+240h+var_268]
0x180037577  inc     rdx
0x18003757a  mov     [rbp+240h+var_268], rdx
0x18003757e  cmp     [rbp+240h+var_270], 0
0x180037582  jnz     short loc_180037597
0x180037584  dec     rdx
0x180037587  lea     rcx, [rbp+240h+var_270]
0x18003758b  call    ?getAt@?$InlineVector@G$0CA@@Core@@AEAAPEAG_K@Z; Core::InlineVector<ushort,32>::getAt(unsigned __int64)
0x180037590  xor     ecx, ecx
0x180037592  mov     [rax], cx
0x180037595  jmp     short loc_1800375A6
0x180037597  lea     rdx, [rsp+340h+var_300]
0x18003759c  lea     rcx, [rbp+240h+var_260]
0x1800375a0  call    ??$emplace_back@G@?$vector@GV?$allocator@G@std@@@std@@QEAAAEAG$$QEAG@Z; std::vector<ushort>::emplace_back<ushort>(ushort &&)
0x1800375a5  nop
0x1800375a6  mov     rax, [r15]
0x1800375a9  mov     r15, [rax+8]
0x1800375ad  mov     rbx, [rax]
0x1800375b0  jmp     short loc_1800375FC
0x1800375b2  lea     rcx, [rbx+20h]
0x1800375b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800375bb  mov     r9, rax
0x1800375be  mov     rcx, rbx
0x1800375c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800375c6  mov     r8, rax
0x1800375c9  lea     rdx, aLsLs; "%ls: %ls"
0x1800375d0  lea     rcx, [rbp+240h+var_270]
0x1800375d4  call    ?formatInto@?$BasicInlineString@G$0BAA@@Core@@QEAAXPEBGZZ; Core::BasicInlineString<ushort,256>::formatInto(ushort const *,...)
0x1800375d9  lea     rcx, [rbp+240h+var_270]
0x1800375dd  call    ?data@?$InlineVector@G$0BE@@Core@@QEAAPEAGXZ; Core::InlineVector<ushort,20>::data(void)
0x1800375e2  mov     rdx, rax; lpszHeaders
0x1800375e5  mov     r9d, 20000000h; dwModifiers
0x1800375eb  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1800375ef  mov     rcx, [rsi]; hRequest
0x1800375f2  call    cs:__imp_WinHttpAddRequestHeaders
0x1800375f8  add     rbx, 40h ; '@'
0x1800375fc  cmp     rbx, r15
0x1800375ff  jnz     short loc_1800375B2
0x180037601  lea     rcx, [rbp+240h+var_270]
0x180037605  call    ??1?$InlineVector@G$0DD@@Core@@QEAA@XZ; Core::InlineVector<ushort,51>::~InlineVector<ushort,51>(void)
0x18003760a  mov     [rsp+340h+var_2E8], 3
0x180037612  mov     [rsp+340h+var_2E4], 6
0x18003761a  mov     [rsp+340h+var_2E0], 5
0x180037622  lea     rbx, [rsp+340h+var_2E8]
0x180037627  lea     rax, [rsp+340h+var_2DC]
0x18003762c  mov     r9d, 4; dwBufferLength
0x180037632  cmp     rbx, rax
0x180037635  jz      short loc_180037657
0x180037637  lea     r8, ?c_networkTimeout@@3KA; lpBuffer
0x18003763e  mov     edx, [rbx]; dwOption
0x180037640  mov     rcx, [rsi]; hInternet
0x180037643  call    cs:__imp_WinHttpSetOption
0x180037649  test    eax, eax
0x18003764b  jz      loc_180037523
0x180037651  add     rbx, 4
0x180037655  jmp     short loc_180037627
0x180037657  mov     [rsp+340h+Buffer], 1
0x18003765f  lea     r8, [rsp+340h+Buffer]; lpBuffer
0x180037664  mov     edx, 76h ; 'v'; dwOption
0x180037669  mov     rcx, [rsi]; hInternet
0x18003766c  call    cs:__imp_WinHttpSetOption
0x180037672  test    eax, eax
0x180037674  jz      loc_180037523
0x18003767a  xor     r9d, r9d; dwReserved
0x18003767d  mov     r8d, 97E0C00h; dwNotificationFlags
0x180037683  lea     rdx, ?winHttpStatusCallback@NetworkRequestInternalWinHttp@Pal@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18003768a  mov     rcx, [rsi]; hInternet
0x18003768d  call    cs:__imp_WinHttpSetStatusCallback
0x180037693  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037697  jz      loc_180037523
0x18003769d  lea     rdx, aHost; "Host: "
0x1800376a4  lea     rcx, [rbp+240h+var_2B8]
0x1800376a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800376ad  nop
0x1800376ae  mov     rdx, r12
0x1800376b1  lea     rcx, [rbp+240h+var_2B8]
0x1800376b5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800376ba  lea     rdx, asc_1800A5428; "\r\n"
0x1800376c1  lea     rcx, [rbp+240h+var_2B8]
0x1800376c5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800376ca  xor     r10d, r10d
0x1800376cd  xor     r9d, r9d
0x1800376d0  mov     rdx, [r14+128h]
0x1800376d7  test    rdx, rdx
0x1800376da  jz      short loc_1800376EE
0x1800376dc  mov     rax, [rdx+8]
0x1800376e0  cmp     rax, [rdx]
0x1800376e3  jz      short loc_1800376EE
0x1800376e5  mov     r10, [rdx]
0x1800376e8  mov     r9d, eax
0x1800376eb  sub     r9d, r10d
0x1800376ee  mov     r8d, [rbp+240h+var_2A8]
0x1800376f2  add     r8d, 0FFFFFFFEh
0x1800376f6  lea     rcx, [rbp+240h+var_2B8]
0x1800376fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800376ff  mov     rdx, rax; lpszHeaders
0x180037702  mov     qword ptr [rsp+340h+var_310], r14; dwContext
0x180037707  mov     dword ptr [rsp+340h+ppwszAcceptTypes], r9d; dwTotalLength
0x18003770c  mov     [rsp+340h+dwFlags], r9d; dwOptionalLength
0x180037711  mov     r9, r10; lpOptional
0x180037714  mov     rcx, [rsi]; hRequest
0x180037717  call    cs:__imp_WinHttpSendRequest
0x18003771d  test    eax, eax
0x18003771f  jnz     short loc_180037737
0x180037721  call    cs:__imp_GetLastError
0x180037727  mov     ebx, eax
0x180037729  lea     rcx, [rbp+240h+var_2B8]
0x18003772d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037732  jmp     loc_18003752B
0x180037737  lea     rcx, [rbp+240h+var_2B8]
0x18003773b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037740  nop
0x180037741  mov     rcx, [rsp+340h+var_2F0]; this
0x180037746  test    rcx, rcx
0x180037749  jz      short loc_180037751
0x18003774b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037750  nop
0x180037751  mov     rcx, rdi; this
0x180037754  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037759  xor     ebx, ebx
0x18003775b  lea     rcx, [rbp+240h+var_298]
0x18003775f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037764  mov     eax, ebx
0x180037766  mov     rcx, [rbp+240h+var_40]
0x18003776d  xor     rcx, rsp; StackCookie
0x180037770  call    __security_check_cookie
0x180037775  add     rsp, 310h
0x18003777c  pop     r15
0x18003777e  pop     r14
0x180037780  pop     r12
0x180037782  pop     rdi
0x180037783  pop     rsi
0x180037784  pop     rbx
0x180037785  pop     rbp
0x180037786  retn
```
