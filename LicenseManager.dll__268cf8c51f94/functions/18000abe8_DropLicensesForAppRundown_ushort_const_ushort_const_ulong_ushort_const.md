# DropLicensesForAppRundown(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x18000abe8`
- end: `0x18000b146`
- name: `?DropLicensesForAppRundown@@YAXPEBG0K0@Z`
- size: `1374`
- prototype: `void(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046fac`

## callees

- `0x18000a98c`
- `0x18000abe8`
- `0x18000b3f4`
- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x1800173e0`
- `0x180018d48`
- `0x180028ae8`
- `0x18002bf04`
- `0x18003b7a8`
- `0x18003ba34`
- `0x180054a54`
- `0x180055ab4`
- `0x1800593bc`
- `0x180075e60`
- `0x180076e64`
- `0x18008251f`
- `0x18008d378`
- `0x18008d8c4`
- `0x18008dc28`
- `0x180090f54`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b104`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b104`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ac58`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000adc3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ac58`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000adc3`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x18000b0a6`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x18000b0a6`

## string_xrefs

- `0x18000af44`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18000b0ef`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall DropLicensesForAppRundown(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rsi
  __int64 v8; // rbx
  void *v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rdi
  char v12; // al
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rbx
  void *v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rdi
  char v20; // al
  __int64 *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  int v25; // eax
  char *v26; // rax
  _QWORD *v27; // r14
  int v28; // eax
  int Format; // [rsp+20h] [rbp-E0h]
  void *v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h]
  _BYTE Src[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v36; // [rsp+90h] [rbp-70h]
  _QWORD v37[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v38; // [rsp+B8h] [rbp-48h]
  _BYTE v39[80]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v30 = a4;
  LODWORD(v31) = a3;
  v33 = 0;
  v34 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( v7 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v7 > 7 )
  {
    v8 = std::wstring::_Calculate_growth(v7, 7);
    v9 = (void *)std::allocator<unsigned short>::allocate(&v33, v8 + 1);
    *(_QWORD *)&v33 = v9;
    *(_QWORD *)&v34 = v7;
    *((_QWORD *)&v34 + 1) = v8;
    memcpy_0(v9, a2, 2 * v7);
    *((_WORD *)v9 + v7) = 0;
  }
  else
  {
    *(_QWORD *)&v34 = v7;
    *((_QWORD *)&v34 + 1) = 7;
    memcpy_0(&v33, a2, 2 * v7);
    *((_WORD *)&v33 + v7) = 0;
  }
  GetKey(Src, &v33, v30);
  std::wstring::_Tidy_deallocate(&v33);
  AcquireSRWLockExclusive(&TrialStatesLock);
  v10 = TrialStates;
  v11 = *(_QWORD *)(TrialStates + 8);
  HIDWORD(v33) = 0;
  while ( !*(_BYTE *)(v11 + 25) )
  {
    v12 = std::operator<<unsigned short>(v11 + 32, Src);
    if ( !v12 )
      v10 = v11;
    v13 = (__int64 *)(v11 + 16);
    if ( !v12 )
      v13 = (__int64 *)v11;
    v11 = *v13;
  }
  if ( *(_BYTE *)(v10 + 25) || (unsigned __int8)std::operator<<unsigned short>(Src, v10 + 32) )
    v10 = TrialStates;
  if ( v10 != TrialStates )
  {
    v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::pair<int,std::wstring>>>>::_Extract(
            &TrialStates,
            v10);
    std::_Tree_node<std::pair<std::wstring const,std::pair<int,std::wstring>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::pair<int,std::wstring>>,void *>>>(
      v15,
      v14);
  }
  ReleaseSRWLockExclusive(&TrialStatesLock);
  std::wstring::_Tidy_deallocate(Src);
  v33 = 0;
  v34 = 0;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v6 > 7 )
  {
    v16 = std::wstring::_Calculate_growth(v6, 7);
    v17 = (void *)std::allocator<unsigned short>::allocate(&v33, v16 + 1);
    *(_QWORD *)&v33 = v17;
    *(_QWORD *)&v34 = v6;
    *((_QWORD *)&v34 + 1) = v16;
    memcpy_0(v17, a2, 2 * v6);
    *((_WORD *)v17 + v6) = 0;
  }
  else
  {
    *(_QWORD *)&v34 = v6;
    *((_QWORD *)&v34 + 1) = 7;
    memcpy_0(&v33, a2, 2 * v6);
    *((_WORD *)&v33 + v6) = 0;
  }
  GetKey(v37, &v33, v30);
  if ( *((_QWORD *)&v34 + 1) > 7u )
    std::_Deallocate<16>(v33, 2LL * *((_QWORD *)&v34 + 1) + 2);
  AcquireSRWLockExclusive(&ActiveLicensesLock);
  v32[1] = &ActiveLicensesLock;
  v18 = ActiveLicenses;
  v19 = *(_QWORD *)(ActiveLicenses + 8);
  HIDWORD(v33) = 0;
  while ( !*(_BYTE *)(v19 + 25) )
  {
    v20 = std::operator<<unsigned short>(v19 + 32, v37);
    if ( !v20 )
      v18 = v19;
    v21 = (__int64 *)(v19 + 16);
    if ( !v20 )
      v21 = (__int64 *)v19;
    v19 = *v21;
  }
  if ( *(_BYTE *)(v18 + 25) || (unsigned __int8)std::operator<<unsigned short>(v37, v18 + 32) )
    v18 = ActiveLicenses;
  if ( v18 != ActiveLicenses )
  {
    if ( a1 )
    {
      PsmKeyCompat::PsmKeyCompat((PsmKeyCompat *)v39, a1);
      std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::erase(
        v18 + 64,
        v39);
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((ContentIdString *)v39);
    }
    if ( *(_QWORD *)(v18 + 72) )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x5CAu,
        "DropLicensesForAppRundown",
        (wchar_t *)L"Not dropping license, still tracking %d PsmKeys",
        *(_DWORD *)(v18 + 72));
    }
    else
    {
      ActiveLicense::ActiveLicense((ActiveLicense *)Src, (const struct ActiveLicense *)(v18 + 64));
      std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActiveLicense>>>>,0>(
        v22,
        &v30,
        v18);
      v24 = *v36;
      v32[0] = *v36;
      while ( !*(_BYTE *)(v24 + 25) )
      {
        v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v24 + 64) + 120LL))(
                *(_QWORD *)(v24 + 64),
                *(_QWORD *)(v24 + 72));
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5A8,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v25,
            Format);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          0x5ADu,
          "DropLicensesForAppRundown",
          (wchar_t *)L"DropLicense - drop? true");
        if ( a1 )
        {
          v26 = *(char **)ActiveLicenses;
          v30 = *(void **)ActiveLicenses;
          while ( !v26[25] )
          {
            v27 = v26 + 32;
            PsmKeyCompat::PsmKeyCompat((PsmKeyCompat *)v39, a1);
            std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::find(
              v27 + 4,
              &v31,
              v39);
            std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((ContentIdString *)v39);
            if ( v31 != v27[4] )
            {
              if ( v27[3] > 7u )
                v27 = (_QWORD *)*v27;
              LogMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                0x5B6u,
                "DropLicensesForAppRundown",
                (wchar_t *)L"Not deactivating, found psmkey %s under key %s",
                a1,
                v27);
              goto LABEL_55;
            }
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(&v30);
            v26 = (char *)v30;
          }
        }
        v28 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v24 + 64) + 32LL))(*(_QWORD *)(v24 + 64));
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5BF,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v28,
            Format);
LABEL_55:
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(v32);
        v24 = v32[0];
      }
      if ( !qword_1800F2A68
        && (!(unsigned __int8)IsCompareContentIdPresent(v23) || (unsigned int)ShouldLicenseManagerServiceAutoStop()) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)PushNotificationListener + 32LL))(PushNotificationListener);
      }
      ActiveLicense::~ActiveLicense((ActiveLicense *)Src);
    }
  }
  ReleaseSRWLockExclusive(&ActiveLicensesLock);
  if ( v38 > 7 )
    std::_Deallocate<16>(v37[0], 2 * v38 + 2);
}

```

## disassembly

```asm
0x18000abe8  push    rbp
0x18000abea  push    rbx
0x18000abeb  push    rsi
0x18000abec  push    rdi
0x18000abed  push    r12
0x18000abef  push    r13
0x18000abf1  push    r14
0x18000abf3  push    r15
0x18000abf5  lea     rbp, [rsp-28h]
0x18000abfa  sub     rsp, 128h
0x18000ac01  mov     rax, cs:__security_cookie
0x18000ac08  xor     rax, rsp
0x18000ac0b  mov     [rbp+60h+var_50], rax
0x18000ac0f  mov     [rsp+160h+var_120], r9
0x18000ac14  mov     dword ptr [rsp+160h+var_118], r8d
0x18000ac19  mov     r12, rdx
0x18000ac1c  mov     r13, rcx
0x18000ac1f  xor     eax, eax
0x18000ac21  xorps   xmm0, xmm0
0x18000ac24  movups  [rsp+160h+var_100], xmm0
0x18000ac29  xorps   xmm1, xmm1
0x18000ac2c  movdqu  [rsp+160h+var_F0], xmm1
0x18000ac32  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ac36  mov     rsi, r14
0x18000ac39  inc     rsi
0x18000ac3c  cmp     [rdx+rsi*2], ax
0x18000ac40  jnz     short loc_18000AC39
0x18000ac42  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18000ac4c  cmp     rsi, rcx
0x18000ac4f  jbe     short loc_18000AC5F
0x18000ac51  lea     rcx, aStringTooLong; "string too long"
0x18000ac58  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ac5f  lea     r15, [rsi+rsi]
0x18000ac63  mov     eax, 7
0x18000ac68  cmp     rsi, rax
0x18000ac6b  ja      short loc_18000AC8E
0x18000ac6d  mov     qword ptr [rsp+160h+var_F0], rsi
0x18000ac72  mov     qword ptr [rsp+160h+var_F0+8], rax
0x18000ac77  mov     r8, r15; Size
0x18000ac7a  lea     rcx, [rsp+160h+var_100]; void *
0x18000ac7f  call    memcpy_0
0x18000ac84  xor     esi, esi
0x18000ac86  mov     word ptr [rsp+r15+160h+var_100], si
0x18000ac8c  jmp     short loc_18000ACD4
0x18000ac8e  mov     r8, rcx
0x18000ac91  mov     rdx, rax
0x18000ac94  mov     rcx, rsi
0x18000ac97  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000ac9c  mov     rbx, rax
0x18000ac9f  lea     rdx, [rax+1]
0x18000aca3  lea     rcx, [rsp+160h+var_100]
0x18000aca8  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18000acad  mov     rdi, rax
0x18000acb0  mov     qword ptr [rsp+160h+var_100], rax
0x18000acb5  mov     qword ptr [rsp+160h+var_F0], rsi
0x18000acba  mov     qword ptr [rsp+160h+var_F0+8], rbx
0x18000acbf  mov     r8, r15; Size
0x18000acc2  mov     rdx, r12; Src
0x18000acc5  mov     rcx, rax; void *
0x18000acc8  call    memcpy_0
0x18000accd  xor     esi, esi
0x18000accf  mov     [r15+rdi], si
0x18000acd4  mov     r15d, dword ptr [rsp+160h+var_118]
0x18000acd9  mov     r9d, r15d
0x18000acdc  mov     r8, [rsp+160h+var_120]; void *
0x18000ace1  lea     rdx, [rsp+160h+var_100]; void *
0x18000ace6  lea     rcx, [rbp+60h+Src]; Src
0x18000acea  call    ?GetKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@PEBGK@Z; GetKey(std::wstring const &,ushort const *,ulong)
0x18000acef  nop
0x18000acf0  lea     rcx, [rsp+160h+var_100]
0x18000acf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000acfa  lea     rcx, ?TrialStatesLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000ad01  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad07  mov     rbx, cs:?TrialStates@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::pair<int,std::wstring>> TrialStates
0x18000ad0e  mov     rdi, [rbx+8]
0x18000ad12  xor     eax, eax
0x18000ad14  mov     dword ptr [rsp+160h+var_100+0Ch], eax
0x18000ad18  jmp     short loc_18000AD38
0x18000ad1a  lea     rcx, [rdi+20h]
0x18000ad1e  lea     rdx, [rbp+60h+Src]
0x18000ad22  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000ad27  test    al, al
0x18000ad29  cmovz   rbx, rdi
0x18000ad2d  lea     rcx, [rdi+10h]
0x18000ad31  cmovz   rcx, rdi
0x18000ad35  mov     rdi, [rcx]
0x18000ad38  cmp     [rdi+19h], sil
0x18000ad3c  jz      short loc_18000AD1A
0x18000ad3e  cmp     [rbx+19h], sil
0x18000ad42  jnz     short loc_18000AD55
0x18000ad44  lea     rdx, [rbx+20h]
0x18000ad48  lea     rcx, [rbp+60h+Src]
0x18000ad4c  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000ad51  test    al, al
0x18000ad53  jz      short loc_18000AD5C
0x18000ad55  mov     rbx, cs:?TrialStates@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::pair<int,std::wstring>> TrialStates
0x18000ad5c  cmp     rbx, cs:?TrialStates@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::pair<int,std::wstring>> TrialStates
0x18000ad63  jz      short loc_18000AD7C
0x18000ad65  mov     rdx, rbx
0x18000ad68  lea     rcx, ?TrialStates@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::pair<int,std::wstring>> TrialStates
0x18000ad6f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::pair<int,std::wstring>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::pair<int,std::wstring>>>>,std::_Iterator_base0>)
0x18000ad74  mov     rdx, rax
0x18000ad77  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::wstring const,std::pair<int,std::wstring>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::pair<int,std::wstring>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::pair<int,std::wstring>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::pair<int,std::wstring>>,void *> *)
0x18000ad7c  lea     rcx, ?TrialStatesLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000ad83  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad89  lea     rcx, [rbp+60h+Src]
0x18000ad8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ad92  xorps   xmm0, xmm0
0x18000ad95  movups  [rsp+160h+var_100], xmm0
0x18000ad9a  xorps   xmm1, xmm1
0x18000ad9d  movdqu  [rsp+160h+var_F0], xmm1
0x18000ada3  inc     r14
0x18000ada6  cmp     [r12+r14*2], si
0x18000adab  jnz     short loc_18000ADA3
0x18000adad  mov     r8, 7FFFFFFFFFFFFFFEh
0x18000adb7  cmp     r14, r8
0x18000adba  jbe     short loc_18000ADCA
0x18000adbc  lea     rcx, aStringTooLong; "string too long"
0x18000adc3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000adca  lea     rsi, [r14+r14]
0x18000adce  mov     eax, 7
0x18000add3  cmp     r14, rax
0x18000add6  ja      short loc_18000ADFD
0x18000add8  mov     qword ptr [rsp+160h+var_F0], r14
0x18000addd  mov     qword ptr [rsp+160h+var_F0+8], rax
0x18000ade2  mov     r8, rsi; Size
0x18000ade5  mov     rdx, r12; Src
0x18000ade8  lea     rcx, [rsp+160h+var_100]; void *
0x18000aded  call    memcpy_0
0x18000adf2  xor     r14d, r14d
0x18000adf5  mov     word ptr [rsp+rsi+160h+var_100], r14w
0x18000adfb  jmp     short loc_18000AE41
0x18000adfd  mov     rdx, rax
0x18000ae00  mov     rcx, r14
0x18000ae03  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000ae08  mov     rbx, rax
0x18000ae0b  lea     rdx, [rax+1]
0x18000ae0f  lea     rcx, [rsp+160h+var_100]
0x18000ae14  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18000ae19  mov     rdi, rax
0x18000ae1c  mov     qword ptr [rsp+160h+var_100], rax
0x18000ae21  mov     qword ptr [rsp+160h+var_F0], r14
0x18000ae26  mov     qword ptr [rsp+160h+var_F0+8], rbx
0x18000ae2b  mov     r8, rsi; Size
0x18000ae2e  mov     rdx, r12; Src
0x18000ae31  mov     rcx, rax; void *
0x18000ae34  call    memcpy_0
0x18000ae39  xor     r14d, r14d
0x18000ae3c  mov     [rsi+rdi], r14w
0x18000ae41  mov     r9d, r15d
0x18000ae44  mov     r8, [rsp+160h+var_120]; void *
0x18000ae49  lea     rdx, [rsp+160h+var_100]; void *
0x18000ae4e  lea     rcx, [rbp+60h+var_C0]; Src
0x18000ae52  call    ?GetKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@PEBGK@Z; GetKey(std::wstring const &,ushort const *,ulong)
0x18000ae57  nop
0x18000ae58  mov     rdx, qword ptr [rsp+160h+var_F0+8]
0x18000ae5d  cmp     rdx, 7
0x18000ae61  jbe     short loc_18000AE75
0x18000ae63  lea     rdx, ds:2[rdx*2]
0x18000ae6b  mov     rcx, qword ptr [rsp+160h+var_100]
0x18000ae70  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ae75  lea     r15, ?ActiveLicensesLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock ActiveLicensesLock
0x18000ae7c  mov     rcx, r15; SRWLock
0x18000ae7f  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae85  mov     [rsp+160h+var_108], r15
0x18000ae8a  mov     rbx, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x18000ae91  mov     rdi, [rbx+8]
0x18000ae95  xor     eax, eax
0x18000ae97  mov     dword ptr [rsp+160h+var_100+0Ch], eax
0x18000ae9b  jmp     short loc_18000AEBB
0x18000ae9d  lea     rcx, [rdi+20h]
0x18000aea1  lea     rdx, [rbp+60h+var_C0]
0x18000aea5  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000aeaa  test    al, al
0x18000aeac  cmovz   rbx, rdi
0x18000aeb0  lea     rcx, [rdi+10h]
0x18000aeb4  cmovz   rcx, rdi
0x18000aeb8  mov     rdi, [rcx]
0x18000aebb  cmp     [rdi+19h], r14b
0x18000aebf  jz      short loc_18000AE9D
0x18000aec1  cmp     [rbx+19h], r14b
0x18000aec5  jnz     short loc_18000AED8
0x18000aec7  lea     rdx, [rbx+20h]
0x18000aecb  lea     rcx, [rbp+60h+var_C0]
0x18000aecf  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000aed4  test    al, al
0x18000aed6  jz      short loc_18000AEDF
0x18000aed8  mov     rbx, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x18000aedf  cmp     rbx, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x18000aee6  jz      loc_18000B101
0x18000aeec  test    r13, r13
0x18000aeef  jz      short loc_18000AF13
0x18000aef1  mov     rdx, r13; unsigned __int16 *
0x18000aef4  lea     rcx, [rbp+60h+var_A0]; this
0x18000aef8  call    ??0PsmKeyCompat@@QEAA@PEBG@Z; PsmKeyCompat::PsmKeyCompat(ushort const *)
0x18000aefd  lea     rcx, [rbx+40h]
0x18000af01  lea     rdx, [rbp+60h+var_A0]
0x18000af05  call    ?erase@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@QEAA_KAEBUPsmKeyCompat@@@Z; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::erase(PsmKeyCompat const &)
0x18000af0a  lea     rcx, [rbp+60h+var_A0]; this
0x18000af0e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18000af13  cmp     [rbx+48h], r14
0x18000af17  jnz     loc_18000B0CF
0x18000af1d  lea     rdx, [rbx+40h]; struct ActiveLicense *
0x18000af21  lea     rcx, [rbp+60h+Src]; this
0x18000af25  call    ??0ActiveLicense@@QEAA@AEBU0@@Z; ActiveLicense::ActiveLicense(ActiveLicense const &)
0x18000af2a  nop
0x18000af2b  mov     r8, rbx
0x18000af2e  lea     rdx, [rsp+160h+var_120]
0x18000af33  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActiveLicense>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActiveLicense>>>>)
0x18000af38  mov     rbx, [rbp+60h+var_D0]
0x18000af3c  mov     rbx, [rbx]
0x18000af3f  mov     [rsp+160h+var_110], rbx
0x18000af44  lea     rsi, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000af4b  cmp     [rbx+19h], r14b
0x18000af4f  jnz     loc_18000B094
0x18000af55  mov     rcx, [rbx+40h]
0x18000af59  mov     rax, [rcx]
0x18000af5c  mov     rdx, [rbx+48h]
0x18000af60  mov     rax, [rax+78h]
0x18000af64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af69  mov     rcx, [rbp+68h]; this
0x18000af6d  test    eax, eax
0x18000af6f  js      loc_18000B083
0x18000af75  lea     rax, aDroplicenseDro; "DropLicense - drop? true"
0x18000af7c  mov     [rsp+160h+Format], rax; int
0x18000af81  lea     r9, aDroplicensesfo; "DropLicensesForAppRundown"
0x18000af88  mov     r8d, 5ADh; unsigned int
0x18000af8e  mov     rdx, rsi; char *
0x18000af91  mov     ecx, 3; unsigned int
0x18000af96  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000af9b  test    r13, r13
0x18000af9e  jz      loc_18000B046
0x18000afa4  mov     rax, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x18000afab  mov     rax, [rax]
0x18000afae  mov     [rsp+160h+var_120], rax
0x18000afb3  cmp     [rax+19h], r14b
0x18000afb7  jnz     loc_18000B046
0x18000afbd  lea     r14, [rax+20h]
0x18000afc1  mov     rdx, r13; unsigned __int16 *
0x18000afc4  lea     rcx, [rbp+60h+var_A0]; this
0x18000afc8  call    ??0PsmKeyCompat@@QEAA@PEBG@Z; PsmKeyCompat::PsmKeyCompat(ushort const *)
0x18000afcd  lea     r8, [rbp+60h+var_A0]
0x18000afd1  lea     rdx, [rsp+160h+var_118]
0x18000afd6  lea     rcx, [r14+20h]
0x18000afda  call    ?find@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UPsmKeyCompat@@@std@@@std@@@2@AEBUPsmKeyCompat@@@Z; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::find(PsmKeyCompat const &)
0x18000afdf  lea     rcx, [rbp+60h+var_A0]; this
0x18000afe3  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18000afe8  mov     rax, [r14+20h]
0x18000afec  cmp     [rsp+160h+var_118], rax
0x18000aff1  jnz     short loc_18000B007
0x18000aff3  lea     rcx, [rsp+160h+var_120]
0x18000aff8  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UPsmKeyCompat@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(void)
0x18000affd  mov     rax, [rsp+160h+var_120]
0x18000b002  xor     r14d, r14d
0x18000b005  jmp     short loc_18000AFB3
0x18000b007  cmp     qword ptr [r14+18h], 7
0x18000b00c  jbe     short loc_18000B011
0x18000b00e  mov     r14, [r14]
0x18000b011  mov     [rsp+160h+var_130], r14
0x18000b016  mov     [rsp+160h+var_138], r13
0x18000b01b  lea     rax, aNotDeactivatin; "Not deactivating, found psmkey %s under"...
0x18000b022  mov     [rsp+160h+Format], rax; Format
0x18000b027  lea     r9, aDroplicensesfo; "DropLicensesForAppRundown"
0x18000b02e  mov     r8d, 5B6h; unsigned int
0x18000b034  mov     rdx, rsi; char *
0x18000b037  mov     ecx, 3; unsigned int
0x18000b03c  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000b041  xor     r14d, r14d
0x18000b044  jmp     short loc_18000B05E
0x18000b046  mov     rcx, [rbx+40h]
0x18000b04a  mov     rax, [rcx]
0x18000b04d  mov     rax, [rax+20h]
0x18000b051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b056  mov     rcx, [rbp+68h]; this
0x18000b05a  test    eax, eax
0x18000b05c  js      short loc_18000B072
0x18000b05e  lea     rcx, [rsp+160h+var_110]
0x18000b063  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UPsmKeyCompat@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(void)
0x18000b068  mov     rbx, [rsp+160h+var_110]
0x18000b06d  jmp     loc_18000AF4B
0x18000b072  mov     r9d, eax; char *
0x18000b075  mov     r8, rsi; unsigned int
0x18000b078  mov     edx, 5BFh; void *
0x18000b07d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b083  mov     r9d, eax; char *
0x18000b086  mov     r8, rsi; unsigned int
0x18000b089  mov     edx, 5A8h; void *
0x18000b08e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b094  cmp     cs:qword_1800F2A68, r14
0x18000b09b  jnz     short loc_18000B0C4
0x18000b09d  call    IsCompareContentIdPresent
0x18000b0a2  test    al, al
0x18000b0a4  jz      short loc_18000B0B0
0x18000b0a6  call    cs:__imp_ShouldLicenseManagerServiceAutoStop
0x18000b0ac  test    eax, eax
0x18000b0ae  jz      short loc_18000B0C4
0x18000b0b0  mov     rcx, cs:?PushNotificationListener@@3V?$ComPtr@UIWnsListener@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IWnsListener> PushNotificationListener
0x18000b0b7  mov     rax, [rcx]
0x18000b0ba  mov     rax, [rax+20h]
0x18000b0be  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
