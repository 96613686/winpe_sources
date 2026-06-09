# WpnGetDeviceVersionFromRegistry(unsigned __int64 *)

- ea: `0x18000568c`
- end: `0x180005907`
- name: `?WpnGetDeviceVersionFromRegistry@@YAXPEA_K@Z`
- size: `635`
- prototype: `void __fastcall(unsigned __int64 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004644`
- `0x1800052ac`

## callees

- `0x18000522c`
- `0x18000568c`
- `0x180005910`
- `0x180005994`
- `0x180005a08`
- `0x180005aec`
- `0x18000e5f4`
- `0x180013360`
- `0x180014160`
- `0x1800b99f0`
- `0x1800ba574`
- `0x1800bc49c`
- `0x1800f2460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000571d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000571d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005868`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005868`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005757`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800057e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005757`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800057e0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800056e8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800056e8`

## string_xrefs

- `0x180005897`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800058ac`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800058f5`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WpnGetDeviceVersionFromRegistry(unsigned __int64 *a1)
{
  WCHAR *v2; // rsi
  int PersistedRegistryLocationW; // eax
  LSTATUS v4; // eax
  char *v5; // rdi
  unsigned __int64 v6; // rcx
  unsigned int ValueW; // eax
  __int64 v8; // r8
  char *v9; // rax
  size_t v10; // rbx
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  DWORD pcbData; // [rsp+40h] [rbp-39h] BYREF
  int v14; // [rsp+44h] [rbp-35h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-31h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-29h] BYREF
  void *v17; // [rsp+58h] [rbp-21h]
  __int64 v18; // [rsp+60h] [rbp-19h]
  WCHAR *v19; // [rsp+68h] [rbp-11h]
  wchar_t String[8]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v21; // [rsp+80h] [rbp+7h]
  unsigned __int64 v22; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v14 = 260;
  v2 = (WCHAR *)operator new[](0x208u);
  v19 = v2;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"DeviceInfoDeviceVersion",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo\\DeviceVersion",
                                 v2,
                                 260);
  if ( PersistedRegistryLocationW < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x760,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)PersistedRegistryLocationW,
      (int)&v14);
  hkey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hkey);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x768,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
  pcbData = 0;
  if ( RegGetValueW(hkey, 0, L"DeviceVersionValue", 2u, 0, 0, &pcbData) || !pcbData )
  {
    *a1 = 1;
    WpnSaveDeviceVersionToRegistry();
    goto LABEL_15;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&pvData);
  v5 = (char *)v17;
  v6 = ((_BYTE *)v17 - (_BYTE *)pvData) >> 1;
  if ( pcbData < v6 )
  {
    v9 = (char *)pvData + 2 * pcbData;
    goto LABEL_22;
  }
  if ( pcbData > v6 )
  {
    if ( pcbData > (unsigned __int64)((v18 - (__int64)pvData) >> 1) )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pvData, pcbData);
      goto LABEL_9;
    }
    v10 = 2 * (pcbData - v6);
    memset_0(v17, 0, v10);
    v9 = &v5[v10];
LABEL_22:
    v17 = v9;
  }
LABEL_9:
  ValueW = RegGetValueW(hkey, 0, L"DeviceVersionValue", 2u, 0, pvData, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x778,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)ValueW,
      phkResulta);
  *(_OWORD *)String = 0;
  v21 = 0;
  v22 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)pvData + v8) );
  std::wstring::_Construct<1,unsigned short const *>(String, pvData);
  *a1 = std::stoull(String);
  if ( v22 > 7 )
    std::_Deallocate<16>(*(void **)String, 2 * v22 + 2);
  v21 = 0;
  v22 = 7;
  String[0] = 0;
  std::vector<unsigned short>::_Tidy(&pvData);
LABEL_15:
  if ( hkey )
    RegCloseKey(hkey);
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18000568c  push    rbp
0x18000568e  push    rbx
0x18000568f  push    rsi
0x180005690  push    rdi
0x180005691  push    r14
0x180005693  push    r15
0x180005695  lea     rbp, [rsp-2Fh]
0x18000569a  sub     rsp, 0A8h
0x1800056a1  mov     rax, cs:__security_cookie
0x1800056a8  xor     rax, rsp
0x1800056ab  mov     [rbp+57h+var_40], rax
0x1800056af  mov     r14, rcx
0x1800056b2  mov     [rbp+57h+var_8C], 104h
0x1800056b9  mov     ecx, 208h; unsigned __int64
0x1800056be  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800056c3  mov     rsi, rax
0x1800056c6  mov     [rbp+57h+var_68], rax
0x1800056ca  lea     rax, [rbp+57h+var_8C]
0x1800056ce  mov     [rsp+0D0h+phkResult], rax; int
0x1800056d3  mov     r9d, [rbp+57h+var_8C]
0x1800056d7  mov     r8, rsi
0x1800056da  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800056e1  lea     rcx, aDeviceinfodevi; "DeviceInfoDeviceVersion"
0x1800056e8  call    cs:__imp_GetPersistedRegistryLocationW
0x1800056ee  mov     rcx, [rbp+5Fh]; this
0x1800056f2  xor     r15d, r15d
0x1800056f5  test    eax, eax
0x1800056f7  js      loc_180005894
0x1800056fd  mov     [rbp+57h+hkey], r15
0x180005701  lea     rax, [rbp+57h+hkey]
0x180005705  mov     [rsp+0D0h+phkResult], rax; int
0x18000570a  mov     r9d, 20019h; samDesired
0x180005710  xor     r8d, r8d; ulOptions
0x180005713  mov     rdx, rsi; lpSubKey
0x180005716  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000571d  call    cs:__imp_RegOpenKeyExW
0x180005723  mov     rcx, [rbp+5Fh]; this
0x180005727  test    eax, eax
0x180005729  js      loc_1800058A9
0x18000572f  mov     [rbp+57h+var_90], r15d
0x180005733  lea     rax, [rbp+57h+var_90]
0x180005737  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18000573c  mov     [rsp+0D0h+pvData], r15; pvData
0x180005741  mov     [rsp+0D0h+phkResult], r15; pdwType
0x180005746  lea     r9d, [r15+2]; dwFlags
0x18000574a  lea     r8, ValueName; "DeviceVersionValue"
0x180005751  xor     edx, edx; lpSubKey
0x180005753  mov     rcx, [rbp+57h+hkey]; hkey
0x180005757  call    cs:__imp_RegGetValueW
0x18000575d  test    eax, eax
0x18000575f  jnz     loc_1800058BE
0x180005765  cmp     [rbp+57h+var_90], r15d
0x180005769  jz      loc_1800058BE
0x18000576f  lea     rcx, [rbp+57h+var_80]
0x180005773  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x180005778  nop
0x180005779  mov     ebx, [rbp+57h+var_90]
0x18000577c  mov     rdi, [rbp+57h+var_78]
0x180005780  mov     rdx, [rbp+57h+var_80]
0x180005784  mov     rcx, rdi
0x180005787  sub     rcx, rdx
0x18000578a  sar     rcx, 1
0x18000578d  cmp     rbx, rcx
0x180005790  jb      loc_1800058CC
0x180005796  jbe     short loc_1800057B6
0x180005798  mov     rax, [rbp+57h+var_70]
0x18000579c  sub     rax, rdx
0x18000579f  sar     rax, 1
0x1800057a2  cmp     rbx, rax
0x1800057a5  jbe     loc_1800058D9
0x1800057ab  mov     edx, ebx
0x1800057ad  lea     rcx, [rbp+57h+var_80]
0x1800057b1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800057b6  mov     rax, [rbp+57h+var_80]
0x1800057ba  lea     rcx, [rbp+57h+var_90]
0x1800057be  mov     [rsp+0D0h+pcbData], rcx; pcbData
0x1800057c3  mov     [rsp+0D0h+pvData], rax; pvData
0x1800057c8  mov     [rsp+0D0h+phkResult], r15; unsigned int
0x1800057cd  mov     r9d, 2; dwFlags
0x1800057d3  lea     r8, ValueName; "DeviceVersionValue"
0x1800057da  xor     edx, edx; lpSubKey
0x1800057dc  mov     rcx, [rbp+57h+hkey]; hkey
0x1800057e0  call    cs:__imp_RegGetValueW
0x1800057e6  mov     rcx, [rbp+5Fh]; this
0x1800057ea  test    eax, eax
0x1800057ec  jnz     loc_1800058F2
0x1800057f2  mov     rdx, [rbp+57h+var_80]
0x1800057f6  xorps   xmm0, xmm0
0x1800057f9  movups  xmmword ptr [rbp+57h+String], xmm0
0x1800057fd  mov     [rbp+57h+var_50], r15
0x180005801  mov     [rbp+57h+var_48], r15
0x180005805  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005809  inc     r8
0x18000580c  cmp     [rdx+r8*2], r15w
0x180005811  jnz     short loc_180005809
0x180005813  lea     rcx, [rbp+57h+String]
0x180005817  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000581c  nop
0x18000581d  lea     rcx, [rbp+57h+String]; String
0x180005821  call    ?stoull@std@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoull(std::wstring const &,unsigned __int64 *,int)
0x180005826  mov     [r14], rax
0x180005829  mov     rdx, [rbp+57h+var_48]
0x18000582d  cmp     rdx, 7
0x180005831  jbe     short loc_180005844
0x180005833  lea     rdx, ds:2[rdx*2]
0x18000583b  mov     rcx, qword ptr [rbp+57h+String]
0x18000583f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005844  mov     [rbp+57h+var_50], r15
0x180005848  mov     [rbp+57h+var_48], 7
0x180005850  mov     [rbp+57h+String], r15w
0x180005855  lea     rcx, [rbp+57h+var_80]
0x180005859  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18000585e  nop
0x18000585f  mov     rcx, [rbp+57h+hkey]; hKey
0x180005863  test    rcx, rcx
0x180005866  jz      short loc_18000586F
0x180005868  call    cs:__imp_RegCloseKey
0x18000586e  nop
0x18000586f  mov     rcx, rsi; pv
0x180005872  call    cs:__imp_CoTaskMemFree
0x180005878  mov     rcx, [rbp+57h+var_40]
0x18000587c  xor     rcx, rsp; StackCookie
0x18000587f  call    __security_check_cookie
0x180005884  add     rsp, 0A8h
0x18000588b  pop     r15
0x18000588d  pop     r14
0x18000588f  pop     rdi
0x180005890  pop     rsi
0x180005891  pop     rbx
0x180005892  pop     rbp
0x180005893  retn
0x180005894  mov     r9d, eax; char *
0x180005897  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000589e  mov     edx, 760h; void *
0x1800058a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800058a9  mov     r9d, eax; char *
0x1800058ac  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800058b3  mov     edx, 768h; void *
0x1800058b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800058be  mov     qword ptr [r14], 1
0x1800058c5  call    ?WpnSaveDeviceVersionToRegistry@@YAX_K@Z; WpnSaveDeviceVersionToRegistry(unsigned __int64)
0x1800058ca  jmp     short loc_18000585F
0x1800058cc  lea     rax, [rdx+rbx*2]
0x1800058d0  mov     [rbp+57h+var_78], rax
0x1800058d4  jmp     loc_1800057B6
0x1800058d9  sub     rbx, rcx
0x1800058dc  add     rbx, rbx
0x1800058df  mov     r8, rbx; Size
0x1800058e2  xor     edx, edx; Val
0x1800058e4  mov     rcx, rdi; void *
0x1800058e7  call    memset_0
0x1800058ec  lea     rax, [rbx+rdi]
0x1800058f0  jmp     short loc_1800058D0
0x1800058f2  mov     r9d, eax; char *
0x1800058f5  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800058fc  mov     edx, 778h; void *
0x180005901  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
