# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::getDeviceVolumes(void)

- ea: `0x18004763c`
- end: `0x180047950`
- name: `?getDeviceVolumes@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAAJXZ`
- size: `788`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180045ca0`

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
- `0x18004763c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047870`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004789c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047870`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004789c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478f4`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18004790e`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18004790e`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800476b4`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800476b4`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18004776d`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18004776d`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800478da`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800478da`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800477a1`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800477a1`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::getDeviceVolumes(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton *this)
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
    v5 = 1372;
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
  v5 = 1394;
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v5,
           (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
           v2);
}

```

## disassembly

```asm
0x18004763c  push    rbp
0x18004763e  push    rbx
0x18004763f  push    rsi
0x180047640  push    rdi
0x180047641  push    r12
0x180047643  push    r13
0x180047645  push    r14
0x180047647  push    r15
0x180047649  lea     rbp, [rsp-3A8h]
0x180047651  sub     rsp, 4A8h
0x180047658  mov     rax, cs:__security_cookie
0x18004765f  xor     rax, rsp
0x180047662  mov     [rbp+3E0h+var_50], rax
0x180047669  mov     r13, rcx
0x18004766c  mov     ebx, 206h
0x180047671  xor     r12d, r12d
0x180047674  lea     rcx, [rsp+4E0h+var_46E]; void *
0x180047679  mov     r8d, ebx; Size
0x18004767c  mov     [rsp+4E0h+szVolumeName], r12w
0x180047682  xor     edx, edx; Val
0x180047684  call    memset_0
0x180047689  mov     r8d, ebx; Size
0x18004768c  mov     [rbp+3E0h+TargetPath], r12w
0x180047694  xor     edx, edx; Val
0x180047696  lea     rcx, [rbp+3E0h+var_25E]; void *
0x18004769d  call    memset_0
0x1800476a2  mov     edx, 104h; cchBufferLength
0x1800476a7  mov     [rsp+4E0h+cchReturnLength], 105h
0x1800476af  lea     rcx, [rsp+4E0h+szVolumeName]; lpszVolumeName
0x1800476b4  call    cs:__imp_FindFirstVolumeW
0x1800476ba  mov     r15, rax
0x1800476bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800476c1  cmp     r15, rax
0x1800476c4  jnz     short loc_1800476E3
0x1800476c6  mov     edx, 55Ch; void *
0x1800476cb  mov     rcx, [rbp+3E8h]; this
0x1800476d2  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800476d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800476de  jmp     loc_180047927
0x1800476e3  mov     edi, 5Ch ; '\'
0x1800476e8  mov     [rsp+4E0h+cchReturnLength], 105h
0x1800476f0  lea     rcx, [rsp+4E0h+szVolumeName]
0x1800476f5  inc     rax
0x1800476f8  cmp     [rcx+rax*2], r12w
0x1800476fd  jnz     short loc_1800476F5
0x1800476ff  lea     rbx, [rax-1]
0x180047703  cmp     rbx, 4
0x180047707  jb      loc_180047922
0x18004770d  cmp     [rsp+4E0h+szVolumeName], di
0x180047712  jnz     loc_180047922
0x180047718  cmp     [rsp+4E0h+var_46E], di
0x18004771d  jnz     loc_180047922
0x180047723  cmp     [rsp+4E0h+var_46C], 3Fh ; '?'
0x180047729  jnz     loc_180047922
0x18004772f  cmp     [rsp+4E0h+var_46A], di
0x180047734  jnz     loc_180047922
0x18004773a  add     rbx, rbx
0x18004773d  cmp     [rsp+rbx+4E0h+szVolumeName], di
0x180047742  jnz     loc_180047922
0x180047748  cmp     rbx, 208h
0x18004774f  jnb     loc_18004794A
0x180047755  mov     r8d, 104h; ucchMax
0x18004775b  mov     [rsp+rbx+4E0h+szVolumeName], r12w
0x180047761  lea     rdx, [rbp+3E0h+TargetPath]; lpTargetPath
0x180047768  lea     rcx, [rsp+4E0h+DeviceName]; lpDeviceName
0x18004776d  call    cs:__imp_QueryDosDeviceW
0x180047773  mov     [rsp+rbx+4E0h+szVolumeName], di
0x180047778  test    eax, eax
0x18004777a  jz      loc_180047918
0x180047780  mov     ecx, [rsp+4E0h+cchReturnLength]
0x180047784  add     rcx, rcx; unsigned __int64
0x180047787  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004778c  mov     r8d, [rsp+4E0h+cchReturnLength]; cchBufferLength
0x180047791  lea     r9, [rsp+4E0h+cchReturnLength]; lpcchReturnLength
0x180047796  mov     rdx, rax; lpszVolumePathNames
0x180047799  lea     rcx, [rsp+4E0h+szVolumeName]; lpszVolumeName
0x18004779e  mov     rsi, rax
0x1800477a1  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800477a7  test    eax, eax
0x1800477a9  jz      loc_1800478CC
0x1800477af  lea     rdx, [rbp+3E0h+TargetPath]
0x1800477b6  lea     rcx, [rsp+4E0h+var_490]
0x1800477bb  lea     r14, [r13+120h]
0x1800477c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800477c7  lea     r8, [rsp+4E0h+var_490]
0x1800477cc  mov     rcx, r14
0x1800477cf  lea     rdx, [rsp+4E0h+var_4A8]
0x1800477d4  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800477d9  mov     rdi, [r14]
0x1800477dc  lea     rcx, [rsp+4E0h+var_490]
0x1800477e1  mov     rbx, [rax]
0x1800477e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800477e9  cmp     rbx, rdi
0x1800477ec  jnz     loc_1800478C7
0x1800477f2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800477f6  lea     rax, [rbp+3E0h+TargetPath]
0x1800477fd  mov     rcx, rbx
0x180047800  inc     rcx
0x180047803  cmp     [rax+rcx*2], r12w
0x180047808  jnz     short loc_180047800
0x18004780a  inc     rcx
0x18004780d  mov     eax, 2
0x180047812  mul     rcx
0x180047815  cmovb   rax, rbx
0x180047819  mov     rcx, rax; unsigned __int64
0x18004781c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180047821  mov     rdi, rax
0x180047824  mov     rcx, rbx
0x180047827  inc     rcx
0x18004782a  cmp     [rsi+rcx*2], r12w
0x18004782f  jnz     short loc_180047827
0x180047831  inc     rcx
0x180047834  mov     eax, 2
0x180047839  mul     rcx
0x18004783c  cmovb   rax, rbx
0x180047840  mov     rcx, rax; unsigned __int64
0x180047843  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180047848  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004784c  mov     rbx, rax
0x18004784f  mov     rdx, r9
0x180047852  lea     rax, [rbp+3E0h+TargetPath]
0x180047859  inc     rdx
0x18004785c  cmp     [rax+rdx*2], r12w
0x180047861  jnz     short loc_180047859
0x180047863  inc     rdx
0x180047866  lea     r8, [rbp+3E0h+TargetPath]
0x18004786d  mov     rcx, rdi
0x180047870  call    cs:__imp__o_wcsncpy_s
0x180047876  cmp     eax, 50h ; 'P'
0x180047879  jz      short loc_18004787F
0x18004787b  test    eax, eax
0x18004787d  jnz     short loc_1800478ED
0x18004787f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047883  mov     rdx, rax
0x180047886  inc     rdx
0x180047889  cmp     [rsi+rdx*2], r12w
0x18004788e  jnz     short loc_180047886
0x180047890  inc     rdx
0x180047893  mov     r9, rax
0x180047896  mov     r8, rsi
0x180047899  mov     rcx, rbx
0x18004789c  call    cs:__imp__o_wcsncpy_s
0x1800478a2  cmp     eax, 50h ; 'P'
0x1800478a5  jz      short loc_1800478AB
0x1800478a7  test    eax, eax
0x1800478a9  jnz     short loc_1800478ED
0x1800478ab  lea     r8, [rsp+4E0h+var_4B8]
0x1800478b0  mov     [rsp+4E0h+var_4B8], rdi
0x1800478b5  lea     rdx, [rsp+4E0h+var_4A0]
0x1800478ba  mov     [rsp+4E0h+var_4B0], rbx
0x1800478bf  mov     rcx, r14
0x1800478c2  call    ??$insert@U?$pair@PEAGPEAG@std@@$0A@@?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEAGPEAG@1@@Z; std::map<std::wstring const,std::wstring>::insert<std::pair<ushort *,ushort *>,0>(std::pair<ushort *,ushort *> &&)
0x1800478c7  mov     edi, 5Ch ; '\'
0x1800478cc  mov     r8d, 104h; cchBufferLength
0x1800478d2  lea     rdx, [rsp+4E0h+szVolumeName]; lpszVolumeName
0x1800478d7  mov     rcx, r15; hFindVolume
0x1800478da  call    cs:__imp_FindNextVolumeW
0x1800478e0  test    eax, eax
0x1800478e2  jz      short loc_1800478F4
0x1800478e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800478e8  jmp     loc_1800476E8
0x1800478ed  mov     ebx, 80004005h
0x1800478f2  jmp     short loc_180047903
0x1800478f4  call    cs:__imp_GetLastError
0x1800478fa  cmp     eax, 12h
0x1800478fd  mov     ebx, eax
0x1800478ff  cmovz   ebx, r12d
0x180047903  mov     rcx, rsi; void *
0x180047906  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004790b  mov     rcx, r15; hFindVolume
0x18004790e  call    cs:__imp_FindVolumeClose
0x180047914  mov     eax, ebx
0x180047916  jmp     short loc_180047927
0x180047918  mov     edx, 572h
0x18004791d  jmp     loc_1800476CB
0x180047922  mov     eax, 0A1h
0x180047927  mov     rcx, [rbp+3E0h+var_50]
0x18004792e  xor     rcx, rsp; StackCookie
0x180047931  call    __security_check_cookie
0x180047936  add     rsp, 4A8h
0x18004793d  pop     r15
0x18004793f  pop     r14
0x180047941  pop     r13
0x180047943  pop     r12
0x180047945  pop     rdi
0x180047946  pop     rsi
0x180047947  pop     rbx
0x180047948  pop     rbp
0x180047949  retn
0x18004794a  call    __report_rangecheckfailure
```
