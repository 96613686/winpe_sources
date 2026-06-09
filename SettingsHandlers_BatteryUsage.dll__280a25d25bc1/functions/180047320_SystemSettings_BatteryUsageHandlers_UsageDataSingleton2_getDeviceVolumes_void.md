# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::getDeviceVolumes(void)

- ea: `0x180047320`
- end: `0x180047634`
- name: `?getDeviceVolumes@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJXZ`
- size: `788`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180045c30`

## callees

- `0x1800028d0`
- `0x1800029d0`
- `0x180002f80`
- `0x1800033a0`
- `0x1800043d8`
- `0x18000a11c`
- `0x18001e5c8`
- `0x180023c78`
- `0x18003d854`
- `0x18004719c`
- `0x180047320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047554`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047580`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047554`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475d8`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800475f2`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800475f2`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180047398`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180047398`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180047451`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180047451`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800475be`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800475be`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180047485`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180047485`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::getDeviceVolumes(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *this)
{
  const char *v2; // r9
  HANDLE FirstVolumeW; // r15
  __int64 v4; // rax
  __int64 v5; // rdx
  unsigned __int64 v7; // rbx
  DWORD v8; // eax
  _WORD *v9; // rsi
  __int64 *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  void *v14; // rdi
  __int64 v15; // rcx
  void *v16; // rbx
  __int64 v17; // rdx
  int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  __int64 v20; // rdx
  int v21; // eax
  DWORD LastError; // ebx
  DWORD cchReturnLength; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v24[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v25[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumeName; // [rsp+70h] [rbp-90h] BYREF
  _WORD v29[3]; // [rsp+72h] [rbp-8Eh] BYREF
  WCHAR DeviceName[260]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR TargetPath; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v32[526]; // [rsp+282h] [rbp+182h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  szVolumeName = 0;
  memset_0(v29, 0, 0x206u);
  TargetPath = 0;
  memset_0(v32, 0, 0x206u);
  cchReturnLength = 261;
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x104u);
  v4 = -1;
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    v5 = 2841;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
             v2);
  }
  while ( 1 )
  {
    cchReturnLength = 261;
    do
      ++v4;
    while ( v29[v4 - 1] );
    if ( (unsigned __int64)(v4 - 1) < 4 )
      return 161;
    if ( szVolumeName != 92 )
      return 161;
    if ( v29[0] != 92 )
      return 161;
    if ( v29[1] != 63 )
      return 161;
    if ( v29[2] != 92 )
      return 161;
    v7 = v4 - 1;
    if ( v29[v7 - 1] != 92 )
      return 161;
    if ( v7 >= 260 )
      _report_rangecheckfailure(&szVolumeName);
    v29[v7 - 1] = 0;
    v8 = QueryDosDeviceW(DeviceName, &TargetPath, 0x104u);
    v29[v7 - 1] = 92;
    if ( !v8 )
      break;
    v9 = operator new[](2LL * cchReturnLength);
    if ( GetVolumePathNamesForVolumeNameW(&szVolumeName, v9, cchReturnLength, &cchReturnLength) )
    {
      std::wstring::wstring((__int64)v27, (__int64)&TargetPath);
      v10 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                         (char *)this + 288,
                         v25,
                         v27);
      v11 = *((_QWORD *)this + 36);
      v12 = *v10;
      std::wstring::_Tidy_deallocate(v27);
      if ( v12 == v11 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v32[2 * v13 - 2] );
        v14 = operator new[](saturated_mul(v13 + 1, 2u));
        v15 = -1;
        do
          ++v15;
        while ( v9[v15] );
        v16 = operator new[](saturated_mul(v15 + 1, 2u));
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)&v32[2 * v17 - 2] );
        v18 = _o_wcsncpy_s(v14, v17 + 1, &TargetPath);
        if ( v18 != 80 && v18 )
          goto LABEL_31;
        v20 = -1;
        do
          ++v20;
        while ( v9[v20] );
        v21 = _o_wcsncpy_s(v16, v20 + 1, v9);
        if ( v21 != 80 )
        {
          if ( v21 )
          {
LABEL_31:
            LastError = -2147467259;
LABEL_34:
            operator delete(v9, v19);
            FindVolumeClose(FirstVolumeW);
            return LastError;
          }
        }
        v24[0] = v14;
        v24[1] = v16;
        std::map<std::wstring const,std::wstring>::insert<std::pair<unsigned short *,unsigned short *>,0>(
          (char *)this + 288,
          v26,
          v24);
      }
    }
    if ( !FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x104u) )
    {
      LastError = GetLastError();
      if ( LastError == 18 )
        LastError = 0;
      goto LABEL_34;
    }
    v4 = -1;
  }
  v5 = 2863;
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v5,
           (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
           v2);
}

```

## disassembly

```asm
0x180047320  push    rbp
0x180047322  push    rbx
0x180047323  push    rsi
0x180047324  push    rdi
0x180047325  push    r12
0x180047327  push    r13
0x180047329  push    r14
0x18004732b  push    r15
0x18004732d  lea     rbp, [rsp-3A8h]
0x180047335  sub     rsp, 4A8h
0x18004733c  mov     rax, cs:__security_cookie
0x180047343  xor     rax, rsp
0x180047346  mov     [rbp+3E0h+var_50], rax
0x18004734d  mov     r13, rcx
0x180047350  mov     ebx, 206h
0x180047355  xor     r12d, r12d
0x180047358  lea     rcx, [rsp+4E0h+var_46E]; void *
0x18004735d  mov     r8d, ebx; Size
0x180047360  mov     [rsp+4E0h+szVolumeName], r12w
0x180047366  xor     edx, edx; Val
0x180047368  call    memset_0
0x18004736d  mov     r8d, ebx; Size
0x180047370  mov     [rbp+3E0h+TargetPath], r12w
0x180047378  xor     edx, edx; Val
0x18004737a  lea     rcx, [rbp+3E0h+var_25E]; void *
0x180047381  call    memset_0
0x180047386  mov     edx, 104h; cchBufferLength
0x18004738b  mov     [rsp+4E0h+cchReturnLength], 105h
0x180047393  lea     rcx, [rsp+4E0h+szVolumeName]; lpszVolumeName
0x180047398  call    cs:__imp_FindFirstVolumeW
0x18004739e  mov     r15, rax
0x1800473a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800473a5  cmp     r15, rax
0x1800473a8  jnz     short loc_1800473C7
0x1800473aa  mov     edx, 0B19h; void *
0x1800473af  mov     rcx, [rbp+3E8h]; this
0x1800473b6  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800473bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800473c2  jmp     loc_18004760B
0x1800473c7  mov     edi, 5Ch ; '\'
0x1800473cc  mov     [rsp+4E0h+cchReturnLength], 105h
0x1800473d4  lea     rcx, [rsp+4E0h+szVolumeName]
0x1800473d9  inc     rax
0x1800473dc  cmp     [rcx+rax*2], r12w
0x1800473e1  jnz     short loc_1800473D9
0x1800473e3  lea     rbx, [rax-1]
0x1800473e7  cmp     rbx, 4
0x1800473eb  jb      loc_180047606
0x1800473f1  cmp     [rsp+4E0h+szVolumeName], di
0x1800473f6  jnz     loc_180047606
0x1800473fc  cmp     [rsp+4E0h+var_46E], di
0x180047401  jnz     loc_180047606
0x180047407  cmp     [rsp+4E0h+var_46C], 3Fh ; '?'
0x18004740d  jnz     loc_180047606
0x180047413  cmp     [rsp+4E0h+var_46A], di
0x180047418  jnz     loc_180047606
0x18004741e  add     rbx, rbx
0x180047421  cmp     [rsp+rbx+4E0h+szVolumeName], di
0x180047426  jnz     loc_180047606
0x18004742c  cmp     rbx, 208h
0x180047433  jnb     loc_18004762E
0x180047439  mov     r8d, 104h; ucchMax
0x18004743f  mov     [rsp+rbx+4E0h+szVolumeName], r12w
0x180047445  lea     rdx, [rbp+3E0h+TargetPath]; lpTargetPath
0x18004744c  lea     rcx, [rsp+4E0h+DeviceName]; lpDeviceName
0x180047451  call    cs:__imp_QueryDosDeviceW
0x180047457  mov     [rsp+rbx+4E0h+szVolumeName], di
0x18004745c  test    eax, eax
0x18004745e  jz      loc_1800475FC
0x180047464  mov     ecx, [rsp+4E0h+cchReturnLength]
0x180047468  add     rcx, rcx; unsigned __int64
0x18004746b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180047470  mov     r8d, [rsp+4E0h+cchReturnLength]; cchBufferLength
0x180047475  lea     r9, [rsp+4E0h+cchReturnLength]; lpcchReturnLength
0x18004747a  mov     rdx, rax; lpszVolumePathNames
0x18004747d  lea     rcx, [rsp+4E0h+szVolumeName]; lpszVolumeName
0x180047482  mov     rsi, rax
0x180047485  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18004748b  test    eax, eax
0x18004748d  jz      loc_1800475B0
0x180047493  lea     rdx, [rbp+3E0h+TargetPath]
0x18004749a  lea     rcx, [rsp+4E0h+var_490]
0x18004749f  lea     r14, [r13+120h]
0x1800474a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800474ab  lea     r8, [rsp+4E0h+var_490]
0x1800474b0  mov     rcx, r14
0x1800474b3  lea     rdx, [rsp+4E0h+var_4A8]
0x1800474b8  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800474bd  mov     rdi, [r14]
0x1800474c0  lea     rcx, [rsp+4E0h+var_490]
0x1800474c5  mov     rbx, [rax]
0x1800474c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800474cd  cmp     rbx, rdi
0x1800474d0  jnz     loc_1800475AB
0x1800474d6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800474da  lea     rax, [rbp+3E0h+TargetPath]
0x1800474e1  mov     rcx, rbx
0x1800474e4  inc     rcx
0x1800474e7  cmp     [rax+rcx*2], r12w
0x1800474ec  jnz     short loc_1800474E4
0x1800474ee  inc     rcx
0x1800474f1  mov     eax, 2
0x1800474f6  mul     rcx
0x1800474f9  cmovb   rax, rbx
0x1800474fd  mov     rcx, rax; unsigned __int64
0x180047500  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180047505  mov     rdi, rax
0x180047508  mov     rcx, rbx
0x18004750b  inc     rcx
0x18004750e  cmp     [rsi+rcx*2], r12w
0x180047513  jnz     short loc_18004750B
0x180047515  inc     rcx
0x180047518  mov     eax, 2
0x18004751d  mul     rcx
0x180047520  cmovb   rax, rbx
0x180047524  mov     rcx, rax; unsigned __int64
0x180047527  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004752c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180047530  mov     rbx, rax
0x180047533  mov     rdx, r9
0x180047536  lea     rax, [rbp+3E0h+TargetPath]
0x18004753d  inc     rdx
0x180047540  cmp     [rax+rdx*2], r12w
0x180047545  jnz     short loc_18004753D
0x180047547  inc     rdx
0x18004754a  lea     r8, [rbp+3E0h+TargetPath]
0x180047551  mov     rcx, rdi
0x180047554  call    cs:__imp__o_wcsncpy_s
0x18004755a  cmp     eax, 50h ; 'P'
0x18004755d  jz      short loc_180047563
0x18004755f  test    eax, eax
0x180047561  jnz     short loc_1800475D1
0x180047563  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047567  mov     rdx, rax
0x18004756a  inc     rdx
0x18004756d  cmp     [rsi+rdx*2], r12w
0x180047572  jnz     short loc_18004756A
0x180047574  inc     rdx
0x180047577  mov     r9, rax
0x18004757a  mov     r8, rsi
0x18004757d  mov     rcx, rbx
0x180047580  call    cs:__imp__o_wcsncpy_s
0x180047586  cmp     eax, 50h ; 'P'
0x180047589  jz      short loc_18004758F
0x18004758b  test    eax, eax
0x18004758d  jnz     short loc_1800475D1
0x18004758f  lea     r8, [rsp+4E0h+var_4B8]
0x180047594  mov     [rsp+4E0h+var_4B8], rdi
0x180047599  lea     rdx, [rsp+4E0h+var_4A0]
0x18004759e  mov     [rsp+4E0h+var_4B0], rbx
0x1800475a3  mov     rcx, r14
0x1800475a6  call    ??$insert@U?$pair@PEAGPEAG@std@@$0A@@?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEAGPEAG@1@@Z; std::map<std::wstring const,std::wstring>::insert<std::pair<ushort *,ushort *>,0>(std::pair<ushort *,ushort *> &&)
0x1800475ab  mov     edi, 5Ch ; '\'
0x1800475b0  mov     r8d, 104h; cchBufferLength
0x1800475b6  lea     rdx, [rsp+4E0h+szVolumeName]; lpszVolumeName
0x1800475bb  mov     rcx, r15; hFindVolume
0x1800475be  call    cs:__imp_FindNextVolumeW
0x1800475c4  test    eax, eax
0x1800475c6  jz      short loc_1800475D8
0x1800475c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800475cc  jmp     loc_1800473CC
0x1800475d1  mov     ebx, 80004005h
0x1800475d6  jmp     short loc_1800475E7
0x1800475d8  call    cs:__imp_GetLastError
0x1800475de  cmp     eax, 12h
0x1800475e1  mov     ebx, eax
0x1800475e3  cmovz   ebx, r12d
0x1800475e7  mov     rcx, rsi; void *
0x1800475ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800475ef  mov     rcx, r15; hFindVolume
0x1800475f2  call    cs:__imp_FindVolumeClose
0x1800475f8  mov     eax, ebx
0x1800475fa  jmp     short loc_18004760B
0x1800475fc  mov     edx, 0B2Fh
0x180047601  jmp     loc_1800473AF
0x180047606  mov     eax, 0A1h
0x18004760b  mov     rcx, [rbp+3E0h+var_50]
0x180047612  xor     rcx, rsp; StackCookie
0x180047615  call    __security_check_cookie
0x18004761a  add     rsp, 4A8h
0x180047621  pop     r15
0x180047623  pop     r14
0x180047625  pop     r13
0x180047627  pop     r12
0x180047629  pop     rdi
0x18004762a  pop     rsi
0x18004762b  pop     rbx
0x18004762c  pop     rbp
0x18004762d  retn
0x18004762e  call    __report_rangecheckfailure
```
