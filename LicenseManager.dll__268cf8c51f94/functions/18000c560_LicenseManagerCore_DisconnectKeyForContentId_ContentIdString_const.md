# LicenseManagerCore::DisconnectKeyForContentId(ContentIdString const &)

- ea: `0x18000c560`
- end: `0x18000c704`
- name: `?DisconnectKeyForContentId@LicenseManagerCore@@EEAAXAEBVContentIdString@@@Z`
- size: `420`
- prototype: `void __fastcall(LicenseManagerCore *__hidden this, const struct ContentIdString *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004738`
- `0x18000c560`
- `0x18000c70c`
- `0x18000c760`
- `0x180013b50`
- `0x18001f5ac`
- `0x1800670f8`
- `0x180069a3c`
- `0x180076e64`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c583`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c583`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000c5fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000c5fb`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18000c5d3`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18000c5d3`

## string_xrefs

- `0x18000c618`: `Trying to remove key not in table`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LicenseManagerCore::DisconnectKeyForContentId(LicenseManagerCore *this, const WCHAR *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rcx
  __int64 *i; // rsi
  const WCHAR *v7; // r14
  __int64 v8; // r15
  __int64 v9; // r12
  __int64 *v10; // rcx
  int v11; // eax
  const WCHAR *v12; // rcx
  __int64 *v14; // r14
  __int64 *j; // rdi

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  for ( i = (__int64 *)*((_QWORD *)this + 13); i != *((__int64 **)this + 14); i += 6 )
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v7 = a2;
    else
      v7 = *(const WCHAR **)a2;
    v8 = *((_QWORD *)a2 + 2);
    v9 = i[2];
    if ( (unsigned __int8)IsCompareContentIdPresent(v5) )
    {
      if ( (unsigned __int64)i[3] <= 7 )
        v10 = i;
      else
        v10 = (__int64 *)*i;
      v11 = CompareContentId(v10, (unsigned int)v9, v7, (unsigned int)v8);
    }
    else
    {
      if ( (unsigned __int64)i[3] <= 7 )
        v12 = (const WCHAR *)i;
      else
        v12 = (const WCHAR *)*i;
      v11 = CompareStringOrdinal(v12, v9, v7, v8, 1) - 2;
    }
    if ( !v11 )
      goto LABEL_18;
  }
  i = (__int64 *)*((_QWORD *)this + 14);
LABEL_18:
  if ( i != *((__int64 **)this + 14)
    || (LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          0x58Du,
          "LicenseManagerCore::DisconnectKeyForContentId",
          (wchar_t *)L"Assert (%s): %s",
          L"(iterator != _keyTable.end())",
          L"Trying to remove key not in table"),
        i != *((__int64 **)this + 14)) )
  {
    if ( (*((_DWORD *)i + 8))-- == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)i[5] + 88LL))(i[5]);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(i + 5);
      v14 = (__int64 *)*((_QWORD *)this + 14);
      for ( j = i + 6; j != v14; j += 6 )
      {
        if ( i != j )
        {
          std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Tidy_deallocate(i);
          std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Take_contents(i, j);
        }
        *((_DWORD *)i + 8) = *((_DWORD *)j + 8);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(i + 5, j + 5);
        i += 6;
      }
      std::pair<ContentIdString,KeyEntry>::~pair<ContentIdString,KeyEntry>((ContentIdString *)(*((_QWORD *)this + 14)
                                                                                             - 48LL));
      *((_QWORD *)this + 14) -= 48LL;
      LicenseManagerCore::MaybeDisconnectTimer((LicenseManagerCore *)((char *)this - 32));
    }
  }
  if ( v4 )
    LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x18000c560  mov     [rsp+arg_8], rbx
0x18000c565  mov     [rsp+arg_18], rbp
0x18000c56a  push    rsi
0x18000c56b  push    rdi
0x18000c56c  push    r12
0x18000c56e  push    r14
0x18000c570  push    r15
0x18000c572  sub     rsp, 40h
0x18000c576  mov     rdi, rdx
0x18000c579  mov     rbp, rcx
0x18000c57c  lea     rbx, [rcx+20h]
0x18000c580  mov     rcx, rbx; lpCriticalSection
0x18000c583  call    cs:__imp_EnterCriticalSection
0x18000c589  mov     [rsp+68h+arg_10], rbx
0x18000c591  mov     rsi, [rbp+68h]
0x18000c595  cmp     rsi, [rbp+70h]
0x18000c599  jz      short loc_18000C60E
0x18000c59b  cmp     qword ptr [rdi+18h], 7
0x18000c5a0  jbe     short loc_18000C5A7
0x18000c5a2  mov     r14, [rdi]
0x18000c5a5  jmp     short loc_18000C5AA
0x18000c5a7  mov     r14, rdi
0x18000c5aa  mov     r15, [rdi+10h]
0x18000c5ae  mov     r12, [rsi+10h]
0x18000c5b2  call    IsCompareContentIdPresent
0x18000c5b7  test    al, al
0x18000c5b9  jz      short loc_18000C5DB
0x18000c5bb  cmp     qword ptr [rsi+18h], 7
0x18000c5c0  jbe     short loc_18000C5C7
0x18000c5c2  mov     rcx, [rsi]
0x18000c5c5  jmp     short loc_18000C5CA
0x18000c5c7  mov     rcx, rsi
0x18000c5ca  mov     r9d, r15d
0x18000c5cd  mov     edx, r12d
0x18000c5d0  mov     r8, r14
0x18000c5d3  call    cs:__imp_CompareContentId
0x18000c5d9  jmp     short loc_18000C604
0x18000c5db  cmp     qword ptr [rsi+18h], 7
0x18000c5e0  jbe     short loc_18000C5E7
0x18000c5e2  mov     rcx, [rsi]
0x18000c5e5  jmp     short loc_18000C5EA
0x18000c5e7  mov     rcx, rsi; lpString1
0x18000c5ea  mov     r9d, r15d; cchCount2
0x18000c5ed  mov     edx, r12d; cchCount1
0x18000c5f0  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18000c5f8  mov     r8, r14; lpString2
0x18000c5fb  call    cs:__imp_CompareStringOrdinal
0x18000c601  sub     eax, 2
0x18000c604  test    eax, eax
0x18000c606  jz      short loc_18000C612
0x18000c608  add     rsi, 30h ; '0'
0x18000c60c  jmp     short loc_18000C595
0x18000c60e  mov     rsi, [rbp+70h]
0x18000c612  cmp     rsi, [rbp+70h]
0x18000c616  jnz     short loc_18000C660
0x18000c618  lea     rax, aTryingToRemove_1; "Trying to remove key not in table"
0x18000c61f  mov     [rsp+68h+var_38], rax
0x18000c624  lea     rax, aIteratorKeytab; "(iterator != _keyTable.end())"
0x18000c62b  mov     [rsp+68h+var_40], rax
0x18000c630  lea     rax, aAssertSS; "Assert (%s): %s"
0x18000c637  mov     qword ptr [rsp+68h+bIgnoreCase], rax; Format
0x18000c63c  lea     r9, aLicensemanager_2; "LicenseManagerCore::DisconnectKeyForCon"...
0x18000c643  mov     r8d, 58Dh; unsigned int
0x18000c649  lea     rdx, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000c650  mov     ecx, 1; unsigned int
0x18000c655  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c65a  cmp     rsi, [rbp+70h]
0x18000c65e  jz      short loc_18000C6DD
0x18000c660  sub     dword ptr [rsi+20h], 1
0x18000c664  jnz     short loc_18000C6DD
0x18000c666  mov     rcx, [rsi+28h]
0x18000c66a  mov     rax, [rcx]
0x18000c66d  mov     rax, [rax+58h]
0x18000c671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c676  lea     rcx, [rsi+28h]
0x18000c67a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c67f  mov     r14, [rbp+70h]
0x18000c683  lea     rdi, [rsi+30h]
0x18000c687  jmp     short loc_18000C6BC
0x18000c689  cmp     rsi, rdi
0x18000c68c  jz      short loc_18000C6A1
0x18000c68e  mov     rcx, rsi
0x18000c691  call    ?_Tidy_deallocate@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@AEAAXXZ; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Tidy_deallocate(void)
0x18000c696  mov     rdx, rdi
0x18000c699  mov     rcx, rsi
0x18000c69c  call    ?_Take_contents@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@AEAAXAEAV12@@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Take_contents(std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>> &)
0x18000c6a1  mov     eax, [rdi+20h]
0x18000c6a4  mov     [rsi+20h], eax
0x18000c6a7  lea     rdx, [rdi+28h]
0x18000c6ab  lea     rcx, [rsi+28h]
0x18000c6af  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18000c6b4  add     rsi, 30h ; '0'
0x18000c6b8  add     rdi, 30h ; '0'
0x18000c6bc  cmp     rdi, r14
0x18000c6bf  jnz     short loc_18000C689
0x18000c6c1  mov     rcx, [rbp+70h]
0x18000c6c5  sub     rcx, 30h ; '0'; this
0x18000c6c9  call    ??1?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@XZ; std::pair<ContentIdString,KeyEntry>::~pair<ContentIdString,KeyEntry>(void)
0x18000c6ce  add     qword ptr [rbp+70h], 0FFFFFFFFFFFFFFD0h
0x18000c6d3  lea     rcx, [rbp-20h]; this
0x18000c6d7  call    ?MaybeDisconnectTimer@LicenseManagerCore@@AEAAXXZ; LicenseManagerCore::MaybeDisconnectTimer(void)
0x18000c6dc  nop
0x18000c6dd  test    rbx, rbx
0x18000c6e0  jz      short loc_18000C6EB
0x18000c6e2  mov     rcx, rbx; lpCriticalSection
0x18000c6e5  call    cs:__imp_LeaveCriticalSection
0x18000c6eb  lea     r11, [rsp+68h+var_28]
0x18000c6f0  mov     rbx, [r11+38h]
0x18000c6f4  mov     rbp, [r11+48h]
0x18000c6f8  mov     rsp, r11
0x18000c6fb  pop     r15
0x18000c6fd  pop     r14
0x18000c6ff  pop     r12
0x18000c701  pop     rdi
0x18000c702  pop     rsi
0x18000c703  retn
```
