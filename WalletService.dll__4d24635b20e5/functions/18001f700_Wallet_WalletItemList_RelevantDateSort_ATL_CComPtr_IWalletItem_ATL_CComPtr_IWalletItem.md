# Wallet::WalletItemList::RelevantDateSort(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &)

- ea: `0x18001f700`
- end: `0x18001f7b6`
- name: `?RelevantDateSort@WalletItemList@Wallet@@SA_NAEAV?$CComPtr@UIWalletItem@@@ATL@@0@Z`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001f700`
- `0x180036b60`
- `0x18003996c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f776`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f776`

## pseudocode

```c
bool __fastcall Wallet::WalletItemList::RelevantDateSort(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rcx
  int TFileTime; // ebx
  int v5; // eax
  int v6; // edx
  int IsWalletFiletimePast; // ebx
  __int64 v8; // rdx
  int v9; // eax
  FILETIME *p_FileTime2; // rdx
  FILETIME *p_FileTime1; // rcx
  LONG v12; // eax
  int v13; // ecx
  FILETIME FileTime1; // [rsp+30h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a1;
  FileTime2 = 0;
  FileTime1 = 0;
  TFileTime = Wallet::Utils::GetTFileTimeProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                v2,
                165,
                &FileTime2);
  v5 = Wallet::Utils::GetTFileTimeProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
         *a2,
         165,
         &FileTime1);
  v6 = v5;
  if ( TFileTime < 0 )
  {
    v12 = 0;
    if ( v6 >= 0 )
      v12 = -1;
    goto LABEL_13;
  }
  if ( v5 < 0 )
  {
LABEL_10:
    v13 = 1;
    return v13 <= 0;
  }
  IsWalletFiletimePast = Wallet::Utils::IsWalletFiletimePast(&FileTime2, (unsigned int)v5);
  v9 = Wallet::Utils::IsWalletFiletimePast(&FileTime1, v8);
  if ( IsWalletFiletimePast )
  {
    if ( v9 )
    {
      p_FileTime2 = &FileTime2;
      p_FileTime1 = &FileTime1;
LABEL_6:
      v12 = CompareFileTime(p_FileTime1, p_FileTime2);
LABEL_13:
      v13 = v12;
      return v13 <= 0;
    }
    goto LABEL_10;
  }
  if ( !v9 )
  {
    p_FileTime2 = &FileTime1;
    p_FileTime1 = &FileTime2;
    goto LABEL_6;
  }
  v13 = -1;
  return v13 <= 0;
}

```

## disassembly

```asm
0x18001f700  mov     rax, rsp
0x18001f703  mov     [rax+18h], rbx
0x18001f707  push    rdi
0x18001f708  sub     rsp, 20h
0x18001f70c  mov     rcx, [rcx]
0x18001f70f  lea     r8, [rax+10h]
0x18001f713  mov     rdi, rdx
0x18001f716  mov     qword ptr [rax+10h], 0
0x18001f71e  mov     edx, 0A5h
0x18001f723  mov     qword ptr [rax+8], 0
0x18001f72b  call    ??$GetTFileTimeProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAU_FILETIME@@@Z; Wallet::Utils::GetTFileTimeProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,_FILETIME *)
0x18001f730  mov     rcx, [rdi]
0x18001f733  lea     r8, [rsp+28h+FileTime1]
0x18001f738  mov     edx, 0A5h
0x18001f73d  mov     ebx, eax
0x18001f73f  call    ??$GetTFileTimeProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAU_FILETIME@@@Z; Wallet::Utils::GetTFileTimeProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,_FILETIME *)
0x18001f744  mov     edx, eax
0x18001f746  test    ebx, ebx
0x18001f748  js      short loc_18001F79A
0x18001f74a  test    eax, eax
0x18001f74c  js      short loc_18001F793
0x18001f74e  lea     rcx, [rsp+28h+FileTime2]
0x18001f753  call    ?IsWalletFiletimePast@Utils@Wallet@@YAHAEBU_FILETIME@@W4TimeOption@12@@Z; Wallet::Utils::IsWalletFiletimePast(_FILETIME const &,Wallet::Utils::TimeOption)
0x18001f758  lea     rcx, [rsp+28h+FileTime1]
0x18001f75d  mov     ebx, eax
0x18001f75f  call    ?IsWalletFiletimePast@Utils@Wallet@@YAHAEBU_FILETIME@@W4TimeOption@12@@Z; Wallet::Utils::IsWalletFiletimePast(_FILETIME const &,Wallet::Utils::TimeOption)
0x18001f764  test    ebx, ebx
0x18001f766  jz      short loc_18001F77E
0x18001f768  test    eax, eax
0x18001f76a  jz      short loc_18001F793
0x18001f76c  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x18001f771  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18001f776  call    cs:__imp_CompareFileTime
0x18001f77c  jmp     short loc_18001F7A4
0x18001f77e  test    eax, eax
0x18001f780  jz      short loc_18001F787
0x18001f782  or      ecx, 0FFFFFFFFh
0x18001f785  jmp     short loc_18001F7A6
0x18001f787  lea     rdx, [rsp+28h+FileTime1]
0x18001f78c  lea     rcx, [rsp+28h+FileTime2]
0x18001f791  jmp     short loc_18001F776
0x18001f793  mov     ecx, 1
0x18001f798  jmp     short loc_18001F7A6
0x18001f79a  xor     eax, eax
0x18001f79c  or      ecx, 0FFFFFFFFh
0x18001f79f  test    edx, edx
0x18001f7a1  cmovns  eax, ecx
0x18001f7a4  mov     ecx, eax
0x18001f7a6  mov     rbx, [rsp+28h+arg_10]
0x18001f7ab  test    ecx, ecx
0x18001f7ad  setle   al
0x18001f7b0  add     rsp, 20h
0x18001f7b4  pop     rdi
0x18001f7b5  retn
```
