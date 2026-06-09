# Uev::TemplateAdministrator::AddTemplate(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14003b0a0`
- end: `0x14003b8c1`
- name: `?AddTemplate@TemplateAdministrator@Uev@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `2081`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `44`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140004ab4`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000bc7c`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d2d8`
- `0x14000e30c`
- `0x14000eccc`
- `0x14000f358`
- `0x140019748`
- `0x140020568`
- `0x1400270f8`
- `0x140028c20`
- `0x1400322b8`
- `0x140032354`
- `0x140034c14`
- `0x140034db4`
- `0x140038458`
- `0x140038614`
- `0x140038fa0`
- `0x140039410`
- `0x140039c60`
- `0x140039ff4`
- `0x14003a094`
- `0x14003a0bc`
- `0x14003a354`
- `0x14003a58c`
- `0x14003b0a0`
- `0x14003b94c`
- `0x14003be24`
- `0x14003c630`
- `0x14003d094`
- `0x14003e7c8`
- `0x14003f370`
- `0x140045724`
- `0x140045af8`
- `0x140045ea8`
- `0x140065c20`
- `0x140065e48`
- `0x140065f7c`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14003b120`
- `ADVAPI32!RegOpenKeyExW` at `0x14003b120`
- `ADVAPI32!RegCloseKey` at `0x14003b185`
- `ADVAPI32!RegCloseKey` at `0x14003b185`
- `ADVAPI32!RegQueryValueExW` at `0x14003b160`
- `ADVAPI32!RegQueryValueExW` at `0x14003b160`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x14003b5e2`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x14003b5e2`

## string_xrefs

- `0x14003b85b`: `SLAPI check failed. The template cannot be added.`
- `0x14003b7e8`: `Unable to set template registration timestamp`
- `0x14003b890`: `The template has been previously replaced`
- `0x14003b824`: `Template ID already exists`

## pseudocode

```c
__int64 __fastcall Uev::TemplateAdministrator::AddTemplate(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdi
  bool v5; // bl
  LSTATUS v6; // eax
  bool v7; // sf
  LSTATUS v8; // eax
  bool v9; // sf
  signed int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  _WORD *v13; // rax
  _QWORD *v14; // rax
  __int64 i; // rbx
  __int64 j; // rdi
  __int64 PrimaryTemplateIdFromSecondaryId; // rax
  size_t v18; // r15
  const wchar_t *v19; // rdx
  size_t v20; // r14
  size_t v21; // r8
  bool v22; // r14
  const struct Uev::TemplateInfo *v23; // rdi
  struct Uev::TemplateInfo *k; // r12
  __int64 v25; // rbx
  __int64 v26; // r15
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 m; // rbx
  int v30; // eax
  int v31; // edx
  __int64 n; // rbx
  __int64 v33; // rdi
  void *v35; // rbx
  int phkResult; // [rsp+20h] [rbp-E0h]
  _BYTE v37[64]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+78h] [rbp-88h] BYREF
  __int128 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h]
  BYTE Data[8]; // [rsp+98h] [rbp-68h] BYREF
  DWORD cbData[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *S2[2]; // [rsp+A8h] [rbp-58h] BYREF
  size_t N; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v46; // [rsp+C0h] [rbp-40h]
  _QWORD v47[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v48; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v49; // [rsp+E8h] [rbp-18h]
  __int128 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+100h] [rbp+0h]
  struct Uev::TemplateInfo *v52[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v53; // [rsp+118h] [rbp+18h]
  _BYTE v54[16]; // [rsp+120h] [rbp+20h] BYREF
  DWORD *p_Type; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]
  __int128 v57; // [rsp+160h] [rbp+60h] BYREF
  __int64 v58; // [rsp+170h] [rbp+70h]
  __int128 v59; // [rsp+178h] [rbp+78h] BYREF
  __int64 v60; // [rsp+188h] [rbp+88h]
  __int64 v61; // [rsp+190h] [rbp+90h]
  WCHAR Src[16]; // [rsp+198h] [rbp+98h] BYREF
  __int128 v63; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v64; // [rsp+1C8h] [rbp+C8h]
  void **v65; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v66[33]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int16 v67; // [rsp+1F9h] [rbp+F9h]
  __int128 v68; // [rsp+200h] [rbp+100h] BYREF
  __int64 v69; // [rsp+210h] [rbp+110h]
  __int64 v70; // [rsp+218h] [rbp+118h]
  _QWORD v71[2]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v72[16]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v73[48]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v74[32]; // [rsp+270h] [rbp+170h] BYREF
  _QWORD v75[3]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v76[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v77[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v78[40]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v79[48]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v80[32]; // [rsp+340h] [rbp+240h] BYREF

  Type = 0;
  v4 = *(_QWORD **)(a1 + 8);
  LODWORD(pExceptionObject) = 0;
  v5 = 0;
  Type = 4;
  *(_DWORD *)Data = 0;
  cbData[0] = 4;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Hvsi\\Office", 0, 0x20019u, &hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( !v7 )
  {
    v8 = RegQueryValueExW(hKey, L"OfficeWDAGEnabledOnHost", 0, &Type, Data, cbData);
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
    if ( !v9 )
      v5 = *(_DWORD *)Data == 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v5 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int128 *))(*(_QWORD *)*v4 + 8LL))(
            *v4,
            L"AppMan-UEV-Subscription-Active",
            &pExceptionObject);
    if ( v10 >= 0 )
    {
      v12 = pExceptionObject;
    }
    else
    {
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
      {
        Type = v10;
        p_Type = &Type;
        v56 = 4;
        McGenEventWrite_EventWriteTransfer(UevAppAgentProvider_Context, SLAPIFailure, v11, 2, v54);
      }
      v12 = 0;
    }
    if ( !v12 )
    {
      std::wstring::wstring(Src, L"SLAPI check failed. The template cannot be added.");
      Uev::SlapiDisabledException::SlapiDisabledException(v54, Src);
      throw (Uev::SlapiDisabledException *)v54;
    }
  }
  v63 = 0;
  v64 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 16LL))(a1, &v63);
  *(_OWORD *)S2 = 0;
  N = 0;
  v46 = 7;
  LOWORD(S2[0]) = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v59, &::Data, 0);
  v57 = 0;
  v58 = 0;
  *(_OWORD *)v52 = 0;
  v53 = 0;
  v65 = &Uev::TemplateParser::`vftable';
  std::wstring::wstring(v66, a2);
  v67 = 1;
  v68 = 0;
  v69 = 0;
  v70 = 7;
  LOWORD(v68) = 0;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v13 = (_WORD *)a2;
  else
    v13 = *(_WORD **)a2;
  v66[32] = *v13 != 60;
  Uev::TemplateParser::ParseTemplateInfo(&v65, &v59, v52, 0);
  Uev::TemplateParser::ParsePrimaryIdAndProcessFileCriteria(&v65, S2, &v57);
  if ( (unsigned __int8)Uev::FindExistingId(S2, &v63) )
  {
    std::wstring::wstring(Src, L"Template ID already exists");
    Uev::DuplicateTemplateException::DuplicateTemplateException(v37, Src);
    throw (Uev::DuplicateTemplateException *)v37;
  }
  v50 = 0;
  v51 = 0;
  if ( !*(_BYTE *)(a1 + 72) || *(_QWORD *)(a1 + 24) == *(_QWORD *)(a1 + 32) )
  {
    LOBYTE(phkResult) = 0;
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *, _QWORD, int))(*(_QWORD *)a1 + 64LL))(
      a1,
      &v59,
      &v50,
      0,
      phkResult);
    if ( (__int128 *)(a1 + 24) != &v50 )
      std::vector<Uev::TemplateInfo>::_Assign_counted_range<Uev::TemplateInfo *>(
        a1 + 24,
        v50,
        0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)&v50 + 1) - v50) >> 3));
  }
  v47[0] = 0;
  v47[1] = 0;
  v14 = operator new(0x40u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  v47[0] = v14;
  for ( i = v50; i != *((_QWORD *)&v50 + 1); i += 232 )
  {
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v47,
      &pExceptionObject,
      i);
    for ( j = *(_QWORD *)(i + 32); j != *(_QWORD *)(i + 40); j += 32 )
    {
      PrimaryTemplateIdFromSecondaryId = Uev::TemplateAdministrator::GetPrimaryTemplateIdFromSecondaryId(v54, j);
      v18 = N;
      v19 = (const wchar_t *)S2;
      if ( v46 > 7 )
        v19 = S2[0];
      v20 = *(_QWORD *)(PrimaryTemplateIdFromSecondaryId + 16);
      if ( *(_QWORD *)(PrimaryTemplateIdFromSecondaryId + 24) > 7u )
        PrimaryTemplateIdFromSecondaryId = *(_QWORD *)PrimaryTemplateIdFromSecondaryId;
      v21 = v20;
      if ( N < v20 )
        v21 = N;
      v22 = !wmemcmp((const wchar_t *)PrimaryTemplateIdFromSecondaryId, v19, v21) && v20 >= v18 && v20 <= v18;
      std::wstring::_Tidy_deallocate(v54);
      if ( v22 )
      {
        std::wstring::wstring(v54, L"The template has been previously replaced");
        Uev::TemplateReplacedException::TemplateReplacedException(v37, v54);
        throw (Uev::TemplateReplacedException *)v37;
      }
    }
  }
  v48 = 0;
  v49 = 0;
  v23 = v52[0];
  for ( k = v52[1]; v23 != k; v23 = (const struct Uev::TemplateInfo *)((char *)v23 + 232) )
  {
    Uev::TemplateInfo::TemplateInfo((Uev::TemplateInfo *)v74, v23);
    v25 = v75[0];
    v26 = v75[1];
    while ( v25 != v26 )
    {
      std::wstring::wstring(v54, v25);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        v47,
        &pExceptionObject,
        v54);
      v27 = v41;
      if ( !*(_BYTE *)(v41 + 25) && !(unsigned __int8)std::operator<<wchar_t>(v54, v41 + 32) && v27 != v47[0] )
      {
        if ( *((_QWORD *)&v48 + 1) == v49 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v48, *((_QWORD *)&v48 + 1), v54);
        }
        else
        {
          std::wstring::wstring(*((_QWORD *)&v48 + 1), v54);
          *((_QWORD *)&v48 + 1) += 32LL;
        }
      }
      std::wstring::_Tidy_deallocate(v54);
      v25 += 32;
    }
    std::vector<Uev::ProcessFileCriteriaDefinition>::_Tidy(v80);
    std::wstring::_Tidy_deallocate(v79);
    std::wstring::_Tidy_deallocate(v78);
    std::wstring::_Tidy_deallocate(v77);
    std::wstring::_Tidy_deallocate(v76);
    std::vector<std::wstring>::_Tidy(v75);
    std::wstring::_Tidy_deallocate(v74);
  }
  Uev::TemplateAdministrator::GetTemplateFilenameForId(Src, (__int64)S2);
  Uev::Common::WriteUtf8File(Src, (LPCWCH)a2);
  Uev::TemplateAdministrator::InstrumentTemplate(v28, a2, 1);
  Uev::TemplateIndex::TemplateIndex((Uev::TemplateIndex *)v71);
  Uev::TemplateIndex::LoadIndex((Uev::TemplateIndex *)v71);
  for ( m = v57; m != *((_QWORD *)&v57 + 1); m += 168 )
    Uev::TemplateIndex::AddTemplateID(v71, m, S2);
  Uev::TemplateIndex::SaveIndex((Uev::TemplateIndex *)v71);
  *(_QWORD *)cbData = _time64(0);
  hKey = 0;
  v30 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
  if ( !(unsigned __int8)Uev::SettingGroup<unsigned __int64>::Set(
                           v30 + 19808,
                           v31,
                           (unsigned int)S2,
                           (unsigned int)cbData,
                           (__int64)&hKey) )
  {
    v35 = operator new(0x68u);
    *(_QWORD *)Data = v35;
    std::wstring::wstring(v54, L"Unable to set template registration timestamp");
    Type = 1;
    *(_QWORD *)&pExceptionObject = Uev::SystemException::SystemException(v35, v54, (unsigned int)hKey);
    throw (Uev::SystemException **)&pExceptionObject;
  }
  v33 = *((_QWORD *)&v48 + 1);
  for ( n = v48; n != v33; n += 32 )
  {
    std::wstring::wstring(v54, n);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 152LL))(a1, v54);
    std::wstring::_Tidy_deallocate(v54);
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    std::vector<Uev::TemplateInfo>::_Insert_counted_range<Uev::TemplateInfo const *>(
      a1 + 24,
      *(_QWORD *)(a1 + 32),
      v52[0],
      0x34F72C234F72C235LL * ((v52[1] - v52[0]) >> 3));
    if ( *(_QWORD *)(a1 + 56) == *(_QWORD *)(a1 + 64) )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1 + 48, *(_QWORD *)(a1 + 56), S2);
    }
    else
    {
      std::wstring::wstring(*(_QWORD *)(a1 + 56), S2);
      *(_QWORD *)(a1 + 56) += 32LL;
    }
    pExceptionObject = 0;
    v41 = 0;
    Uev::TemplateParser::ParseSecondaryIds(&v65, &pExceptionObject);
    std::vector<std::wstring>::_Insert_counted_range<std::wstring const *>(
      a1 + 48,
      *(_QWORD *)(a1 + 56),
      pExceptionObject,
      (__int64)(*((_QWORD *)&pExceptionObject + 1) - pExceptionObject) >> 5);
    std::vector<std::wstring>::_Tidy(&pExceptionObject);
  }
  v71[0] = &Uev::TemplateIndex::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v73);
  std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v72);
  std::wstring::_Tidy_deallocate(Src);
  std::vector<std::wstring>::_Tidy(&v48);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v47);
  std::vector<Uev::TemplateInfo>::~vector<Uev::TemplateInfo>(&v50);
  v65 = &Uev::TemplateParser::`vftable';
  std::wstring::_Tidy_deallocate(&v68);
  std::wstring::_Tidy_deallocate(v66);
  std::vector<Uev::TemplateInfo>::~vector<Uev::TemplateInfo>(v52);
  std::vector<Uev::ProcessFileCriteria>::_Tidy(&v57);
  std::wstring::_Tidy_deallocate(&v59);
  std::wstring::_Tidy_deallocate(S2);
  return std::vector<std::wstring>::_Tidy(&v63);
}

```

## disassembly

```asm
0x14003b0a0  mov     [rsp-8+arg_10], rbx
0x14003b0a5  push    rbp
0x14003b0a6  push    rsi
0x14003b0a7  push    rdi
0x14003b0a8  push    r12
0x14003b0aa  push    r13
0x14003b0ac  push    r14
0x14003b0ae  push    r15
0x14003b0b0  lea     rbp, [rsp-270h]
0x14003b0b8  sub     rsp, 370h
0x14003b0bf  mov     rax, cs:__security_cookie
0x14003b0c6  xor     rax, rsp
0x14003b0c9  mov     [rbp+2A0h+var_40], rax
0x14003b0d0  mov     r13, rdx
0x14003b0d3  mov     rsi, rcx
0x14003b0d6  xor     r14d, r14d
0x14003b0d9  mov     [rsp+3A0h+Type], r14d
0x14003b0de  mov     rdi, [rcx+8]
0x14003b0e2  mov     dword ptr [rbp+2A0h+pExceptionObject], r14d
0x14003b0e6  mov     bl, r14b
0x14003b0e9  lea     r15d, [r14+4]
0x14003b0ed  mov     [rsp+3A0h+Type], r15d
0x14003b0f2  mov     dword ptr [rbp+2A0h+Data], r14d
0x14003b0f6  mov     [rbp+2A0h+cbData], r15d
0x14003b0fa  mov     [rsp+3A0h+hKey], r14
0x14003b0ff  lea     rax, [rsp+3A0h+hKey]
0x14003b104  mov     [rsp+3A0h+phkResult], rax; phkResult
0x14003b109  mov     r9d, 20019h; samDesired
0x14003b10f  xor     r8d, r8d; ulOptions
0x14003b112  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Hvsi\\Office"
0x14003b119  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003b120  call    cs:__imp_RegOpenKeyExW
0x14003b126  mov     r12d, 80070000h
0x14003b12c  test    eax, eax
0x14003b12e  jle     short loc_14003B138
0x14003b130  movzx   eax, ax
0x14003b133  or      eax, r12d
0x14003b136  test    eax, eax
0x14003b138  js      short loc_14003B17B
0x14003b13a  lea     rax, [rbp+2A0h+cbData]
0x14003b13e  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x14003b143  lea     rax, [rbp+2A0h+Data]
0x14003b147  mov     [rsp+3A0h+phkResult], rax; lpData
0x14003b14c  lea     r9, [rsp+3A0h+Type]; lpType
0x14003b151  xor     r8d, r8d; lpReserved
0x14003b154  lea     rdx, ValueName; "OfficeWDAGEnabledOnHost"
0x14003b15b  mov     rcx, [rsp+3A0h+hKey]; hKey
0x14003b160  call    cs:__imp_RegQueryValueExW
0x14003b166  test    eax, eax
0x14003b168  jle     short loc_14003B172
0x14003b16a  movzx   eax, ax
0x14003b16d  or      eax, r12d
0x14003b170  test    eax, eax
0x14003b172  js      short loc_14003B17B
0x14003b174  cmp     dword ptr [rbp+2A0h+Data], 1
0x14003b178  setz    bl
0x14003b17b  mov     rcx, [rsp+3A0h+hKey]; hKey
0x14003b180  test    rcx, rcx
0x14003b183  jz      short loc_14003B18B
0x14003b185  call    cs:__imp_RegCloseKey
0x14003b18b  test    bl, bl
0x14003b18d  jnz     short loc_14003B1F9
0x14003b18f  mov     rcx, [rdi]
0x14003b192  mov     rax, [rcx]
0x14003b195  lea     r8, [rbp+2A0h+pExceptionObject]
0x14003b199  lea     rdx, aAppmanUevSubsc; "AppMan-UEV-Subscription-Active"
0x14003b1a0  mov     rax, [rax+8]
0x14003b1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b1a9  test    eax, eax
0x14003b1ab  jns     short loc_14003B1EE
0x14003b1ad  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, r15b
0x14003b1b4  jz      short loc_14003B1E9
0x14003b1b6  mov     [rsp+3A0h+Type], eax
0x14003b1ba  lea     rax, [rsp+3A0h+Type]
0x14003b1bf  mov     [rbp+2A0h+var_270], rax
0x14003b1c3  mov     [rbp+2A0h+var_268], r15
0x14003b1c7  lea     rax, [rbp+2A0h+var_280]
0x14003b1cb  mov     [rsp+3A0h+phkResult], rax
0x14003b1d0  mov     r9d, 2
0x14003b1d6  lea     rdx, SLAPIFailure
0x14003b1dd  lea     rcx, UevAppAgentProvider_Context
0x14003b1e4  call    McGenEventWrite_EventWriteTransfer
0x14003b1e9  mov     eax, r14d
0x14003b1ec  jmp     short loc_14003B1F1
0x14003b1ee  mov     eax, dword ptr [rbp+2A0h+pExceptionObject]
0x14003b1f1  test    eax, eax
0x14003b1f3  jz      loc_14003B85B
0x14003b1f9  xorps   xmm0, xmm0
0x14003b1fc  movdqu  [rbp+2A0h+var_1E8], xmm0
0x14003b204  mov     [rbp+2A0h+var_1D8], r14
0x14003b20b  mov     rax, [rsi]
0x14003b20e  lea     rdx, [rbp+2A0h+var_1E8]
0x14003b215  mov     rcx, rsi
0x14003b218  mov     rax, [rax+10h]
0x14003b21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b221  xorps   xmm0, xmm0
0x14003b224  movups  xmmword ptr [rbp+2A0h+S2], xmm0
0x14003b228  mov     [rbp+2A0h+N], r14
0x14003b22c  mov     r12d, 7
0x14003b232  mov     [rbp+2A0h+var_2E0], r12
0x14003b236  mov     word ptr [rbp+2A0h+S2], r14w
0x14003b23b  movups  [rbp+2A0h+var_228], xmm0
0x14003b23f  mov     [rbp+2A0h+var_218], r14
0x14003b246  mov     [rbp+2A0h+var_210], r14
0x14003b24d  xor     r8d, r8d
0x14003b250  lea     rdx, Data
0x14003b257  lea     rcx, [rbp+2A0h+var_228]
0x14003b25b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14003b260  nop
0x14003b261  xorps   xmm0, xmm0
0x14003b264  movdqu  [rbp+2A0h+var_240], xmm0
0x14003b269  mov     [rbp+2A0h+var_230], r14
0x14003b26d  movdqu  xmmword ptr [rbp+2A0h+var_298], xmm0
0x14003b272  mov     [rbp+2A0h+var_288], r14
0x14003b276  lea     rax, ??_7TemplateParser@Uev@@6B@; const Uev::TemplateParser::`vftable'
0x14003b27d  mov     [rbp+2A0h+var_1D0], rax
0x14003b284  mov     rdx, r13
0x14003b287  lea     rcx, [rbp+2A0h+var_1C8]
0x14003b28e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003b293  mov     [rbp+2A0h+var_1A7], 1
0x14003b29c  xorps   xmm0, xmm0
0x14003b29f  movups  [rbp+2A0h+var_1A0], xmm0
0x14003b2a6  mov     [rbp+2A0h+var_190], r14
0x14003b2ad  mov     [rbp+2A0h+var_188], r12
0x14003b2b4  mov     word ptr [rbp+2A0h+var_1A0], r14w
0x14003b2bc  cmp     [r13+18h], r12
0x14003b2c0  jbe     short loc_14003B2C8
0x14003b2c2  mov     rax, [r13+0]
0x14003b2c6  jmp     short loc_14003B2CB
0x14003b2c8  mov     rax, r13
0x14003b2cb  cmp     word ptr [rax], 3Ch ; '<'
0x14003b2cf  setnz   [rbp+2A0h+var_1A8]
0x14003b2d6  xor     r9d, r9d
0x14003b2d9  lea     r8, [rbp+2A0h+var_298]
0x14003b2dd  lea     rdx, [rbp+2A0h+var_228]
0x14003b2e1  lea     rcx, [rbp+2A0h+var_1D0]
0x14003b2e8  call    ?ParseTemplateInfo@TemplateParser@Uev@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@VTemplateInfo@Uev@@V?$allocator@VTemplateInfo@Uev@@@std@@@4@_N@Z; Uev::TemplateParser::ParseTemplateInfo(std::wstring const &,std::vector<Uev::TemplateInfo> &,bool)
0x14003b2ed  lea     r8, [rbp+2A0h+var_240]
0x14003b2f1  lea     rdx, [rbp+2A0h+S2]
0x14003b2f5  lea     rcx, [rbp+2A0h+var_1D0]
0x14003b2fc  call    ?ParsePrimaryIdAndProcessFileCriteria@TemplateParser@Uev@@QEAAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@VProcessFileCriteria@Uev@@V?$allocator@VProcessFileCriteria@Uev@@@std@@@4@@Z; Uev::TemplateParser::ParsePrimaryIdAndProcessFileCriteria(std::wstring &,std::vector<Uev::ProcessFileCriteria> &)
0x14003b301  lea     rdx, [rbp+2A0h+var_1E8]
0x14003b308  lea     rcx, [rbp+2A0h+S2]
0x14003b30c  call    ?FindExistingId@Uev@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@@Z; Uev::FindExistingId(std::wstring const &,std::vector<std::wstring> const &)
0x14003b311  test    al, al
0x14003b313  jnz     loc_14003B824
0x14003b319  xorps   xmm0, xmm0
0x14003b31c  movdqu  [rbp+2A0h+var_2B0], xmm0
0x14003b321  mov     [rbp+2A0h+var_2A0], r14
0x14003b325  mov     r15, 34F72C234F72C235h
0x14003b32f  cmp     [rsi+48h], r14b
0x14003b333  jz      short loc_14003B33F
0x14003b335  mov     rax, [rsi+20h]
0x14003b339  cmp     [rsi+18h], rax
0x14003b33d  jnz     short loc_14003B383
0x14003b33f  mov     rax, [rsi]
0x14003b342  mov     byte ptr [rsp+3A0h+phkResult], r14b
0x14003b347  xor     r9d, r9d
0x14003b34a  lea     r8, [rbp+2A0h+var_2B0]
0x14003b34e  lea     rdx, [rbp+2A0h+var_228]
0x14003b352  mov     rcx, rsi
0x14003b355  mov     rax, [rax+40h]
0x14003b359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b35e  lea     rcx, [rsi+18h]
0x14003b362  lea     rax, [rbp+2A0h+var_2B0]
0x14003b366  cmp     rcx, rax
0x14003b369  jz      short loc_14003B383
0x14003b36b  mov     r8, qword ptr [rbp+2A0h+var_2B0+8]
0x14003b36f  mov     rdx, qword ptr [rbp+2A0h+var_2B0]
0x14003b373  sub     r8, rdx
0x14003b376  sar     r8, 3
0x14003b37a  imul    r8, r15
0x14003b37e  call    ??$_Assign_counted_range@PEAVTemplateInfo@Uev@@@?$vector@VTemplateInfo@Uev@@V?$allocator@VTemplateInfo@Uev@@@std@@@std@@AEAAXPEAVTemplateInfo@Uev@@_K@Z; std::vector<Uev::TemplateInfo>::_Assign_counted_range<Uev::TemplateInfo *>(Uev::TemplateInfo *,unsigned __int64)
0x14003b383  mov     [rbp+2A0h+var_2D8], r14
0x14003b387  mov     [rbp+2A0h+var_2D0], r14
0x14003b38b  mov     ecx, 40h ; '@'; Size
0x14003b390  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003b395  mov     [rax], rax
0x14003b398  mov     [rax+8], rax
0x14003b39c  mov     [rax+10h], rax
0x14003b3a0  mov     word ptr [rax+18h], 101h
0x14003b3a6  mov     [rbp+2A0h+var_2D8], rax
0x14003b3aa  mov     rbx, qword ptr [rbp+2A0h+var_2B0]
0x14003b3ae  cmp     rbx, qword ptr [rbp+2A0h+var_2B0+8]
0x14003b3b2  jz      loc_14003B445
0x14003b3b8  mov     r8, rbx
0x14003b3bb  lea     rdx, [rbp+2A0h+pExceptionObject]
0x14003b3bf  lea     rcx, [rbp+2A0h+var_2D8]
0x14003b3c3  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x14003b3c8  mov     rdi, [rbx+20h]
0x14003b3cc  cmp     rdi, [rbx+28h]
0x14003b3d0  jz      short loc_14003B439
0x14003b3d2  mov     rdx, rdi
0x14003b3d5  lea     rcx, [rbp+2A0h+var_280]
0x14003b3d9  call    ?GetPrimaryTemplateIdFromSecondaryId@TemplateAdministrator@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::TemplateAdministrator::GetPrimaryTemplateIdFromSecondaryId(std::wstring const &)
0x14003b3de  mov     r15, [rbp+2A0h+N]
0x14003b3e2  lea     rdx, [rbp+2A0h+S2]
0x14003b3e6  cmp     [rbp+2A0h+var_2E0], r12
0x14003b3ea  cmova   rdx, [rbp+2A0h+S2]; S2
0x14003b3ef  mov     r14, [rax+10h]
0x14003b3f3  cmp     [rax+18h], r12
0x14003b3f7  jbe     short loc_14003B3FC
0x14003b3f9  mov     rax, [rax]
0x14003b3fc  mov     r8, r14
0x14003b3ff  cmp     r15, r14
0x14003b402  cmovb   r8, r15; N
0x14003b406  mov     rcx, rax; S1
0x14003b409  call    wmemcmp
0x14003b40e  test    eax, eax
0x14003b410  jnz     short loc_14003B41E
0x14003b412  cmp     r14, r15
0x14003b415  jb      short loc_14003B41E
0x14003b417  ja      short loc_14003B41E
0x14003b419  mov     r14b, 1
0x14003b41c  jmp     short loc_14003B421
0x14003b41e  xor     r14b, r14b
0x14003b421  lea     rcx, [rbp+2A0h+var_280]
0x14003b425  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b42a  test    r14b, r14b
0x14003b42d  jnz     loc_14003B890
0x14003b433  add     rdi, 20h ; ' '
0x14003b437  jmp     short loc_14003B3CC
0x14003b439  add     rbx, 0E8h
0x14003b440  jmp     loc_14003B3AE
0x14003b445  xorps   xmm0, xmm0
0x14003b448  movdqu  [rbp+2A0h+var_2C8], xmm0
0x14003b44d  xor     r14d, r14d
0x14003b450  mov     [rbp+2A0h+var_2B8], r14
0x14003b454  mov     rdi, [rbp+2A0h+var_298]
0x14003b458  mov     r12, [rbp+2A0h+var_298+8]
0x14003b45c  cmp     rdi, r12
0x14003b45f  jz      loc_14003B56C
0x14003b465  mov     rdx, rdi; struct Uev::TemplateInfo *
0x14003b468  lea     rcx, [rbp+2A0h+var_130]; this
0x14003b46f  call    ??0TemplateInfo@Uev@@QEAA@AEBV01@@Z; Uev::TemplateInfo::TemplateInfo(Uev::TemplateInfo const &)
0x14003b474  nop
0x14003b475  mov     rbx, [rbp+2A0h+var_110]
0x14003b47c  mov     r15, [rbp+2A0h+var_108]
0x14003b483  jmp     short loc_14003B500
0x14003b485  mov     rdx, rbx
0x14003b488  lea     rcx, [rbp+2A0h+var_280]
0x14003b48c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003b491  nop
0x14003b492  lea     r8, [rbp+2A0h+var_280]
0x14003b496  lea     rdx, [rbp+2A0h+pExceptionObject]
0x14003b49a  lea     rcx, [rbp+2A0h+var_2D8]
0x14003b49e  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14003b4a3  mov     r14, [rbp+2A0h+var_310]
0x14003b4a7  cmp     byte ptr [r14+19h], 0
0x14003b4ac  jnz     short loc_14003B4F3
0x14003b4ae  lea     rdx, [r14+20h]
0x14003b4b2  lea     rcx, [rbp+2A0h+var_280]
0x14003b4b6  call    ??$?M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<<wchar_t>(std::wstring const &,std::wstring const &)
0x14003b4bb  test    al, al
0x14003b4bd  jnz     short loc_14003B4F3
0x14003b4bf  cmp     r14, [rbp+2A0h+var_2D8]
0x14003b4c3  jz      short loc_14003B4F3
0x14003b4c5  mov     rax, qword ptr [rbp+2A0h+var_2C8+8]
0x14003b4c9  cmp     rax, [rbp+2A0h+var_2B8]
0x14003b4cd  jz      short loc_14003B4E2
0x14003b4cf  lea     rdx, [rbp+2A0h+var_280]
0x14003b4d3  mov     rcx, rax
0x14003b4d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003b4db  add     qword ptr [rbp+2A0h+var_2C8+8], 20h ; ' '
0x14003b4e0  jmp     short loc_14003B4F3
0x14003b4e2  lea     r8, [rbp+2A0h+var_280]
0x14003b4e6  mov     rdx, rax
0x14003b4e9  lea     rcx, [rbp+2A0h+var_2C8]
0x14003b4ed  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x14003b4f2  nop
0x14003b4f3  lea     rcx, [rbp+2A0h+var_280]
0x14003b4f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b4fc  add     rbx, 20h ; ' '
0x14003b500  cmp     rbx, r15
0x14003b503  jnz     short loc_14003B485
0x14003b505  lea     rcx, [rbp+2A0h+var_60]
0x14003b50c  call    ?_Tidy@?$vector@VProcessFileCriteriaDefinition@Uev@@V?$allocator@VProcessFileCriteriaDefinition@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::ProcessFileCriteriaDefinition>::_Tidy(void)
0x14003b511  lea     rcx, [rbp+2A0h+var_90]
0x14003b518  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b51d  lea     rcx, [rbp+2A0h+var_B8]
0x14003b524  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b529  lea     rcx, [rbp+2A0h+var_D8]
0x14003b530  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b535  lea     rcx, [rbp+2A0h+var_F8]
0x14003b53c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b541  lea     rcx, [rbp+2A0h+var_110]
0x14003b548  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x14003b54d  lea     rcx, [rbp+2A0h+var_130]
0x14003b554  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003b559  add     rdi, 0E8h
0x14003b560  cmp     rdi, r12
0x14003b563  jnz     loc_14003B465
0x14003b569  xor     r14d, r14d
0x14003b56c  lea     rdx, [rbp+2A0h+S2]
0x14003b570  lea     rcx, [rbp+2A0h+Src]; Src
0x14003b577  call    ?GetTemplateFilenameForId@TemplateAdministrator@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::TemplateAdministrator::GetTemplateFilenameForId(std::wstring const &)
0x14003b57c  nop
0x14003b57d  mov     rdx, r13; lpWideCharStr
0x14003b580  lea     rcx, [rbp+2A0h+Src]; lpFileName
0x14003b587  call    ?WriteUtf8File@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; Uev::Common::WriteUtf8File(std::wstring const &,std::wstring const &)
  ... truncated ...
```
