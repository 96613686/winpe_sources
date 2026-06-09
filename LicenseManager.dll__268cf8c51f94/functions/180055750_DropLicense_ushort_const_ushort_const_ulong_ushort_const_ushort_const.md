# DropLicense(ushort const *,ushort const *,ulong,ushort const *,ushort const *)

- ea: `0x180055750`
- end: `0x180055aab`
- name: `?DropLicense@@YAXPEBG0K00@Z`
- size: `859`
- prototype: `void __usercall(const unsigned __int16 *@<rcx>, LPCWCH lpString1@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063534`
- `0x18008fff0`

## callees

- `0x180004738`
- `0x18000a110`
- `0x18000b3f4`
- `0x18000b7fc`
- `0x180012dc0`
- `0x180013b50`
- `0x180018d48`
- `0x180022e80`
- `0x180028ae8`
- `0x18002bf04`
- `0x180033c04`
- `0x18003ba34`
- `0x180042bbc`
- `0x180055750`
- `0x180055ab4`
- `0x180055b04`
- `0x180056d74`
- `0x1800593bc`
- `0x180075e60`
- `0x180076e64`
- `0x18008d3d0`
- `0x180090f54`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055a4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055a4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055855`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055855`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180055a27`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180055a27`

## string_xrefs

- `0x18005589f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall DropLicense(
        const unsigned __int16 *a1,
        LPCWCH lpString1,
        __int64 a3,
        unsigned __int16 *a4,
        const unsigned __int16 *lpString2)
{
  __int64 v8; // rcx
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rcx
  bool v12; // si
  const wchar_t *v13; // rax
  _QWORD *v14; // rsi
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rdi
  int v21; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  _QWORD *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Src[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[80]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  std::wstring::wstring(v27, lpString1);
  GetKey(Src, v27, a4);
  ContentIdString::~ContentIdString((ContentIdString *)v27);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &ActiveLicensesLock);
  std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::find(
    v8,
    &v23,
    Src);
  v9 = v23;
  if ( v23 != (_QWORD *)ActiveLicenses )
  {
    if ( a1 )
    {
      PsmKeyCompat::PsmKeyCompat((PsmKeyCompat *)v29, a1);
      std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::erase(
        v9 + 8,
        v29);
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((ContentIdString *)v29);
    }
    std::wstring::wstring(v27, lpString2);
    v10 = std::_Tree<std::_Tmap_traits<std::wstring,PackageLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageLicense>>,0>>::_Find<std::wstring>(
            v9 + 10,
            v27);
    ContentIdString::~ContentIdString((ContentIdString *)v27);
    if ( v10 != v9[10] )
    {
      v12 = 1;
      if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 0) == 2 )
        v12 = v9[9] == 0;
      v13 = L"true";
      if ( !v12 )
        v13 = L"false";
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x55Au,
        "DropLicense",
        (wchar_t *)L"DropLicense - drop? %s",
        v13);
      if ( v12 )
      {
        v14 = *(_QWORD **)(v10 + 64);
        v23 = v14;
        Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v23);
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v10 + 64) + 120LL))(
                *(_QWORD *)(v10 + 64),
                *(_QWORD *)(v10 + 72));
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x560,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v15,
            bIgnoreCase);
        v16 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,PackageLicense>>>::_Extract(
                v9 + 10,
                v10);
        std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>>>(
          v17,
          v16);
        if ( !v9[11] )
        {
          if ( v9[9] )
          {
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
              0x564u,
              "DropLicense",
              (wchar_t *)L"Assert (%s): %s");
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActiveLicense>>>>,0>(
            v18,
            &v25,
            v9);
        }
        if ( a1 )
        {
          v19 = *(_QWORD *)ActiveLicenses;
          v24 = *(_QWORD *)ActiveLicenses;
          while ( !*(_BYTE *)(v19 + 25) )
          {
            v20 = (_QWORD *)(v19 + 32);
            PsmKeyCompat::PsmKeyCompat((PsmKeyCompat *)v29, a1);
            std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::find(
              v20 + 4,
              &v25,
              v29);
            std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((ContentIdString *)v29);
            if ( v25 != v20[4] )
            {
              if ( v20[3] > 7u )
                v20 = (_QWORD *)*v20;
              LogMessage(
                3u,
                "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                0x573u,
                "DropLicense",
                (wchar_t *)L"Not deactivating, found psmkey %s under key %s",
                a1,
                v20);
              goto LABEL_24;
            }
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(&v24);
            v19 = v24;
          }
        }
        v21 = (*(__int64 (__fastcall **)(_QWORD *))(*v14 + 32LL))(v14);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x57C,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v21,
            bIgnoreCase);
LABEL_24:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
      }
    }
    if ( !qword_1800F2A68
      && (!(unsigned __int8)IsCompareContentIdPresent(v11) || (unsigned int)ShouldLicenseManagerServiceAutoStop()) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)PushNotificationListener + 32LL))(PushNotificationListener);
    }
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  ContentIdString::~ContentIdString((ContentIdString *)Src);
}

```

## disassembly

```asm
0x180055750  push    rbp
0x180055752  push    rbx
0x180055753  push    rsi
0x180055754  push    rdi
0x180055755  push    r12
0x180055757  push    r13
0x180055759  push    r14
0x18005575b  push    r15
0x18005575d  lea     rbp, [rsp-8]
0x180055762  sub     rsp, 108h
0x180055769  mov     rax, cs:__security_cookie
0x180055770  xor     rax, rsp
0x180055773  mov     [rbp+40h+var_50], rax
0x180055777  mov     rdi, r9
0x18005577a  mov     ebx, r8d
0x18005577d  mov     r13, rdx
0x180055780  mov     r14, rcx
0x180055783  mov     r12, [rbp+40h+lpString2]
0x180055787  lea     rcx, [rsp+140h+var_E0]
0x18005578c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055791  nop
0x180055792  mov     r9d, ebx
0x180055795  mov     r8, rdi; void *
0x180055798  lea     rdx, [rsp+140h+var_E0]; void *
0x18005579d  lea     rcx, [rbp+40h+Src]; Src
0x1800557a1  call    ?GetKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@PEBGK@Z; GetKey(std::wstring const &,ushort const *,ulong)
0x1800557a6  nop
0x1800557a7  lea     rcx, [rsp+140h+var_E0]; this
0x1800557ac  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800557b1  lea     rdx, ?ActiveLicensesLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock ActiveLicensesLock
0x1800557b8  lea     rcx, [rsp+140h+SRWLock]
0x1800557bd  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800557c2  nop
0x1800557c3  lea     r8, [rbp+40h+Src]
0x1800557c7  lea     rdx, [rsp+140h+var_100]
0x1800557cc  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::find(std::wstring const &)
0x1800557d1  mov     rbx, [rsp+140h+var_100]
0x1800557d6  cmp     rbx, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x1800557dd  jz      loc_180055A45
0x1800557e3  test    r14, r14
0x1800557e6  jz      short loc_18005580A
0x1800557e8  mov     rdx, r14; unsigned __int16 *
0x1800557eb  lea     rcx, [rbp+40h+var_A0]; this
0x1800557ef  call    ??0PsmKeyCompat@@QEAA@PEBG@Z; PsmKeyCompat::PsmKeyCompat(ushort const *)
0x1800557f4  lea     rcx, [rbx+40h]
0x1800557f8  lea     rdx, [rbp+40h+var_A0]
0x1800557fc  call    ?erase@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@QEAA_KAEBUPsmKeyCompat@@@Z; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::erase(PsmKeyCompat const &)
0x180055801  lea     rcx, [rbp+40h+var_A0]; this
0x180055805  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18005580a  lea     r15, [rbx+50h]
0x18005580e  mov     rdx, r12
0x180055811  lea     rcx, [rsp+140h+var_E0]
0x180055816  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005581b  lea     rdx, [rsp+140h+var_E0]
0x180055820  mov     rcx, r15
0x180055823  call    ??$_Find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PackageLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageLicense>>,0>>::_Find<std::wstring>(std::wstring const &)
0x180055828  mov     rdi, rax
0x18005582b  lea     rcx, [rsp+140h+var_E0]; this
0x180055830  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180055835  cmp     rdi, [r15]
0x180055838  jz      loc_180055A14
0x18005583e  mov     sil, 1
0x180055841  mov     [rsp+140h+bIgnoreCase], 0; bIgnoreCase
0x180055849  or      edx, 0FFFFFFFFh; cchCount1
0x18005584c  mov     r9d, edx; cchCount2
0x18005584f  mov     r8, r12; lpString2
0x180055852  mov     rcx, r13; lpString1
0x180055855  call    cs:__imp_CompareStringOrdinal
0x18005585b  cmp     eax, 2
0x18005585e  jnz     short loc_180055869
0x180055860  cmp     qword ptr [rbx+48h], 0
0x180055865  setz    sil
0x180055869  lea     rcx, aFalse_0; "false"
0x180055870  lea     rax, aTrue; "true"
0x180055877  test    sil, sil
0x18005587a  cmovz   rax, rcx
0x18005587e  mov     [rsp+140h+var_118], rax
0x180055883  lea     rax, aDroplicenseDro_0; "DropLicense - drop? %s"
0x18005588a  mov     qword ptr [rsp+140h+bIgnoreCase], rax; int
0x18005588f  lea     r13, aDroplicense; "DropLicense"
0x180055896  mov     r9, r13; char *
0x180055899  mov     r8d, 55Ah; unsigned int
0x18005589f  lea     r12, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800558a6  mov     rdx, r12; char *
0x1800558a9  mov     ecx, 3; unsigned int
0x1800558ae  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800558b3  test    sil, sil
0x1800558b6  jz      loc_180055A14
0x1800558bc  mov     rsi, [rdi+40h]
0x1800558c0  mov     [rsp+140h+var_100], rsi
0x1800558c5  lea     rcx, [rsp+140h+var_100]
0x1800558ca  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x1800558cf  nop
0x1800558d0  mov     rcx, [rdi+40h]
0x1800558d4  mov     rax, [rcx]
0x1800558d7  mov     rdx, [rdi+48h]
0x1800558db  mov     rax, [rax+78h]
0x1800558df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558e4  mov     rcx, [rbp+48h]; this
0x1800558e8  test    eax, eax
0x1800558ea  jns     short loc_1800558FD
0x1800558ec  mov     r9d, eax; char *
0x1800558ef  mov     r8, r12; unsigned int
0x1800558f2  mov     edx, 560h; void *
0x1800558f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800558fd  mov     rdx, rdi
0x180055900  mov     rcx, r15
0x180055903  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,PackageLicense>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,PackageLicense>>>,std::_Iterator_base0>)
0x180055908  mov     rdx, rax
0x18005590b  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPackageLicense@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *>> &,std::_Tree_node<std::pair<std::wstring const,PackageLicense>,void *> *)
0x180055910  cmp     qword ptr [rbx+58h], 0
0x180055915  jnz     short loc_18005596A
0x180055917  cmp     qword ptr [rbx+48h], 0
0x18005591c  jz      short loc_18005595D
0x18005591e  lea     rax, aPosSecondPsmke; "pos->second.PsmKeys.empty()"
0x180055925  mov     [rsp+140h+var_110], rax
0x18005592a  lea     rax, a0; "0"
0x180055931  mov     [rsp+140h+var_118], rax
0x180055936  lea     rax, aAssertSS; "Assert (%s): %s"
0x18005593d  mov     qword ptr [rsp+140h+bIgnoreCase], rax; int
0x180055942  mov     r9, r13; char *
0x180055945  mov     r8d, 564h; unsigned int
0x18005594b  mov     rdx, r12; char *
0x18005594e  mov     ecx, 1; unsigned int
0x180055953  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180055958  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005595d  mov     r8, rbx
0x180055960  lea     rdx, [rsp+140h+var_F0]
0x180055965  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ActiveLicense,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ActiveLicense>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActiveLicense>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActiveLicense>>>>)
0x18005596a  test    r14, r14
0x18005596d  jz      loc_180055A7F
0x180055973  mov     rax, cs:?ActiveLicenses@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveLicense@@@std@@@2@@std@@A; std::map<std::wstring,ActiveLicense> ActiveLicenses
0x18005597a  mov     rax, [rax]
0x18005597d  mov     [rsp+140h+var_F8], rax
0x180055982  cmp     byte ptr [rax+19h], 0
0x180055986  jnz     loc_180055A7F
0x18005598c  lea     rdi, [rax+20h]
0x180055990  mov     rdx, r14; unsigned __int16 *
0x180055993  lea     rcx, [rbp+40h+var_A0]; this
0x180055997  call    ??0PsmKeyCompat@@QEAA@PEBG@Z; PsmKeyCompat::PsmKeyCompat(ushort const *)
0x18005599c  lea     r8, [rbp+40h+var_A0]
0x1800559a0  lea     rdx, [rsp+140h+var_F0]
0x1800559a5  lea     rcx, [rdi+20h]
0x1800559a9  call    ?find@?$_Tree@V?$_Tset_traits@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UPsmKeyCompat@@@std@@@std@@@2@AEBUPsmKeyCompat@@@Z; std::_Tree<std::_Tset_traits<PsmKeyCompat,std::less<PsmKeyCompat>,std::allocator<PsmKeyCompat>,0>>::find(PsmKeyCompat const &)
0x1800559ae  lea     rcx, [rbp+40h+var_A0]; this
0x1800559b2  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800559b7  mov     rax, [rdi+20h]
0x1800559bb  cmp     [rsp+140h+var_F0], rax
0x1800559c0  jnz     short loc_1800559D3
0x1800559c2  lea     rcx, [rsp+140h+var_F8]
0x1800559c7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UPsmKeyCompat@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<PsmKeyCompat>>,std::_Iterator_base0>::operator++(void)
0x1800559cc  mov     rax, [rsp+140h+var_F8]
0x1800559d1  jmp     short loc_180055982
0x1800559d3  cmp     qword ptr [rdi+18h], 7
0x1800559d8  jbe     short loc_1800559DD
0x1800559da  mov     rdi, [rdi]
0x1800559dd  mov     [rsp+140h+var_110], rdi
0x1800559e2  mov     [rsp+140h+var_118], r14
0x1800559e7  lea     rax, aNotDeactivatin; "Not deactivating, found psmkey %s under"...
0x1800559ee  mov     qword ptr [rsp+140h+bIgnoreCase], rax; Format
0x1800559f3  mov     r9, r13; char *
0x1800559f6  mov     r8d, 573h; unsigned int
0x1800559fc  mov     rdx, r12; char *
0x1800559ff  mov     ecx, 3; unsigned int
0x180055a04  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180055a09  nop
0x180055a0a  lea     rcx, [rsp+140h+var_100]
0x180055a0f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055a14  cmp     cs:qword_1800F2A68, 0
0x180055a1c  jnz     short loc_180055A45
0x180055a1e  call    IsCompareContentIdPresent
0x180055a23  test    al, al
0x180055a25  jz      short loc_180055A31
0x180055a27  call    cs:__imp_ShouldLicenseManagerServiceAutoStop
0x180055a2d  test    eax, eax
0x180055a2f  jz      short loc_180055A45
0x180055a31  mov     rcx, cs:?PushNotificationListener@@3V?$ComPtr@UIWnsListener@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IWnsListener> PushNotificationListener
0x180055a38  mov     rax, [rcx]
0x180055a3b  mov     rax, [rax+20h]
0x180055a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a44  nop
0x180055a45  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x180055a4a  test    rcx, rcx
0x180055a4d  jz      short loc_180055A56
0x180055a4f  call    cs:__imp_ReleaseSRWLockExclusive
0x180055a55  nop
0x180055a56  lea     rcx, [rbp+40h+Src]; this
0x180055a5a  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180055a5f  mov     rcx, [rbp+40h+var_50]
0x180055a63  xor     rcx, rsp; StackCookie
0x180055a66  call    __security_check_cookie
0x180055a6b  add     rsp, 108h
0x180055a72  pop     r15
0x180055a74  pop     r14
0x180055a76  pop     r13
0x180055a78  pop     r12
0x180055a7a  pop     rdi
0x180055a7b  pop     rsi
0x180055a7c  pop     rbx
0x180055a7d  pop     rbp
0x180055a7e  retn
0x180055a7f  mov     rax, [rsi]
0x180055a82  mov     rcx, rsi
0x180055a85  mov     rax, [rax+20h]
0x180055a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a8e  mov     rcx, [rbp+48h]; this
0x180055a92  test    eax, eax
0x180055a94  jns     loc_180055A0A
0x180055a9a  mov     r9d, eax; char *
0x180055a9d  mov     r8, r12; unsigned int
0x180055aa0  mov     edx, 57Ch; void *
0x180055aa5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
