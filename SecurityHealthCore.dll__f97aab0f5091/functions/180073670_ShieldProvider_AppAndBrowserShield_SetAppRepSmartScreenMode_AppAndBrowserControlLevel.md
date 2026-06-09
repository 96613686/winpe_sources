# ShieldProvider::AppAndBrowserShield::SetAppRepSmartScreenMode(AppAndBrowserControlLevel)

- ea: `0x180073670`
- end: `0x180073a3a`
- name: `?SetAppRepSmartScreenMode@AppAndBrowserShield@ShieldProvider@@UEAAJW4AppAndBrowserControlLevel@@@Z`
- size: `970`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073a40`
- `0x180073a50`
- `0x180073a60`
- `0x180073a70`

## callees

- `0x180004710`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000d888`
- `0x180011730`
- `0x18001b458`
- `0x18001ca28`
- `0x18001ca48`
- `0x18001caa0`
- `0x18006d73c`
- `0x18007314c`
- `0x180073670`
- `0x1800ceb24`
- `0x1800d0180`
- `0x1800d0c14`
- `0x1800d3750`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073894`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073894`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007390e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007390e`

## string_xrefs

- `0x1800736a1`: `SecurityHealthHost.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ShieldProvider::AppAndBrowserShield::SetAppRepSmartScreenMode(ShieldProvider *a1, int a2)
{
  ShieldProvider *v4; // rcx
  unsigned __int16 *v5; // r8
  int v6; // eax
  int v7; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  const void *v19; // rax
  DWORD cbData; // edx
  unsigned int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-88h]
  unsigned int phkResulta; // [rsp+20h] [rbp-88h]
  __int64 v28; // [rsp+30h] [rbp-78h] BYREF
  int v29; // [rsp+38h] [rbp-70h] BYREF
  int v30; // [rsp+3Ch] [rbp-6Ch] BYREF
  HKEY hKey; // [rsp+40h] [rbp-68h] BYREF
  int v32; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v33[16]; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v28 = 0;
  if ( ShieldProvider::IsOSWcos(a1) )
  {
    LOBYTE(v4) = (_BYTE)g_fDevMode;
    v6 = ShieldProvider::ValidateCaller(v4, (bool)L"SecurityHealthHost.exe", v5);
  }
  else
  {
    v6 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v28);
  }
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v6);
LABEL_12:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v28);
    return (unsigned int)v7;
  }
  v32 = 0;
  v30 = 0;
  v7 = (*(__int64 (__fastcall **)(ShieldProvider *, int *, int *))(*(_QWORD *)a1 + 24LL))(a1, &v32, &v30);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v7);
    goto LABEL_12;
  }
  if ( v30 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, 2147943185LL);
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v28);
    return 2147943185LL;
  }
  std::wstring::wstring(v33, L"Off");
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v11 = std::_WChar_traits<unsigned short>::length(L"Warn", v9, v10);
      v12 = v13;
    }
    else
    {
      if ( a2 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            2147549183LL);
        std::wstring::_Tidy_deallocate(v33);
        CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v28);
        return 2147549183LL;
      }
      v11 = std::_WChar_traits<unsigned short>::length(L"Off", v9, v10);
      v12 = L"Off";
    }
    std::wstring::_Assign<unsigned short>(v33, v12, v11);
  }
  else
  {
    v14 = std::_WChar_traits<unsigned short>::length(L"Block", v9, v10);
    std::wstring::_Assign<unsigned short>(v33, v15, v14);
  }
  hKey = 0;
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer", 0, 2u, &hKey);
  if ( v16 )
  {
    v18 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xFA, v17, (const char *)v16, phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v33);
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v28);
    return v18;
  }
  else
  {
    v19 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    v21 = RegSetKeyValueW(hKey, 0, L"SmartScreenEnabled", 1u, v19, cbData);
    if ( !v21 )
    {
      if ( a2 != 2 )
      {
        if ( (unsigned __int8)ShieldProvider::IsWarningStateDismissed(49) )
        {
          v25 = ShieldProvider::SetOrRemoveWarningStateDismissal(0x31u, 1);
          v23 = (unsigned int)v25;
          if ( v25 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
              (unsigned int)v25);
        }
      }
      v29 = 0;
      (*(void (__fastcall **)(ShieldProvider *, int *, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, &v29, v22, v23);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(v33);
      v7 = 0;
      goto LABEL_12;
    }
    v24 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xFE, v22, (const char *)v21, phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v33);
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v28);
    return v24;
  }
}

```

## disassembly

```asm
0x180073670  push    rbx
0x180073672  push    rsi
0x180073673  push    rdi
0x180073674  push    r14
0x180073676  sub     rsp, 88h
0x18007367d  mov     rax, cs:__security_cookie
0x180073684  xor     rax, rsp
0x180073687  mov     [rsp+0A8h+var_30], rax
0x18007368c  mov     esi, edx
0x18007368e  mov     r14, rcx
0x180073691  xor     ebx, ebx
0x180073693  mov     [rsp+0A8h+var_78], rbx
0x180073698  call    ?IsOSWcos@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcos(void)
0x18007369d  test    al, al
0x18007369f  jz      short loc_1800736B5
0x1800736a1  lea     rdx, aSecurityhealth_4; "SecurityHealthHost.exe"
0x1800736a8  mov     cl, cs:?g_fDevMode@@3_NA; this
0x1800736ae  call    ?ValidateCaller@ShieldProvider@@YAJ_NPEAG@Z; ShieldProvider::ValidateCaller(bool,ushort *)
0x1800736b3  jmp     short loc_1800736BF
0x1800736b5  lea     rcx, [rsp+0A8h+var_78]
0x1800736ba  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800736bf  mov     edi, eax
0x1800736c1  test    eax, eax
0x1800736c3  jns     short loc_1800736F0
0x1800736c5  lea     rax, WPP_GLOBAL_Control
0x1800736cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736d3  cmp     rcx, rax
0x1800736d6  jz      loc_1800739D8
0x1800736dc  test    byte ptr [rcx+1Ch], 1
0x1800736e0  jz      loc_1800739D8
0x1800736e6  mov     edx, 0Fh
0x1800736eb  jmp     loc_180073A24
0x1800736f0  mov     [rsp+0A8h+var_60], ebx
0x1800736f4  mov     [rsp+0A8h+var_6C], ebx
0x1800736f8  mov     rax, [r14]
0x1800736fb  lea     r8, [rsp+0A8h+var_6C]
0x180073700  lea     rdx, [rsp+0A8h+var_60]
0x180073705  mov     rcx, r14
0x180073708  mov     rax, [rax+18h]
0x18007370c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073711  mov     edi, eax
0x180073713  test    eax, eax
0x180073715  jns     short loc_18007375A
0x180073717  lea     rax, WPP_GLOBAL_Control
0x18007371e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073725  cmp     rcx, rax
0x180073728  jz      short loc_180073749
0x18007372a  test    byte ptr [rcx+1Ch], 1
0x18007372e  jz      short loc_180073749
0x180073730  mov     edx, 10h
0x180073735  mov     r9d, edi
0x180073738  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007373f  mov     rcx, [rcx+10h]
0x180073743  call    WPP_SF_d
0x180073748  nop
0x180073749  lea     rcx, [rsp+0A8h+var_78]
0x18007374e  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x180073753  mov     eax, edi
0x180073755  jmp     loc_1800739E4
0x18007375a  cmp     [rsp+0A8h+var_6C], ebx
0x18007375e  jz      short loc_1800737A9
0x180073760  lea     rax, WPP_GLOBAL_Control
0x180073767  mov     rcx, cs:WPP_GLOBAL_Control
0x18007376e  cmp     rcx, rax
0x180073771  jz      short loc_180073795
0x180073773  test    byte ptr [rcx+1Ch], 1
0x180073777  jz      short loc_180073795
0x180073779  mov     edx, 11h
0x18007377e  mov     r9d, 80070311h
0x180073784  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007378b  mov     rcx, [rcx+10h]
0x18007378f  call    WPP_SF_d
0x180073794  nop
0x180073795  lea     rcx, [rsp+0A8h+var_78]
0x18007379a  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007379f  mov     eax, 80070311h
0x1800737a4  jmp     loc_1800739E4
0x1800737a9  lea     rdi, aOff; "Off"
0x1800737b0  mov     rdx, rdi
0x1800737b3  lea     rcx, [rsp+0A8h+var_58]
0x1800737b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800737bd  nop
0x1800737be  mov     ecx, esi
0x1800737c0  test    esi, esi
0x1800737c2  jz      loc_180073851
0x1800737c8  sub     ecx, 1
0x1800737cb  jz      short loc_180073833
0x1800737cd  cmp     ecx, 1
0x1800737d0  jz      short loc_180073826
0x1800737d2  lea     rax, WPP_GLOBAL_Control
0x1800737d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800737e0  cmp     rcx, rax
0x1800737e3  jz      short loc_180073807
0x1800737e5  test    byte ptr [rcx+1Ch], 1
0x1800737e9  jz      short loc_180073807
0x1800737eb  mov     edx, 12h
0x1800737f0  mov     r9d, 8000FFFFh
0x1800737f6  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800737fd  mov     rcx, [rcx+10h]
0x180073801  call    WPP_SF_d
0x180073806  nop
0x180073807  lea     rcx, [rsp+0A8h+var_58]
0x18007380c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073811  nop
0x180073812  lea     rcx, [rsp+0A8h+var_78]
0x180073817  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007381c  mov     eax, 8000FFFFh
0x180073821  jmp     loc_1800739E4
0x180073826  mov     rcx, rdi
0x180073829  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18007382e  mov     rdx, rdi
0x180073831  jmp     short loc_180073842
0x180073833  lea     rcx, aWarn; "Warn"
0x18007383a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18007383f  mov     rdx, rcx
0x180073842  mov     r8, rax
0x180073845  lea     rcx, [rsp+0A8h+var_58]
0x18007384a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007384f  jmp     short loc_18007386E
0x180073851  lea     rcx, aBlock; "Block"
0x180073858  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18007385d  mov     r8, rax
0x180073860  mov     rdx, rcx
0x180073863  lea     rcx, [rsp+0A8h+var_58]
0x180073868  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007386d  nop
0x18007386e  mov     [rsp+0A8h+hKey], rbx
0x180073873  lea     rax, [rsp+0A8h+hKey]
0x180073878  mov     [rsp+0A8h+phkResult], rax; unsigned int
0x18007387d  mov     r9d, 2; samDesired
0x180073883  xor     r8d, r8d; ulOptions
0x180073886  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007388d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073894  call    cs:__imp_RegOpenKeyExW
0x18007389a  test    eax, eax
0x18007389c  jz      short loc_1800738DC
0x18007389e  mov     rcx, [rsp+0A8h]; this
0x1800738a6  mov     r9d, eax; char *
0x1800738a9  mov     edx, 0FAh; void *
0x1800738ae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800738b3  mov     ebx, eax
0x1800738b5  lea     rcx, [rsp+0A8h+hKey]
0x1800738ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800738bf  nop
0x1800738c0  lea     rcx, [rsp+0A8h+var_58]
0x1800738c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800738ca  nop
0x1800738cb  lea     rcx, [rsp+0A8h+var_78]
0x1800738d0  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800738d5  mov     eax, ebx
0x1800738d7  jmp     loc_1800739E4
0x1800738dc  mov     eax, [rsp+0A8h+var_48]
0x1800738e0  lea     edx, ds:2[rax*2]
0x1800738e7  lea     rcx, [rsp+0A8h+var_58]
0x1800738ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800738f1  mov     [rsp+0A8h+cbData], edx; cbData
0x1800738f5  mov     [rsp+0A8h+phkResult], rax; unsigned int
0x1800738fa  mov     r9d, 1; dwType
0x180073900  lea     r8, ValueName; "SmartScreenEnabled"
0x180073907  xor     edx, edx; lpSubKey
0x180073909  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18007390e  call    cs:__imp_RegSetKeyValueW
0x180073914  test    eax, eax
0x180073916  jz      short loc_180073956
0x180073918  mov     rcx, [rsp+0A8h]; this
0x180073920  mov     r9d, eax; char *
0x180073923  mov     edx, 0FEh; void *
0x180073928  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007392d  mov     ebx, eax
0x18007392f  lea     rcx, [rsp+0A8h+hKey]
0x180073934  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180073939  nop
0x18007393a  lea     rcx, [rsp+0A8h+var_58]
0x18007393f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073944  nop
0x180073945  lea     rcx, [rsp+0A8h+var_78]
0x18007394a  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007394f  mov     eax, ebx
0x180073951  jmp     loc_1800739E4
0x180073956  cmp     esi, 2
0x180073959  jz      short loc_1800739A7
0x18007395b  mov     edi, 31h ; '1'
0x180073960  mov     ecx, edi
0x180073962  call    ?IsWarningStateDismissed@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsWarningStateDismissed(PillarStatusFlag)
0x180073967  test    al, al
0x180073969  jz      short loc_1800739A7
0x18007396b  mov     dl, 1
0x18007396d  mov     ecx, edi
0x18007396f  call    ShieldProvider__SetOrRemoveWarningStateDismissal
0x180073974  mov     r9d, eax
0x180073977  test    eax, eax
0x180073979  jns     short loc_1800739A7
0x18007397b  lea     rax, WPP_GLOBAL_Control
0x180073982  mov     rcx, cs:WPP_GLOBAL_Control
0x180073989  cmp     rcx, rax
0x18007398c  jz      short loc_1800739A7
0x18007398e  test    byte ptr [rcx+1Ch], 1
0x180073992  jz      short loc_1800739A7
0x180073994  lea     edx, [rdi-1Eh]
0x180073997  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007399e  mov     rcx, [rcx+10h]
0x1800739a2  call    WPP_SF_d
0x1800739a7  mov     [rsp+0A8h+var_70], ebx
0x1800739ab  mov     rax, [r14]
0x1800739ae  lea     rdx, [rsp+0A8h+var_70]
0x1800739b3  mov     rcx, r14
0x1800739b6  mov     rax, [rax+58h]
0x1800739ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739bf  nop
0x1800739c0  lea     rcx, [rsp+0A8h+hKey]
0x1800739c5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800739ca  nop
0x1800739cb  lea     rcx, [rsp+0A8h+var_58]
0x1800739d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800739d5  nop
0x1800739d6  mov     edi, ebx
0x1800739d8  lea     rcx, [rsp+0A8h+var_78]
0x1800739dd  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800739e2  mov     eax, edi
0x1800739e4  mov     rcx, [rsp+0A8h+var_30]
0x1800739e9  xor     rcx, rsp; StackCookie
0x1800739ec  call    __security_check_cookie
0x1800739f1  add     rsp, 88h
0x1800739f8  pop     r14
0x1800739fa  pop     rdi
0x1800739fb  pop     rsi
0x1800739fc  pop     rbx
0x1800739fd  retn
0x1800739fe  mov     edi, [rsp+0A8h+var_70]
0x180073a02  xor     ebx, ebx
0x180073a04  test    edi, edi
0x180073a06  jns     short loc_1800739D6
0x180073a08  lea     rax, WPP_GLOBAL_Control
0x180073a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a16  cmp     rcx, rax
0x180073a19  jz      short loc_1800739D8
0x180073a1b  test    byte ptr [rcx+1Ch], 1
0x180073a1f  jz      short loc_1800739D8
0x180073a21  lea     edx, [rbx+14h]
0x180073a24  mov     r9d, edi
0x180073a27  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180073a2e  mov     rcx, [rcx+10h]
0x180073a32  call    WPP_SF_d
0x180073a37  jmp     short loc_1800739D8
```
