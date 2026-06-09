# PolicyManager::ReadPassportCspPolicy

- ea: `0x180053248`
- end: `0x18005357a`
- name: `PolicyManager::ReadPassportCspPolicy`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9e4`
- `0x1800521f8`

## callees

- `0x1800067c0`
- `0x18000a8e0`
- `0x180012300`
- `0x180018194`
- `0x180019c94`
- `0x18001b974`
- `0x18002c640`
- `0x180053248`
- `0x18005366c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005334c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053406`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005334c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053406`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyManager::ReadPassportCspPolicy(__int64 a1, __int64 a2, _OWORD *a3)
{
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  signed int v10; // ebx
  int v11; // ebx
  int v12; // eax
  LSTATUS v14; // [rsp+30h] [rbp-79h] BYREF
  void **v15; // [rsp+38h] [rbp-71h] BYREF
  HKEY v16; // [rsp+40h] [rbp-69h] BYREF
  void **v17; // [rsp+48h] [rbp-61h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-59h] BYREF
  __int128 v19; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v20[44]; // [rsp+68h] [rbp-41h]
  LPCWSTR lpSubKey[4]; // [rsp+98h] [rbp-11h] BYREF
  LPCWSTR v22[4]; // [rsp+B8h] [rbp+Fh] BYREF

  LOBYTE(v19) = 0;
  DWORD1(v19) = 1;
  *((_QWORD *)&v19 + 1) = 1;
  v20[0] = 0;
  *(_QWORD *)&v20[4] = 0x7F00000008LL;
  *(_OWORD *)&v20[12] = 0;
  *(_DWORD *)&v20[28] = 2;
  *(_QWORD *)&v20[32] = 1;
  *(_DWORD *)&v20[40] = 0;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork");
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, a2);
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, a1);
  std::wstring::append(lpSubKey, L"\\Policies");
  v17 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  phkResult = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v17);
  v6 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &phkResult);
  if ( v7 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      v14 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&dword_1800AD04C,
        0,
        0,
        (__int64)&v14);
    }
    std::wstring::wstring(v22, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork");
    std::wstring::append(v22, L"\\");
    std::wstring::append(v22, a2);
    std::wstring::append(v22, L"\\Device\\Policies");
    v15 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    v16 = 0;
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v15);
    v8 = (const WCHAR *)v22;
    if ( v22[3] > (LPCWSTR)7 )
      v8 = v22[0];
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &v16);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 == 2 )
        goto LABEL_13;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v14 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800AD0B9,
          0,
          0,
          (__int64)&v14);
      }
      if ( v10 > 0 )
LABEL_13:
        v10 = (unsigned __int16)v10 | 0x80070000;
      v11 = HResultToSecurityStatus(v10);
    }
    else
    {
      v12 = PolicyManager::ReadProPolicyValuesFromRegistry((int)&v15, &v19);
      v11 = v12;
      if ( v12 >= 0 )
      {
        *a3 = v19;
        a3[1] = *(_OWORD *)v20;
        a3[2] = *(_OWORD *)&v20[16];
        *(_OWORD *)((char *)a3 + 44) = *(_OWORD *)&v20[28];
      }
      else if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v14 = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800ACFC5,
          0,
          0,
          (__int64)&v14);
      }
    }
    v15 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v15);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v22);
  }
  else
  {
    v11 = PolicyManager::ReadProPolicyValuesFromRegistry((int)&v17, &v19);
    if ( v11 >= 0 )
    {
      *a3 = v19;
      a3[1] = *(_OWORD *)v20;
      a3[2] = *(_OWORD *)&v20[16];
      *(_OWORD *)((char *)a3 + 44) = *(_OWORD *)&v20[28];
    }
    else if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v14 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AD0F7,
        0,
        0,
        (__int64)&v14);
    }
  }
  v17 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v17);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180053248  push    rbp
0x18005324a  push    rbx
0x18005324b  push    rsi
0x18005324c  push    rdi
0x18005324d  push    r14
0x18005324f  lea     rbp, [rsp-37h]
0x180053254  sub     rsp, 0E0h
0x18005325b  mov     rax, cs:__security_cookie
0x180053262  xor     rax, rsp
0x180053265  mov     [rbp+57h+var_28], rax
0x180053269  mov     rdi, r8
0x18005326c  mov     rsi, rdx
0x18005326f  mov     rbx, rcx
0x180053272  mov     byte ptr [rbp+57h+var_A8], 0
0x180053276  mov     eax, 1
0x18005327b  mov     dword ptr [rbp+57h+var_A8+4], eax
0x18005327e  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180053282  mov     byte ptr [rbp+57h+var_98], 0
0x180053286  mov     dword ptr [rbp+57h+var_98+4], 8
0x18005328d  mov     dword ptr [rbp+57h+var_98+8], 7Fh
0x180053294  xorps   xmm0, xmm0
0x180053297  movdqu  [rbp+57h+var_98+0Ch], xmm0
0x18005329c  mov     dword ptr [rbp+57h+var_7C], 2
0x1800532a3  mov     qword ptr [rbp+57h+var_7C+4], rax
0x1800532a7  mov     dword ptr [rbp+57h+var_7C+0Ch], 0
0x1800532ae  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x1800532b5  lea     rcx, [rbp+57h+lpSubKey]
0x1800532b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800532be  nop
0x1800532bf  lea     rdx, asc_18008F0A4; "\\"
0x1800532c6  lea     rcx, [rbp+57h+lpSubKey]
0x1800532ca  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800532cf  mov     rdx, rsi
0x1800532d2  lea     rcx, [rbp+57h+lpSubKey]
0x1800532d6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800532db  lea     rdx, asc_18008F0A4; "\\"
0x1800532e2  lea     rcx, [rbp+57h+lpSubKey]
0x1800532e6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800532eb  mov     rdx, rbx
0x1800532ee  lea     rcx, [rbp+57h+lpSubKey]
0x1800532f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800532f7  lea     rdx, aPolicies; "\\Policies"
0x1800532fe  lea     rcx, [rbp+57h+lpSubKey]
0x180053302  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180053307  lea     r14, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18005330e  mov     [rbp+57h+var_B8], r14
0x180053312  mov     [rbp+57h+var_B0], 0
0x18005331a  lea     rcx, [rbp+57h+var_B8]
0x18005331e  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180053323  lea     rdx, [rbp+57h+lpSubKey]
0x180053327  cmp     [rbp+57h+var_50], 7
0x18005332c  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180053331  lea     rax, [rbp+57h+var_B0]
0x180053335  mov     [rsp+100h+phkResult], rax; phkResult
0x18005333a  mov     ebx, 20019h
0x18005333f  mov     r9d, ebx; samDesired
0x180053342  xor     r8d, r8d; ulOptions
0x180053345  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005334c  call    cs:__imp_RegOpenKeyExW
0x180053353  nop     dword ptr [rax+rax+00h]
0x180053358  test    eax, eax
0x18005335a  jz      loc_1800534E2
0x180053360  mov     ecx, cs:dword_1800BE0B8
0x180053366  cmp     ecx, 4
0x180053369  jbe     short loc_180053390
0x18005336b  mov     [rbp+57h+var_D0], eax
0x18005336e  lea     rax, [rbp+57h+var_D0]
0x180053372  mov     [rsp+100h+phkResult], rax
0x180053377  xor     r9d, r9d
0x18005337a  xor     r8d, r8d
0x18005337d  lea     rdx, dword_1800AD04C
0x180053384  lea     rcx, dword_1800BE0B8
0x18005338b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180053390  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x180053397  lea     rcx, [rbp+57h+var_48]
0x18005339b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800533a0  nop
0x1800533a1  lea     rdx, asc_18008F0A4; "\\"
0x1800533a8  lea     rcx, [rbp+57h+var_48]
0x1800533ac  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800533b1  mov     rdx, rsi
0x1800533b4  lea     rcx, [rbp+57h+var_48]
0x1800533b8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800533bd  lea     rdx, aDevicePolicies; "\\Device\\Policies"
0x1800533c4  lea     rcx, [rbp+57h+var_48]
0x1800533c8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800533cd  mov     [rbp+57h+var_C8], r14
0x1800533d1  mov     [rbp+57h+var_C0], 0
0x1800533d9  lea     rcx, [rbp+57h+var_C8]
0x1800533dd  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x1800533e2  lea     rdx, [rbp+57h+var_48]
0x1800533e6  cmp     [rbp+57h+var_30], 7
0x1800533eb  cmova   rdx, [rbp+57h+var_48]; lpSubKey
0x1800533f0  lea     rax, [rbp+57h+var_C0]
0x1800533f4  mov     [rsp+100h+phkResult], rax; phkResult
0x1800533f9  mov     r9d, ebx; samDesired
0x1800533fc  xor     r8d, r8d; ulOptions
0x1800533ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053406  call    cs:__imp_RegOpenKeyExW
0x18005340d  nop     dword ptr [rax+rax+00h]
0x180053412  mov     ebx, eax
0x180053414  test    eax, eax
0x180053416  jz      short loc_180053465
0x180053418  cmp     eax, 2
0x18005341b  jz      short loc_180053451
0x18005341d  mov     eax, cs:dword_1800BE0B8
0x180053423  cmp     eax, 2
0x180053426  jbe     short loc_18005344D
0x180053428  mov     [rbp+57h+var_D0], ebx
0x18005342b  lea     rax, [rbp+57h+var_D0]
0x18005342f  mov     [rsp+100h+phkResult], rax
0x180053434  xor     r9d, r9d
0x180053437  xor     r8d, r8d
0x18005343a  lea     rdx, byte_1800AD0B9
0x180053441  lea     rcx, dword_1800BE0B8
0x180053448  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005344d  test    ebx, ebx
0x18005344f  jle     short loc_18005345A
0x180053451  movzx   ebx, bx
0x180053454  or      ebx, 80070000h
0x18005345a  mov     ecx, ebx; int
0x18005345c  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180053461  mov     ebx, eax
0x180053463  jmp     short loc_1800534C9
0x180053465  lea     rdx, [rbp+57h+var_A8]
0x180053469  lea     rcx, [rbp+57h+var_C8]
0x18005346d  call    PolicyManager__ReadProPolicyValuesFromRegistry
0x180053472  mov     ebx, eax
0x180053474  test    eax, eax
0x180053476  jns     short loc_1800534AA
0x180053478  mov     ecx, cs:dword_1800BE0B8
0x18005347e  cmp     ecx, 2
0x180053481  jbe     short loc_1800534C9
0x180053483  mov     [rbp+57h+var_D0], eax
0x180053486  lea     rax, [rbp+57h+var_D0]
0x18005348a  mov     [rsp+100h+phkResult], rax
0x18005348f  xor     r9d, r9d
0x180053492  xor     r8d, r8d
0x180053495  lea     rdx, byte_1800ACFC5
0x18005349c  lea     rcx, dword_1800BE0B8
0x1800534a3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800534a8  jmp     short loc_1800534C9
0x1800534aa  movups  xmm0, [rbp+57h+var_A8]
0x1800534ae  movups  xmmword ptr [rdi], xmm0
0x1800534b1  movups  xmm1, [rbp+57h+var_98]
0x1800534b5  movups  xmmword ptr [rdi+10h], xmm1
0x1800534b9  movups  xmm0, xmmword ptr [rbp-31h]
0x1800534bd  movups  xmmword ptr [rdi+20h], xmm0
0x1800534c1  movups  xmm1, [rbp+57h+var_7C]
0x1800534c5  movups  xmmword ptr [rdi+2Ch], xmm1
0x1800534c9  mov     [rbp+57h+var_C8], r14
0x1800534cd  lea     rcx, [rbp+57h+var_C8]
0x1800534d1  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x1800534d6  nop
0x1800534d7  lea     rcx, [rbp+57h+var_48]
0x1800534db  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800534e0  jmp     short loc_180053546
0x1800534e2  lea     rdx, [rbp+57h+var_A8]
0x1800534e6  lea     rcx, [rbp+57h+var_B8]
0x1800534ea  call    PolicyManager__ReadProPolicyValuesFromRegistry
0x1800534ef  mov     ebx, eax
0x1800534f1  test    eax, eax
0x1800534f3  jns     short loc_180053527
0x1800534f5  mov     eax, cs:dword_1800BE0B8
0x1800534fb  cmp     eax, 2
0x1800534fe  jbe     short loc_180053546
0x180053500  mov     [rbp+57h+var_D0], ebx
0x180053503  lea     rax, [rbp+57h+var_D0]
0x180053507  mov     [rsp+100h+phkResult], rax
0x18005350c  xor     r9d, r9d
0x18005350f  xor     r8d, r8d
0x180053512  lea     rdx, byte_1800AD0F7
0x180053519  lea     rcx, dword_1800BE0B8
0x180053520  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180053525  jmp     short loc_180053546
0x180053527  movups  xmm0, [rbp+57h+var_A8]
0x18005352b  movups  xmmword ptr [rdi], xmm0
0x18005352e  movups  xmm1, [rbp+57h+var_98]
0x180053532  movups  xmmword ptr [rdi+10h], xmm1
0x180053536  movups  xmm0, xmmword ptr [rbp-31h]
0x18005353a  movups  xmmword ptr [rdi+20h], xmm0
0x18005353e  movups  xmm1, [rbp+57h+var_7C]
0x180053542  movups  xmmword ptr [rdi+2Ch], xmm1
0x180053546  mov     [rbp+57h+var_B8], r14
0x18005354a  lea     rcx, [rbp+57h+var_B8]
0x18005354e  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180053553  nop
0x180053554  lea     rcx, [rbp+57h+lpSubKey]
0x180053558  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005355d  mov     eax, ebx
0x18005355f  mov     rcx, [rbp+57h+var_28]
0x180053563  xor     rcx, rsp; StackCookie
0x180053566  call    __security_check_cookie
0x18005356b  add     rsp, 0E0h
0x180053572  pop     r14
0x180053574  pop     rdi
0x180053575  pop     rsi
0x180053576  pop     rbx
0x180053577  pop     rbp
0x180053578  retn
```
