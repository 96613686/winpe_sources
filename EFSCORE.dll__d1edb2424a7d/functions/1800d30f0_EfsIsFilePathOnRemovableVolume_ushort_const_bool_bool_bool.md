# EfsIsFilePathOnRemovableVolume(ushort const *,bool,bool *,bool *)

- ea: `0x1800d30f0`
- end: `0x1800d33d2`
- name: `?EfsIsFilePathOnRemovableVolume@@YAJPEBG_NPEA_N2@Z`
- size: `738`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, bool, bool *, bool *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180071530`
- `0x1800d2b2c`

## callees

- `0x180005045`
- `0x1800474dc`
- `0x1800483ac`
- `0x1800483c8`
- `0x18004844c`
- `0x1800484e4`
- `0x1800485ec`
- `0x1800d2574`
- `0x1800d30f0`
- `0x1800d39dc`
- `0x1800d4094`
- `0x1800d4254`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800d3228`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800d3228`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800d315f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800d315f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800d31f1`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800d31f1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800d3298`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800d3298`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800d331f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800d331f`
- `ext-ms-win-fveapi-query-l1-1-0!FveGetStatusW` at `0x1800d32dd`
- `ext-ms-win-fveapi-query-l1-1-0!FveGetStatusW` at `0x1800d32dd`

## string_xrefs

- `0x1800d3391`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d33ab`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d33bf`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EfsIsFilePathOnRemovableVolume(LPCWSTR pszPath, char a2, bool *a3, bool *a4)
{
  const char *v8; // r9
  LPCWSTR *v9; // rax
  LPCWSTR v10; // rdx
  unsigned __int64 v11; // r9
  LPCWSTR *v12; // rcx
  __int64 v13; // rdx
  UINT DriveTypeW; // esi
  const char *v15; // r9
  __int64 result; // rax
  unsigned __int64 v17; // rcx
  bool v18; // bl
  bool v19; // al
  const WCHAR *v20; // rcx
  const char *v21; // r9
  int StatusW; // eax
  LPWSTR ExtensionW; // rax
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-528h] BYREF
  UINT v26; // [rsp+24h] [rbp-524h] BYREF
  LPWSTR v27; // [rsp+28h] [rbp-520h] BYREF
  unsigned __int64 v28; // [rsp+30h] [rbp-518h] BYREF
  LPCWSTR lpRootPathName[2]; // [rsp+38h] [rbp-510h] BYREF
  __int64 v30; // [rsp+48h] [rbp-500h]
  unsigned __int64 v31; // [rsp+50h] [rbp-4F8h]
  _DWORD v32[2]; // [rsp+60h] [rbp-4E8h] BYREF
  _BYTE v33[4]; // [rsp+68h] [rbp-4E0h] BYREF
  int v34; // [rsp+6Ch] [rbp-4DCh]
  WCHAR szVolumePathName[264]; // [rsp+F0h] [rbp-458h] BYREF
  WCHAR szVolumeName[264]; // [rsp+300h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+0h]

  try
  {
    *a3 = 0;
    if ( !qword_1801170B0 )
      SetupRemovableVolumesTestHook();
    v31 = 7;
    v30 = 0;
    LOWORD(lpRootPathName[0]) = 0;
    if ( a2 )
    {
      std::wstring::assign(lpRootPathName, pszPath);
    }
    else
    {
      if ( !GetVolumePathNameW(pszPath, szVolumePathName, 0x104u) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x70,
          (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
          v8);
      std::wstring::assign(lpRootPathName, szVolumePathName);
    }
    if ( !v30 )
      std::wstring::_Xran(lpRootPathName);
    v9 = lpRootPathName;
    v10 = lpRootPathName[0];
    v11 = v31;
    if ( v31 >= 8 )
      v9 = (LPCWSTR *)lpRootPathName[0];
    if ( *((_WORD *)v9 + v30 - 1) != 92 )
    {
      std::wstring::append(lpRootPathName, 1);
      v11 = v31;
      v10 = lpRootPathName[0];
    }
    v12 = lpRootPathName;
    if ( v11 >= 8 )
      v12 = (LPCWSTR *)v10;
    DriveTypeW = GetDriveTypeW((LPCWSTR)v12);
    v26 = DriveTypeW;
    if ( DriveTypeW - 2 <= 1 )
    {
      v17 = (unsigned __int64)&stru_1801170E0 & -(__int64)(TryAcquireSRWLockShared(&stru_1801170E0) != 0);
      v28 = v17;
      LOBYTE(v25) = 0;
      if ( v17
        && (std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::lower_bound(
              v17,
              &v27,
              lpRootPathName),
            v18 = v27 != (LPWSTR)qword_1801170F0,
            LOBYTE(v25) = v27 != (LPWSTR)qword_1801170F0,
            Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v28),
            v18) )
      {
        v19 = 1;
      }
      else
      {
        v20 = (const WCHAR *)lpRootPathName;
        if ( v31 >= 8 )
          v20 = lpRootPathName[0];
        if ( !GetVolumeNameForVolumeMountPointW(v20, szVolumeName, 0x104u) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0xA2,
            (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
            v21);
        memset_0(v33, 0, 0x88u);
        v32[0] = 144;
        v32[1] = 10;
        StatusW = FveGetStatusW(szVolumeName, v32);
        if ( StatusW == -2147024769 )
        {
          v19 = DriveTypeW == 2;
        }
        else
        {
          if ( StatusW < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xB0,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
              (const char *)(unsigned int)StatusW,
              v25);
          v19 = (v34 & 0x400000) != 0;
        }
      }
      BYTE1(v25) = v19;
      *a4 = v19;
      if ( !a2 )
      {
        if ( !pszPath || (ExtensionW = PathFindExtensionW(pszPath)) == 0 )
          ExtensionW = L"NA";
        v27 = ExtensionW;
        EfsTelemetry::LogEfsIsFilePathOnRemovableVolume<unsigned short const *,unsigned int &,bool &,bool &>(
          &v27,
          (int *)&v26,
          (_BYTE *)&v25 + 1,
          (char *)&v25);
      }
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v28);
      LOBYTE(v24) = 1;
      std::wstring::_Tidy(lpRootPathName, v24, 0);
      result = 0;
    }
    else
    {
      *a3 = 1;
      LOBYTE(v13) = 1;
      std::wstring::_Tidy(lpRootPathName, v13, 0);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC8,
                           (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800d30f0  push    rbx
0x1800d30f2  push    rsi
0x1800d30f3  push    rdi
0x1800d30f4  push    r14
0x1800d30f6  push    r15
0x1800d30f8  sub     rsp, 520h
0x1800d30ff  mov     rax, cs:__security_cookie
0x1800d3106  xor     rax, rsp
0x1800d3109  mov     [rsp+548h+var_38], rax
0x1800d3111  mov     r15, r9
0x1800d3114  mov     rbx, r8
0x1800d3117  mov     r14b, dl
0x1800d311a  mov     rdi, rcx
0x1800d311d  mov     byte ptr [r8], 0
0x1800d3121  cmp     cs:qword_1801170B0, 0
0x1800d3129  jnz     short loc_1800D3130
0x1800d312b  call    SetupRemovableVolumesTestHook
0x1800d3130  mov     [rsp+548h+var_4F8], 7
0x1800d3139  mov     [rsp+548h+var_500], 0
0x1800d3142  xor     eax, eax
0x1800d3144  mov     word ptr [rsp+548h+lpRootPathName], ax
0x1800d3149  test    r14b, r14b
0x1800d314c  jnz     short loc_1800D3189
0x1800d314e  mov     r8d, 104h; cchBufferLength
0x1800d3154  lea     rdx, [rsp+548h+szVolumePathName]; lpszVolumePathName
0x1800d315c  mov     rcx, rdi; lpszFileName
0x1800d315f  call    cs:__imp_GetVolumePathNameW
0x1800d3165  mov     rcx, [rsp+548h]; this
0x1800d316d  test    eax, eax
0x1800d316f  jz      loc_1800D3391
0x1800d3175  lea     rdx, [rsp+548h+szVolumePathName]
0x1800d317d  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d3182  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800d3187  jmp     short loc_1800D3196
0x1800d3189  mov     rdx, rdi
0x1800d318c  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d3191  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800d3196  mov     rax, [rsp+548h+var_500]
0x1800d319b  lea     rcx, [rax-1]
0x1800d319f  cmp     rax, rcx
0x1800d31a2  jbe     loc_1800D33A0
0x1800d31a8  lea     rax, [rsp+548h+lpRootPathName]
0x1800d31ad  mov     rdx, [rsp+548h+lpRootPathName]
0x1800d31b2  mov     r9, [rsp+548h+var_4F8]
0x1800d31b7  cmp     r9, 8
0x1800d31bb  cmovnb  rax, rdx
0x1800d31bf  mov     r8d, 5Ch ; '\'
0x1800d31c5  cmp     [rax+rcx*2], r8w
0x1800d31ca  jz      short loc_1800D31E4
0x1800d31cc  lea     edx, [r8-5Bh]
0x1800d31d0  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d31d5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1800d31da  mov     r9, [rsp+548h+var_4F8]
0x1800d31df  mov     rdx, [rsp+548h+lpRootPathName]
0x1800d31e4  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d31e9  cmp     r9, 8
0x1800d31ed  cmovnb  rcx, rdx; lpRootPathName
0x1800d31f1  call    cs:__imp_GetDriveTypeW
0x1800d31f7  mov     esi, eax
0x1800d31f9  mov     [rsp+548h+var_524], eax
0x1800d31fd  lea     ecx, [rax-2]
0x1800d3200  cmp     ecx, 1
0x1800d3203  jbe     short loc_1800D321E
0x1800d3205  mov     byte ptr [rbx], 1
0x1800d3208  xor     r8d, r8d
0x1800d320b  mov     dl, 1
0x1800d320d  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d3212  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800d3217  xor     eax, eax
0x1800d3219  jmp     loc_1800D3372
0x1800d321e  lea     rbx, stru_1801170E0
0x1800d3225  mov     rcx, rbx; SRWLock
0x1800d3228  call    cs:__imp_TryAcquireSRWLockShared
0x1800d322e  neg     al
0x1800d3230  sbb     rcx, rcx
0x1800d3233  and     rcx, rbx
0x1800d3236  mov     [rsp+548h+var_518], rcx
0x1800d323b  mov     byte ptr [rsp+548h+var_528], 0; int
0x1800d3240  jz      short loc_1800D3279
0x1800d3242  lea     r8, [rsp+548h+lpRootPathName]
0x1800d3247  lea     rdx, [rsp+548h+var_520]
0x1800d324c  call    ?lower_bound@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::lower_bound(std::wstring const &)
0x1800d3251  mov     rax, cs:qword_1801170F0
0x1800d3258  cmp     [rsp+548h+var_520], rax
0x1800d325d  setnz   bl
0x1800d3260  mov     byte ptr [rsp+548h+var_528], bl
0x1800d3264  lea     rcx, [rsp+548h+var_518]; this
0x1800d3269  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800d326e  test    bl, bl
0x1800d3270  jz      short loc_1800D3279
0x1800d3272  mov     al, 1
0x1800d3274  jmp     loc_1800D330B
0x1800d3279  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d327e  cmp     [rsp+548h+var_4F8], 8
0x1800d3284  cmovnb  rcx, [rsp+548h+lpRootPathName]; lpszVolumeMountPoint
0x1800d328a  mov     r8d, 104h; cchBufferLength
0x1800d3290  lea     rdx, [rsp+548h+szVolumeName]; lpszVolumeName
0x1800d3298  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800d329e  mov     rcx, [rsp+548h]; this
0x1800d32a6  test    eax, eax
0x1800d32a8  jz      loc_1800D33AB
0x1800d32ae  xor     edx, edx; Val
0x1800d32b0  mov     r8d, 88h; Size
0x1800d32b6  lea     rcx, [rsp+548h+var_4E0]; void *
0x1800d32bb  call    memset_0
0x1800d32c0  mov     [rsp+548h+var_4E8], 90h
0x1800d32c8  mov     [rsp+548h+var_4E4], 0Ah
0x1800d32d0  lea     rdx, [rsp+548h+var_4E8]
0x1800d32d5  lea     rcx, [rsp+548h+szVolumeName]
0x1800d32dd  call    cs:__imp_FveGetStatusW
0x1800d32e3  cmp     eax, 8007007Fh
0x1800d32e8  jnz     short loc_1800D32F2
0x1800d32ea  cmp     esi, 2
0x1800d32ed  setz    al
0x1800d32f0  jmp     short loc_1800D330B
0x1800d32f2  mov     rcx, [rsp+548h]; this
0x1800d32fa  test    eax, eax
0x1800d32fc  js      loc_1800D33BC
0x1800d3302  mov     eax, [rsp+548h+var_4DC]
0x1800d3306  shr     eax, 16h
0x1800d3309  and     al, 1
0x1800d330b  mov     byte ptr [rsp+548h+var_528+1], al
0x1800d330f  mov     [r15], al
0x1800d3312  test    r14b, r14b
0x1800d3315  jnz     short loc_1800D3350
0x1800d3317  test    rdi, rdi
0x1800d331a  jz      short loc_1800D332A
0x1800d331c  mov     rcx, rdi; pszPath
0x1800d331f  call    cs:__imp_PathFindExtensionW
0x1800d3325  test    rax, rax
0x1800d3328  jnz     short loc_1800D3331
0x1800d332a  lea     rax, aNa; "NA"
0x1800d3331  mov     [rsp+548h+var_520], rax
0x1800d3336  lea     r9, [rsp+548h+var_528]
0x1800d333b  lea     r8, [rsp+548h+var_528+1]
0x1800d3340  lea     rdx, [rsp+548h+var_524]
0x1800d3345  lea     rcx, [rsp+548h+var_520]
0x1800d334a  call    ??$LogEfsIsFilePathOnRemovableVolume@PEBGAEAIAEA_NAEA_N@EfsTelemetry@@SAX$$QEAPEBGAEAIAEA_N2@Z; EfsTelemetry::LogEfsIsFilePathOnRemovableVolume<ushort const *,uint &,bool &,bool &>(ushort const * &&,uint &,bool &,bool &)
0x1800d334f  nop
0x1800d3350  lea     rcx, [rsp+548h+var_518]; this
0x1800d3355  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800d335a  nop
0x1800d335b  xor     r8d, r8d
0x1800d335e  mov     dl, 1
0x1800d3360  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d3365  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800d336a  xor     eax, eax
0x1800d336c  jmp     short loc_1800D3372
0x1800d336e  mov     eax, [rsp+548h+var_524]
0x1800d3372  mov     rcx, [rsp+548h+var_38]
0x1800d337a  xor     rcx, rsp; StackCookie
0x1800d337d  call    __security_check_cookie
0x1800d3382  add     rsp, 520h
0x1800d3389  pop     r15
0x1800d338b  pop     r14
0x1800d338d  pop     rdi
0x1800d338e  pop     rsi
0x1800d338f  pop     rbx
0x1800d3390  retn
0x1800d3391  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d3398  lea     edx, [rax+70h]; void *
0x1800d339b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800d33a0  lea     rcx, [rsp+548h+lpRootPathName]
0x1800d33a5  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800d33ab  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d33b2  mov     edx, 0A2h; void *
0x1800d33b7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800d33bc  mov     r9d, eax; char *
0x1800d33bf  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d33c6  mov     edx, 0B0h; void *
0x1800d33cb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
