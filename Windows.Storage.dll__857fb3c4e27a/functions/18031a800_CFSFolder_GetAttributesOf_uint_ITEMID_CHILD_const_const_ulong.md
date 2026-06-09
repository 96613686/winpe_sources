# CFSFolder::GetAttributesOf(uint,_ITEMID_CHILD const * const *,ulong *)

- ea: `0x18031a800`
- end: `0x18031afe3`
- name: `?GetAttributesOf@CFSFolder@@UEAAJIPEBQEFBU_ITEMID_CHILD@@PEAK@Z`
- size: `2019`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, unsigned int, const struct _ITEMID_CHILD *const *, unsigned int *)`
- caller_count: `0`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180040290`
- `0x1800432f0`
- `0x180043320`
- `0x18004c600`
- `0x18008acc0`
- `0x18008b3a0`
- `0x180091870`
- `0x180093d60`
- `0x180093ef0`
- `0x180096e70`
- `0x1800979d0`
- `0x1800989e0`
- `0x1800997b0`
- `0x1800e02b0`
- `0x1800e08b0`
- `0x18012dc90`
- `0x18012e870`
- `0x18012fa50`
- `0x18013189c`
- `0x180174660`
- `0x180221318`
- `0x18031a800`
- `0x1803a4cb0`
- `0x1803a96d9`
- `0x1805bca3c`
- `0x18065a010`

## import_xrefs

- `ntdll!RtlIsPartialPlaceholder` at `0x18031aa0f`
- `ntdll!RtlIsPartialPlaceholder` at `0x18031aa0f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18031aade`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18031aade`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031a8f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031a937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031ab88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031aee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031af84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031a8f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031a937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031ab88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031aee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18031af84`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18031acaf`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18031ad0d`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18031ad60`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18031acaf`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18031ad0d`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18031ad60`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18031ad83`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18031ad83`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18031a923`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18031a923`
- `ext-ms-win-shell-ntshrui-l1-1-0!IsPathSharedW` at `0x18031ac3f`
- `ext-ms-win-shell-ntshrui-l1-1-0!IsPathSharedW` at `0x18031ac3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CFSFolder::GetAttributesOf(
        CFSFolder *this,
        int a2,
        const struct _ITEMID_CHILD **a3,
        unsigned int *a4)
{
  const struct IDFOLDER *v7; // rax
  const struct IDFOLDER *v8; // r12
  int v9; // edi
  __int16 FullFileAttributes; // r15
  CFSFolder *v11; // r13
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // eax
  int v17; // eax
  unsigned int ReparsePointTag; // ebx
  unsigned int v19; // eax
  int v20; // eax
  bool v21; // bl
  __int16 v22; // r12
  CMountPoint *v23; // r14
  CFSFolder *v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // edi
  CCLSIDInfoCache *v28; // rcx
  unsigned int v29; // ebx
  CCLSIDInfoCache *v30; // rcx
  unsigned int RestrictedAttributes; // eax
  int v32; // eax
  int (__fastcall **v33)(LPCWSTR, GUID *, struct _GUID *); // rax
  int (__fastcall **v34)(LPCWSTR, GUID *, struct _GUID *); // rax
  char v35; // bl
  int v36; // [rsp+20h] [rbp-E0h]
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v38; // [rsp+38h] [rbp-C8h] BYREF
  const struct IDFOLDER *v39; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v42; // [rsp+60h] [rbp-A0h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v43; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v44[80]; // [rsp+A0h] [rbp-60h] BYREF
  struct IDFOLDER *v45; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v38 = a3;
  if ( !a2 )
  {
    v9 = 1073742149;
    goto LABEL_142;
  }
  v7 = CFSFolder::_IsValidID(this, *a3);
  v8 = v7;
  v39 = v7;
  v9 = 1073742149;
  if ( a2 != 1 || !v7 )
  {
LABEL_142:
    if ( (*(_BYTE *)a4 & 0x32) != 0
      && (CFSFolder::_GetVolumeInformationFlags((CFSFolder *)((char *)this - 48)) & 0x80000) == 0 )
    {
      v9 = 1073742199;
    }
    goto LABEL_145;
  }
  FullFileAttributes = GetFullFileAttributes(v7);
  v11 = (CFSFolder *)((char *)this - 48);
  CFileSysItemString::CFileSysItemString(
    (CFileSysItemString *)v44,
    (CFSFolder *)((char *)this - 48),
    *(const struct _ITEMIDLIST_RELATIVE **)v38,
    v8);
  pv = 0;
  if ( (*a4 & 0x3020010) != 0 )
  {
    pv = 0;
    v12 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, LPVOID *))(*((_QWORD *)this + 33) + 112LL))(
            (char *)this + 264,
            *(_QWORD *)v38,
            1,
            &pv);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE03,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v12,
        v36);
      if ( pv )
        CoTaskMemFree(pv);
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v44);
      return v13;
    }
  }
  if ( (*a4 & 0x1000000) == 0 || (LODWORD(pszPath) = 0, (unsigned int)PathFileExistsAndAttributesW(pv, &pszPath)) )
  {
    v15 = *a4;
    if ( (*a4 & 0x4000000) != 0 && (FullFileAttributes & 0x800) != 0 )
      v9 = 1140851013;
    if ( (v15 & 0x2000) != 0 && (FullFileAttributes & 0x4000) != 0 )
      v9 |= 0x2000u;
    if ( (*((_BYTE *)this + 488) & 0x40) != 0 )
      goto LABEL_29;
    if ( (v15 & 0x40000) != 0
      && !((FullFileAttributes & 0x10) != 0
         ? (CFSFolder::_GetVolumeInformationFlags((CFSFolder *)((char *)this - 48)) & 0x80000) == 0
         : (FullFileAttributes & 1) == 0) )
    {
      v9 |= 0x40000u;
    }
    if ( (*(_BYTE *)a4 & 0x22) != 0
      && (CFSFolder::_GetVolumeInformationFlags((CFSFolder *)((char *)this - 48)) & 0x80000) == 0 )
    {
LABEL_29:
      v9 |= 0x22u;
    }
    v17 = *a4;
    if ( (*a4 & 0x80000) != 0 && (FullFileAttributes & 2) != 0 )
      v9 |= 0x80000u;
    if ( (v17 & 0x1000) != 0
      && (FullFileAttributes & 4) != 0
      && ((FullFileAttributes & 0x10) == 0 || (FullFileAttributes & 2) != 0) )
    {
      v9 |= 0x1000u;
    }
    if ( (v17 & 0x800) != 0 )
    {
      if ( v45 )
      {
        ReparsePointTag = CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v44);
        v19 = GetFullFileAttributes(v45);
        if ( (unsigned __int8)RtlIsPartialPlaceholder(v19, ReparsePointTag) )
          v9 |= 0x800u;
      }
    }
    if ( (*a4 & 0x100000) != 0 )
    {
      if ( !(unsigned int)ShowSuperHidden() && (FullFileAttributes & 6) == 6
        || (FullFileAttributes & 2) != 0
        && (memset(&v42, 0, sizeof(v42)), SHGetSetSettings(&v42, 1u, 0), (*(_BYTE *)&v42 & 1) == 0) )
      {
        v9 |= 0x100000u;
      }
    }
    if ( (*a4 & 0x4000) != 0 )
    {
      if ( (*(unsigned int (__fastcall **)(char *, const struct IDFOLDER *))(*((_QWORD *)this + 33) + 104LL))(
             (char *)this + 264,
             v8) )
      {
        goto LABEL_70;
      }
      v20 = *((_DWORD *)v11 + 141);
      if ( !v20 )
      {
        v21 = 0;
        if ( *((_DWORD *)v11 + 148) != 2 )
        {
          pszPath = 0;
          if ( CFSFolder::GetFolderPath(v11, (unsigned __int16 **)&pszPath) >= 0 )
          {
            v22 = CFSFolder::_Attributes(v11);
            if ( PathIsUNCW(pszPath) )
            {
              v21 = (v22 & 0x1000) != 0 || GetUNCPathSpeed(pszPath) - 1 <= 0x18F;
            }
            else
            {
              *(_QWORD *)&Buf1.Data1 = 0;
              if ( (int)CMountPoint::GetMountPoint(pszPath, 1, &Buf1) >= 0 )
              {
                v23 = *(CMountPoint **)&Buf1.Data1;
                if ( *((_DWORD *)v11 + 148) == 1
                  || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&Buf1.Data1 + 360LL))(*(_QWORD *)&Buf1.Data1) )
                {
                  v21 = (v22 & 0x1000) != 0
                     || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v23 + 512LL))(v23);
                }
                CMountPoint::Release(v23);
              }
            }
            v8 = v39;
          }
          if ( pszPath )
            CoTaskMemFree((LPVOID)pszPath);
        }
        v20 = 2 - v21;
        *((_DWORD *)v11 + 141) = v20;
      }
      if ( v20 == 1 )
LABEL_70:
        v9 |= 0x4000u;
    }
    if ( (((*((_BYTE *)v8 + 2) & 0x37) - 49) & 0xFB) != 0 )
    {
      if ( (*a4 & 0x400000) != 0
        && ((FullFileAttributes & 0x400) == 0
         || CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v44) != -1610612724) )
      {
        v9 |= 0x400000u;
      }
      if ( (*(_BYTE *)a4 & 0x10) != 0 && (CFSFolder::_GetVolumeInformationFlags(v11) & 0x80000) == 0 )
        v9 |= 0x10u;
    }
    else
    {
      v9 |= 0x30800008u;
      if ( (*(_BYTE *)a4 & 0x10) != 0
        && (CFSFolder::_GetVolumeInformationFlags(v11) & 0x80000) == 0
        && (unsigned int)CFSFolder::_CanRenameFolder(v24, (const unsigned __int16 *)pv) )
      {
        v9 |= 0x10u;
      }
      if ( (*a4 & 0x2000000) != 0 && CFSFolder::IsOnRemovableVolume(v11) )
        v9 |= 0x2000000u;
      if ( (*a4 & 0x20000) != 0 && (unsigned int)IsPathSharedW(pv, 0) )
        v9 |= 0x20000u;
    }
    if ( (*a4 & 0x10000) != 0 )
    {
      if ( (CFileSysItemString::ClassFlags((CFileSysItemString *)v44) & 0x1000000) != 0
        || (FullFileAttributes & 0x400) != 0
        && ((v25 = CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v44), v25 == -2147483638)
         || v25 == -1610612733
         || v25 == -1610612724) )
      {
        v9 |= 0x10000u;
      }
    }
    v26 = v9 & *a4;
    if ( (v26 & 0xB080013F) != 0 || (*a4 & 0xB0C50108) != 0 )
    {
      Buf1 = 0;
      if ( (unsigned int)CFileSysItemString::GetJunctionClsid(v44, 3, &Buf1) )
      {
        v27 = v9 & 0xEF7FFEF7;
        if ( !memcmp_0(&Buf1, &CLSID_FolderShortcut, 0x10u) && (unsigned int)IsAppCompatModeEnabled(9) )
          v27 &= ~0x20000000u;
        v29 = v27 | CCLSIDInfoCache::GetAttribute(v28, &Buf1, 0x80000000, 0xB0C50108) & 0xB0C50108;
        RestrictedAttributes = CCLSIDInfoCache::GetRestrictedAttributes(v30, &Buf1);
        if ( RestrictedAttributes )
        {
          v32 = ~RestrictedAttributes;
          v9 = v29 & v32;
          *a4 &= v32;
        }
        else
        {
          v9 = v29;
        }
        if ( (FullFileAttributes & 0x10) == 0 && (unsigned int)IsAppCompatModeEnabled(9) )
          v9 &= ~0x20000000u;
        if ( (v9 & 0x30000000) == 0x20000000 && (SHGetObjectCompatFlags(0, &Buf1) & 0x10) != 0 )
          v9 |= 0x10000000u;
      }
    }
    else if ( !v26 && !(unsigned int)IsAppCompatModeEnabled(21) )
    {
      v9 = 0;
LABEL_131:
      if ( (*a4 & 0x8000) != 0 )
      {
        v35 = GetFullFileAttributes(v8);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudFileStateIcon>::__private_IsEnabledPreCheck(
          &`wil::Feature<__WilFeatureTraits_Feature_CloudFileStateIcon>::GetImpl'::`2'::impl,
          0);
        if ( (v35 & 2) != 0 )
          v9 |= 0x8000u;
      }
      if ( (*a4 & 0x8000000) != 0
        && (((*((_BYTE *)v8 + 2) & 0x37) - 50) & 0xFB) == 0
        && (CFileSysItemString::ClassFlags((CFileSysItemString *)v44) & 0x500000) != 0 )
      {
        v9 |= 0x8000000u;
      }
      if ( pv )
        CoTaskMemFree(pv);
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v44);
LABEL_145:
      *a4 = v9;
      return 0;
    }
    if ( (v9 & 0x20000000) != 0 && (*a4 & 0x80000000) != 0 )
    {
      if ( (FullFileAttributes & 0x400) != 0 )
      {
        v9 |= 0x80000000;
      }
      else if ( v9 >= 0 )
      {
        pszPath = 0;
        if ( (int)CFSFolder::_Bind(
                    v11,
                    0,
                    *(const struct _ITEMIDLIST_RELATIVE **)v38,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    (void **)&pszPath) >= 0 )
        {
          *(_QWORD *)&Buf1.Data1 = 0;
          *(GUID *)&v42 = GUID_NULL;
          v33 = *(int (__fastcall ***)(LPCWSTR, GUID *, struct _GUID *))pszPath;
          *(_QWORD *)&Buf1.Data1 = 0;
          if ( (*v33)(pszPath, &GUID_053b4a86_0dc9_40a3_b7ed_bc6a2e951f48, &Buf1) >= 0 )
            (*(void (__fastcall **)(_QWORD, struct $D321FDA48A4D82B6F6ABB6499405B63E *))(**(_QWORD **)&Buf1.Data1 + 24LL))(
              *(_QWORD *)&Buf1.Data1,
              &v42);
          if ( !memcmp_0(&v42, &FOLDERTYPEID_CompressedFolder, 0x10u) )
          {
            v9 |= 0x80000000;
          }
          else
          {
            memset(&v43, 0, sizeof(v43));
            SHGetSetSettings(&v43, 1u, 0);
            v39 = 0;
            v34 = *(int (__fastcall ***)(LPCWSTR, GUID *, struct _GUID *))pszPath;
            v39 = 0;
            if ( !((unsigned int (__fastcall *)(LPCWSTR, _QWORD, _QWORD, const struct IDFOLDER **))v34[4])(
                    pszPath,
                    0,
                    ((*(_BYTE *)&v43 & 1) << 7) | 0x30u,
                    &v39) )
            {
              v38 = 0;
              if ( !(*(unsigned int (__fastcall **)(const struct IDFOLDER *, __int64, LPVOID *, _QWORD))(*(_QWORD *)v39 + 24LL))(
                      v39,
                      1,
                      &v38,
                      0) )
              {
                v9 |= 0x80000000;
                CoTaskMemFree(v38);
              }
            }
            if ( v39 )
              (*(void (__fastcall **)(const struct IDFOLDER *))(*(_QWORD *)v39 + 16LL))(v39);
          }
          (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
          if ( *(_QWORD *)&Buf1.Data1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&Buf1.Data1 + 16LL))(*(_QWORD *)&Buf1.Data1);
        }
      }
    }
    goto LABEL_131;
  }
  if ( pv )
    CoTaskMemFree(pv);
  CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v44);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18031a800  mov     [rsp-8+arg_8], rbx
0x18031a805  push    rbp
0x18031a806  push    rsi
0x18031a807  push    rdi
0x18031a808  push    r12
0x18031a80a  push    r13
0x18031a80c  push    r14
0x18031a80e  push    r15
0x18031a810  lea     rbp, [rsp-260h]
0x18031a818  sub     rsp, 360h
0x18031a81f  mov     rax, cs:__security_cookie
0x18031a826  xor     rax, rsp
0x18031a829  mov     [rbp+290h+var_40], rax
0x18031a830  mov     rsi, r9
0x18031a833  mov     [rsp+390h+var_358], r8
0x18031a838  mov     ebx, edx
0x18031a83a  mov     r14, rcx
0x18031a83d  test    edx, edx
0x18031a83f  jz      loc_18031AF96
0x18031a845  mov     rdx, [r8]; struct _ITEMIDLIST_RELATIVE *
0x18031a848  call    ?_IsValidID@CFSFolder@@IEAAPEFBUIDFOLDER@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CFSFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x18031a84d  mov     r12, rax
0x18031a850  mov     [rsp+390h+var_350], rax
0x18031a855  mov     edi, 40000145h
0x18031a85a  cmp     ebx, 1
0x18031a85d  jnz     loc_18031AF9B
0x18031a863  test    rax, rax
0x18031a866  jz      loc_18031AF9B
0x18031a86c  mov     rcx, rax; struct IDFOLDER *
0x18031a86f  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x18031a874  mov     r15d, eax
0x18031a877  lea     r13, [r14-30h]
0x18031a87b  mov     r9, r12; struct IDFOLDER *
0x18031a87e  mov     rbx, [rsp+390h+var_358]
0x18031a883  mov     r8, [rbx]; struct _ITEMIDLIST_RELATIVE *
0x18031a886  mov     rdx, r13; struct CFSFolder *
0x18031a889  lea     rcx, [rbp+290h+var_2F0]; this
0x18031a88d  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x18031a892  nop
0x18031a893  xor     eax, eax
0x18031a895  mov     [rsp+390h+pv], rax
0x18031a89a  test    dword ptr [rsi], 3020010h
0x18031a8a0  jz      short loc_18031A90D
0x18031a8a2  lea     rcx, [r14+108h]
0x18031a8a9  mov     [rsp+390h+pv], rax
0x18031a8ae  mov     rax, [rcx]
0x18031a8b1  lea     r9, [rsp+390h+pv]
0x18031a8b6  mov     r8d, 1
0x18031a8bc  mov     rdx, [rbx]
0x18031a8bf  mov     rax, [rax+70h]
0x18031a8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031a8c8  mov     ebx, eax
0x18031a8ca  test    eax, eax
0x18031a8cc  jns     short loc_18031A90B
0x18031a8ce  mov     rcx, [rbp+298h]; this
0x18031a8d5  mov     r9d, eax; char *
0x18031a8d8  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18031a8df  mov     edx, 0E03h; void *
0x18031a8e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031a8e9  nop
0x18031a8ea  mov     rcx, [rsp+390h+pv]; pv
0x18031a8ef  test    rcx, rcx
0x18031a8f2  jz      short loc_18031A8FB
0x18031a8f4  call    cs:__imp_CoTaskMemFree
0x18031a8fa  nop
0x18031a8fb  lea     rcx, [rbp+290h+var_2F0]; this
0x18031a8ff  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x18031a904  mov     eax, ebx
0x18031a906  jmp     loc_18031AFB9
0x18031a90b  xor     eax, eax
0x18031a90d  test    dword ptr [rsi], 1000000h
0x18031a913  jz      short loc_18031A951
0x18031a915  mov     dword ptr [rsp+390h+pszPath], eax
0x18031a919  lea     rdx, [rsp+390h+pszPath]
0x18031a91e  mov     rcx, [rsp+390h+pv]
0x18031a923  call    cs:__imp_PathFileExistsAndAttributesW
0x18031a929  test    eax, eax
0x18031a92b  jnz     short loc_18031A951
0x18031a92d  mov     rcx, [rsp+390h+pv]; pv
0x18031a932  test    rcx, rcx
0x18031a935  jz      short loc_18031A93E
0x18031a937  call    cs:__imp_CoTaskMemFree
0x18031a93d  nop
0x18031a93e  lea     rcx, [rbp+290h+var_2F0]; this
0x18031a942  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x18031a947  mov     eax, 80004005h
0x18031a94c  jmp     loc_18031AFB9
0x18031a951  mov     eax, [rsi]
0x18031a953  bt      eax, 1Ah
0x18031a957  jnb     short loc_18031A966
0x18031a959  bt      r15d, 0Bh
0x18031a95e  mov     ecx, 44000145h
0x18031a963  cmovb   edi, ecx
0x18031a966  bt      eax, 0Dh
0x18031a96a  jnb     short loc_18031A977
0x18031a96c  bt      r15d, 0Eh
0x18031a971  jnb     short loc_18031A977
0x18031a973  bts     edi, 0Dh
0x18031a977  test    byte ptr [r14+1E8h], 40h
0x18031a97f  jnz     short loc_18031A9B9
0x18031a981  bt      eax, 12h
0x18031a985  jnb     short loc_18031A9A6
0x18031a987  test    r15b, 10h
0x18031a98b  jz      short loc_18031A99C
0x18031a98d  mov     rcx, r13; this
0x18031a990  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18031a995  test    eax, 80000h
0x18031a99a  jmp     short loc_18031A9A0
0x18031a99c  test    r15b, 1
0x18031a9a0  jz      short loc_18031A9A6
0x18031a9a2  bts     edi, 12h
0x18031a9a6  test    byte ptr [rsi], 22h
0x18031a9a9  jz      short loc_18031A9BC
0x18031a9ab  mov     rcx, r13; this
0x18031a9ae  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18031a9b3  bt      eax, 13h
0x18031a9b7  jb      short loc_18031A9BC
0x18031a9b9  or      edi, 22h
0x18031a9bc  mov     eax, [rsi]
0x18031a9be  bt      eax, 13h
0x18031a9c2  jnb     short loc_18031A9CE
0x18031a9c4  test    r15b, 2
0x18031a9c8  jz      short loc_18031A9CE
0x18031a9ca  bts     edi, 13h
0x18031a9ce  bt      eax, 0Ch
0x18031a9d2  jnb     short loc_18031A9EA
0x18031a9d4  test    r15b, 4
0x18031a9d8  jz      short loc_18031A9EA
0x18031a9da  test    r15b, 10h
0x18031a9de  jz      short loc_18031A9E6
0x18031a9e0  test    r15b, 2
0x18031a9e4  jz      short loc_18031A9EA
0x18031a9e6  bts     edi, 0Ch
0x18031a9ea  bt      eax, 0Bh
0x18031a9ee  jnb     short loc_18031AA1D
0x18031a9f0  cmp     [rbp+290h+var_2A0], 0
0x18031a9f5  jz      short loc_18031AA1D
0x18031a9f7  lea     rcx, [rbp+290h+var_2F0]; this
0x18031a9fb  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x18031aa00  mov     ebx, eax
0x18031aa02  mov     rcx, [rbp+290h+var_2A0]; struct IDFOLDER *
0x18031aa06  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x18031aa0b  mov     edx, ebx
0x18031aa0d  mov     ecx, eax
0x18031aa0f  call    cs:__imp_RtlIsPartialPlaceholder
0x18031aa15  test    al, al
0x18031aa17  jz      short loc_18031AA1D
0x18031aa19  bts     edi, 0Bh
0x18031aa1d  test    dword ptr [rsi], 100000h
0x18031aa23  jz      short loc_18031AA68
0x18031aa25  call    ShowSuperHidden
0x18031aa2a  test    eax, eax
0x18031aa2c  jnz     short loc_18031AA38
0x18031aa2e  mov     eax, r15d
0x18031aa31  and     eax, 6
0x18031aa34  cmp     al, 6
0x18031aa36  jz      short loc_18031AA64
0x18031aa38  test    r15b, 2
0x18031aa3c  jz      short loc_18031AA68
0x18031aa3e  xorps   xmm0, xmm0
0x18031aa41  movups  xmmword ptr [rsp+390h+var_330.fShowAllObjects], xmm0
0x18031aa46  movups  xmmword ptr [rsp+390h+var_330.iSortDirection], xmm0
0x18031aa4b  xor     r8d, r8d; bSet
0x18031aa4e  mov     edx, 1; dwMask
0x18031aa53  lea     rcx, [rsp+390h+var_330]; lpss
0x18031aa58  call    SHGetSetSettings
0x18031aa5d  test    byte ptr [rsp+390h+var_330.fShowAllObjects], 1
0x18031aa62  jnz     short loc_18031AA68
0x18031aa64  bts     edi, 14h
0x18031aa68  test    dword ptr [rsi], 4000h
0x18031aa6e  jz      loc_18031ABA5
0x18031aa74  lea     rcx, [r14+108h]
0x18031aa7b  mov     rax, [rcx]
0x18031aa7e  mov     rdx, r12
0x18031aa81  mov     rax, [rax+68h]
0x18031aa85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031aa8a  test    eax, eax
0x18031aa8c  jnz     loc_18031ABA1
0x18031aa92  mov     eax, [r13+234h]
0x18031aa99  test    eax, eax
0x18031aa9b  jnz     loc_18031AB9C
0x18031aaa1  xor     bl, bl
0x18031aaa3  cmp     dword ptr [r13+250h], 2
0x18031aaab  jz      loc_18031AB8E
0x18031aab1  xor     r14d, r14d
0x18031aab4  mov     [rsp+390h+pszPath], r14
0x18031aab9  lea     rdx, [rsp+390h+pszPath]; unsigned __int16 **
0x18031aabe  mov     rcx, r13; this
0x18031aac1  call    ?GetFolderPath@CFSFolder@@QEAAJPEAPEAG@Z; CFSFolder::GetFolderPath(ushort * *)
0x18031aac6  test    eax, eax
0x18031aac8  js      loc_18031AB7E
0x18031aace  mov     rcx, r13; this
0x18031aad1  call    ?_Attributes@CFSFolder@@IEAAKXZ; CFSFolder::_Attributes(void)
0x18031aad6  mov     r12d, eax
0x18031aad9  mov     rcx, [rsp+390h+pszPath]; pszPath
0x18031aade  call    cs:__imp_PathIsUNCW
0x18031aae4  test    eax, eax
0x18031aae6  jz      short loc_18031AB0C
0x18031aae8  bt      r12d, 0Ch
0x18031aaed  jnb     short loc_18031AAF6
0x18031aaef  mov     bl, 1
0x18031aaf1  jmp     loc_18031AB79
0x18031aaf6  mov     rcx, [rsp+390h+pszPath]; unsigned __int16 *
0x18031aafb  call    ?GetUNCPathSpeed@@YAKPEBG@Z; GetUNCPathSpeed(ushort const *)
0x18031ab00  dec     eax
0x18031ab02  cmp     eax, 18Fh
0x18031ab07  setbe   bl
0x18031ab0a  jmp     short loc_18031AB79
0x18031ab0c  mov     qword ptr [rsp+390h+Buf1], r14
0x18031ab11  lea     r8, [rsp+390h+Buf1]
0x18031ab16  mov     edx, 1
0x18031ab1b  mov     rcx, [rsp+390h+pszPath]
0x18031ab20  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x18031ab25  test    eax, eax
0x18031ab27  js      short loc_18031AB79
0x18031ab29  mov     r14, qword ptr [rsp+390h+Buf1]
0x18031ab2e  cmp     dword ptr [r13+250h], 1
0x18031ab36  jz      short loc_18031AB4E
0x18031ab38  mov     rax, [r14]
0x18031ab3b  mov     rcx, r14
0x18031ab3e  mov     rax, [rax+168h]
0x18031ab45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031ab4a  test    eax, eax
0x18031ab4c  jz      short loc_18031AB71
0x18031ab4e  bt      r12d, 0Ch
0x18031ab53  jb      short loc_18031AB6F
0x18031ab55  mov     rax, [r14]
0x18031ab58  mov     rcx, r14
0x18031ab5b  mov     rax, [rax+200h]
0x18031ab62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031ab67  test    eax, eax
0x18031ab69  jnz     short loc_18031AB6F
0x18031ab6b  xor     bl, bl
0x18031ab6d  jmp     short loc_18031AB71
0x18031ab6f  mov     bl, 1
0x18031ab71  mov     rcx, r14; this
0x18031ab74  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18031ab79  mov     r12, [rsp+390h+var_350]
0x18031ab7e  mov     rcx, [rsp+390h+pszPath]; pv
0x18031ab83  test    rcx, rcx
0x18031ab86  jz      short loc_18031AB8E
0x18031ab88  call    cs:__imp_CoTaskMemFree
0x18031ab8e  neg     bl
0x18031ab90  sbb     eax, eax
0x18031ab92  add     eax, 2
0x18031ab95  mov     [r13+234h], eax
0x18031ab9c  cmp     eax, 1
0x18031ab9f  jnz     short loc_18031ABA5
0x18031aba1  bts     edi, 0Eh
0x18031aba5  movzx   eax, byte ptr [r12+2]
0x18031abab  and     al, 37h
0x18031abad  sub     al, 31h ; '1'
0x18031abaf  test    al, 0FBh
0x18031abb1  jz      short loc_18031ABEE
0x18031abb3  test    dword ptr [rsi], 400000h
0x18031abb9  jz      short loc_18031ABD6
0x18031abbb  bt      r15d, 0Ah
0x18031abc0  jnb     short loc_18031ABD2
0x18031abc2  lea     rcx, [rbp+290h+var_2F0]; this
0x18031abc6  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x18031abcb  cmp     eax, 0A000000Ch
0x18031abd0  jz      short loc_18031ABD6
0x18031abd2  bts     edi, 16h
0x18031abd6  test    byte ptr [rsi], 10h
0x18031abd9  jz      short loc_18031AC4D
0x18031abdb  mov     rcx, r13; this
0x18031abde  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18031abe3  bt      eax, 13h
0x18031abe7  jb      short loc_18031AC4D
0x18031abe9  or      edi, 10h
0x18031abec  jmp     short loc_18031AC4D
0x18031abee  or      edi, 30800008h
0x18031abf4  test    byte ptr [rsi], 10h
0x18031abf7  jz      short loc_18031AC18
0x18031abf9  mov     rcx, r13; this
0x18031abfc  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18031ac01  bt      eax, 13h
0x18031ac05  jb      short loc_18031AC18
0x18031ac07  mov     rdx, [rsp+390h+pv]; unsigned __int16 *
0x18031ac0c  call    ?_CanRenameFolder@CFSFolder@@IEAAHPEBG@Z; CFSFolder::_CanRenameFolder(ushort const *)
0x18031ac11  test    eax, eax
0x18031ac13  jz      short loc_18031AC18
0x18031ac15  or      edi, 10h
0x18031ac18  test    dword ptr [rsi], 2000000h
0x18031ac1e  jz      short loc_18031AC30
0x18031ac20  mov     rcx, r13; this
0x18031ac23  call    ?IsOnRemovableVolume@CFSFolder@@IEAA_NXZ; CFSFolder::IsOnRemovableVolume(void)
0x18031ac28  test    al, al
0x18031ac2a  jz      short loc_18031AC30
0x18031ac2c  bts     edi, 19h
0x18031ac30  test    dword ptr [rsi], 20000h
0x18031ac36  jz      short loc_18031AC4D
0x18031ac38  xor     edx, edx
0x18031ac3a  mov     rcx, [rsp+390h+pv]
0x18031ac3f  call    cs:__imp_IsPathSharedW
0x18031ac45  test    eax, eax
0x18031ac47  jz      short loc_18031AC4D
0x18031ac49  bts     edi, 11h
0x18031ac4d  test    dword ptr [rsi], 10000h
0x18031ac53  jz      short loc_18031AC8D
  ... truncated ...
```
