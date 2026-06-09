# LicenseManagerCore::UpdateRootForKey(Microsoft::WRL::ComPtr<IKeyForCore> const &,ContentIdString const &,ContentIdString const &)

- ea: `0x180040400`
- end: `0x1800405da`
- name: `?UpdateRootForKey@LicenseManagerCore@@UEAAXAEBV?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@AEBVContentIdString@@1@Z`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000b7fc`
- `0x180013b50`
- `0x180040400`
- `0x180043a20`
- `0x180076e64`
- `0x1800957d8`
- `0x180096ad4`
- `0x180096b3c`
- `0x180096bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040498`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040498`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040480`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040480`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180040458`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180040458`

## string_xrefs

- `0x1800404f7`: `Trying to remove a key from a root that it wasn't a leaf of`
- `0x18004051b`: `LicenseManagerCore::UpdateRootForKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LicenseManagerCore::UpdateRootForKey(__int64 a1, _QWORD *a2, const WCHAR *a3, __int64 a4)
{
  const WCHAR *v8; // rsi
  __int64 v9; // rbp
  __int64 v10; // r14
  const WCHAR *v11; // rcx
  int v12; // eax
  const WCHAR *v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // r14
  _QWORD *v16; // rsi
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // [rsp+90h] [rbp+18h] BYREF
  __int64 v20; // [rsp+98h] [rbp+20h]

  if ( *(_QWORD *)(a4 + 24) <= 7u )
    v8 = (const WCHAR *)a4;
  else
    v8 = *(const WCHAR **)a4;
  v9 = *(_QWORD *)(a4 + 16);
  v10 = *((_QWORD *)a3 + 2);
  if ( (unsigned __int8)IsCompareContentIdPresent(a1) )
  {
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v11 = a3;
    else
      v11 = *(const WCHAR **)a3;
    v12 = CompareContentId(v11, (unsigned int)v10, v8, (unsigned int)v9);
  }
  else
  {
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v13 = a3;
    else
      v13 = *(const WCHAR **)a3;
    v12 = CompareStringOrdinal(v13, v10, v8, v9, 1) - 2;
  }
  if ( v12 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    v20 = a1 + 64;
    if ( *((_QWORD *)a3 + 2) )
    {
      LicenseManagerCore::ContentIdMap<std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>::find(a1 + 112, &v19, a3);
      v14 = v19;
      if ( v19 != *(_QWORD *)(a1 + 120) )
      {
        v15 = (_QWORD *)(v19 + 32);
        v16 = *(_QWORD **)(v19 + 32);
        if ( v16 == *(_QWORD **)(v19 + 40) )
        {
LABEL_19:
          LogMessage(
            1u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
            0x1D1u,
            "LicenseManagerCore::UpdateRootForKey",
            (wchar_t *)L"Assert (%s): %s",
            L"(keyIterator != rootIterator->second.end())",
            L"Trying to remove a key from a root that it wasn't a leaf of");
        }
        else
        {
          while ( *v16 != *a2 )
          {
            if ( ++v16 == *(_QWORD **)(v19 + 40) )
              goto LABEL_19;
          }
        }
        if ( v16 != *(_QWORD **)(v14 + 40) )
          std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>::erase(v14 + 32, &v19, v16);
        if ( *v15 == *(_QWORD *)(v14 + 40) )
          std::vector<std::pair<ContentIdString,std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>>::erase(
            a1 + 112,
            &v19,
            v14);
      }
    }
    if ( *(_QWORD *)(a4 + 16) )
    {
      v17 = LicenseManagerCore::ContentIdMap<std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>::operator[](a1 + 112, a4);
      v18 = *(_QWORD **)(v17 + 8);
      if ( v18 == *(_QWORD **)(v17 + 16) )
      {
        std::vector<Microsoft::WRL::ComPtr<IKeyLicenseCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &>(
          v17,
          v18,
          a2);
      }
      else
      {
        *v18 = *a2;
        Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(v18);
        *(_QWORD *)(v17 + 8) += 8LL;
      }
    }
    if ( a1 != -64 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  }
}

```

## disassembly

```asm
0x180040400  mov     [rsp+arg_0], rbx
0x180040405  push    rbp
0x180040406  push    rsi
0x180040407  push    rdi
0x180040408  push    r12
0x18004040a  push    r13
0x18004040c  push    r14
0x18004040e  push    r15
0x180040410  sub     rsp, 40h
0x180040414  mov     rdi, r9
0x180040417  mov     rbx, r8
0x18004041a  mov     r12, rdx
0x18004041d  mov     r15, rcx
0x180040420  cmp     qword ptr [r9+18h], 7
0x180040425  jbe     short loc_18004042C
0x180040427  mov     rsi, [r9]
0x18004042a  jmp     short loc_18004042F
0x18004042c  mov     rsi, rdi
0x18004042f  mov     rbp, [r9+10h]
0x180040433  mov     r14, [r8+10h]
0x180040437  call    IsCompareContentIdPresent
0x18004043c  test    al, al
0x18004043e  jz      short loc_180040460
0x180040440  cmp     qword ptr [rbx+18h], 7
0x180040445  jbe     short loc_18004044C
0x180040447  mov     rcx, [rbx]
0x18004044a  jmp     short loc_18004044F
0x18004044c  mov     rcx, rbx
0x18004044f  mov     r9d, ebp
0x180040452  mov     edx, r14d
0x180040455  mov     r8, rsi
0x180040458  call    cs:__imp_CompareContentId
0x18004045e  jmp     short loc_180040489
0x180040460  cmp     qword ptr [rbx+18h], 7
0x180040465  jbe     short loc_18004046C
0x180040467  mov     rcx, [rbx]
0x18004046a  jmp     short loc_18004046F
0x18004046c  mov     rcx, rbx; lpString1
0x18004046f  mov     r9d, ebp; cchCount2
0x180040472  mov     edx, r14d; cchCount1
0x180040475  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004047d  mov     r8, rsi; lpString2
0x180040480  call    cs:__imp_CompareStringOrdinal
0x180040486  sub     eax, 2
0x180040489  test    eax, eax
0x18004048b  jz      loc_1800405C2
0x180040491  lea     rbp, [r15+40h]
0x180040495  mov     rcx, rbp; lpCriticalSection
0x180040498  call    cs:__imp_EnterCriticalSection
0x18004049e  mov     [rsp+78h+arg_18], rbp
0x1800404a6  cmp     qword ptr [rbx+10h], 0
0x1800404ab  jz      loc_18004056F
0x1800404b1  mov     r8, rbx
0x1800404b4  lea     rdx, [rsp+78h+arg_10]
0x1800404bc  lea     rcx, [r15+70h]
0x1800404c0  call    ?find@?$ContentIdMap@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@LicenseManagerCore@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@VContentIdString@@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@AEBVContentIdString@@@Z; LicenseManagerCore::ContentIdMap<std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>::find(ContentIdString const &)
0x1800404c5  mov     rbx, [rsp+78h+arg_10]
0x1800404cd  cmp     rbx, [r15+78h]
0x1800404d1  jz      loc_18004056F
0x1800404d7  lea     r14, [rbx+20h]
0x1800404db  mov     rsi, [r14]
0x1800404de  cmp     rsi, [r14+8]
0x1800404e2  jz      short loc_1800404F7
0x1800404e4  mov     rax, [r12]
0x1800404e8  cmp     [rsi], rax
0x1800404eb  jz      short loc_180040539
0x1800404ed  add     rsi, 8
0x1800404f1  cmp     rsi, [r14+8]
0x1800404f5  jnz     short loc_1800404E8
0x1800404f7  lea     rax, aTryingToRemove_0; "Trying to remove a key from a root that"...
0x1800404fe  mov     [rsp+78h+var_48], rax
0x180040503  lea     rax, aKeyiteratorRoo; "(keyIterator != rootIterator->second.en"...
0x18004050a  mov     [rsp+78h+var_50], rax
0x18004050f  lea     rax, aAssertSS; "Assert (%s): %s"
0x180040516  mov     qword ptr [rsp+78h+bIgnoreCase], rax; Format
0x18004051b  lea     r9, aLicensemanager_15; "LicenseManagerCore::UpdateRootForKey"
0x180040522  mov     r8d, 1D1h; unsigned int
0x180040528  lea     rdx, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18004052f  mov     ecx, 1; unsigned int
0x180040534  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180040539  cmp     rsi, [r14+8]
0x18004053d  jz      short loc_180040552
0x18004053f  mov     r8, rsi
0x180040542  lea     rdx, [rsp+78h+arg_10]
0x18004054a  mov     rcx, r14
0x18004054d  call    ?erase@?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IKeyForCore>>>>)
0x180040552  mov     rax, [r14+8]
0x180040556  cmp     [r14], rax
0x180040559  jnz     short loc_18004056F
0x18004055b  mov     r8, rbx
0x18004055e  lea     rdx, [rsp+78h+arg_10]
0x180040566  lea     rcx, [r15+70h]
0x18004056a  call    ?erase@?$vector@U?$pair@VContentIdString@@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@std@@V?$allocator@U?$pair@VContentIdString@@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@VContentIdString@@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@VContentIdString@@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::vector<std::pair<ContentIdString,std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::pair<ContentIdString,std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>>>>)
0x18004056f  cmp     qword ptr [rdi+10h], 0
0x180040574  jz      short loc_1800405B4
0x180040576  lea     rcx, [r15+70h]
0x18004057a  mov     rdx, rdi
0x18004057d  call    ??A?$ContentIdMap@V?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@@LicenseManagerCore@@QEAAAEAV?$vector@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyForCore@@@WRL@Microsoft@@@std@@@std@@AEBVContentIdString@@@Z; LicenseManagerCore::ContentIdMap<std::vector<Microsoft::WRL::ComPtr<IKeyForCore>>>::operator[](ContentIdString const &)
0x180040582  mov     rbx, rax
0x180040585  mov     rax, [rax+8]
0x180040589  cmp     rax, [rbx+10h]
0x18004058d  jz      short loc_1800405A5
0x18004058f  mov     rdx, [r12]
0x180040593  mov     [rax], rdx
0x180040596  mov     rcx, rax
0x180040599  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18004059e  add     qword ptr [rbx+8], 8
0x1800405a3  jmp     short loc_1800405B4
0x1800405a5  mov     r8, r12
0x1800405a8  mov     rdx, rax
0x1800405ab  mov     rcx, rbx
0x1800405ae  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIKeyLicenseCallback@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IKeyLicenseCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &>(Microsoft::WRL::ComPtr<IKeyLicenseCallback> * const,Microsoft::WRL::ComPtr<IKeyLicenseCallback> const &)
0x1800405b3  nop
0x1800405b4  test    rbp, rbp
0x1800405b7  jz      short loc_1800405C2
0x1800405b9  mov     rcx, rbp; lpCriticalSection
0x1800405bc  call    cs:__imp_LeaveCriticalSection
0x1800405c2  mov     rbx, [rsp+78h+arg_0]
0x1800405ca  add     rsp, 40h
0x1800405ce  pop     r15
0x1800405d0  pop     r14
0x1800405d2  pop     r13
0x1800405d4  pop     r12
0x1800405d6  pop     rdi
0x1800405d7  pop     rsi
0x1800405d8  pop     rbp
0x1800405d9  retn
```
