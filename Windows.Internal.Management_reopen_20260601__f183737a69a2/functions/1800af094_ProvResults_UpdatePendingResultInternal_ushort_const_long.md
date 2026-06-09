# ProvResults::UpdatePendingResultInternal(ushort const *,long)

- ea: `0x1800af094`
- end: `0x1800af3e7`
- name: `?UpdatePendingResultInternal@ProvResults@@CA_NPEBGJ@Z`
- size: `851`
- prototype: `bool __fastcall(LPCWSTR lpSubKey, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x1800ae8c0`

## callees

- `0x180004eb0`
- `0x18000dc18`
- `0x18001656c`
- `0x180016698`
- `0x180017024`
- `0x180017078`
- `0x180017118`
- `0x1800184c0`
- `0x18003e5d4`
- `0x180094ee4`
- `0x1800ac230`
- `0x1800ae564`
- `0x1800af094`
- `0x1800af48c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800af1ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800af1ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af22a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af271`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af32a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af381`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af22a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af271`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af32a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800af381`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800af12f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800af12f`

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
0x1800af094  mov     [rsp-8+arg_10], rbx
0x1800af099  push    rbp
0x1800af09a  lea     rbp, [rsp-57h]
0x1800af09f  sub     rsp, 90h
0x1800af0a6  mov     rax, cs:__security_cookie
0x1800af0ad  xor     rax, rsp
0x1800af0b0  mov     [rbp+57h+var_8], rax
0x1800af0b4  mov     rbx, rcx
0x1800af0b7  mov     dword ptr [rbp+57h+Data], edx
0x1800af0ba  lea     rcx, [rbp+57h+var_28]
0x1800af0be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800af0c3  nop
0x1800af0c4  mov     eax, dword ptr [rbp+57h+Data]
0x1800af0c7  test    eax, eax
0x1800af0c9  jns     short loc_1800AF0D4
0x1800af0cb  lea     rdx, ?gc_provresultProvisioningFailed@@3QBGB; "Provisioning failed"
0x1800af0d2  jmp     short loc_1800AF0EB
0x1800af0d4  lea     rdx, ?gc_provresultProvisioningPending@@3QBGB; "Provisioning pending"
0x1800af0db  lea     rcx, ?gc_provresultProvisioningSucceeded@@3QBGB; "Provisioning succeeded"
0x1800af0e2  cmp     eax, 2AB0003h
0x1800af0e7  cmovnz  rdx, rcx
0x1800af0eb  lea     rcx, [rbp+57h+var_28]
0x1800af0ef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800af0f4  mov     edx, 20019h; samDesired
0x1800af0f9  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800af0fd  call    ?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ProvResults::GetRootKey(ulong)
0x1800af102  nop
0x1800af103  mov     [rbp+57h+hkey], 0
0x1800af10b  xor     edx, edx
0x1800af10d  lea     rcx, [rbp+57h+hkey]
0x1800af111  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800af116  lea     rax, [rbp+57h+hkey]
0x1800af11a  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800af11f  mov     r9d, 3; samDesired
0x1800af125  xor     r8d, r8d; ulOptions
0x1800af128  mov     rdx, rbx; lpSubKey
0x1800af12b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800af12f  call    cs:__imp_RegOpenKeyExW
0x1800af136  nop     dword ptr [rax+rax+00h]
0x1800af13b  mov     rcx, [rbp+5Fh]; this
0x1800af13f  test    eax, eax
0x1800af141  jz      short loc_1800AF158
0x1800af143  mov     r9d, eax; char *
0x1800af146  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af14d  mov     edx, 1DAh; void *
0x1800af152  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800af158  mov     dword ptr [rbp+57h+var_44], 0
0x1800af15f  mov     ebx, 4
0x1800af164  test    dword ptr [rbp+57h+Data], 80000000h
0x1800af16b  jnz     short loc_1800AF17A
0x1800af16d  cmp     dword ptr [rbp+57h+Data], 2AB0003h
0x1800af174  jnz     loc_1800AF20C
0x1800af17a  mov     [rbp+57h+cbData], ebx
0x1800af17d  lea     rax, [rbp+57h+cbData]
0x1800af181  mov     [rsp+90h+pcbData], rax; pcbData
0x1800af186  lea     rax, [rbp+57h+var_44]
0x1800af18a  mov     [rsp+90h+pvData], rax; pvData
0x1800af18f  mov     [rsp+90h+phkResult], 0; int
0x1800af198  mov     r9d, 10h; dwFlags
0x1800af19e  lea     r8, aNumfailures; "NumFailures"
0x1800af1a5  xor     edx, edx; lpSubKey
0x1800af1a7  mov     rcx, [rbp+57h+hkey]; hkey
0x1800af1ab  call    cs:__imp_RegGetValueW
0x1800af1b2  nop     dword ptr [rax+rax+00h]
0x1800af1b7  mov     rcx, [rbp+5Fh]; this
0x1800af1bb  test    eax, eax
0x1800af1bd  jz      short loc_1800AF1CE
0x1800af1bf  mov     r9d, eax; char *
0x1800af1c2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800af1c7  xor     ecx, ecx
0x1800af1c9  mov     dword ptr [rbp+57h+var_44], ecx
0x1800af1cc  jmp     short loc_1800AF1D1
0x1800af1ce  mov     ecx, dword ptr [rbp+57h+var_44]
0x1800af1d1  cmp     dword ptr [rbp+57h+Data], 0
0x1800af1d5  jge     short loc_1800AF20C
0x1800af1d7  lea     edx, [rcx+1]
0x1800af1da  or      eax, 0FFFFFFFFh
0x1800af1dd  cmp     edx, ecx
0x1800af1df  cmovnb  eax, edx
0x1800af1e2  sbb     r9d, r9d
0x1800af1e5  and     r9d, 80070216h; char *
0x1800af1ec  mov     dword ptr [rbp+57h+var_44], eax
0x1800af1ef  mov     rax, [rbp+5Fh]
0x1800af1f3  cmp     edx, ecx
0x1800af1f5  jnb     short loc_1800AF20C
0x1800af1f7  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af1fe  mov     edx, 1EEh; void *
0x1800af203  mov     rcx, rax; this
0x1800af206  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af20c  mov     dword ptr [rsp+90h+pvData], ebx; cbData
0x1800af210  lea     rax, [rbp+57h+Data]
0x1800af214  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800af219  mov     r9d, ebx; dwType
0x1800af21c  xor     r8d, r8d; Reserved
0x1800af21f  lea     rdx, aLastresult; "LastResult"
0x1800af226  mov     rcx, [rbp+57h+hkey]; hKey
0x1800af22a  call    cs:__imp_RegSetValueExW
0x1800af231  nop     dword ptr [rax+rax+00h]
0x1800af236  mov     rcx, [rbp+5Fh]; this
0x1800af23a  test    eax, eax
0x1800af23c  jz      short loc_1800AF253
0x1800af23e  mov     r9d, eax; char *
0x1800af241  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af248  mov     edx, 1F4h; void *
0x1800af24d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800af253  mov     dword ptr [rsp+90h+pvData], ebx; cbData
0x1800af257  lea     rax, [rbp+57h+var_44]
0x1800af25b  mov     [rsp+90h+phkResult], rax; int
0x1800af260  mov     r9d, ebx; dwType
0x1800af263  xor     r8d, r8d; Reserved
0x1800af266  lea     rdx, aNumfailures; "NumFailures"
0x1800af26d  mov     rcx, [rbp+57h+hkey]; hKey
0x1800af271  call    cs:__imp_RegSetValueExW
0x1800af278  nop     dword ptr [rax+rax+00h]
0x1800af27d  mov     rcx, [rbp+5Fh]; this
0x1800af281  test    eax, eax
0x1800af283  jz      short loc_1800AF29A
0x1800af285  mov     r9d, eax; char *
0x1800af288  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af28f  mov     edx, 1F6h; void *
0x1800af294  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800af29a  mov     rcx, [rbp+57h+var_18]
0x1800af29e  inc     rcx; unsigned __int64
0x1800af2a1  mov     [rbp+57h+var_38], rcx
0x1800af2a5  mov     [rbp+57h+cbData], 0
0x1800af2ac  lea     r8, [rbp+57h+var_38]; unsigned __int64 *
0x1800af2b0  mov     edx, 2; unsigned __int64
0x1800af2b5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800af2ba  mov     rcx, [rbp+5Fh]; this
0x1800af2be  test    eax, eax
0x1800af2c0  jns     short loc_1800AF2D7
0x1800af2c2  mov     r9d, eax; char *
0x1800af2c5  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af2cc  mov     edx, 1FBh; void *
0x1800af2d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af2d7  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x1800af2db  mov     rcx, [rbp+57h+var_38]; unsigned __int64
0x1800af2df  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800af2e4  mov     rcx, [rbp+5Fh]; this
0x1800af2e8  test    eax, eax
0x1800af2ea  jns     short loc_1800AF301
0x1800af2ec  mov     r9d, eax; char *
0x1800af2ef  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af2f6  mov     edx, 1FCh; void *
0x1800af2fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af301  lea     rcx, [rbp+57h+var_28]
0x1800af305  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800af30a  mov     edx, [rbp+57h+cbData]
0x1800af30d  mov     dword ptr [rsp+90h+pvData], edx; cbData
0x1800af311  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800af316  mov     r9d, 1; dwType
0x1800af31c  xor     r8d, r8d; Reserved
0x1800af31f  lea     rdx, aMessage; "Message"
0x1800af326  mov     rcx, [rbp+57h+hkey]; hKey
0x1800af32a  call    cs:__imp_RegSetValueExW
0x1800af331  nop     dword ptr [rax+rax+00h]
0x1800af336  mov     rcx, [rbp+5Fh]; this
0x1800af33a  test    eax, eax
0x1800af33c  jz      short loc_1800AF353
0x1800af33e  mov     r9d, eax; char *
0x1800af341  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af348  mov     edx, 1FEh; void *
0x1800af34d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800af353  cmp     dword ptr [rbp+57h+Data], 2AB0003h
0x1800af35a  jz      short loc_1800AF3AA
0x1800af35c  mov     [rbp+57h+cbData], 3
0x1800af363  mov     dword ptr [rsp+90h+pvData], ebx; cbData
0x1800af367  lea     rax, [rbp+57h+cbData]
0x1800af36b  mov     [rsp+90h+phkResult], rax; unsigned int
0x1800af370  mov     r9d, ebx; dwType
0x1800af373  xor     r8d, r8d; Reserved
0x1800af376  lea     rdx, aState; "State"
0x1800af37d  mov     rcx, [rbp+57h+hkey]; hKey
0x1800af381  call    cs:__imp_RegSetValueExW
0x1800af388  nop     dword ptr [rax+rax+00h]
0x1800af38d  mov     rcx, [rbp+5Fh]; this
0x1800af391  test    eax, eax
0x1800af393  jz      short loc_1800AF3AA
0x1800af395  mov     r9d, eax; char *
0x1800af398  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x1800af39f  mov     edx, 205h; void *
0x1800af3a4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800af3aa  lea     rcx, [rbp+57h+hkey]
0x1800af3ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800af3b3  nop
0x1800af3b4  lea     rcx, [rbp+57h+hKey]
0x1800af3b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800af3bd  nop
0x1800af3be  lea     rcx, [rbp+57h+var_28]
0x1800af3c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800af3c7  mov     al, 1
0x1800af3c9  mov     rcx, [rbp+57h+var_8]
0x1800af3cd  xor     rcx, rsp; StackCookie
0x1800af3d0  call    __security_check_cookie
0x1800af3d5  mov     rbx, [rsp+90h+arg_10]
0x1800af3dd  add     rsp, 90h
0x1800af3e4  pop     rbp
0x1800af3e5  retn
```
