# RegistryListener::CheckForAddedOrUpdatedProductCodes(RegistryLocation &)

- ea: `0x18008109c`
- end: `0x1800814b2`
- name: `?CheckForAddedOrUpdatedProductCodes@RegistryListener@@AEAAXAEAURegistryLocation@@@Z`
- size: `1046`
- prototype: `void __fastcall(RegistryListener *__hidden this, struct RegistryLocation *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180080f58`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180012b84`
- `0x180012c0c`
- `0x18002498c`
- `0x180035dac`
- `0x180047164`
- `0x180052244`
- `0x18005c7e4`
- `0x18007d93c`
- `0x18007e754`
- `0x180080a3c`
- `0x180080b24`
- `0x180080f14`
- `0x18008109c`
- `0x1800821ac`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180081325`
- `KERNEL32!CompareStringOrdinal` at `0x18008135a`
- `KERNEL32!CompareStringOrdinal` at `0x180081325`
- `KERNEL32!CompareStringOrdinal` at `0x18008135a`
- `ADVAPI32!RegGetValueW` at `0x1800811c6`
- `ADVAPI32!RegGetValueW` at `0x1800811fd`
- `ADVAPI32!RegGetValueW` at `0x1800811c6`
- `ADVAPI32!RegGetValueW` at `0x1800811fd`
- `ADVAPI32!RegEnumKeyExW` at `0x18008146d`
- `ADVAPI32!RegEnumKeyExW` at `0x18008146d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800810f4`
- `ADVAPI32!RegOpenKeyExW` at `0x1800810f4`

## string_xrefs

- `0x180081108`: `pcshell\shell\cloudrestorelauncher\apprestore\lib\registrylistener.cpp`
- `0x180081147`: `pcshell\shell\cloudrestorelauncher\apprestore\lib\registrylistener.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall RegistryListener::CheckForAddedOrUpdatedProductCodes(
        RegistryListener *this,
        struct RegistryLocation *a2)
{
  unsigned int v4; // eax
  DWORD v5; // r14d
  DWORD i; // edx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  RegistryProductInfo *v13; // rcx
  const WCHAR *v14; // rax
  int v15; // r9d
  int v16; // edi
  const WCHAR *v17; // rax
  int v18; // r9d
  __int64 v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v29; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v30[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v35[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v37[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v38; // [rsp+98h] [rbp-68h]
  _BYTE *v39; // [rsp+A0h] [rbp-60h]
  _BYTE *v40; // [rsp+A8h] [rbp-58h]
  _QWORD v41[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v42[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v43[24]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v45[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v46[24]; // [rsp+118h] [rbp+18h] BYREF
  WCHAR SubKey[256]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR pvData[256]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR String1[256]; // [rsp+530h] [rbp+430h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+678h]

  hkey = 0;
  v4 = RegOpenKeyExW(*(HKEY *)a2, *((LPCWSTR *)a2 + 1), 0, 0x20019u, &hkey);
  if ( !v4 )
  {
    v5 = 0;
    memset_0(SubKey, 0, sizeof(SubKey));
    for ( i = 0; ; i = v5 )
    {
      cchName = 256;
      v23 = RegEnumKeyExW(hkey, i, SubKey, &cchName, 0, 0, 0, 0);
      if ( v23 == 259 )
        goto LABEL_16;
      if ( v23 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0xFA,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\registrylistener.cpp",
          (const char *)v23,
          phkResulta);
        goto LABEL_14;
      }
      memset_0(String1, 0, sizeof(String1));
      pcbData = 256;
      memset_0(pvData, 0, sizeof(pvData));
      v29 = 256;
      RegGetValueW(hkey, SubKey, L"DisplayName", 0x20000002u, 0, String1, &pcbData);
      RegGetValueW(hkey, SubKey, L"Publisher", 0x20000002u, 0, pvData, &v29);
      winrt::hstring::hstring((winrt::hstring *)v30, SubKey);
      v8 = std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>::operator()<winrt::hstring>(
             v7,
             (__int64)v30);
      v9 = std::_Hash<std::_Umap_traits<winrt::hstring,AppMetaData const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,AppMetaData const>>,0>>::_Find_last<winrt::hstring>(
             (_QWORD *)a2 + 3,
             &v44,
             (__int64)v30,
             v8)[1];
      if ( !v9 )
        v9 = *((_QWORD *)a2 + 4);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v30);
      if ( v9 == *((_QWORD *)a2 + 4) )
        break;
      v14 = winrt::hstring::c_str((winrt::hstring *)(v9 + 24));
      v16 = CompareStringOrdinal(String1, pcbData, v14, v15, 0);
      v17 = winrt::hstring::c_str((winrt::hstring *)(v9 + 32));
      if ( CompareStringOrdinal(pvData, v29, v17, v18, 0) != 2 || v16 != 2 )
      {
        winrt::hstring::hstring((winrt::hstring *)v31, SubKey);
        v19 = *(_QWORD *)std::_Hash<std::_Umap_traits<winrt::hstring,std::pair<winrt::hstring,winrt::hstring>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>>,0>>::_Try_emplace<winrt::hstring,>(
                           (_QWORD *)a2 + 3,
                           (__int64)v46,
                           (__int64)v31);
        winrt::hstring::operator=(v19 + 24, String1);
        winrt::hstring::operator=(v19 + 32, pvData);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v31);
        v40 = v35;
        v20 = winrt::hstring::hstring((winrt::hstring *)v35, pvData);
        v39 = v36;
        v21 = winrt::hstring::hstring((winrt::hstring *)v36, String1);
        v22 = winrt::hstring::hstring((winrt::hstring *)v37, SubKey);
        PackageInfo::PackageInfo(v43, v22, v21, v20);
        std::_Func_class<void,RegistryProductInfo const &>::operator()((char *)this + 440, v43);
        v13 = (RegistryProductInfo *)v43;
        goto LABEL_13;
      }
LABEL_14:
      ++v5;
      memset_0(SubKey, 0, sizeof(SubKey));
    }
    v41[0] = SubKey;
    v41[1] = String1;
    v41[2] = pvData;
    std::_Hash<std::_Umap_traits<winrt::hstring,std::pair<winrt::hstring,winrt::hstring>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>>,0>>::emplace<std::pair<unsigned short *,std::pair<unsigned short *,unsigned short *>>>(
      (char *)a2 + 24,
      v45,
      v41);
    v38 = v32;
    v10 = winrt::hstring::hstring((winrt::hstring *)v32, pvData);
    v39 = v33;
    v11 = winrt::hstring::hstring((winrt::hstring *)v33, String1);
    v12 = winrt::hstring::hstring((winrt::hstring *)v34, SubKey);
    PackageInfo::PackageInfo(v42, v12, v11, v10);
    std::_Func_class<void,RegistryProductInfo const &>::operator()((char *)this + 376, v42);
    v13 = (RegistryProductInfo *)v42;
LABEL_13:
    RegistryProductInfo::~RegistryProductInfo(v13);
    goto LABEL_14;
  }
  wil::details::in1diag3::_Log_Win32(
    retaddr,
    (void *)0xDF,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\registrylistener.cpp",
    (const char *)v4,
    phkResult);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
}

```

## disassembly

```asm
0x18008109c  mov     [rsp-8+arg_10], rbx
0x1800810a1  push    rbp
0x1800810a2  push    rsi
0x1800810a3  push    rdi
0x1800810a4  push    r12
0x1800810a6  push    r13
0x1800810a8  push    r14
0x1800810aa  push    r15
0x1800810ac  lea     rbp, [rsp-640h]
0x1800810b4  sub     rsp, 740h
0x1800810bb  mov     rax, cs:__security_cookie
0x1800810c2  xor     rax, rsp
0x1800810c5  mov     [rbp+670h+var_40], rax
0x1800810cc  mov     rsi, rdx
0x1800810cf  mov     r13, rcx
0x1800810d2  xor     r12d, r12d
0x1800810d5  mov     [rsp+770h+hkey], r12
0x1800810da  lea     rax, [rsp+770h+hkey]
0x1800810df  mov     [rsp+770h+phkResult], rax; unsigned int
0x1800810e4  mov     r9d, 20019h; samDesired
0x1800810ea  xor     r8d, r8d; ulOptions
0x1800810ed  mov     rdx, [rdx+8]; lpSubKey
0x1800810f1  mov     rcx, [rsi]; hKey
0x1800810f4  call    cs:__imp_RegOpenKeyExW
0x1800810fa  mov     rcx, [rbp+678h]; this
0x180081101  test    eax, eax
0x180081103  jz      short loc_18008111E
0x180081105  mov     r9d, eax; char *
0x180081108  lea     r8, aPcshellShellCl_35; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x18008110f  mov     edx, 0DFh; void *
0x180081114  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180081119  jmp     loc_18008147E
0x18008111e  mov     r14d, r12d
0x180081121  xor     edx, edx; Val
0x180081123  mov     r8d, 200h; Size
0x180081129  lea     rcx, [rbp+670h+SubKey]; void *
0x18008112d  call    memset_0
0x180081132  xor     edx, edx
0x180081134  jmp     loc_180081443
0x180081139  mov     rcx, [rbp+678h]; this
0x180081140  test    eax, eax
0x180081142  jz      short loc_18008115D
0x180081144  mov     r9d, eax; char *
0x180081147  lea     r8, aPcshellShellCl_35; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x18008114e  mov     edx, 0FAh; void *
0x180081153  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180081158  jmp     loc_18008142C
0x18008115d  xor     edx, edx; Val
0x18008115f  mov     r8d, 200h; Size
0x180081165  lea     rcx, [rbp+670h+String1]; void *
0x18008116c  call    memset_0
0x180081171  mov     [rsp+770h+var_720], 100h
0x180081179  xor     edx, edx; Val
0x18008117b  mov     r8d, 200h; Size
0x180081181  lea     rcx, [rbp+670h+var_440]; void *
0x180081188  call    memset_0
0x18008118d  mov     [rsp+770h+var_71C], 100h
0x180081195  lea     rax, [rsp+770h+var_720]
0x18008119a  mov     [rsp+770h+pcbData], rax; pcbData
0x18008119f  lea     rax, [rbp+670h+String1]
0x1800811a6  mov     [rsp+770h+pvData], rax; pvData
0x1800811ab  mov     [rsp+770h+phkResult], r12; pdwType
0x1800811b0  mov     r9d, 20000002h; dwFlags
0x1800811b6  lea     r8, Value; "DisplayName"
0x1800811bd  lea     rdx, [rbp+670h+SubKey]; lpSubKey
0x1800811c1  mov     rcx, [rsp+770h+hkey]; hkey
0x1800811c6  call    cs:__imp_RegGetValueW
0x1800811cc  lea     rax, [rsp+770h+var_71C]
0x1800811d1  mov     [rsp+770h+pcbData], rax; pcbData
0x1800811d6  lea     rax, [rbp+670h+var_440]
0x1800811dd  mov     [rsp+770h+pvData], rax; pvData
0x1800811e2  mov     [rsp+770h+phkResult], r12; pdwType
0x1800811e7  mov     r9d, 20000002h; dwFlags
0x1800811ed  lea     r8, aPublisher_0; "Publisher"
0x1800811f4  lea     rdx, [rbp+670h+SubKey]; lpSubKey
0x1800811f8  mov     rcx, [rsp+770h+hkey]; hkey
0x1800811fd  call    cs:__imp_RegGetValueW
0x180081203  lea     r15, [rsi+18h]
0x180081207  lea     rdx, [rbp+670h+SubKey]; unsigned __int16 *
0x18008120b  lea     rcx, [rsp+770h+var_718]; this
0x180081210  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180081215  lea     rdx, [rsp+770h+var_718]
0x18008121a  call    ??$?RUhstring@winrt@@@?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@QEBA_KAEBUhstring@winrt@@@Z; std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>::operator()<winrt::hstring>(winrt::hstring const &)
0x18008121f  mov     r9, rax
0x180081222  lea     r8, [rsp+770h+var_718]
0x180081227  lea     rdx, [rbp+670h+var_678]
0x18008122b  mov     rcx, r15
0x18008122e  call    ??$_Find_last@Uhstring@winrt@@@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@$$CBUAppMetaData@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@$$CBUAppMetaData@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUhstring@winrt@@$$CBUAppMetaData@@@std@@PEAX@std@@@1@AEBUhstring@winrt@@_K@Z; std::_Hash<std::_Umap_traits<winrt::hstring,AppMetaData const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,AppMetaData const>>,0>>::_Find_last<winrt::hstring>(winrt::hstring const &,unsigned __int64)
0x180081233  mov     rbx, [rax+8]
0x180081237  test    rbx, rbx
0x18008123a  jnz     short loc_180081240
0x18008123c  mov     rbx, [r15+8]
0x180081240  lea     rcx, [rsp+770h+var_718]
0x180081245  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18008124a  cmp     rbx, [rsi+20h]
0x18008124e  jnz     loc_1800812F8
0x180081254  lea     rax, [rbp+670h+SubKey]
0x180081258  mov     [rbp+670h+var_6C0], rax
0x18008125c  lea     rax, [rbp+670h+String1]
0x180081263  mov     [rbp+670h+var_6B8], rax
0x180081267  lea     rax, [rbp+670h+var_440]
0x18008126e  mov     [rbp+670h+var_6B0], rax
0x180081272  lea     r8, [rbp+670h+var_6C0]
0x180081276  lea     rdx, [rbp+670h+var_668]
0x18008127a  mov     rcx, r15
0x18008127d  call    ??$emplace@U?$pair@PEAGU?$pair@PEAGPEAG@std@@@std@@@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEAGU?$pair@PEAGPEAG@std@@@1@@Z; std::_Hash<std::_Umap_traits<winrt::hstring,std::pair<winrt::hstring,winrt::hstring>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>>,0>>::emplace<std::pair<ushort *,std::pair<ushort *,ushort *>>>(std::pair<ushort *,std::pair<ushort *,ushort *>> &&)
0x180081282  lea     rax, [rsp+770h+var_708]
0x180081287  mov     [rbp+670h+var_6D8], rax
0x18008128b  lea     rdx, [rbp+670h+var_440]; unsigned __int16 *
0x180081292  lea     rcx, [rsp+770h+var_708]; this
0x180081297  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18008129c  mov     rdi, rax
0x18008129f  lea     rax, [rsp+770h+var_700]
0x1800812a4  mov     [rbp+670h+var_6D0], rax
0x1800812a8  lea     rdx, [rbp+670h+String1]; unsigned __int16 *
0x1800812af  lea     rcx, [rsp+770h+var_700]; this
0x1800812b4  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800812b9  mov     rbx, rax
0x1800812bc  lea     rdx, [rbp+670h+SubKey]; unsigned __int16 *
0x1800812c0  lea     rcx, [rsp+770h+var_6F8]; this
0x1800812c5  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800812ca  nop
0x1800812cb  mov     r9, rdi
0x1800812ce  mov     r8, rbx
0x1800812d1  mov     rdx, rax
0x1800812d4  lea     rcx, [rbp+670h+var_6A8]
0x1800812d8  call    ??0PackageInfo@@QEAA@Uhstring@winrt@@00@Z; PackageInfo::PackageInfo(winrt::hstring,winrt::hstring,winrt::hstring)
0x1800812dd  nop
0x1800812de  lea     rcx, [r13+178h]
0x1800812e5  lea     rdx, [rbp+670h+var_6A8]
0x1800812e9  call    ??R?$_Func_class@XAEBURegistryProductInfo@@@std@@QEBAXAEBURegistryProductInfo@@@Z; std::_Func_class<void,RegistryProductInfo const &>::operator()(RegistryProductInfo const &)
0x1800812ee  nop
0x1800812ef  lea     rcx, [rbp+670h+var_6A8]
0x1800812f3  jmp     loc_180081427
0x1800812f8  lea     rcx, [rbx+18h]; this
0x1800812fc  mov     rax, [rcx]
0x1800812ff  test    rax, rax
0x180081302  jz      short loc_18008130A
0x180081304  mov     r9d, [rax+4]
0x180081308  jmp     short loc_18008130D
0x18008130a  mov     r9d, r12d
0x18008130d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180081312  mov     dword ptr [rsp+770h+phkResult], r12d; bIgnoreCase
0x180081317  mov     r8, rax; lpString2
0x18008131a  mov     edx, [rsp+770h+var_720]; cchCount1
0x18008131e  lea     rcx, [rbp+670h+String1]; lpString1
0x180081325  call    cs:__imp_CompareStringOrdinal
0x18008132b  mov     edi, eax
0x18008132d  lea     rcx, [rbx+20h]; this
0x180081331  mov     r9, [rcx]
0x180081334  test    r9, r9
0x180081337  jz      short loc_18008133F
0x180081339  mov     r9d, [r9+4]
0x18008133d  jmp     short loc_180081342
0x18008133f  mov     r9d, r12d
0x180081342  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180081347  mov     dword ptr [rsp+770h+phkResult], r12d; bIgnoreCase
0x18008134c  mov     r8, rax; lpString2
0x18008134f  mov     edx, [rsp+770h+var_71C]; cchCount1
0x180081353  lea     rcx, [rbp+670h+var_440]; lpString1
0x18008135a  call    cs:__imp_CompareStringOrdinal
0x180081360  cmp     eax, 2
0x180081363  jnz     short loc_18008136D
0x180081365  cmp     edi, eax
0x180081367  jz      loc_18008142C
0x18008136d  lea     rdx, [rbp+670h+SubKey]; unsigned __int16 *
0x180081371  lea     rcx, [rsp+770h+var_710]; this
0x180081376  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18008137b  nop
0x18008137c  lea     r8, [rsp+770h+var_710]
0x180081381  lea     rdx, [rbp+670h+var_658]
0x180081385  mov     rcx, r15
0x180081388  call    ??$_Try_emplace@Uhstring@winrt@@$$V@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@PEAX@std@@_N@1@$$QEAUhstring@winrt@@@Z; std::_Hash<std::_Umap_traits<winrt::hstring,std::pair<winrt::hstring,winrt::hstring>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>>,0>>::_Try_emplace<winrt::hstring,>(winrt::hstring &&)
0x18008138d  mov     rbx, [rax]
0x180081390  lea     rdx, [rbp+670h+String1]
0x180081397  lea     rcx, [rbx+18h]
0x18008139b  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x1800813a0  lea     rcx, [rbx+20h]
0x1800813a4  lea     rdx, [rbp+670h+var_440]
0x1800813ab  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x1800813b0  nop
0x1800813b1  lea     rcx, [rsp+770h+var_710]
0x1800813b6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800813bb  lea     rax, [rbp+670h+var_6F0]
0x1800813bf  mov     [rbp+670h+var_6C8], rax
0x1800813c3  lea     rdx, [rbp+670h+var_440]; unsigned __int16 *
0x1800813ca  lea     rcx, [rbp+670h+var_6F0]; this
0x1800813ce  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800813d3  mov     rdi, rax
0x1800813d6  lea     rax, [rbp+670h+var_6E8]
0x1800813da  mov     [rbp+670h+var_6D0], rax
0x1800813de  lea     rdx, [rbp+670h+String1]; unsigned __int16 *
0x1800813e5  lea     rcx, [rbp+670h+var_6E8]; this
0x1800813e9  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800813ee  mov     rbx, rax
0x1800813f1  lea     rdx, [rbp+670h+SubKey]; unsigned __int16 *
0x1800813f5  lea     rcx, [rbp+670h+var_6E0]; this
0x1800813f9  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800813fe  nop
0x1800813ff  mov     r9, rdi
0x180081402  mov     r8, rbx
0x180081405  mov     rdx, rax
0x180081408  lea     rcx, [rbp+670h+var_690]
0x18008140c  call    ??0PackageInfo@@QEAA@Uhstring@winrt@@00@Z; PackageInfo::PackageInfo(winrt::hstring,winrt::hstring,winrt::hstring)
0x180081411  nop
0x180081412  lea     rcx, [r13+1B8h]
0x180081419  lea     rdx, [rbp+670h+var_690]
0x18008141d  call    ??R?$_Func_class@XAEBURegistryProductInfo@@@std@@QEBAXAEBURegistryProductInfo@@@Z; std::_Func_class<void,RegistryProductInfo const &>::operator()(RegistryProductInfo const &)
0x180081422  nop
0x180081423  lea     rcx, [rbp+670h+var_690]; this
0x180081427  call    ??1RegistryProductInfo@@QEAA@XZ; RegistryProductInfo::~RegistryProductInfo(void)
0x18008142c  inc     r14d
0x18008142f  xor     edx, edx; Val
0x180081431  mov     r8d, 200h; Size
0x180081437  lea     rcx, [rbp+670h+SubKey]; void *
0x18008143b  call    memset_0
0x180081440  mov     edx, r14d; dwIndex
0x180081443  mov     [rsp+770h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180081448  mov     [rsp+770h+pcbData], r12; lpcchClass
0x18008144d  mov     [rsp+770h+pvData], r12; lpClass
0x180081452  mov     [rsp+770h+phkResult], r12; unsigned int
0x180081457  mov     [rsp+770h+cchName], 100h
0x18008145f  lea     r9, [rsp+770h+cchName]; lpcchName
0x180081464  lea     r8, [rbp+670h+SubKey]; lpName
0x180081468  mov     rcx, [rsp+770h+hkey]; hKey
0x18008146d  call    cs:__imp_RegEnumKeyExW
0x180081473  cmp     eax, 103h
0x180081478  jnz     loc_180081139
0x18008147e  lea     rcx, [rsp+770h+hkey]
0x180081483  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081488  mov     rcx, [rbp+670h+var_40]
0x18008148f  xor     rcx, rsp; StackCookie
0x180081492  call    __security_check_cookie
0x180081497  mov     rbx, [rsp+770h+arg_10]
0x18008149f  add     rsp, 740h
0x1800814a6  pop     r15
0x1800814a8  pop     r14
0x1800814aa  pop     r13
0x1800814ac  pop     r12
0x1800814ae  pop     rdi
0x1800814af  pop     rsi
0x1800814b0  pop     rbp
0x1800814b1  retn
```
