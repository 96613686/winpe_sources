# ProvResults::UpdatePendingResultInternal(ushort const *,long)

- ea: `0x1800abf44`
- end: `0x1800ac272`
- name: `?UpdatePendingResultInternal@ProvResults@@CA_NPEBGJ@Z`
- size: `814`
- prototype: `bool __fastcall(LPCWSTR lpSubKey, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x1800ab7a4`

## callees

- `0x180004d50`
- `0x18000d724`
- `0x180015e4c`
- `0x180015f70`
- `0x1800168d0`
- `0x180016918`
- `0x1800169b8`
- `0x180019ae4`
- `0x18003ec00`
- `0x180092784`
- `0x1800a8d18`
- `0x1800ab460`
- `0x1800abf44`
- `0x1800ac314`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ac055`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ac055`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac0ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac10f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac1c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac213`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac0ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac10f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac1c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac213`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abfdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abfdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ProvResults::UpdatePendingResultInternal(LPCWSTR lpSubKey, int a2)
{
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // eax
  unsigned int ValueW; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  unsigned int v8; // ecx
  unsigned int v9; // edx
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v13; // eax
  int v14; // eax
  const BYTE *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-19h]
  unsigned int phkResulta; // [rsp+20h] [rbp-19h]
  unsigned int phkResultb; // [rsp+20h] [rbp-19h]
  unsigned int phkResultc; // [rsp+20h] [rbp-19h]
  unsigned int phkResultd; // [rsp+20h] [rbp-19h]
  unsigned int phkResulte; // [rsp+20h] [rbp-19h]
  BYTE Data[4]; // [rsp+40h] [rbp+7h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+Fh] BYREF
  BYTE pvData[4]; // [rsp+4Ch] [rbp+13h] BYREF
  HKEY hkey; // [rsp+50h] [rbp+17h] BYREF
  unsigned __int64 v29; // [rsp+58h] [rbp+1Fh] BYREF
  HKEY hKey; // [rsp+60h] [rbp+27h] BYREF
  _BYTE v31[16]; // [rsp+68h] [rbp+2Fh] BYREF
  __int64 v32; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  *(_DWORD *)Data = a2;
  std::wstring::wstring(v31);
  if ( *(int *)Data >= 0 )
  {
    v3 = L"Provisioning pending";
    if ( *(_DWORD *)Data != 44761091 )
      v3 = L"Provisioning succeeded";
  }
  else
  {
    v3 = L"Provisioning failed";
  }
  std::wstring::operator=(v31, v3);
  ProvResults::GetRootKey(&hKey, 0x20019u);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 3u, &hkey);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v4,
      phkResult);
  *(_DWORD *)pvData = 0;
  if ( *(int *)Data < 0 || *(_DWORD *)Data == 44761091 )
  {
    cbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"NumFailures", 0x10u, 0, pvData, &cbData);
    if ( ValueW )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, v6, v7, (const char *)ValueW, phkResulta);
      v8 = 0;
      *(_DWORD *)pvData = 0;
    }
    else
    {
      v8 = *(_DWORD *)pvData;
    }
    if ( *(int *)Data < 0 )
    {
      v9 = v8 + 1;
      v10 = -1;
      if ( v8 + 1 >= v8 )
        v10 = v8 + 1;
      *(_DWORD *)pvData = v10;
      if ( v9 < v8 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1EE,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          v9 < v8 ? (const char *)0x80070216LL : 0,
          phkResulta);
    }
  }
  v11 = RegSetValueExW(hkey, L"LastResult", 0, 4u, Data, 4u);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v11,
      phkResultb);
  v12 = RegSetValueExW(hkey, L"NumFailures", 0, 4u, pvData, 4u);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v12,
      phkResultc);
  v29 = v32 + 1;
  cbData = 0;
  v13 = ULongLongMult(v32 + 1, 2u, &v29);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)(unsigned int)v13,
      phkResultc);
  v14 = ULongLongToULong(v29, &cbData);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)(unsigned int)v14,
      phkResultc);
  v15 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
  v16 = RegSetValueExW(hkey, L"Message", 0, 1u, v15, cbData);
  if ( v16 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v16,
      phkResultd);
  if ( *(_DWORD *)Data != 44761091 )
  {
    cbData = 3;
    v17 = RegSetValueExW(hkey, L"State", 0, 4u, (const BYTE *)&cbData, 4u);
    if ( v17 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v17,
        phkResulte);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::~wstring(v31);
  return 1;
}

```

## disassembly

```asm
0x1800abf44  mov     [rsp-8+arg_10], rbx
0x1800abf49  push    rbp
0x1800abf4a  lea     rbp, [rsp-57h]
0x1800abf4f  sub     rsp, 90h
0x1800abf56  mov     rax, cs:__security_cookie
0x1800abf5d  xor     rax, rsp
0x1800abf60  mov     [rbp+57h+var_8], rax
0x1800abf64  mov     rbx, rcx
0x1800abf67  mov     dword ptr [rbp+57h+Data], edx
0x1800abf6a  lea     rcx, [rbp+57h+var_28]
0x1800abf6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800abf73  nop
0x1800abf74  mov     eax, dword ptr [rbp+57h+Data]
0x1800abf77  test    eax, eax
0x1800abf79  jns     short loc_1800ABF84
0x1800abf7b  lea     rdx, ?gc_provresultProvisioningFailed@@3QBGB; "Provisioning failed"
0x1800abf82  jmp     short loc_1800ABF9B
0x1800abf84  lea     rdx, ?gc_provresultProvisioningPending@@3QBGB; "Provisioning pending"
0x1800abf8b  lea     rcx, ?gc_provresultProvisioningSucceeded@@3QBGB; "Provisioning succeeded"
0x1800abf92  cmp     eax, 2AB0003h
0x1800abf97  cmovnz  rdx, rcx
0x1800abf9b  lea     rcx, [rbp+57h+var_28]
0x1800abf9f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800abfa4  mov     edx, 20019h; samDesired
0x1800abfa9  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800abfad  call    ?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ProvResults::GetRootKey(ulong)
0x1800abfb2  nop
0x1800abfb3  mov     [rbp+57h+hkey], 0
0x1800abfbb  xor     edx, edx
0x1800abfbd  lea     rcx, [rbp+57h+hkey]
0x1800abfc1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800abfc6  lea     rax, [rbp+57h+hkey]
0x1800abfca  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800abfcf  mov     r9d, 3; samDesired
0x1800abfd5  xor     r8d, r8d; ulOptions
0x1800abfd8  mov     rdx, rbx; lpSubKey
0x1800abfdb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800abfdf  call    cs:__imp_RegOpenKeyExW
0x1800abfe5  mov     rcx, [rbp+5Fh]; this
0x1800abfe9  test    eax, eax
0x1800abfeb  jz      short loc_1800AC002
0x1800abfed  mov     r9d, eax; char *
0x1800abff0  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800abff7  mov     edx, 1DAh; void *
0x1800abffc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ac002  mov     dword ptr [rbp+57h+var_44], 0
0x1800ac009  mov     ebx, 4
0x1800ac00e  test    dword ptr [rbp+57h+Data], 80000000h
0x1800ac015  jnz     short loc_1800AC024
0x1800ac017  cmp     dword ptr [rbp+57h+Data], 2AB0003h
0x1800ac01e  jnz     loc_1800AC0B0
0x1800ac024  mov     [rbp+57h+cbData], ebx
0x1800ac027  lea     rax, [rbp+57h+cbData]
0x1800ac02b  mov     [rsp+90h+pcbData], rax; pcbData
0x1800ac030  lea     rax, [rbp+57h+var_44]
0x1800ac034  mov     [rsp+90h+pvData], rax; pvData
0x1800ac039  mov     [rsp+90h+phkResult], 0; int
0x1800ac042  mov     r9d, 10h; dwFlags
0x1800ac048  lea     r8, aNumfailures; "NumFailures"
0x1800ac04f  xor     edx, edx; lpSubKey
0x1800ac051  mov     rcx, [rbp+57h+hkey]; hkey
0x1800ac055  call    cs:__imp_RegGetValueW
0x1800ac05b  mov     rcx, [rbp+5Fh]; this
0x1800ac05f  test    eax, eax
0x1800ac061  jz      short loc_1800AC072
0x1800ac063  mov     r9d, eax; char *
0x1800ac066  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800ac06b  xor     ecx, ecx
0x1800ac06d  mov     dword ptr [rbp+57h+var_44], ecx
0x1800ac070  jmp     short loc_1800AC075
0x1800ac072  mov     ecx, dword ptr [rbp+57h+var_44]
0x1800ac075  cmp     dword ptr [rbp+57h+Data], 0
0x1800ac079  jge     short loc_1800AC0B0
0x1800ac07b  lea     edx, [rcx+1]
0x1800ac07e  or      eax, 0FFFFFFFFh
0x1800ac081  cmp     edx, ecx
0x1800ac083  cmovnb  eax, edx
0x1800ac086  sbb     r9d, r9d
0x1800ac089  and     r9d, 80070216h; char *
0x1800ac090  mov     dword ptr [rbp+57h+var_44], eax
0x1800ac093  mov     rax, [rbp+5Fh]
0x1800ac097  cmp     edx, ecx
0x1800ac099  jnb     short loc_1800AC0B0
0x1800ac09b  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac0a2  mov     edx, 1EEh; void *
0x1800ac0a7  mov     rcx, rax; this
0x1800ac0aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ac0b0  mov     dword ptr [rsp+90h+pvData], ebx; cbData
0x1800ac0b4  lea     rax, [rbp+57h+Data]
0x1800ac0b8  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800ac0bd  mov     r9d, ebx; dwType
0x1800ac0c0  xor     r8d, r8d; Reserved
0x1800ac0c3  lea     rdx, aLastresult; "LastResult"
0x1800ac0ca  mov     rcx, [rbp+57h+hkey]; hKey
0x1800ac0ce  call    cs:__imp_RegSetValueExW
0x1800ac0d4  mov     rcx, [rbp+5Fh]; this
0x1800ac0d8  test    eax, eax
0x1800ac0da  jz      short loc_1800AC0F1
0x1800ac0dc  mov     r9d, eax; char *
0x1800ac0df  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac0e6  mov     edx, 1F4h; void *
0x1800ac0eb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ac0f1  mov     dword ptr [rsp+90h+pvData], ebx; cbData
0x1800ac0f5  lea     rax, [rbp+57h+var_44]
0x1800ac0f9  mov     [rsp+90h+phkResult], rax; int
0x1800ac0fe  mov     r9d, ebx; dwType
0x1800ac101  xor     r8d, r8d; Reserved
0x1800ac104  lea     rdx, aNumfailures; "NumFailures"
0x1800ac10b  mov     rcx, [rbp+57h+hkey]; hKey
0x1800ac10f  call    cs:__imp_RegSetValueExW
0x1800ac115  mov     rcx, [rbp+5Fh]; this
0x1800ac119  test    eax, eax
0x1800ac11b  jz      short loc_1800AC132
0x1800ac11d  mov     r9d, eax; char *
0x1800ac120  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac127  mov     edx, 1F6h; void *
0x1800ac12c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ac132  mov     rcx, [rbp+57h+var_18]
0x1800ac136  inc     rcx; unsigned __int64
0x1800ac139  mov     [rbp+57h+var_38], rcx
0x1800ac13d  mov     [rbp+57h+cbData], 0
0x1800ac144  lea     r8, [rbp+57h+var_38]; unsigned __int64 *
0x1800ac148  mov     edx, 2; unsigned __int64
0x1800ac14d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800ac152  mov     rcx, [rbp+5Fh]; this
0x1800ac156  test    eax, eax
0x1800ac158  jns     short loc_1800AC16F
0x1800ac15a  mov     r9d, eax; char *
0x1800ac15d  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac164  mov     edx, 1FBh; void *
0x1800ac169  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ac16f  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x1800ac173  mov     rcx, [rbp+57h+var_38]; unsigned __int64
0x1800ac177  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ac17c  mov     rcx, [rbp+5Fh]; this
0x1800ac180  test    eax, eax
0x1800ac182  jns     short loc_1800AC199
0x1800ac184  mov     r9d, eax; char *
0x1800ac187  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac18e  mov     edx, 1FCh; void *
0x1800ac193  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ac199  lea     rcx, [rbp+57h+var_28]
0x1800ac19d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ac1a2  mov     edx, [rbp+57h+cbData]
0x1800ac1a5  mov     dword ptr [rsp+90h+pvData], edx; cbData
0x1800ac1a9  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800ac1ae  mov     r9d, 1; dwType
0x1800ac1b4  xor     r8d, r8d; Reserved
0x1800ac1b7  lea     rdx, aMessage; "Message"
0x1800ac1be  mov     rcx, [rbp+57h+hkey]; hKey
0x1800ac1c2  call    cs:__imp_RegSetValueExW
0x1800ac1c8  mov     rcx, [rbp+5Fh]; this
0x1800ac1cc  test    eax, eax
0x1800ac1ce  jz      short loc_1800AC1E5
0x1800ac1d0  mov     r9d, eax; char *
0x1800ac1d3  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac1da  mov     edx, 1FEh; void *
0x1800ac1df  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ac1e5  cmp     dword ptr [rbp+57h+Data], 2AB0003h
0x1800ac1ec  jz      short loc_1800AC236
0x1800ac1ee  mov     [rbp+57h+cbData], 3
0x1800ac1f5  mov     dword ptr [rsp+90h+pvData], ebx; cbData
0x1800ac1f9  lea     rax, [rbp+57h+cbData]
0x1800ac1fd  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800ac202  mov     r9d, ebx; dwType
0x1800ac205  xor     r8d, r8d; Reserved
0x1800ac208  lea     rdx, aState; "State"
0x1800ac20f  mov     rcx, [rbp+57h+hkey]; hKey
0x1800ac213  call    cs:__imp_RegSetValueExW
0x1800ac219  mov     rcx, [rbp+5Fh]; this
0x1800ac21d  test    eax, eax
0x1800ac21f  jz      short loc_1800AC236
0x1800ac221  mov     r9d, eax; char *
0x1800ac224  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800ac22b  mov     edx, 205h; void *
0x1800ac230  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ac236  lea     rcx, [rbp+57h+hkey]
0x1800ac23a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ac23f  nop
0x1800ac240  lea     rcx, [rbp+57h+hKey]
0x1800ac244  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ac249  nop
0x1800ac24a  lea     rcx, [rbp+57h+var_28]
0x1800ac24e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ac253  mov     al, 1
0x1800ac255  mov     rcx, [rbp+57h+var_8]
0x1800ac259  xor     rcx, rsp; StackCookie
0x1800ac25c  call    __security_check_cookie
0x1800ac261  mov     rbx, [rsp+90h+arg_10]
0x1800ac269  add     rsp, 90h
0x1800ac270  pop     rbp
0x1800ac271  retn
```
