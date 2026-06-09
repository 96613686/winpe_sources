# RegistryOwnershipManager::SaveOriginalSecurityInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1801154d4`
- end: `0x1801158ca`
- name: `?SaveOriginalSecurityInfo@RegistryOwnershipManager@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180116408`

## callees

- `0x180004bd0`
- `0x1800069db`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x18003de70`
- `0x18003e87c`
- `0x1800fdd8c`
- `0x1801010cc`
- `0x180113ad8`
- `0x1801154d4`
- `0x180117220`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801156b5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801156b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180115692`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180115692`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18011567a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18011567a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801155af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801155af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801155a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801155e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180115814`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011587b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801155a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801155e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180115814`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011587b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801155fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011582a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115891`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801155fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011582a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115891`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18011556b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18011556b`

## string_xrefs

- `0x1801155cc`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180115621`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x1801156c9`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180115845`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryOwnershipManager::SaveOriginalSecurityInfo(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // r8
  DWORD SecurityInfo; // r15d
  PSECURITY_DESCRIPTOR v6; // r12
  HLOCAL *v7; // rsi
  HLOCAL v8; // r14
  DWORD LastError; // ebx
  unsigned int v10; // ebx
  DWORD LengthSid; // ebx
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned int AclSize; // ebx
  __int64 v16; // r9
  void *v17; // rdx
  PSID v18; // rcx
  PSID v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  void *v22; // rax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-99h]
  HLOCAL hMem; // [rsp+40h] [rbp-79h] BYREF
  HANDLE handle; // [rsp+48h] [rbp-71h] BYREF
  PSID ppsidOwner; // [rsp+50h] [rbp-69h] BYREF
  PACL ppDacl; // [rsp+58h] [rbp-61h] BYREF
  HLOCAL *p_hMem; // [rsp+60h] [rbp-59h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+68h] [rbp-51h] BYREF
  char v30; // [rsp+70h] [rbp-49h]
  __int128 v31; // [rsp+80h] [rbp-39h] BYREF
  __m128i si128; // [rsp+90h] [rbp-29h]
  PSID pDestinationSid[2]; // [rsp+A0h] [rbp-19h] BYREF
  void *v34[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v35; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v4 = (const WCHAR *)a2;
  else
    v4 = *(const WCHAR **)a2;
  wil::reg::open_unique_key((int)&handle, *(HKEY *)a1, v4);
  ppsidOwner = 0;
  ppDacl = 0;
  hMem = 0;
  p_hMem = &hMem;
  ppSecurityDescriptor = 0;
  v30 = 1;
  SecurityInfo = GetSecurityInfo(handle, SE_REGISTRY_KEY, 5u, &ppsidOwner, 0, &ppDacl, 0, &ppSecurityDescriptor);
  if ( v30 )
  {
    v6 = ppSecurityDescriptor;
    v7 = p_hMem;
    v8 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v8);
      SetLastError(LastError);
    }
    *v7 = v6;
  }
  if ( SecurityInfo )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
            (const char *)SecurityInfo,
            ppsidGroup);
LABEL_10:
    if ( hMem )
      LocalFree(hMem);
    if ( handle )
      RegCloseKey((HKEY)handle);
    return v10;
  }
  if ( !hMem )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
      (const char *)0x8000FFFFLL,
      ppsidGroup);
LABEL_33:
    if ( hMem )
      LocalFree(hMem);
    if ( handle )
      RegCloseKey((HKEY)handle);
    return 2147549183LL;
  }
  v31 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31) = 0;
  *(_OWORD *)pDestinationSid = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  std::wstring::operator=(&v31, a2);
  if ( !ppsidOwner || !IsValidSid(ppsidOwner) )
  {
    v14 = 139;
    goto LABEL_32;
  }
  LengthSid = GetLengthSid(ppsidOwner);
  std::vector<unsigned char>::resize(pDestinationSid, LengthSid);
  if ( !CopySid(LengthSid, pDestinationSid[0], ppsidOwner) )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x8F,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
            v13);
    std::vector<unsigned char>::~vector<unsigned char>(&v34[1]);
    std::vector<unsigned char>::~vector<unsigned char>(pDestinationSid);
    std::wstring::~wstring(&v31);
    goto LABEL_10;
  }
  if ( !ppDacl )
  {
    v14 = 146;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
      (const char *)0x8000FFFFLL,
      ppsidGroup);
    std::vector<unsigned char>::~vector<unsigned char>(&v34[1]);
    std::vector<unsigned char>::~vector<unsigned char>(pDestinationSid);
    std::wstring::~wstring(&v31);
    goto LABEL_33;
  }
  AclSize = ppDacl->AclSize;
  std::vector<unsigned char>::resize(&v34[1], ppDacl->AclSize);
  memcpy_0(v34[1], ppDacl, AclSize);
  v16 = *(_QWORD *)(a1 + 64);
  if ( v16 == *(_QWORD *)(a1 + 72) )
  {
    std::vector<RegistryOwnershipManager::OriginalSecurityInfo>::_Emplace_reallocate<RegistryOwnershipManager::OriginalSecurityInfo>(
      a1 + 56,
      *(_QWORD *)(a1 + 64),
      &v31);
  }
  else
  {
    *(_OWORD *)v16 = 0;
    *(_QWORD *)(v16 + 16) = 0;
    *(_QWORD *)(v16 + 24) = 0;
    *(_OWORD *)v16 = v31;
    *(__m128i *)(v16 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v31) = 0;
    v17 = v34[0];
    v34[0] = 0;
    v18 = pDestinationSid[1];
    pDestinationSid[1] = 0;
    v19 = pDestinationSid[0];
    pDestinationSid[0] = 0;
    *(_QWORD *)(v16 + 32) = v19;
    *(_QWORD *)(v16 + 40) = v18;
    *(_QWORD *)(v16 + 48) = v17;
    v20 = *((_QWORD *)&v35 + 1);
    v21 = v35;
    v35 = 0u;
    v22 = v34[1];
    v34[1] = 0;
    *(_QWORD *)(v16 + 56) = v22;
    *(_QWORD *)(v16 + 64) = v21;
    *(_QWORD *)(v16 + 72) = v20;
    *(_QWORD *)(a1 + 64) += 80LL;
  }
  std::vector<unsigned char>::~vector<unsigned char>(&v34[1]);
  std::vector<unsigned char>::~vector<unsigned char>(pDestinationSid);
  std::wstring::~wstring(&v31);
  if ( hMem )
    LocalFree(hMem);
  if ( handle )
    RegCloseKey((HKEY)handle);
  return 0;
}

```

## disassembly

```asm
0x1801154d4  mov     [rsp-8+arg_10], rbx
0x1801154d9  push    rbp
0x1801154da  push    rsi
0x1801154db  push    rdi
0x1801154dc  push    r12
0x1801154de  push    r13
0x1801154e0  push    r14
0x1801154e2  push    r15
0x1801154e4  lea     rbp, [rsp-27h]
0x1801154e9  sub     rsp, 0E0h
0x1801154f0  mov     rax, cs:__security_cookie
0x1801154f7  xor     rax, rsp
0x1801154fa  mov     [rbp+57h+var_40], rax
0x1801154fe  mov     rdi, rdx
0x180115501  mov     r13, rcx
0x180115504  xor     esi, esi
0x180115506  cmp     qword ptr [rdx+18h], 7
0x18011550b  jbe     short loc_180115512
0x18011550d  mov     r8, [rdx]
0x180115510  jmp     short loc_180115515
0x180115512  mov     r8, rdi; lpSubKey
0x180115515  mov     rdx, [rcx]; hKey
0x180115518  lea     rcx, [rbp+57h+handle]; int
0x18011551c  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x180115521  nop
0x180115522  mov     [rbp+57h+ppsidOwner], rsi
0x180115526  mov     [rbp+57h+var_B8], rsi
0x18011552a  mov     [rbp+57h+hMem], rsi
0x18011552e  lea     rax, [rbp+57h+hMem]
0x180115532  mov     [rbp+57h+var_B0], rax
0x180115536  mov     [rbp+57h+var_A8], rsi
0x18011553a  mov     [rbp+57h+var_A0], 1
0x18011553e  lea     rax, [rbp+57h+var_A8]
0x180115542  mov     [rsp+110h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180115547  mov     [rsp+110h+ppSacl], rsi; ppSacl
0x18011554c  lea     rax, [rbp+57h+var_B8]
0x180115550  mov     [rsp+110h+ppDacl], rax; ppDacl
0x180115555  mov     [rsp+110h+ppsidGroup], rsi; int
0x18011555a  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x18011555e  mov     edx, 4; ObjectType
0x180115563  lea     r8d, [rdx+1]; SecurityInfo
0x180115567  mov     rcx, [rbp+57h+handle]; handle
0x18011556b  call    cs:__imp_GetSecurityInfo
0x180115572  nop     dword ptr [rax+rax+00h]
0x180115577  mov     r15d, eax
0x18011557a  cmp     [rbp+57h+var_A0], sil
0x18011557e  jz      short loc_1801155C0
0x180115580  mov     r12, [rbp+57h+var_A8]
0x180115584  mov     rsi, [rbp+57h+var_B0]
0x180115588  mov     r14, [rsi]
0x18011558b  test    r14, r14
0x18011558e  jz      short loc_1801155BB
0x180115590  call    cs:__imp_GetLastError
0x180115597  nop     dword ptr [rax+rax+00h]
0x18011559c  mov     ebx, eax
0x18011559e  mov     rcx, r14; hMem
0x1801155a1  call    cs:__imp_LocalFree
0x1801155a8  nop     dword ptr [rax+rax+00h]
0x1801155ad  mov     ecx, ebx; dwErrCode
0x1801155af  call    cs:__imp_SetLastError
0x1801155b6  nop     dword ptr [rax+rax+00h]
0x1801155bb  mov     [rsi], r12
0x1801155be  xor     esi, esi
0x1801155c0  test    r15d, r15d
0x1801155c3  jz      short loc_180115611
0x1801155c5  mov     rcx, [rbp+5Fh]; this
0x1801155c9  mov     r9d, r15d; char *
0x1801155cc  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x1801155d3  mov     edx, 83h; void *
0x1801155d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801155dd  mov     ebx, eax
0x1801155df  mov     rcx, [rbp+57h+hMem]; hMem
0x1801155e3  test    rcx, rcx
0x1801155e6  jz      short loc_1801155F5
0x1801155e8  call    cs:__imp_LocalFree
0x1801155ef  nop     dword ptr [rax+rax+00h]
0x1801155f4  nop
0x1801155f5  mov     rcx, [rbp+57h+handle]; hKey
0x1801155f9  test    rcx, rcx
0x1801155fc  jz      short loc_18011560A
0x1801155fe  call    cs:__imp_RegCloseKey
0x180115605  nop     dword ptr [rax+rax+00h]
0x18011560a  mov     eax, ebx
0x18011560c  jmp     loc_1801158A2
0x180115611  cmp     [rbp+57h+hMem], rsi
0x180115615  jnz     short loc_180115637
0x180115617  mov     rcx, [rbp+5Fh]; this
0x18011561b  mov     r9d, 8000FFFFh; char *
0x180115621  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180115628  mov     edx, 85h; void *
0x18011562d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115632  jmp     loc_180115872
0x180115637  xorps   xmm0, xmm0
0x18011563a  movups  [rbp+57h+var_90], xmm0
0x18011563e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180115646  movdqa  [rbp+57h+var_80], xmm1
0x18011564b  mov     word ptr [rbp+57h+var_90], si
0x18011564f  movdqa  xmmword ptr [rbp+57h+pDestinationSid], xmm0
0x180115654  xorps   xmm1, xmm1
0x180115657  movdqa  xmmword ptr [rbp+57h+var_60], xmm1
0x18011565c  movdqa  [rbp+57h+var_50], xmm0
0x180115661  mov     rdx, rdi
0x180115664  lea     rcx, [rbp+57h+var_90]
0x180115668  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18011566d  mov     rcx, [rbp+57h+ppsidOwner]; pSid
0x180115671  test    rcx, rcx
0x180115674  jz      loc_18011583A
0x18011567a  call    cs:__imp_IsValidSid
0x180115681  nop     dword ptr [rax+rax+00h]
0x180115686  test    eax, eax
0x180115688  jz      loc_18011583A
0x18011568e  mov     rcx, [rbp+57h+ppsidOwner]; pSid
0x180115692  call    cs:__imp_GetLengthSid
0x180115699  nop     dword ptr [rax+rax+00h]
0x18011569e  mov     ebx, eax
0x1801156a0  mov     edx, eax
0x1801156a2  lea     rcx, [rbp+57h+pDestinationSid]
0x1801156a6  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1801156ab  mov     r8, [rbp+57h+ppsidOwner]; pSourceSid
0x1801156af  mov     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x1801156b3  mov     ecx, ebx; nDestinationSidLength
0x1801156b5  call    cs:__imp_CopySid
0x1801156bc  nop     dword ptr [rax+rax+00h]
0x1801156c1  test    eax, eax
0x1801156c3  jnz     short loc_1801156FC
0x1801156c5  mov     rcx, [rbp+5Fh]; this
0x1801156c9  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x1801156d0  mov     edx, 8Fh; void *
0x1801156d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801156da  mov     ebx, eax
0x1801156dc  lea     rcx, [rbp+57h+var_60+8]
0x1801156e0  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1801156e5  lea     rcx, [rbp+57h+pDestinationSid]
0x1801156e9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1801156ee  lea     rcx, [rbp+57h+var_90]; void *
0x1801156f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801156f7  jmp     loc_1801155DF
0x1801156fc  mov     rax, [rbp+57h+var_B8]
0x180115700  test    rax, rax
0x180115703  jnz     short loc_18011570F
0x180115705  mov     edx, 92h
0x18011570a  jmp     loc_18011583F
0x18011570f  movzx   ebx, word ptr [rax+2]
0x180115713  mov     edx, ebx
0x180115715  lea     rcx, [rbp+57h+var_60+8]
0x180115719  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18011571e  mov     r8d, ebx; Size
0x180115721  mov     rdx, [rbp+57h+var_B8]; Src
0x180115725  mov     rcx, [rbp+57h+var_60+8]; void *
0x180115729  call    memcpy_0
0x18011572e  mov     r9, [r13+40h]
0x180115732  cmp     r9, [r13+48h]
0x180115736  jz      loc_1801157DE
0x18011573c  xorps   xmm0, xmm0
0x18011573f  movups  xmmword ptr [r9], xmm0
0x180115743  mov     [r9+10h], rsi
0x180115747  mov     [r9+18h], rsi
0x18011574b  movzx   eax, word ptr [rbp+57h+var_90]
0x18011574f  mov     [r9], ax
0x180115753  movsd   xmm0, qword ptr [rbp+57h+var_90+2]
0x180115758  movsd   qword ptr [r9+2], xmm0
0x18011575e  mov     eax, dword ptr [rbp+57h+var_90+0Ah]
0x180115761  mov     [r9+0Ah], eax
0x180115765  movzx   eax, word ptr [rbp+57h+var_90+0Eh]
0x180115769  mov     [r9+0Eh], ax
0x18011576e  mov     rax, qword ptr [rbp+57h+var_80]
0x180115772  mov     [r9+10h], rax
0x180115776  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18011577a  mov     [r9+18h], rax
0x18011577e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180115786  movdqa  [rbp+57h+var_80], xmm0
0x18011578b  mov     word ptr [rbp+57h+var_90], si
0x18011578f  mov     rdx, [rbp+57h+var_60]
0x180115793  mov     [rbp+57h+var_60], rsi
0x180115797  mov     rcx, [rbp+57h+pDestinationSid+8]
0x18011579b  mov     [rbp+57h+pDestinationSid+8], rsi
0x18011579f  mov     rax, [rbp+57h+pDestinationSid]
0x1801157a3  mov     [rbp+57h+pDestinationSid], rsi
0x1801157a7  mov     [r9+20h], rax
0x1801157ab  mov     [r9+28h], rcx
0x1801157af  mov     [r9+30h], rdx
0x1801157b3  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x1801157b7  mov     qword ptr [rbp+57h+var_50+8], rsi
0x1801157bb  mov     rcx, qword ptr [rbp+57h+var_50]
0x1801157bf  mov     qword ptr [rbp+57h+var_50], rsi
0x1801157c3  mov     rax, [rbp+57h+var_60+8]
0x1801157c7  mov     [rbp+57h+var_60+8], rsi
0x1801157cb  mov     [r9+38h], rax
0x1801157cf  mov     [r9+40h], rcx
0x1801157d3  mov     [r9+48h], rdx
0x1801157d7  add     qword ptr [r13+40h], 50h ; 'P'
0x1801157dc  jmp     short loc_1801157EF
0x1801157de  lea     r8, [rbp+57h+var_90]
0x1801157e2  mov     rdx, r9
0x1801157e5  lea     rcx, [r13+38h]
0x1801157e9  call    ??$_Emplace_reallocate@UOriginalSecurityInfo@RegistryOwnershipManager@@@?$vector@UOriginalSecurityInfo@RegistryOwnershipManager@@V?$allocator@UOriginalSecurityInfo@RegistryOwnershipManager@@@std@@@std@@AEAAPEAUOriginalSecurityInfo@RegistryOwnershipManager@@QEAU23@$$QEAU23@@Z; std::vector<RegistryOwnershipManager::OriginalSecurityInfo>::_Emplace_reallocate<RegistryOwnershipManager::OriginalSecurityInfo>(RegistryOwnershipManager::OriginalSecurityInfo * const,RegistryOwnershipManager::OriginalSecurityInfo &&)
0x1801157ee  nop
0x1801157ef  lea     rcx, [rbp+57h+var_60+8]
0x1801157f3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1801157f8  lea     rcx, [rbp+57h+pDestinationSid]
0x1801157fc  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180115801  lea     rcx, [rbp+57h+var_90]; void *
0x180115805  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18011580a  nop
0x18011580b  mov     rcx, [rbp+57h+hMem]; hMem
0x18011580f  test    rcx, rcx
0x180115812  jz      short loc_180115821
0x180115814  call    cs:__imp_LocalFree
0x18011581b  nop     dword ptr [rax+rax+00h]
0x180115820  nop
0x180115821  mov     rcx, [rbp+57h+handle]; hKey
0x180115825  test    rcx, rcx
0x180115828  jz      short loc_180115836
0x18011582a  call    cs:__imp_RegCloseKey
0x180115831  nop     dword ptr [rax+rax+00h]
0x180115836  xor     eax, eax
0x180115838  jmp     short loc_1801158A2
0x18011583a  mov     edx, 8Bh; void *
0x18011583f  mov     r9d, 8000FFFFh; char *
0x180115845  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x18011584c  mov     rcx, [rbp+5Fh]; this
0x180115850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115855  nop
0x180115856  lea     rcx, [rbp+57h+var_60+8]
0x18011585a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18011585f  lea     rcx, [rbp+57h+pDestinationSid]
0x180115863  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180115868  lea     rcx, [rbp+57h+var_90]; void *
0x18011586c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180115871  nop
0x180115872  mov     rcx, [rbp+57h+hMem]; hMem
0x180115876  test    rcx, rcx
0x180115879  jz      short loc_180115888
0x18011587b  call    cs:__imp_LocalFree
0x180115882  nop     dword ptr [rax+rax+00h]
0x180115887  nop
0x180115888  mov     rcx, [rbp+57h+handle]; hKey
0x18011588c  test    rcx, rcx
0x18011588f  jz      short loc_18011589D
0x180115891  call    cs:__imp_RegCloseKey
0x180115898  nop     dword ptr [rax+rax+00h]
0x18011589d  mov     eax, 8000FFFFh
0x1801158a2  mov     rcx, [rbp+57h+var_40]
0x1801158a6  xor     rcx, rsp; StackCookie
0x1801158a9  call    __security_check_cookie
0x1801158ae  mov     rbx, [rsp+110h+arg_10]
0x1801158b6  add     rsp, 0E0h
0x1801158bd  pop     r15
0x1801158bf  pop     r14
0x1801158c1  pop     r13
0x1801158c3  pop     r12
0x1801158c5  pop     rdi
0x1801158c6  pop     rsi
0x1801158c7  pop     rbp
0x1801158c8  retn
```
