# Microsoft::Windows::DisplayEnhancement::Foundation::RegKeyUtils::IsPowerGuidsShimDisabled(void)

- ea: `0x180024f38`
- end: `0x180025195`
- name: `?IsPowerGuidsShimDisabled@RegKeyUtils@Foundation@DisplayEnhancement@Windows@Microsoft@@SA_NXZ`
- size: `605`
- prototype: `bool(void)`
- caller_count: `8`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023e50`
- `0x180024ca8`
- `0x1800252e8`
- `0x18007ecf0`
- `0x1800ae29c`
- `0x1800d6768`
- `0x1800d73ac`
- `0x1800da5d4`

## callees

- `0x180005860`
- `0x180009050`
- `0x18000fb14`
- `0x180013578`
- `0x18001d264`
- `0x18001f890`
- `0x18001f9d8`
- `0x180024f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025115`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025115`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool Microsoft::Windows::DisplayEnhancement::Foundation::RegKeyUtils::IsPowerGuidsShimDisabled(void)
{
  bool v0; // di
  __int64 v1; // rdx
  __int64 v2; // r8
  const WCHAR *v3; // rax
  LSTATUS v4; // ebx
  _DWORD v6[12]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v7[40]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v8; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v9[4]; // [rsp+108h] [rbp+8h] BYREF
  int v10; // [rsp+10Ch] [rbp+Ch]
  __int64 *v11; // [rsp+110h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+118h] [rbp+18h] BYREF
  char v13; // [rsp+120h] [rbp+20h]
  _BYTE v14[32]; // [rsp+130h] [rbp+30h] BYREF

  v7[0] = 5832787;
  v7[1] = 5505107;
  v7[2] = 5046341;
  v7[3] = 4391004;
  v7[4] = 7471221;
  v7[5] = 6619250;
  v7[6] = 7602286;
  v7[7] = 7274563;
  v7[8] = 7602286;
  v7[9] = 7274610;
  v7[10] = 5439596;
  v7[11] = 7602277;
  v7[12] = 5439580;
  v7[13] = 7471205;
  v7[14] = 6881398;
  v7[15] = 6619235;
  v7[16] = 6029427;
  v7[17] = 6881348;
  v7[18] = 7340147;
  v7[19] = 6357100;
  v7[20] = 4522105;
  v7[21] = 6815854;
  v7[22] = 7209057;
  v7[23] = 6619235;
  v7[24] = 6619245;
  v7[25] = 7602286;
  v7[26] = 6619219;
  v7[27] = 7733362;
  v7[28] = 6488169;
  v7[29] = 6029413;
  v7[30] = 6357072;
  v7[31] = 6357106;
  v7[32] = 6619245;
  v7[33] = 6619252;
  v7[34] = 7536754;
  v7[35] = 5242972;
  v7[36] = 7077999;
  v7[37] = 6488169;
  v7[38] = 6619241;
  v7[39] = 115;
  v6[0] = 6881348;
  v6[1] = 6357107;
  v6[2] = 7077986;
  v6[3] = 5242981;
  v6[4] = 7798895;
  v6[5] = 7471205;
  v6[6] = 7667783;
  v6[7] = 6553705;
  v6[8] = 115;
  v0 = 0;
  v8 = 0;
  std::wstring::wstring(v14, v7);
  v11 = &v8;
  phkResult = 0;
  v13 = 1;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14, v1, v2);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v11);
  if ( !v4 )
  {
    std::wstring::wstring(&v11, v6);
    Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadDwordFromRegistryIfPresent<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(
      (__int64)v9,
      (__int64)&v8,
      (__int64)&v11,
      0);
    std::wstring::_Tidy_deallocate(&v11);
    v0 = v10 != 0;
  }
  std::wstring::_Tidy_deallocate(v14);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
  return v0;
}

```

## disassembly

```asm
0x180024f38  push    rbp
0x180024f3a  push    rbx
0x180024f3b  push    rsi
0x180024f3c  push    rdi
0x180024f3d  push    r12
0x180024f3f  push    r13
0x180024f41  push    r14
0x180024f43  push    r15
0x180024f45  lea     rbp, [rsp-68h]
0x180024f4a  sub     rsp, 168h
0x180024f51  mov     rax, cs:__security_cookie
0x180024f58  xor     rax, rsp
0x180024f5b  mov     [rbp+0A0h+var_50], rax
0x180024f5f  mov     [rsp+1A0h+var_140], 590053h
0x180024f67  mov     [rsp+1A0h+var_13C], 540053h
0x180024f6f  mov     [rsp+1A0h+var_138], 4D0045h
0x180024f77  mov     [rsp+1A0h+var_134], 43005Ch
0x180024f7f  mov     [rsp+1A0h+var_130], 720075h
0x180024f87  mov     [rsp+1A0h+var_12C], 650072h
0x180024f8f  mov     [rsp+1A0h+var_128], 74006Eh
0x180024f97  mov     [rsp+1A0h+var_124], 6F0043h
0x180024f9f  mov     [rbp+0A0h+var_120], 74006Eh
0x180024fa6  mov     [rbp+0A0h+var_11C], 6F0072h
0x180024fad  mov     [rbp+0A0h+var_118], 53006Ch
0x180024fb4  mov     [rbp+0A0h+var_114], 740065h
0x180024fbb  mov     [rbp+0A0h+var_110], 53005Ch
0x180024fc2  mov     [rbp+0A0h+var_10C], 720065h
0x180024fc9  mov     [rbp+0A0h+var_108], 690076h
0x180024fd0  mov     [rbp+0A0h+var_104], 650063h
0x180024fd7  mov     [rbp+0A0h+var_100], 5C0073h
0x180024fde  mov     [rbp+0A0h+var_FC], 690044h
0x180024fe5  mov     [rbp+0A0h+var_F8], 700073h
0x180024fec  mov     [rbp+0A0h+var_F4], 61006Ch
0x180024ff3  mov     [rbp+0A0h+var_F0], 450079h
0x180024ffa  mov     [rbp+0A0h+var_EC], 68006Eh
0x180025001  mov     [rbp+0A0h+var_E8], 6E0061h
0x180025008  mov     [rbp+0A0h+var_E4], 650063h
0x18002500f  mov     [rbp+0A0h+var_E0], 65006Dh
0x180025016  mov     [rbp+0A0h+var_DC], 74006Eh
0x18002501d  mov     [rbp+0A0h+var_D8], 650053h
0x180025024  mov     [rbp+0A0h+var_D4], 760072h
0x18002502b  mov     [rbp+0A0h+var_D0], 630069h
0x180025032  mov     [rbp+0A0h+var_CC], 5C0065h
0x180025039  mov     [rbp+0A0h+var_C8], 610050h
0x180025040  mov     [rbp+0A0h+var_C4], 610072h
0x180025047  mov     [rbp+0A0h+var_C0], 65006Dh
0x18002504e  mov     [rbp+0A0h+var_BC], 650074h
0x180025055  mov     [rbp+0A0h+var_B8], 730072h
0x18002505c  mov     [rbp+0A0h+var_B4], 50005Ch
0x180025063  mov     [rbp+0A0h+var_B0], 6C006Fh
0x18002506a  mov     [rbp+0A0h+var_AC], 630069h
0x180025071  mov     [rbp+0A0h+var_A8], 650069h
0x180025078  mov     [rbp+0A0h+var_A4], 73h ; 's'
0x18002507f  xor     r12d, r12d
0x180025082  mov     [rsp+1A0h+var_170], 690044h
0x18002508a  mov     [rsp+1A0h+var_16C], 610073h
0x180025092  mov     [rsp+1A0h+var_168], 6C0062h
0x18002509a  mov     [rsp+1A0h+var_164], 500065h
0x1800250a2  mov     [rsp+1A0h+var_160], 77006Fh
0x1800250aa  mov     [rsp+1A0h+var_15C], 720065h
0x1800250b2  mov     [rsp+1A0h+var_158], 750047h
0x1800250ba  mov     [rsp+1A0h+var_154], 640069h
0x1800250c2  mov     [rsp+1A0h+var_150], 73h ; 's'
0x1800250ca  mov     dil, r12b
0x1800250cd  mov     [rbp+0A0h+var_A0], r12
0x1800250d1  lea     rdx, [rsp+1A0h+var_140]
0x1800250d6  lea     rcx, [rbp+0A0h+var_70]
0x1800250da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800250df  nop
0x1800250e0  lea     rax, [rbp+0A0h+var_A0]
0x1800250e4  mov     [rbp+0A0h+var_90], rax
0x1800250e8  mov     [rbp+0A0h+var_88], r12
0x1800250ec  mov     [rbp+0A0h+var_80], 1
0x1800250f0  lea     rcx, [rbp+0A0h+var_70]
0x1800250f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800250f9  mov     rdx, rax; lpSubKey
0x1800250fc  lea     rax, [rbp+0A0h+var_88]
0x180025100  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180025105  mov     r9d, 20019h; samDesired
0x18002510b  xor     r8d, r8d; ulOptions
0x18002510e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025115  call    cs:__imp_RegOpenKeyExW
0x18002511b  mov     ebx, eax
0x18002511d  lea     rcx, [rbp+0A0h+var_90]
0x180025121  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180025126  test    ebx, ebx
0x180025128  jnz     short loc_18002515F
0x18002512a  lea     rdx, [rsp+1A0h+var_170]
0x18002512f  lea     rcx, [rbp+0A0h+var_90]
0x180025133  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025138  nop
0x180025139  xor     r9d, r9d
0x18002513c  lea     r8, [rbp+0A0h+var_90]
0x180025140  lea     rdx, [rbp+0A0h+var_A0]
0x180025144  lea     rcx, [rbp+0A0h+var_98]
0x180025148  call    ??$ReadDwordFromRegistryIfPresent@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@RegistryHelpers@Foundation@Bluetooth@Microsoft@@SA?AU?$pair@_NK@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@K@Z; Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadDwordFromRegistryIfPresent<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,ulong)
0x18002514d  nop
0x18002514e  lea     rcx, [rbp+0A0h+var_90]
0x180025152  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025157  cmp     [rbp+0A0h+var_94], r12d
0x18002515b  setnz   dil
0x18002515f  lea     rcx, [rbp+0A0h+var_70]
0x180025163  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025168  nop
0x180025169  lea     rcx, [rbp+0A0h+var_A0]
0x18002516d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180025172  mov     al, dil
0x180025175  mov     rcx, [rbp+0A0h+var_50]
0x180025179  xor     rcx, rsp; StackCookie
0x18002517c  call    __security_check_cookie
0x180025181  add     rsp, 168h
0x180025188  pop     r15
0x18002518a  pop     r14
0x18002518c  pop     r13
0x18002518e  pop     r12
0x180025190  pop     rdi
0x180025191  pop     rsi
0x180025192  pop     rbx
0x180025193  pop     rbp
0x180025194  retn
```
