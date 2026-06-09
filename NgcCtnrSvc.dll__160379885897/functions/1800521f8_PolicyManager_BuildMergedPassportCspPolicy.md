# PolicyManager::BuildMergedPassportCspPolicy

- ea: `0x1800521f8`
- end: `0x1800526b2`
- name: `PolicyManager::BuildMergedPassportCspPolicy`
- size: `1210`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9e4`

## callees

- `0x180002348`
- `0x1800026b4`
- `0x1800067c0`
- `0x18000a8e0`
- `0x180018194`
- `0x180019c94`
- `0x18002b2fc`
- `0x18002c640`
- `0x18002d518`
- `0x18003d08c`
- `0x18003d400`
- `0x180051de8`
- `0x1800521f8`
- `0x180053248`
- `0x18005ec98`
- `0x18005ee08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800523d6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800523d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052315`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052315`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052262`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052262`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyManager::BuildMergedPassportCspPolicy(__int64 a1, _OWORD *a2)
{
  signed int v4; // edi
  unsigned __int8 *v5; // rdx
  int v6; // r14d
  DWORD v7; // r12d
  LSTATUS v8; // eax
  __int64 v9; // rax
  char *v10; // r15
  unsigned __int64 v11; // rcx
  WCHAR *v12; // rax
  size_t v13; // rbx
  _QWORD *v14; // rcx
  _QWORD *v15; // rdx
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  const wchar_t *v20; // rax
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp-90h] BYREF
  void *v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  const wchar_t *v29; // [rsp+88h] [rbp-78h] BYREF
  void **v30; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[44]; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+E0h] [rbp-20h] BYREF
  char v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+F4h] [rbp-Ch]
  int v37; // [rsp+F8h] [rbp-8h]
  __int128 v38; // [rsp+FCh] [rbp-4h]
  int v39; // [rsp+10Ch] [rbp+Ch]
  __int64 v40; // [rsp+110h] [rbp+10h]
  int v41; // [rsp+118h] [rbp+18h]
  _QWORD v42[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v43; // [rsp+138h] [rbp+38h]

  v30 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  hKey = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v30);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork", 0, 0x20019u, &hKey);
  if ( v4 == 2 )
  {
    v4 = -2147024894;
    goto LABEL_49;
  }
  if ( v4 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_7;
    v5 = (unsigned __int8 *)byte_1800ACF9D;
    goto LABEL_6;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
    {
LABEL_7:
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_49;
    }
    v5 = (unsigned __int8 *)qword_1800AD028;
LABEL_6:
    cchName = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      v5,
      0,
      0,
      (__int64)&cchName);
    goto LABEL_7;
  }
  v4 = 0;
  ++cbMaxSubKeyLen;
  v6 = 0;
  LOBYTE(v32) = 0;
  DWORD1(v32) = 1;
  *((_QWORD *)&v32 + 1) = 1;
  v33[0] = 0;
  *(_QWORD *)&v33[4] = 0x7F00000008LL;
  *(_OWORD *)&v33[12] = 0;
  *(_DWORD *)&v33[28] = 2;
  *(_QWORD *)&v33[32] = 1;
  *(_DWORD *)&v33[40] = 0;
  NgcPolicy::NgcPolicy::Initialize(&v32);
  v7 = 0;
  if ( !cSubKeys )
  {
LABEL_44:
    if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      v23 = v6;
      LODWORD(v29) = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (__int64)&word_1800ACF36,
        0,
        0,
        (__int64)&v29,
        (__int64)&v23);
    }
    if ( v6 )
    {
      *a2 = v32;
      a2[1] = *(_OWORD *)v33;
      a2[2] = *(_OWORD *)&v33[16];
      *(_OWORD *)((char *)a2 + 44) = *(_OWORD *)&v33[28];
    }
    else
    {
      v4 = -2146893807;
    }
    goto LABEL_49;
  }
  while ( 1 )
  {
    std::vector<unsigned short>::vector<unsigned short>(&lpName, cbMaxSubKeyLen);
    cchName = ((_BYTE *)v27 - (_BYTE *)lpName) >> 1;
    v8 = RegEnumKeyExW(hKey, v7, lpName, &cchName, 0, 0, 0, 0);
    if ( v8 == 259 )
    {
      std::vector<unsigned short>::_Tidy(&lpName);
      goto LABEL_44;
    }
    if ( v8 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 3 )
      {
        v23 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)qword_1800AD000,
          0,
          0,
          (__int64)&v23);
      }
      goto LABEL_38;
    }
    v9 = cchName + 1;
    cchName = v9;
    v10 = (char *)v27;
    v11 = ((_BYTE *)v27 - (_BYTE *)lpName) >> 1;
    if ( (unsigned int)v9 >= v11 )
    {
      if ( (unsigned int)v9 <= v11 )
        goto LABEL_24;
      if ( (unsigned int)v9 > (unsigned __int64)((v28 - (__int64)lpName) >> 1) )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpName, (unsigned int)v9);
        goto LABEL_24;
      }
      v13 = 2 * ((unsigned int)v9 - v11);
      memset_0(v27, 0, v13);
      v12 = (WCHAR *)&v10[v13];
    }
    else
    {
      v12 = &lpName[v9];
    }
    v27 = v12;
LABEL_24:
    std::wstring::wstring(v42, lpName);
    v14 = v42;
    if ( v43 > 7 )
      v14 = (_QWORD *)v42[0];
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v14, v42[2], L"Biometrics", 10) )
      goto LABEL_37;
    LOBYTE(v34) = 0;
    DWORD1(v34) = 1;
    *((_QWORD *)&v34 + 1) = 1;
    v35 = 0;
    v36 = 8;
    v37 = 127;
    v38 = 0;
    v39 = 2;
    v40 = 1;
    v41 = 0;
    v15 = v42;
    if ( v43 > 7 )
      v15 = (_QWORD *)v42[0];
    v16 = PolicyManager::ReadPassportCspPolicy(a1, (__int64)v15, &v34);
    v19 = (unsigned int)v16;
    if ( v16 >= 0 )
      break;
    v4 = 0;
LABEL_37:
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v42);
LABEL_38:
    std::vector<unsigned short>::_Tidy(&lpName);
    if ( ++v7 >= cSubKeys )
      goto LABEL_44;
  }
  if ( (unsigned int)dword_1800BE0B8 > 4 )
  {
    v20 = (const wchar_t *)v42;
    if ( v43 > 7 )
      v20 = (const wchar_t *)v42[0];
    v29 = v20;
    v23 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v19,
      (__int64)byte_1800ACEFD,
      v17,
      v18,
      (__int64)&v23,
      &v29);
  }
  v4 = NgcPolicy::NgcPolicy::Merge((NgcPolicy::NgcPolicy *)&v32, (const struct NgcPolicy::NgcPolicy *)&v34);
  if ( v4 >= 0 )
  {
    ++v6;
    goto LABEL_37;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v23 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)&dword_1800ACF74,
      0,
      0,
      (__int64)&v23);
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v42);
  std::vector<unsigned short>::_Tidy(&lpName);
LABEL_49:
  v30 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v30);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800521f8  mov     [rsp-8+arg_10], rbx
0x1800521fd  push    rbp
0x1800521fe  push    rsi
0x1800521ff  push    rdi
0x180052200  push    r12
0x180052202  push    r13
0x180052204  push    r14
0x180052206  push    r15
0x180052208  lea     rbp, [rsp-50h]
0x18005220d  sub     rsp, 150h
0x180052214  mov     rax, cs:__security_cookie
0x18005221b  xor     rax, rsp
0x18005221e  mov     [rbp+80h+var_40], rax
0x180052222  mov     rsi, rdx
0x180052225  mov     r13, rcx
0x180052228  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18005222f  mov     [rbp+80h+var_F0], rax
0x180052233  xor     ebx, ebx
0x180052235  mov     [rbp+80h+hKey], rbx
0x180052239  lea     rcx, [rbp+80h+var_F0]
0x18005223d  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180052242  lea     rax, [rbp+80h+hKey]
0x180052246  mov     [rsp+180h+phkResult], rax; phkResult
0x18005224b  mov     r9d, 20019h; samDesired
0x180052251  xor     r8d, r8d; ulOptions
0x180052254  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x18005225b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052262  call    cs:__imp_RegOpenKeyExW
0x180052269  nop     dword ptr [rax+rax+00h]
0x18005226e  mov     edi, eax
0x180052270  lea     r12d, [rbx+2]
0x180052274  cmp     eax, r12d
0x180052277  jnz     short loc_180052283
0x180052279  mov     edi, 80070002h
0x18005227e  jmp     loc_180052674
0x180052283  test    edi, edi
0x180052285  jz      short loc_1800522CF
0x180052287  mov     eax, cs:dword_1800BE0B8
0x18005228d  cmp     eax, r12d
0x180052290  jbe     short loc_1800522B9
0x180052292  lea     rdx, byte_1800ACF9D
0x180052299  xor     r9d, r9d
0x18005229c  lea     rax, [rsp+180h+cchName]
0x1800522a1  xor     r8d, r8d
0x1800522a4  mov     [rsp+180h+phkResult], rax
0x1800522a9  mov     [rsp+180h+cchName], edi
0x1800522ad  lea     rcx, dword_1800BE0B8
0x1800522b4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800522b9  test    edi, edi
0x1800522bb  jle     loc_180052674
0x1800522c1  movzx   edi, di
0x1800522c4  or      edi, 80070000h
0x1800522ca  jmp     loc_180052674
0x1800522cf  mov     [rsp+180h+cSubKeys], ebx
0x1800522d3  mov     [rsp+180h+cbMaxSubKeyLen], ebx
0x1800522d7  mov     [rsp+180h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800522dc  mov     [rsp+180h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800522e1  mov     [rsp+180h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x1800522e6  mov     [rsp+180h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x1800522eb  mov     [rsp+180h+lpcValues], rbx; lpcValues
0x1800522f0  mov     [rsp+180h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x1800522f5  lea     rax, [rsp+180h+cbMaxSubKeyLen]
0x1800522fa  mov     [rsp+180h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800522ff  lea     rax, [rsp+180h+cSubKeys]
0x180052304  mov     [rsp+180h+phkResult], rax; lpcSubKeys
0x180052309  xor     r9d, r9d; lpReserved
0x18005230c  xor     r8d, r8d; lpcchClass
0x18005230f  xor     edx, edx; lpClass
0x180052311  mov     rcx, [rbp+80h+hKey]; hKey
0x180052315  call    cs:__imp_RegQueryInfoKeyW
0x18005231c  nop     dword ptr [rax+rax+00h]
0x180052321  mov     edi, eax
0x180052323  test    eax, eax
0x180052325  jz      short loc_18005233E
0x180052327  mov     eax, cs:dword_1800BE0B8
0x18005232d  cmp     eax, r12d
0x180052330  jbe     short loc_1800522B9
0x180052332  lea     rdx, qword_1800AD028
0x180052339  jmp     loc_180052299
0x18005233e  mov     edi, ebx
0x180052340  mov     r15d, 1
0x180052346  add     [rsp+180h+cbMaxSubKeyLen], r15d
0x18005234b  mov     r14d, ebx
0x18005234e  mov     byte ptr [rbp+80h+var_E0], bl
0x180052351  mov     dword ptr [rbp+80h+var_E0+4], r15d
0x180052355  mov     qword ptr [rbp+80h+var_E0+8], r15
0x180052359  mov     byte ptr [rbp+80h+var_D0], bl
0x18005235c  mov     dword ptr [rbp+80h+var_D0+4], 8
0x180052363  mov     dword ptr [rbp+80h+var_D0+8], 7Fh
0x18005236a  xorps   xmm0, xmm0
0x18005236d  movdqu  [rbp+80h+var_D0+0Ch], xmm0
0x180052372  mov     dword ptr [rbp+80h+var_B4], r12d
0x180052376  mov     qword ptr [rbp+80h+var_B4+4], r15
0x18005237a  mov     dword ptr [rbp+80h+var_B4+0Ch], ebx
0x18005237d  lea     rcx, [rbp+80h+var_E0]
0x180052381  call    ?Initialize@NgcPolicy@1@QEAAJW4_NGC_BIOMETRICS_POLICY@@W4_NGC_SMART_CARD_POLICY@@W4_NGC_HARDWARE_POLICY@@@Z; NgcPolicy::NgcPolicy::Initialize(_NGC_BIOMETRICS_POLICY,_NGC_SMART_CARD_POLICY,_NGC_HARDWARE_POLICY)
0x180052386  mov     r12d, ebx
0x180052389  cmp     [rsp+180h+cSubKeys], ebx
0x18005238d  jbe     loc_18005260A
0x180052393  mov     edx, [rsp+180h+cbMaxSubKeyLen]
0x180052397  lea     rcx, [rsp+180h+lpName]
0x18005239c  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1800523a1  nop
0x1800523a2  mov     r8, [rsp+180h+lpName]; lpName
0x1800523a7  mov     rax, [rsp+180h+var_108]
0x1800523ac  sub     rax, r8
0x1800523af  sar     rax, 1
0x1800523b2  mov     [rsp+180h+cchName], eax
0x1800523b6  mov     [rsp+180h+lpcValues], rbx; lpftLastWriteTime
0x1800523bb  mov     [rsp+180h+lpcbMaxClassLen], rbx; lpcchClass
0x1800523c0  mov     [rsp+180h+lpcbMaxSubKeyLen], rbx; lpClass
0x1800523c5  mov     [rsp+180h+phkResult], rbx; lpReserved
0x1800523ca  lea     r9, [rsp+180h+cchName]; lpcchName
0x1800523cf  mov     edx, r12d; dwIndex
0x1800523d2  mov     rcx, [rbp+80h+hKey]; hKey
0x1800523d6  call    cs:__imp_RegEnumKeyExW
0x1800523dd  nop     dword ptr [rax+rax+00h]
0x1800523e2  mov     ecx, eax
0x1800523e4  cmp     eax, 103h
0x1800523e9  jz      loc_180052600
0x1800523ef  test    eax, eax
0x1800523f1  jz      short loc_18005242E
0x1800523f3  mov     eax, cs:dword_1800BE0B8
0x1800523f9  cmp     eax, 3
0x1800523fc  jbe     loc_18005259D
0x180052402  mov     [rsp+180h+var_11C], ecx
0x180052406  lea     rax, [rsp+180h+var_11C]
0x18005240b  mov     [rsp+180h+phkResult], rax
0x180052410  xor     r9d, r9d
0x180052413  xor     r8d, r8d
0x180052416  lea     rdx, qword_1800AD000
0x18005241d  lea     rcx, dword_1800BE0B8
0x180052424  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052429  jmp     loc_18005259D
0x18005242e  mov     eax, [rsp+180h+cchName]
0x180052432  add     eax, r15d
0x180052435  mov     [rsp+180h+cchName], eax
0x180052439  mov     ebx, eax
0x18005243b  mov     rdx, [rsp+180h+lpName]
0x180052440  mov     r15, [rsp+180h+var_108]
0x180052445  mov     rcx, r15
0x180052448  sub     rcx, rdx
0x18005244b  sar     rcx, 1
0x18005244e  cmp     rbx, rcx
0x180052451  jnb     short loc_180052459
0x180052453  lea     rax, [rdx+rax*2]
0x180052457  jmp     short loc_180052490
0x180052459  jbe     short loc_180052495
0x18005245b  mov     rax, [rbp+80h+var_100]
0x18005245f  sub     rax, rdx
0x180052462  sar     rax, 1
0x180052465  cmp     rbx, rax
0x180052468  jbe     short loc_180052479
0x18005246a  mov     rdx, rbx
0x18005246d  lea     rcx, [rsp+180h+lpName]
0x180052472  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180052477  jmp     short loc_180052495
0x180052479  sub     rbx, rcx
0x18005247c  add     rbx, rbx
0x18005247f  mov     r8, rbx; Size
0x180052482  xor     edx, edx; Val
0x180052484  mov     rcx, r15; void *
0x180052487  call    memset_0
0x18005248c  lea     rax, [r15+rbx]
0x180052490  mov     [rsp+180h+var_108], rax
0x180052495  mov     rdx, [rsp+180h+lpName]
0x18005249a  lea     rcx, [rbp+80h+var_60]
0x18005249e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800524a3  nop
0x1800524a4  lea     rcx, [rbp+80h+var_60]
0x1800524a8  cmp     [rbp+80h+var_48], 7
0x1800524ad  cmova   rcx, [rbp+80h+var_60]
0x1800524b2  mov     r9d, 0Ah
0x1800524b8  lea     r8, aBiometrics; "Biometrics"
0x1800524bf  mov     rdx, [rbp+80h+var_50]
0x1800524c3  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800524c8  xor     ebx, ebx
0x1800524ca  test    al, al
0x1800524cc  jz      short loc_1800524E1
0x1800524ce  lea     rcx, [rbp+80h+var_60]
0x1800524d2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800524d7  nop
0x1800524d8  lea     r15d, [rbx+1]
0x1800524dc  jmp     loc_18005259D
0x1800524e1  mov     [rbp+80h+var_A0], bl
0x1800524e4  mov     r15d, 1
0x1800524ea  mov     [rbp+80h+var_9C], r15d
0x1800524ee  mov     [rbp+80h+var_98], r15
0x1800524f2  mov     [rbp+80h+var_90], bl
0x1800524f5  mov     [rbp+80h+var_8C], 8
0x1800524fc  mov     [rbp+80h+var_88], 7Fh
0x180052503  xorps   xmm0, xmm0
0x180052506  movdqu  [rbp+80h+var_84], xmm0
0x18005250b  mov     [rbp+80h+var_74], 2
0x180052512  mov     [rbp+80h+var_70], r15
0x180052516  mov     [rbp+80h+var_68], ebx
0x180052519  lea     rdx, [rbp+80h+var_60]
0x18005251d  cmp     [rbp+80h+var_48], 7
0x180052522  cmova   rdx, [rbp+80h+var_60]
0x180052527  lea     r8, [rbp+80h+var_A0]
0x18005252b  mov     rcx, r13
0x18005252e  call    PolicyManager__ReadPassportCspPolicy
0x180052533  mov     ecx, eax
0x180052535  test    eax, eax
0x180052537  jns     short loc_18005253D
0x180052539  mov     edi, ebx
0x18005253b  jmp     short loc_180052593
0x18005253d  mov     eax, cs:dword_1800BE0B8
0x180052543  cmp     eax, 4
0x180052546  jbe     short loc_18005257D
0x180052548  lea     rax, [rbp+80h+var_60]
0x18005254c  cmp     [rbp+80h+var_48], 7
0x180052551  cmova   rax, [rbp+80h+var_60]
0x180052556  mov     [rbp+80h+var_F8], rax
0x18005255a  mov     [rsp+180h+var_11C], ecx
0x18005255e  lea     rax, [rbp+80h+var_F8]
0x180052562  mov     [rsp+180h+lpcbMaxSubKeyLen], rax
0x180052567  lea     rax, [rsp+180h+var_11C]
0x18005256c  mov     [rsp+180h+phkResult], rax
0x180052571  lea     rdx, byte_1800ACEFD
0x180052578  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18005257d  lea     rdx, [rbp+80h+var_A0]; struct NgcPolicy::NgcPolicy *
0x180052581  lea     rcx, [rbp+80h+var_E0]; this
0x180052585  call    ?Merge@NgcPolicy@1@QEAAJAEBV11@@Z; NgcPolicy::NgcPolicy::Merge(NgcPolicy::NgcPolicy const &)
0x18005258a  mov     edi, eax
0x18005258c  test    eax, eax
0x18005258e  js      short loc_1800525B7
0x180052590  add     r14d, r15d
0x180052593  lea     rcx, [rbp+80h+var_60]
0x180052597  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005259c  nop
0x18005259d  lea     rcx, [rsp+180h+lpName]
0x1800525a2  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800525a7  add     r12d, r15d
0x1800525aa  cmp     r12d, [rsp+180h+cSubKeys]
0x1800525af  jb      loc_180052393
0x1800525b5  jmp     short loc_18005260A
0x1800525b7  mov     eax, cs:dword_1800BE0B8
0x1800525bd  cmp     eax, 2
0x1800525c0  jbe     short loc_1800525EA
0x1800525c2  mov     [rsp+180h+var_11C], edi
0x1800525c6  lea     rax, [rsp+180h+var_11C]
0x1800525cb  mov     [rsp+180h+phkResult], rax
0x1800525d0  xor     r9d, r9d
0x1800525d3  xor     r8d, r8d
0x1800525d6  lea     rdx, dword_1800ACF74
0x1800525dd  lea     rcx, dword_1800BE0B8
0x1800525e4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800525e9  nop
0x1800525ea  lea     rcx, [rbp+80h+var_60]
0x1800525ee  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800525f3  nop
0x1800525f4  lea     rcx, [rsp+180h+lpName]
0x1800525f9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800525fe  jmp     short loc_180052674
0x180052600  lea     rcx, [rsp+180h+lpName]
0x180052605  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005260a  mov     eax, cs:dword_1800BE0B8
0x180052610  cmp     eax, 4
0x180052613  jbe     short loc_180052649
0x180052615  mov     [rsp+180h+var_11C], r14d
0x18005261a  mov     dword ptr [rbp+80h+var_F8], edi
0x18005261d  lea     rax, [rsp+180h+var_11C]
0x180052622  mov     [rsp+180h+lpcbMaxSubKeyLen], rax
0x180052627  lea     rax, [rbp+80h+var_F8]
0x18005262b  mov     [rsp+180h+phkResult], rax
0x180052630  xor     r9d, r9d
0x180052633  xor     r8d, r8d
0x180052636  lea     rdx, word_1800ACF36
0x18005263d  lea     rcx, dword_1800BE0B8
0x180052644  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180052649  test    r14d, r14d
0x18005264c  jnz     short loc_180052655
0x18005264e  mov     edi, 80090011h
0x180052653  jmp     short loc_180052674
0x180052655  movups  xmm0, [rbp+80h+var_E0]
0x180052659  movups  xmmword ptr [rsi], xmm0
0x18005265c  movups  xmm1, [rbp+80h+var_D0]
0x180052660  movups  xmmword ptr [rsi+10h], xmm1
0x180052664  movups  xmm0, xmmword ptr [rbp-40h]
0x180052668  movups  xmmword ptr [rsi+20h], xmm0
0x18005266c  movups  xmm1, [rbp+80h+var_B4]
0x180052670  movups  xmmword ptr [rsi+2Ch], xmm1
0x180052674  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18005267b  mov     [rbp+80h+var_F0], rax
0x18005267f  lea     rcx, [rbp+80h+var_F0]
0x180052683  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180052688  mov     eax, edi
0x18005268a  mov     rcx, [rbp+80h+var_40]
0x18005268e  xor     rcx, rsp; StackCookie
0x180052691  call    __security_check_cookie
0x180052696  mov     rbx, [rsp+180h+arg_10]
0x18005269e  add     rsp, 150h
0x1800526a5  pop     r15
0x1800526a7  pop     r14
0x1800526a9  pop     r13
0x1800526ab  pop     r12
0x1800526ad  pop     rdi
0x1800526ae  pop     rsi
0x1800526af  pop     rbp
  ... truncated ...
```
