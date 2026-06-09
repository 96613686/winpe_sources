# RegistryListener::LoadExistingProductCodes(bool)

- ea: `0x180081648`
- end: `0x180081901`
- name: `?LoadExistingProductCodes@RegistryListener@@AEAAX_N@Z`
- size: `697`
- prototype: `void __fastcall(RegistryListener *__hidden this, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180081910`
- `0x180081b90`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x18002498c`
- `0x180035dac`
- `0x18005c7e4`
- `0x18007d93c`
- `0x18007e754`
- `0x180080b24`
- `0x180081648`
- `0x1800821ac`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18008177e`
- `ADVAPI32!RegGetValueW` at `0x1800817b5`
- `ADVAPI32!RegGetValueW` at `0x18008177e`
- `ADVAPI32!RegGetValueW` at `0x1800817b5`
- `ADVAPI32!RegEnumKeyExW` at `0x1800818b6`
- `ADVAPI32!RegEnumKeyExW` at `0x1800818b6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800816b5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800816b5`

## string_xrefs

- `0x1800816c9`: `pcshell\shell\cloudrestorelauncher\apprestore\lib\registrylistener.cpp`
- `0x180081705`: `pcshell\shell\cloudrestorelauncher\apprestore\lib\registrylistener.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RegistryListener::LoadExistingProductCodes(RegistryListener *this, char a2)
{
  LPCWSTR *v4; // rsi
  LPCWSTR *v5; // r14
  unsigned int v6; // eax
  DWORD v7; // r15d
  DWORD i; // edx
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned int v12; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v18; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD v19[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v20[8]; // [rsp+70h] [rbp-90h] BYREF
  char v21[8]; // [rsp+78h] [rbp-88h] BYREF
  char v22[8]; // [rsp+80h] [rbp-80h] BYREF
  char *v23; // [rsp+88h] [rbp-78h]
  char *v24; // [rsp+90h] [rbp-70h]
  char v25[16]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 pvData[256]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v28[256]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+608h]

  v4 = (LPCWSTR *)((char *)this + 24);
  v5 = (LPCWSTR *)((char *)this + 376);
  if ( (char *)this + 24 != (char *)this + 376 )
  {
    do
    {
      hkey = 0;
      v6 = RegOpenKeyExW((HKEY)*v4, v4[1], 0, 0x20019u, &hkey);
      if ( v6 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x3A,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\registrylistener.cpp",
          (const char *)v6,
          phkResult);
      }
      else
      {
        v7 = 0;
        memset_0(SubKey, 0, sizeof(SubKey));
        for ( i = 0; ; i = v7 )
        {
          cchName = 256;
          v12 = RegEnumKeyExW(hkey, i, SubKey, &cchName, 0, 0, 0, 0);
          if ( v12 == 259 )
            break;
          if ( v12 )
          {
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x55,
              (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\registrylistener.cpp",
              (const char *)v12,
              phkResulta);
          }
          else
          {
            memset_0(pvData, 0, sizeof(pvData));
            pcbData = 256;
            memset_0(v28, 0, sizeof(v28));
            v18 = 256;
            RegGetValueW(hkey, SubKey, L"DisplayName", 0x20000002u, 0, pvData, &pcbData);
            RegGetValueW(hkey, SubKey, L"Publisher", 0x20000002u, 0, v28, &v18);
            if ( a2 )
            {
              v23 = v20;
              v9 = winrt::hstring::hstring((winrt::hstring *)v20, v28);
              v24 = v21;
              v10 = winrt::hstring::hstring((winrt::hstring *)v21, pvData);
              v11 = winrt::hstring::hstring((winrt::hstring *)v22, SubKey);
              PackageInfo::PackageInfo(v19, v11, v10, v9);
              std::_Func_class<void,RegistryProductInfo const &>::operator()((char *)this + 376, v19);
              RegistryProductInfo::~RegistryProductInfo((RegistryProductInfo *)v19);
            }
            else
            {
              v19[0] = SubKey;
              v19[1] = pvData;
              v19[2] = v28;
              std::_Hash<std::_Umap_traits<winrt::hstring,std::pair<winrt::hstring,winrt::hstring>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>>,0>>::emplace<std::pair<unsigned short *,std::pair<unsigned short *,unsigned short *>>>(
                v4 + 3,
                v25,
                v19);
            }
          }
          ++v7;
          memset_0(SubKey, 0, sizeof(SubKey));
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      v4 += 11;
    }
    while ( v4 != v5 );
  }
}

```

## disassembly

```asm
0x180081648  push    rbp
0x18008164a  push    rbx
0x18008164b  push    rsi
0x18008164c  push    rdi
0x18008164d  push    r12
0x18008164f  push    r13
0x180081651  push    r14
0x180081653  push    r15
0x180081655  lea     rbp, [rsp-5C8h]
0x18008165d  sub     rsp, 6C8h
0x180081664  mov     rax, cs:__security_cookie
0x18008166b  xor     rax, rsp
0x18008166e  mov     [rbp+600h+var_50], rax
0x180081675  mov     r12b, dl
0x180081678  mov     r13, rcx
0x18008167b  lea     rsi, [rcx+18h]
0x18008167f  lea     r14, [rsi+160h]
0x180081686  cmp     rsi, r14
0x180081689  jz      loc_1800818DE
0x18008168f  xor     ebx, ebx
0x180081691  mov     edi, 200h
0x180081696  mov     [rsp+700h+hkey], rbx
0x18008169b  lea     rax, [rsp+700h+hkey]
0x1800816a0  mov     [rsp+700h+phkResult], rax; unsigned int
0x1800816a5  mov     r9d, 20019h; samDesired
0x1800816ab  xor     r8d, r8d; ulOptions
0x1800816ae  mov     rdx, [rsi+8]; lpSubKey
0x1800816b2  mov     rcx, [rsi]; hKey
0x1800816b5  call    cs:__imp_RegOpenKeyExW
0x1800816bb  mov     rcx, [rbp+608h]; this
0x1800816c2  test    eax, eax
0x1800816c4  jz      short loc_1800816DF
0x1800816c6  mov     r9d, eax; char *
0x1800816c9  lea     r8, aPcshellShellCl_35; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800816d0  mov     edx, 3Ah ; ':'; void *
0x1800816d5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800816da  jmp     loc_1800818C7
0x1800816df  mov     r15d, ebx
0x1800816e2  mov     r8, rdi; Size
0x1800816e5  xor     edx, edx; Val
0x1800816e7  lea     rcx, [rbp+600h+SubKey]; void *
0x1800816eb  call    memset_0
0x1800816f0  xor     edx, edx
0x1800816f2  jmp     loc_18008188C
0x1800816f7  mov     rcx, [rbp+608h]; this
0x1800816fe  test    eax, eax
0x180081700  jz      short loc_18008171B
0x180081702  mov     r9d, eax; char *
0x180081705  lea     r8, aPcshellShellCl_35; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x18008170c  mov     edx, 55h ; 'U'; void *
0x180081711  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180081716  jmp     loc_180081878
0x18008171b  mov     r8, rdi; Size
0x18008171e  xor     edx, edx; Val
0x180081720  lea     rcx, [rbp+600h+var_450]; void *
0x180081727  call    memset_0
0x18008172c  mov     [rsp+700h+var_6B0], 100h
0x180081734  mov     r8, rdi; Size
0x180081737  xor     edx, edx; Val
0x180081739  lea     rcx, [rbp+600h+var_250]; void *
0x180081740  call    memset_0
0x180081745  mov     [rsp+700h+var_6AC], 100h
0x18008174d  lea     rax, [rsp+700h+var_6B0]
0x180081752  mov     [rsp+700h+pcbData], rax; pcbData
0x180081757  lea     rax, [rbp+600h+var_450]
0x18008175e  mov     [rsp+700h+pvData], rax; pvData
0x180081763  mov     [rsp+700h+phkResult], rbx; pdwType
0x180081768  mov     r9d, 20000002h; dwFlags
0x18008176e  lea     r8, Value; "DisplayName"
0x180081775  lea     rdx, [rbp+600h+SubKey]; lpSubKey
0x180081779  mov     rcx, [rsp+700h+hkey]; hkey
0x18008177e  call    cs:__imp_RegGetValueW
0x180081784  lea     rax, [rsp+700h+var_6AC]
0x180081789  mov     [rsp+700h+pcbData], rax; pcbData
0x18008178e  lea     rax, [rbp+600h+var_250]
0x180081795  mov     [rsp+700h+pvData], rax; pvData
0x18008179a  mov     [rsp+700h+phkResult], rbx; pdwType
0x18008179f  mov     r9d, 20000002h; dwFlags
0x1800817a5  lea     r8, aPublisher_0; "Publisher"
0x1800817ac  lea     rdx, [rbp+600h+SubKey]; lpSubKey
0x1800817b0  mov     rcx, [rsp+700h+hkey]; hkey
0x1800817b5  call    cs:__imp_RegGetValueW
0x1800817bb  test    r12b, r12b
0x1800817be  jz      loc_180081845
0x1800817c4  lea     rax, [rsp+700h+var_690]
0x1800817c9  mov     [rbp+600h+var_678], rax
0x1800817cd  lea     rdx, [rbp+600h+var_250]; unsigned __int16 *
0x1800817d4  lea     rcx, [rsp+700h+var_690]; this
0x1800817d9  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800817de  mov     rdi, rax
0x1800817e1  lea     rax, [rsp+700h+var_688]
0x1800817e6  mov     [rbp+600h+var_670], rax
0x1800817ea  lea     rdx, [rbp+600h+var_450]; unsigned __int16 *
0x1800817f1  lea     rcx, [rsp+700h+var_688]; this
0x1800817f6  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800817fb  mov     rbx, rax
0x1800817fe  lea     rdx, [rbp+600h+SubKey]; unsigned __int16 *
0x180081802  lea     rcx, [rbp+600h+var_680]; this
0x180081806  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18008180b  nop
0x18008180c  mov     r9, rdi
0x18008180f  mov     r8, rbx
0x180081812  mov     rdx, rax
0x180081815  lea     rcx, [rsp+700h+var_6A8]
0x18008181a  call    ??0PackageInfo@@QEAA@Uhstring@winrt@@00@Z; PackageInfo::PackageInfo(winrt::hstring,winrt::hstring,winrt::hstring)
0x18008181f  nop
0x180081820  lea     rcx, [r13+178h]
0x180081827  lea     rdx, [rsp+700h+var_6A8]
0x18008182c  call    ??R?$_Func_class@XAEBURegistryProductInfo@@@std@@QEBAXAEBURegistryProductInfo@@@Z; std::_Func_class<void,RegistryProductInfo const &>::operator()(RegistryProductInfo const &)
0x180081831  nop
0x180081832  lea     rcx, [rsp+700h+var_6A8]; this
0x180081837  call    ??1RegistryProductInfo@@QEAA@XZ; RegistryProductInfo::~RegistryProductInfo(void)
0x18008183c  xor     ebx, ebx
0x18008183e  mov     edi, 200h
0x180081843  jmp     short loc_180081878
0x180081845  lea     rax, [rbp+600h+SubKey]
0x180081849  mov     [rsp+700h+var_6A8], rax
0x18008184e  lea     rax, [rbp+600h+var_450]
0x180081855  mov     [rsp+700h+var_6A0], rax
0x18008185a  lea     rax, [rbp+600h+var_250]
0x180081861  mov     [rsp+700h+var_698], rax
0x180081866  lea     rcx, [rsi+18h]
0x18008186a  lea     r8, [rsp+700h+var_6A8]
0x18008186f  lea     rdx, [rbp+600h+var_660]
0x180081873  call    ??$emplace@U?$pair@PEAGU?$pair@PEAGPEAG@std@@@std@@@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEAGU?$pair@PEAGPEAG@std@@@1@@Z; std::_Hash<std::_Umap_traits<winrt::hstring,std::pair<winrt::hstring,winrt::hstring>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>>,0>>::emplace<std::pair<ushort *,std::pair<ushort *,ushort *>>>(std::pair<ushort *,std::pair<ushort *,ushort *>> &&)
0x180081878  inc     r15d
0x18008187b  mov     r8, rdi; Size
0x18008187e  xor     edx, edx; Val
0x180081880  lea     rcx, [rbp+600h+SubKey]; void *
0x180081884  call    memset_0
0x180081889  mov     edx, r15d; dwIndex
0x18008188c  mov     [rsp+700h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180081891  mov     [rsp+700h+pcbData], rbx; lpcchClass
0x180081896  mov     [rsp+700h+pvData], rbx; lpClass
0x18008189b  mov     [rsp+700h+phkResult], rbx; unsigned int
0x1800818a0  mov     [rsp+700h+cchName], 100h
0x1800818a8  lea     r9, [rsp+700h+cchName]; lpcchName
0x1800818ad  lea     r8, [rbp+600h+SubKey]; lpName
0x1800818b1  mov     rcx, [rsp+700h+hkey]; hKey
0x1800818b6  call    cs:__imp_RegEnumKeyExW
0x1800818bc  cmp     eax, 103h
0x1800818c1  jnz     loc_1800816F7
0x1800818c7  lea     rcx, [rsp+700h+hkey]
0x1800818cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800818d1  add     rsi, 58h ; 'X'
0x1800818d5  cmp     rsi, r14
0x1800818d8  jnz     loc_180081696
0x1800818de  mov     rcx, [rbp+600h+var_50]
0x1800818e5  xor     rcx, rsp; StackCookie
0x1800818e8  call    __security_check_cookie
0x1800818ed  add     rsp, 6C8h
0x1800818f4  pop     r15
0x1800818f6  pop     r14
0x1800818f8  pop     r13
0x1800818fa  pop     r12
0x1800818fc  pop     rdi
0x1800818fd  pop     rsi
0x1800818fe  pop     rbx
0x1800818ff  pop     rbp
0x180081900  retn
```
