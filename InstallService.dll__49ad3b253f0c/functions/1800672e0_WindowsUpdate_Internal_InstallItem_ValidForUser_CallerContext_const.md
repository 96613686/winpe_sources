# WindowsUpdate::Internal::InstallItem::ValidForUser(CallerContext const &)

- ea: `0x1800672e0`
- end: `0x1800674d5`
- name: `?ValidForUser@InstallItem@Internal@WindowsUpdate@@QEAA_NAEBVCallerContext@@@Z`
- size: `501`
- prototype: `bool(WindowsUpdate::Internal::InstallItem *__hidden this, const struct CallerContext *)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180028e50`
- `0x180028f90`
- `0x180053ed0`
- `0x180059838`
- `0x180066140`

## callees

- `0x180014f18`
- `0x180024fe0`
- `0x18002c310`
- `0x18002ec2c`
- `0x180032d10`
- `0x180032e48`
- `0x18004f73c`
- `0x18004fa08`
- `0x180064220`
- `0x1800672e0`
- `0x180103494`
- `0x1801dafec`
- `0x180215010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180067312`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180067312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006734c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800673f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800674a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800674b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006734c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800673f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800674a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800674b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067441`

## string_xrefs

- `0x18006741b`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x18006747c`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall WindowsUpdate::Internal::InstallItem::ValidForUser(
        WindowsUpdate::Internal::InstallItem *this,
        const struct CallerContext *a2)
{
  HSTRING v4; // r8
  __int64 DSMAToken; // rax
  HSTRING *TokenSid; // rax
  HSTRING v7; // r8
  Microsoft::WRL::Wrappers::Details *v8; // rcx
  int v9; // ebx
  HSTRING *v10; // rdx
  Microsoft::WRL::Wrappers::Details *v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 (__fastcall *v15)(WindowsUpdate::Internal::InstallItem *, HSTRING *); // rbx
  int v16; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v18; // rax
  int v19; // eax
  HSTRING v20[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v21; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF
  HSTRING newString; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v25; // [rsp+88h] [rbp+48h] BYREF

  if ( *((_BYTE *)a2 + 24) || CallerContext::IsClientDSMA(a2) )
    return 1;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    DSMAToken = TokenHelpers::GetDSMAToken(v20);
    TokenSid = (HSTRING *)TokenHelpers::GetTokenSid(&string, DSMAToken);
    v8 = (Microsoft::WRL::Wrappers::Details *)*((_QWORD *)this + 22);
    if ( !v8 )
      v8 = (Microsoft::WRL::Wrappers::Details *)*((_QWORD *)this + 13);
    v9 = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(v8, *TokenSid, v7);
    WindowsDeleteString(string);
    string = 0;
    v20[0] = (HSTRING)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v20);
    if ( !v9 )
      return 1;
  }
  v10 = (HSTRING *)((char *)this + 176);
  if ( !*((_QWORD *)this + 22) )
    v10 = (HSTRING *)((char *)this + 104);
  v11 = (Microsoft::WRL::Wrappers::Details *)*((_QWORD *)a2 + 9);
  if ( !v11 )
    v11 = *(Microsoft::WRL::Wrappers::Details **)a2;
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(v11, *v10, v4) )
    return 1;
  if ( *((_DWORD *)this + 70) != 1 )
    return 0;
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
    (__int64)this + 336,
    v20,
    (HSTRING *)a2);
  v12 = v21;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(
                          v13,
                          v21,
                          a2)
    && v12 != *((_QWORD *)this + 42) )
  {
    return *(_BYTE *)(v12 + 40);
  }
  v25 = 0;
  v15 = *(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, HSTRING *))(*(_QWORD *)this + 112LL);
  WindowsDeleteString(0);
  v25 = 0;
  v16 = v15(this, &v25);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
      (const char *)(unsigned int)v16,
      (int)v20[0]);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a2, 0);
  v18 = WindowsGetStringRawBuffer(v25, 0);
  LOBYTE(string) = IsPackageInstalledForUser(v18, StringRawBuffer);
  newString = 0;
  v20[0] = *(HSTRING *)a2;
  v19 = Microsoft::WRL::Wrappers::HString::Set(&newString, v20);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
      (const char *)(unsigned int)v19,
      (int)v20[0]);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString,bool &>(
    (char *)this + 336,
    v20,
    &newString,
    &string);
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(v25);
  return (char)string;
}

```

## disassembly

```asm
0x1800672e0  push    rbp
0x1800672e2  push    rbx
0x1800672e3  push    rsi
0x1800672e4  push    rdi
0x1800672e5  push    r14
0x1800672e7  mov     rbp, rsp
0x1800672ea  sub     rsp, 40h
0x1800672ee  mov     rsi, rdx
0x1800672f1  mov     r14, rcx
0x1800672f4  cmp     byte ptr [rdx+18h], 0
0x1800672f8  jnz     loc_1800674C8
0x1800672fe  mov     rcx, rdx; this
0x180067301  call    ?IsClientDSMA@CallerContext@@QEBA_NXZ; CallerContext::IsClientDSMA(void)
0x180067306  test    al, al
0x180067308  jnz     loc_1800674C8
0x18006730e  lea     rdi, [r14+68h]
0x180067312  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180067318  test    al, al
0x18006731a  jz      short loc_180067376
0x18006731c  lea     rcx, [rbp+var_20]
0x180067320  call    ?GetDSMAToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetDSMAToken(void)
0x180067325  nop
0x180067326  mov     rdx, rax
0x180067329  lea     rcx, [rbp+string]
0x18006732d  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180067332  mov     rcx, [rdi+48h]
0x180067336  test    rcx, rcx
0x180067339  jnz     short loc_18006733E
0x18006733b  mov     rcx, [rdi]; this
0x18006733e  mov     rdx, [rax]; HSTRING
0x180067341  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180067346  mov     ebx, eax
0x180067348  mov     rcx, [rbp+string]; string
0x18006734c  call    cs:__imp_WindowsDeleteString
0x180067352  mov     [rbp+string], 0
0x18006735a  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180067361  mov     [rbp+var_20], rax
0x180067365  lea     rcx, [rbp+var_20]
0x180067369  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18006736e  test    ebx, ebx
0x180067370  jz      loc_1800674C8
0x180067376  lea     rdx, [rdi+48h]
0x18006737a  cmp     qword ptr [rdx], 0
0x18006737e  cmovz   rdx, rdi
0x180067382  mov     rcx, [rsi+48h]
0x180067386  test    rcx, rcx
0x180067389  jnz     short loc_18006738E
0x18006738b  mov     rcx, [rsi]; this
0x18006738e  mov     rdx, [rdx]; HSTRING
0x180067391  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180067396  test    eax, eax
0x180067398  jz      loc_1800674C8
0x18006739e  cmp     dword ptr [r14+118h], 1
0x1800673a6  jnz     loc_1800674C4
0x1800673ac  lea     rdi, [r14+150h]
0x1800673b3  mov     r8, rsi
0x1800673b6  lea     rdx, [rbp+var_20]
0x1800673ba  mov     rcx, rdi
0x1800673bd  call    ??$_Find_lower_bound@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@_NU?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@PEAX@std@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)
0x1800673c2  mov     r8, rsi
0x1800673c5  mov     rbx, [rbp+var_10]
0x1800673c9  mov     rdx, rbx
0x1800673cc  call    ??$_Lower_bound_duplicate@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@_NU?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@6@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@PEAX@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,bool>,void *> * const,Microsoft::WRL::Wrappers::HString const &)
0x1800673d1  test    al, al
0x1800673d3  jz      short loc_1800673E2
0x1800673d5  cmp     rbx, [rdi]
0x1800673d8  jz      short loc_1800673E2
0x1800673da  mov     al, [rbx+28h]
0x1800673dd  jmp     loc_1800674CA
0x1800673e2  mov     [rbp+arg_18], 0
0x1800673ea  mov     rax, [r14]
0x1800673ed  mov     rbx, [rax+70h]
0x1800673f1  xor     ecx, ecx; string
0x1800673f3  call    cs:__imp_WindowsDeleteString
0x1800673f9  mov     [rbp+arg_18], 0
0x180067401  lea     rdx, [rbp+arg_18]
0x180067405  mov     rcx, r14
0x180067408  mov     rax, rbx
0x18006740b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067410  mov     rcx, [rbp+28h]; this
0x180067414  test    eax, eax
0x180067416  jns     short loc_18006742D
0x180067418  mov     r9d, eax; char *
0x18006741b  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\installs"...
0x180067422  mov     edx, 18Bh; void *
0x180067427  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006742d  xor     edx, edx; length
0x18006742f  mov     rcx, [rsi]; string
0x180067432  call    cs:__imp_WindowsGetStringRawBuffer
0x180067438  mov     rbx, rax
0x18006743b  xor     edx, edx; length
0x18006743d  mov     rcx, [rbp+arg_18]; string
0x180067441  call    cs:__imp_WindowsGetStringRawBuffer
0x180067447  mov     rdx, rbx; unsigned __int16 *
0x18006744a  mov     rcx, rax; unsigned __int16 *
0x18006744d  call    ?IsPackageInstalledForUser@@YA_NPEBG0@Z; IsPackageInstalledForUser(ushort const *,ushort const *)
0x180067452  mov     byte ptr [rbp+string], al
0x180067455  mov     [rbp+newString], 0
0x18006745d  mov     rax, [rsi]
0x180067460  mov     [rbp+var_20], rax
0x180067464  lea     rdx, [rbp+var_20]; HSTRING *
0x180067468  lea     rcx, [rbp+newString]; newString
0x18006746c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180067471  mov     rcx, [rbp+28h]; this
0x180067475  test    eax, eax
0x180067477  jns     short loc_18006748E
0x180067479  mov     r9d, eax; char *
0x18006747c  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\installs"...
0x180067483  mov     edx, 18Eh; void *
0x180067488  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006748e  lea     r9, [rbp+string]
0x180067492  lea     r8, [rbp+newString]
0x180067496  lea     rdx, [rbp+var_20]
0x18006749a  mov     rcx, rdi
0x18006749d  call    ??$_Emplace@VHString@Wrappers@WRL@Microsoft@@AEA_N@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@_NU?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@AEA_N@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString,bool &>(Microsoft::WRL::Wrappers::HString &&,bool &)
0x1800674a2  nop
0x1800674a3  mov     rcx, [rbp+newString]; string
0x1800674a7  call    cs:__imp_WindowsDeleteString
0x1800674ad  mov     [rbp+newString], 0
0x1800674b5  mov     rcx, [rbp+arg_18]; string
0x1800674b9  call    cs:__imp_WindowsDeleteString
0x1800674bf  mov     al, byte ptr [rbp+string]
0x1800674c2  jmp     short loc_1800674CA
0x1800674c4  xor     al, al
0x1800674c6  jmp     short loc_1800674CA
0x1800674c8  mov     al, 1
0x1800674ca  add     rsp, 40h
0x1800674ce  pop     r14
0x1800674d0  pop     rdi
0x1800674d1  pop     rsi
0x1800674d2  pop     rbx
0x1800674d3  pop     rbp
0x1800674d4  retn
```
