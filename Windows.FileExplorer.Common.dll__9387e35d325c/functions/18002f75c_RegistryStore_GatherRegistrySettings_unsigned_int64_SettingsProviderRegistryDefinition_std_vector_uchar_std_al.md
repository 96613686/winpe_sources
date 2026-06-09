# RegistryStore::GatherRegistrySettings(unsigned __int64,SettingsProviderRegistryDefinition *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18002f75c`
- end: `0x18002fece`
- name: `?GatherRegistrySettings@RegistryStore@@QEAAJ_KPEAUSettingsProviderRegistryDefinition@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1906`
- prototype: `__int64 __fastcall(RegistryStore *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18007ad90`

## callees

- `0x1800077c8`
- `0x180013c5c`
- `0x180015fa0`
- `0x180016440`
- `0x180017a98`
- `0x180029dfc`
- `0x18002abc0`
- `0x18002b060`
- `0x18002b18c`
- `0x18002b618`
- `0x18002b8c0`
- `0x18002f75c`
- `0x18002fed4`
- `0x180030bcc`
- `0x180037780`
- `0x18007e4c8`
- `0x18007ffd0`
- `0x1800806dc`
- `0x180080c54`
- `0x180080d60`
- `0x1800812ac`
- `0x1800832f8`
- `0x18008336c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fa8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fb90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fd1b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002f7ed`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002f7ed`

## string_xrefs

- `0x18002f835`: `\Registry\User\`
- `0x18002f841`: `\Registry\User\`
- `0x18002f851`: `\Registry\Machine\`
- `0x18002f85d`: `\Registry\Machine\`
- `0x18002fdaf`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002fdcc`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002fe29`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002fe6a`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x18002fe8a`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall RegistryStore::GatherRegistrySettings(RegistryStore *this, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 *v4; // r12
  unsigned __int64 i; // r13
  __int64 v7; // rcx
  int PersistedStateLocation; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ecx
  int v12; // ecx
  int v13; // eax
  int RegistryValueWithFallback; // ebx
  const wchar_t *v15; // rdx
  __int64 v16; // r15
  unsigned __int64 j; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r14
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rbx
  _QWORD *PathWithUserSid; // rax
  __int64 v28; // rdx
  __int64 v29; // r15
  const WCHAR *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // r14
  _QWORD *v36; // r9
  char v37; // bl
  __int64 v38; // r15
  __int64 v39; // r14
  _QWORD *v40; // rax
  __int64 v41; // rdx
  char v42; // r15
  __int64 v43; // r12
  __int64 v44; // r14
  __int64 *v45; // rax
  __int64 v46; // rbx
  _QWORD *v47; // rax
  int v48; // r14d
  _QWORD *v49; // rax
  int *v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  _BYTE v53[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v54[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  HLOCAL (__stdcall *v57)(HLOCAL); // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v58; // [rsp+70h] [rbp-90h]
  unsigned __int64 v59; // [rsp+78h] [rbp-88h]
  HLOCAL (__stdcall *v60)(HLOCAL); // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v61; // [rsp+88h] [rbp-78h]
  __int64 *v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  _QWORD v65[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v66; // [rsp+B8h] [rbp-48h] BYREF
  char v67; // [rsp+C0h] [rbp-40h] BYREF
  char v68; // [rsp+C8h] [rbp-38h] BYREF
  char v69; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v70[4]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v71[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v72[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v73[40]; // [rsp+138h] [rbp+38h] BYREF
  int v74[132]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v4 = a4;
  v62 = a4;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
      return 0;
    v7 = (__int64)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i);
    if ( !v7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
        (const char *)0x80070057LL,
        (int)v51);
      return -2147024809;
    }
    v51 = v74;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               v7,
                               *(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 1),
                               *(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 2),
                               *((unsigned int *)&g_configForHostSyncRootManagerRegistryValue + 12 * i + 6));
    if ( PersistedStateLocation < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x2EF,
               (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
               (const char *)(unsigned int)PersistedStateLocation,
               (int)v74);
    *((_BYTE *)this + 40) = 0;
    v11 = *((_DWORD *)&g_configForHostSyncRootManagerRegistryValue + 12 * i + 7);
    if ( !v11 )
    {
      *(_QWORD *)this = -2147483646;
      std::_WChar_traits<unsigned short>::length(L"\\Registry\\Machine\\", v9, v10);
      v15 = L"\\Registry\\Machine\\";
      goto LABEL_12;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      *(_QWORD *)this = -2147483645;
      std::_WChar_traits<unsigned short>::length(L"\\Registry\\User\\", v9, v10);
      v15 = L"\\Registry\\User\\";
LABEL_12:
      std::wstring::_Assign<unsigned short>((char *)this + 8, v15);
      goto LABEL_13;
    }
    if ( v12 != 1 )
      return -2147024809;
    v13 = RegistryStore::OpenHKUWithUserSidForHKCU(this);
    RegistryValueWithFallback = v13;
    if ( v13 < 0 )
      break;
    *((_BYTE *)this + 40) = 1;
LABEL_13:
    v16 = 0;
    v56 = 0;
    v63 = v4[1];
    v64 = *v4;
    for ( j = 0; ; j = v59 + 1 )
    {
      v59 = j;
      if ( j >= (unsigned __int64)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 4) )
        break;
      std::wstring::wstring(v71, v74);
      std::wstring::wstring(v70, *(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 2));
      if ( *((_BYTE *)this + 40) )
      {
        std::_WChar_traits<unsigned short>::length(
          *(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 2),
          v18,
          v19);
        std::wstring::_Assign<unsigned short>(v71, v20);
        std::_WChar_traits<unsigned short>::length(&String1, v21, v22);
        std::wstring::_Assign<unsigned short>(v70, &String1);
      }
      v23 = 32 * j;
      if ( **((_WORD **)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5) + 4 * j) )
      {
        std::wstring::push_back(v71, 92);
        std::wstring::append(v71, *((_QWORD *)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5) + 4 * j));
        if ( !*((_BYTE *)this + 40) )
        {
          std::wstring::push_back(v70, 92);
          std::wstring::append(v70, *((_QWORD *)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5) + 4 * j));
        }
      }
      v24 = (__int64)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5);
      if ( *(_BYTE *)(v24 + v23 + 8) )
      {
        std::vector<_GUID>::vector<_GUID>(v54);
        v53[0] = 0;
        v25 = (__int64)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5);
        if ( *((_BYTE *)this + 40) )
        {
          v26 = *(_QWORD *)(v25 + 32 * j);
          PathWithUserSid = (_QWORD *)RegistryStore::GetPathWithUserSid(this, v72, v71);
          if ( PathWithUserSid[3] > 7u )
            PathWithUserSid = (_QWORD *)*PathWithUserSid;
          RegistryValueWithFallback = RegistryStore::RecurseRegistryKeys(
                                        (_DWORD)this,
                                        (_DWORD)PathWithUserSid,
                                        v26,
                                        (unsigned int)v54,
                                        (__int64)v53);
          std::wstring::_Tidy_deallocate(v72);
          if ( RegistryValueWithFallback < 0 )
          {
            v28 = 803;
            goto LABEL_60;
          }
        }
        else
        {
          v29 = *(_QWORD *)(v25 + 32 * j);
          v30 = (const WCHAR *)v70;
          if ( v70[3] > 7u )
            v30 = (const WCHAR *)v70[0];
          v31 = RegistryStore::GetPathWithUserSid(this, v72, v71);
          if ( *(_QWORD *)(v31 + 24) > 7u )
            v31 = *(_QWORD *)v31;
          RegistryValueWithFallback = RegistryStore::RecurseRegistryKeysWithFallback(
                                        (HKEY *)this,
                                        (const WCHAR *)v31,
                                        v30,
                                        v29,
                                        (__int64)v54,
                                        v53);
          std::wstring::_Tidy_deallocate(v72);
          if ( RegistryValueWithFallback < 0 )
          {
            v28 = 807;
LABEL_60:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v28,
              (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
              (const char *)(unsigned int)RegistryValueWithFallback,
              (int)v51);
            if ( *(_QWORD *)v54 )
            {
              std::_Destroy_range<std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>>>(
                *(_QWORD *)v54,
                *(_QWORD *)&v54[2]);
              std::_Deallocate<16>(*(_QWORD *)v54, (v55 - *(_QWORD *)v54) & 0xFFFFFFFFFFFFFFF0uLL);
              *(_OWORD *)v54 = 0;
              v55 = 0;
            }
            goto LABEL_64;
          }
          v16 = v56;
        }
        if ( !v53[0]
          && (v32 = (__int64)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5), *(_BYTE *)(v32 + v23 + 25))
          || (v32 = (__int64)*(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 5), *(_BYTE *)(v32 + v23 + 26)) )
        {
          v60 = LocalFree;
          v61 = 0;
          v33 = RegistryDataEntry::Create(0, *(_QWORD *)(v32 + v23), &String1, 3);
          std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(&v60, v33);
          std::vector<unsigned char>::insert<unsigned char *,0>(
            (_DWORD)v4,
            (unsigned int)&v66,
            v4[1],
            (_DWORD)v61,
            (__int64)v61 + v61[1] + v61[2] + v61[4] + 42);
          v56 = ++v16;
          std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(&v60);
        }
        v34 = *(_QWORD *)v54;
        v35 = *(_QWORD *)&v54[2];
        if ( *(_QWORD *)v54 != *(_QWORD *)&v54[2] )
        {
          do
          {
            v36 = *(_QWORD **)(v34 + 8);
            std::vector<unsigned char>::insert<unsigned char *,0>(
              (_DWORD)v4,
              (unsigned int)&v67,
              v4[1],
              (_DWORD)v36,
              (__int64)v36 + v36[1] + v36[2] + v36[4] + 42);
            ++v16;
            v34 += 16;
          }
          while ( v34 != v35 );
          v56 = v16;
          v35 = *(_QWORD *)&v54[2];
          v34 = *(_QWORD *)v54;
        }
        if ( v34 )
        {
          std::_Destroy_range<std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>>>(v34, v35);
          std::_Deallocate<16>(*(_QWORD *)v54, (v55 - *(_QWORD *)v54) & 0xFFFFFFFFFFFFFFF0uLL);
        }
      }
      else
      {
        v57 = LocalFree;
        v58 = 0;
        if ( *((_BYTE *)this + 40) )
        {
          v37 = *(_BYTE *)(v24 + v23 + 24);
          v38 = *(_QWORD *)(v24 + v23 + 16);
          v39 = *(_QWORD *)(v24 + v23);
          v40 = (_QWORD *)RegistryStore::GetPathWithUserSid(this, v72, v71);
          if ( v40[3] > 7u )
            v40 = (_QWORD *)*v40;
          RegistryValueWithFallback = RegistryStore::GetRegistryValueWithFallback(
                                        (__int64)this,
                                        (__int64)v40,
                                        (__int64)&String1,
                                        v39,
                                        v38,
                                        v37,
                                        (__int64)&v57);
          std::wstring::_Tidy_deallocate(v72);
          if ( RegistryValueWithFallback < 0 )
          {
            v41 = 845;
            goto LABEL_63;
          }
        }
        else
        {
          v42 = *(_BYTE *)(v24 + v23 + 24);
          v43 = *(_QWORD *)(v24 + v23 + 16);
          v44 = *(_QWORD *)(v24 + 32 * j);
          v45 = (__int64 *)RegistryStore::GetPathWithUserSid(this, v73, v70);
          v46 = (__int64)v45;
          if ( (unsigned __int64)v45[3] > 7 )
            v46 = *v45;
          v47 = (_QWORD *)RegistryStore::GetPathWithUserSid(this, v72, v71);
          if ( v47[3] > 7u )
            v47 = (_QWORD *)*v47;
          RegistryValueWithFallback = RegistryStore::GetRegistryValueWithFallback(
                                        (__int64)this,
                                        (__int64)v47,
                                        v46,
                                        v44,
                                        v43,
                                        v42,
                                        (__int64)&v57);
          std::wstring::_Tidy_deallocate(v72);
          std::wstring::_Tidy_deallocate(v73);
          if ( RegistryValueWithFallback < 0 )
          {
            v41 = 854;
LABEL_63:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v41,
              (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
              (const char *)(unsigned int)RegistryValueWithFallback,
              v52);
            std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(&v57);
LABEL_64:
            std::wstring::_Tidy_deallocate(v70);
            std::wstring::_Tidy_deallocate(v71);
            return RegistryValueWithFallback;
          }
          v4 = v62;
        }
        v16 = ++v56;
        std::vector<unsigned char>::insert<unsigned char *,0>(
          (_DWORD)v4,
          (unsigned int)&v68,
          v4[1],
          (_DWORD)v58,
          (__int64)v58 + v58[1] + v58[2] + v58[4] + 42);
        std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(&v57);
      }
      std::wstring::_Tidy_deallocate(v70);
      std::wstring::_Tidy_deallocate(v71);
    }
    if ( v16 )
    {
      v48 = v63 - v64;
      LODWORD(v51) = *((_DWORD *)&g_configForHostSyncRootManagerRegistryValue + 12 * i + 7);
      v49 = (_QWORD *)RegistryData::Create(
                        *(&g_configForHostSyncRootManagerRegistryValue + 6 * i),
                        *(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 1),
                        *(&g_configForHostSyncRootManagerRegistryValue + 6 * i + 2),
                        *((unsigned int *)&g_configForHostSyncRootManagerRegistryValue + 12 * i + 6),
                        v51,
                        v16);
      v65[0] = LocalFree;
      v65[1] = v49;
      std::vector<unsigned char>::insert<unsigned char *,0>(
        (_DWORD)v4,
        (unsigned int)&v69,
        v48 + *(_DWORD *)v4,
        (_DWORD)v49,
        (__int64)v49 + v49[1] + v49[2] + *v49 + 40);
      std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(v65);
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2FD,
    (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
    (const char *)(unsigned int)v13,
    (int)v74);
  return RegistryValueWithFallback;
}

```

## disassembly

```asm
0x18002f75c  mov     [rsp-8+arg_8], rbx
0x18002f761  push    rbp
0x18002f762  push    rsi
0x18002f763  push    rdi
0x18002f764  push    r12
0x18002f766  push    r13
0x18002f768  push    r14
0x18002f76a  push    r15
0x18002f76c  lea     rbp, [rsp-280h]
0x18002f774  sub     rsp, 380h
0x18002f77b  mov     rax, cs:__security_cookie
0x18002f782  xor     rax, rsp
0x18002f785  mov     [rbp+2B0h+var_40], rax
0x18002f78c  mov     r12, r9
0x18002f78f  mov     [rbp+2B0h+var_320], r9
0x18002f793  mov     rsi, rcx
0x18002f796  xor     r14d, r14d
0x18002f799  mov     r13d, r14d
0x18002f79c  lea     r15, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f7a3  cmp     r13, 3
0x18002f7a7  jnb     loc_18002FEA2
0x18002f7ad  lea     rdi, ds:0[r13*2]
0x18002f7b5  add     rdi, r13
0x18002f7b8  add     rdi, rdi
0x18002f7bb  mov     rcx, [r15+rdi*8]
0x18002f7bf  test    rcx, rcx
0x18002f7c2  jz      loc_18002FE7D
0x18002f7c8  mov     [rsp+3B0h+var_380], r14
0x18002f7cd  mov     dword ptr [rsp+3B0h+var_388], 208h
0x18002f7d5  lea     rax, [rbp+2B0h+var_250]
0x18002f7d9  mov     qword ptr [rsp+3B0h+var_390], rax; int
0x18002f7de  mov     r9d, [r15+rdi*8+18h]
0x18002f7e3  mov     r8, [r15+rdi*8+10h]
0x18002f7e8  mov     rdx, [r15+rdi*8+8]
0x18002f7ed  call    cs:__imp_RtlGetPersistedStateLocation
0x18002f7f3  test    eax, eax
0x18002f7f5  js      loc_18002FE60
0x18002f7fb  mov     [rsi+28h], r14b
0x18002f7ff  mov     ecx, [r15+rdi*8+1Ch]
0x18002f804  test    ecx, ecx
0x18002f806  jz      short loc_18002F84A
0x18002f808  sub     ecx, 1
0x18002f80b  jz      short loc_18002F82E
0x18002f80d  cmp     ecx, 1
0x18002f810  jnz     loc_18002FE9B
0x18002f816  mov     rcx, rsi; this
0x18002f819  call    ?OpenHKUWithUserSidForHKCU@RegistryStore@@AEAAJXZ; RegistryStore::OpenHKUWithUserSidForHKCU(void)
0x18002f81e  mov     ebx, eax
0x18002f820  test    eax, eax
0x18002f822  js      loc_18002FDA5
0x18002f828  mov     byte ptr [rsi+28h], 1
0x18002f82c  jmp     short loc_18002F870
0x18002f82e  mov     qword ptr [rsi], 0FFFFFFFF80000003h
0x18002f835  lea     rcx, aRegistryUser; "\\Registry\\User\\"
0x18002f83c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002f841  lea     rdx, aRegistryUser; "\\Registry\\User\\"
0x18002f848  jmp     short loc_18002F864
0x18002f84a  mov     qword ptr [rsi], 0FFFFFFFF80000002h
0x18002f851  lea     rcx, aRegistryMachin; "\\Registry\\Machine\\"
0x18002f858  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002f85d  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\"
0x18002f864  mov     r8, rax
0x18002f867  lea     rcx, [rsi+8]
0x18002f86b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002f870  mov     r15, r14
0x18002f873  mov     [rsp+3B0h+var_350], r14
0x18002f878  mov     rax, [r12+8]
0x18002f87d  mov     [rbp+2B0h+var_318], rax
0x18002f881  mov     rax, [r12]
0x18002f885  mov     [rbp+2B0h+var_310], rax
0x18002f889  mov     rbx, r14
0x18002f88c  mov     [rsp+3B0h+var_338], rbx
0x18002f891  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f898  cmp     rbx, [rax+rdi*8+20h]
0x18002f89d  jnb     loc_18002FD0A
0x18002f8a3  lea     rdx, [rbp+2B0h+var_250]
0x18002f8a7  lea     rcx, [rbp+2B0h+var_2B8]
0x18002f8ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f8b0  nop
0x18002f8b1  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f8b8  mov     rdx, [rax+rdi*8+10h]
0x18002f8bd  lea     rcx, [rbp+2B0h+var_2D8]
0x18002f8c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f8c6  nop
0x18002f8c7  cmp     [rsi+28h], r14b
0x18002f8cb  jz      short loc_18002F90C
0x18002f8cd  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f8d4  mov     rcx, [rax+rdi*8+10h]
0x18002f8d9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002f8de  mov     r8, rax
0x18002f8e1  mov     rdx, rcx
0x18002f8e4  lea     rcx, [rbp+2B0h+var_2B8]
0x18002f8e8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002f8ed  lea     rcx, String1
0x18002f8f4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002f8f9  mov     r8, rax
0x18002f8fc  lea     rdx, String1
0x18002f903  lea     rcx, [rbp+2B0h+var_2D8]
0x18002f907  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002f90c  mov     r14, rbx
0x18002f90f  shl     r14, 5
0x18002f913  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f91a  mov     rax, [rax+rdi*8+28h]
0x18002f91f  mov     rcx, [r14+rax]
0x18002f923  xor     ebx, ebx
0x18002f925  cmp     [rcx], bx
0x18002f928  jz      short loc_18002F979
0x18002f92a  lea     edx, [rbx+5Ch]
0x18002f92d  lea     rcx, [rbp+2B0h+var_2B8]
0x18002f931  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18002f936  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f93d  mov     rdx, [rax+rdi*8+28h]
0x18002f942  mov     rdx, [rdx+r14]
0x18002f946  lea     rcx, [rbp+2B0h+var_2B8]
0x18002f94a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f94f  cmp     [rsi+28h], bl
0x18002f952  jnz     short loc_18002F979
0x18002f954  lea     edx, [rbx+5Ch]
0x18002f957  lea     rcx, [rbp+2B0h+var_2D8]
0x18002f95b  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18002f960  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f967  mov     rdx, [rax+rdi*8+28h]
0x18002f96c  mov     rdx, [rdx+r14]
0x18002f970  lea     rcx, [rbp+2B0h+var_2D8]
0x18002f974  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f979  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f980  mov     rcx, [rax+rdi*8+28h]
0x18002f985  cmp     [rcx+r14+8], bl
0x18002f98a  jz      loc_18002FB90
0x18002f990  lea     rcx, [rsp+3B0h+var_368]
0x18002f995  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18002f99a  nop
0x18002f99b  mov     [rsp+3B0h+var_370], bl
0x18002f99f  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002f9a6  mov     rax, [rax+rdi*8+28h]
0x18002f9ab  lea     r8, [rbp+2B0h+var_2B8]
0x18002f9af  lea     rdx, [rbp+2B0h+var_298]
0x18002f9b3  mov     rcx, rsi
0x18002f9b6  cmp     [rsi+28h], bl
0x18002f9b9  jz      short loc_18002FA07
0x18002f9bb  mov     rbx, [rax+r14]
0x18002f9bf  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x18002f9c4  nop
0x18002f9c5  cmp     qword ptr [rax+18h], 7
0x18002f9ca  jbe     short loc_18002F9CF
0x18002f9cc  mov     rax, [rax]
0x18002f9cf  lea     rcx, [rsp+3B0h+var_370]
0x18002f9d4  mov     qword ptr [rsp+3B0h+var_390], rcx
0x18002f9d9  lea     r9, [rsp+3B0h+var_368]
0x18002f9de  mov     r8, rbx
0x18002f9e1  mov     rdx, rax
0x18002f9e4  mov     rcx, rsi
0x18002f9e7  call    ?RecurseRegistryKeys@RegistryStore@@AEAAJPEBG0AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeys(ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002f9ec  mov     ebx, eax
0x18002f9ee  lea     rcx, [rbp+2B0h+var_298]
0x18002f9f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f9f7  xor     ecx, ecx
0x18002f9f9  test    ebx, ebx
0x18002f9fb  jns     short loc_18002FA68
0x18002f9fd  mov     edx, 323h
0x18002fa02  jmp     loc_18002FDCC
0x18002fa07  mov     r15, [rax+r14]
0x18002fa0b  lea     rbx, [rbp+2B0h+var_2D8]
0x18002fa0f  cmp     [rbp+2B0h+var_2C0], 7
0x18002fa14  cmova   rbx, [rbp+2B0h+var_2D8]
0x18002fa19  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x18002fa1e  nop
0x18002fa1f  cmp     qword ptr [rax+18h], 7
0x18002fa24  jbe     short loc_18002FA29
0x18002fa26  mov     rax, [rax]
0x18002fa29  lea     rcx, [rsp+3B0h+var_370]
0x18002fa2e  mov     [rsp+3B0h+var_388], rcx
0x18002fa33  lea     rcx, [rsp+3B0h+var_368]
0x18002fa38  mov     qword ptr [rsp+3B0h+var_390], rcx; int
0x18002fa3d  mov     r9, r15
0x18002fa40  mov     r8, rbx
0x18002fa43  mov     rdx, rax
0x18002fa46  mov     rcx, rsi
0x18002fa49  call    ?RecurseRegistryKeysWithFallback@RegistryStore@@AEAAJPEBG00AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@AEA_N@Z; RegistryStore::RecurseRegistryKeysWithFallback(ushort const *,ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &,bool &)
0x18002fa4e  mov     ebx, eax
0x18002fa50  lea     rcx, [rbp+2B0h+var_298]
0x18002fa54  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fa59  xor     ecx, ecx
0x18002fa5b  test    ebx, ebx
0x18002fa5d  js      loc_18002FDC7
0x18002fa63  mov     r15, [rsp+3B0h+var_350]
0x18002fa68  lea     rax, ?g_configForHostSyncRootManagerRegistryValue@@3PAUSettingsProviderRegistryDefinition@@A; SettingsProviderRegistryDefinition near * g_configForHostSyncRootManagerRegistryValue
0x18002fa6f  cmp     [rsp+3B0h+var_370], cl
0x18002fa73  jnz     short loc_18002FA81
0x18002fa75  mov     rdx, [rax+rdi*8+28h]
0x18002fa7a  cmp     [rdx+r14+19h], cl
0x18002fa7f  jnz     short loc_18002FA8D
0x18002fa81  mov     rdx, [rax+rdi*8+28h]
0x18002fa86  cmp     [rdx+r14+1Ah], cl
0x18002fa8b  jz      short loc_18002FB0A
0x18002fa8d  mov     rax, cs:__imp_LocalFree
0x18002fa94  mov     [rbp+2B0h+var_330], rax
0x18002fa98  mov     [rbp+2B0h+var_328], rcx
0x18002fa9c  mov     [rsp+3B0h+var_378], rcx
0x18002faa1  mov     byte ptr [rsp+3B0h+var_388], cl
0x18002faa5  mov     byte ptr [rsp+3B0h+var_390], 1
0x18002faaa  mov     r9d, 3
0x18002fab0  lea     r8, String1
0x18002fab7  mov     rdx, [rdx+r14]
0x18002fabb  call    ?Create@RegistryDataEntry@@SAPEAU1@KPEBG0W4SettingsRegistryAction@@_N2PEBX_K@Z; RegistryDataEntry::Create(ulong,ushort const *,ushort const *,SettingsRegistryAction,bool,bool,void const *,unsigned __int64)
0x18002fac0  mov     rdx, rax
0x18002fac3  lea     rcx, [rbp+2B0h+var_330]
0x18002fac7  call    ?reset@?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@QEAAXPEAURegistryDataEntry@@@Z; std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(RegistryDataEntry *)
0x18002facc  mov     r9, [rbp+2B0h+var_328]
0x18002fad0  mov     rax, [r9+20h]
0x18002fad4  add     rax, 2Ah ; '*'
0x18002fad8  add     rax, [r9+10h]
0x18002fadc  add     rax, [r9+8]
0x18002fae0  add     rax, r9
0x18002fae3  mov     qword ptr [rsp+3B0h+var_390], rax
0x18002fae8  mov     r8, [r12+8]
0x18002faed  lea     rdx, [rbp+2B0h+var_2F8]
0x18002faf1  mov     rcx, r12
0x18002faf4  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x18002faf9  inc     r15
0x18002fafc  mov     [rsp+3B0h+var_350], r15
0x18002fb01  lea     rcx, [rbp+2B0h+var_330]
0x18002fb05  call    ??1?$unique_ptr@URegistryData@@P6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(void)
0x18002fb0a  mov     rbx, qword ptr [rsp+3B0h+var_368]
0x18002fb0f  mov     r14, qword ptr [rsp+3B0h+var_368+8]
0x18002fb14  cmp     rbx, r14
0x18002fb17  jz      short loc_18002FB61
0x18002fb19  mov     r9, [rbx+8]
0x18002fb1d  mov     rax, [r9+20h]
0x18002fb21  add     rax, 2Ah ; '*'
0x18002fb25  add     rax, [r9+10h]
0x18002fb29  add     rax, [r9+8]
0x18002fb2d  add     rax, r9
0x18002fb30  mov     qword ptr [rsp+3B0h+var_390], rax
0x18002fb35  mov     r8, [r12+8]
0x18002fb3a  lea     rdx, [rbp+2B0h+var_2F0]
0x18002fb3e  mov     rcx, r12
0x18002fb41  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x18002fb46  inc     r15
0x18002fb49  add     rbx, 10h
0x18002fb4d  cmp     rbx, r14
0x18002fb50  jnz     short loc_18002FB19
0x18002fb52  mov     [rsp+3B0h+var_350], r15
0x18002fb57  mov     r14, qword ptr [rsp+3B0h+var_368+8]
0x18002fb5c  mov     rbx, qword ptr [rsp+3B0h+var_368]
0x18002fb61  test    rbx, rbx
0x18002fb64  jz      loc_18002FCE7
0x18002fb6a  mov     rdx, r14
0x18002fb6d  mov     rcx, rbx
0x18002fb70  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@std@@@std@@YAXPEAV?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@0@QEAV10@AEAV?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>>>(std::unique_ptr<RegistryDataEntry,void * (*)(void *)> *,std::unique_ptr<RegistryDataEntry,void * (*)(void *)> * const,std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>> &)
0x18002fb75  mov     rcx, qword ptr [rsp+3B0h+var_368]
0x18002fb7a  mov     rdx, [rsp+3B0h+var_358]
0x18002fb7f  sub     rdx, rcx
0x18002fb82  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002fb86  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002fb8b  jmp     loc_18002FCE7
0x18002fb90  mov     rax, cs:__imp_LocalFree
0x18002fb97  mov     [rsp+3B0h+var_348], rax
0x18002fb9c  mov     [rsp+3B0h+var_340], rbx
0x18002fba1  cmp     [rsi+28h], bl
0x18002fba4  jz      short loc_18002FC14
0x18002fba6  mov     bl, [rcx+r14+18h]
0x18002fbab  mov     r15, [rcx+r14+10h]
0x18002fbb0  mov     r14, [rcx+r14]
0x18002fbb4  lea     r8, [rbp+2B0h+var_2B8]
0x18002fbb8  lea     rdx, [rbp+2B0h+var_298]
0x18002fbbc  mov     rcx, rsi
0x18002fbbf  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x18002fbc4  nop
0x18002fbc5  cmp     qword ptr [rax+18h], 7
0x18002fbca  jbe     short loc_18002FBCF
0x18002fbcc  mov     rax, [rax]
0x18002fbcf  lea     rcx, [rsp+3B0h+var_348]
0x18002fbd4  mov     [rsp+3B0h+var_380], rcx
0x18002fbd9  mov     byte ptr [rsp+3B0h+var_388], bl
0x18002fbdd  mov     qword ptr [rsp+3B0h+var_390], r15
0x18002fbe2  mov     r9, r14
0x18002fbe5  lea     r8, String1
0x18002fbec  mov     rdx, rax
0x18002fbef  mov     rcx, rsi
0x18002fbf2  call    ?GetRegistryValueWithFallback@RegistryStore@@QEAAJPEBG000_NAEAV?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@Z; RegistryStore::GetRegistryValueWithFallback(ushort const *,ushort const *,ushort const *,ushort const *,bool,std::unique_ptr<RegistryDataEntry,void * (*)(void *)> &)
0x18002fbf7  mov     ebx, eax
0x18002fbf9  lea     rcx, [rbp+2B0h+var_298]
0x18002fbfd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fc02  test    ebx, ebx
0x18002fc04  jns     loc_18002FCA0
0x18002fc0a  mov     edx, 34Dh
0x18002fc0f  jmp     loc_18002FE26
0x18002fc14  mov     r15b, [rcx+r14+18h]
0x18002fc19  mov     r12, [rcx+r14+10h]
0x18002fc1e  mov     r14, [rcx+r14]
0x18002fc22  lea     r8, [rbp+2B0h+var_2D8]
0x18002fc26  lea     rdx, [rbp+2B0h+var_278]
0x18002fc2a  mov     rcx, rsi
0x18002fc2d  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x18002fc32  mov     rbx, rax
0x18002fc35  cmp     qword ptr [rax+18h], 7
0x18002fc3a  jbe     short loc_18002FC3F
0x18002fc3c  mov     rbx, [rax]
0x18002fc3f  lea     r8, [rbp+2B0h+var_2B8]
  ... truncated ...
```
