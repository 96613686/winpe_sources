# EnterpriseResourceManagerStore_GetResourcesForEnrollment(ushort const *,std::vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x1800a50e8`
- end: `0x1800a53d9`
- name: `?EnterpriseResourceManagerStore_GetResourcesForEnrollment@@YAJPEBGAEAV?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a56b8`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x180014348`
- `0x18001440c`
- `0x180018a70`
- `0x18001cec8`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x180055d14`
- `0x1800a28f4`
- `0x1800a4d9c`
- `0x1800a50e8`
- `0x1800a6634`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a51b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5292`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a51b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5292`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a5148`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a521f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a5148`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a521f`

## string_xrefs

- `0x1800a512d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a535e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a5384`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall EnterpriseResourceManagerStore_GetResourcesForEnrollment(__int64 a1, __int64 a2)
{
  unsigned int ResourceUris; // ebx
  __int64 v5; // rdx
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v7; // r8
  LSTATUS v8; // eax
  int SubkeyNames; // eax
  __int64 v10; // rdx
  _QWORD *v11; // rdi
  _QWORD *v12; // r12
  _QWORD *v13; // rbx
  char v14; // al
  const unsigned __int16 *v15; // r8
  __int64 v16; // rsi
  __int64 v17; // r15
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v22; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v29[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  if ( !a1 )
  {
    ResourceUris = -2147024809;
    v5 = 873;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
      (const char *)ResourceUris,
      phkResult);
    return ResourceUris;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v7 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\%s";
  if ( !IsStateSeparationEnabled )
    v7 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\%s";
  ResourceUris = StringCchPrintfW(SubKey, 0x104u, v7, a1);
  if ( (ResourceUris & 0x80000000) != 0 )
  {
    v5 = 882;
    goto LABEL_3;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey);
  ResourceUris = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      ResourceUris = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    std::vector<ConfigDoc>::vector<ConfigDoc>(v24);
    SubkeyNames = GetSubkeyNames(hKey);
    ResourceUris = SubkeyNames;
    if ( SubkeyNames >= 0 )
    {
      v11 = (_QWORD *)v24[0];
      v12 = (_QWORD *)v24[1];
      while ( v11 != v12 )
      {
        if ( v11[3] <= 7u )
          v13 = v11;
        else
          v13 = (_QWORD *)*v11;
        v14 = RtlIsStateSeparationEnabled();
        v15 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\%s\\%s\\default";
        if ( !v14 )
          v15 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked\\%s\\%s\\default";
        SubkeyNames = StringCchPrintfW(v29, 0x104u, v15, a1, v13);
        ResourceUris = SubkeyNames;
        if ( SubkeyNames < 0 )
        {
          v10 = 910;
          goto LABEL_33;
        }
        v22 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v29, 0, 0x20119u, &v22) )
        {
          if ( !v22 )
          {
            ResourceUris = -2147418113;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x39D,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
              (const char *)0x8000FFFFLL,
              phkResultb);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
            break;
          }
          std::vector<ConfigDoc>::vector<ConfigDoc>(v25);
          ResourceUris = EnterpriseResourceManagerStore_GetResourceUris(v22);
          v16 = v25[0];
          v17 = v25[1];
          while ( v16 != v17 )
          {
            std::wstring::wstring(v26, v11);
            std::wstring::wstring(v27, v16);
            if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
            {
              std::vector<std::tuple<std::wstring,std::wstring>>::_Emplace_reallocate<std::tuple<std::wstring,std::wstring>>(
                a2,
                *(_QWORD *)(a2 + 8),
                v26);
            }
            else
            {
              std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(*(_QWORD *)(a2 + 8), v26);
              *(_QWORD *)(a2 + 8) += 64LL;
            }
            std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v26);
            v16 += 32;
          }
          std::vector<std::wstring>::_Tidy(v25);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
        v11 += 4;
      }
    }
    else
    {
      v10 = 899;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
        (const char *)(unsigned int)SubkeyNames,
        phkResulta);
    }
    std::vector<std::wstring>::_Tidy(v24);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return ResourceUris;
}

```

## disassembly

```asm
0x1800a50e8  mov     [rsp-8+arg_10], rbx
0x1800a50ed  push    rbp
0x1800a50ee  push    rsi
0x1800a50ef  push    rdi
0x1800a50f0  push    r12
0x1800a50f2  push    r13
0x1800a50f4  push    r14
0x1800a50f6  push    r15
0x1800a50f8  lea     rbp, [rsp-3E0h]
0x1800a5100  sub     rsp, 4E0h
0x1800a5107  mov     rax, cs:__security_cookie
0x1800a510e  xor     rax, rsp
0x1800a5111  mov     [rbp+410h+var_40], rax
0x1800a5118  mov     r13, rdx
0x1800a511b  mov     r14, rcx
0x1800a511e  test    rcx, rcx
0x1800a5121  jnz     short loc_1800A5148
0x1800a5123  mov     ebx, 80070057h
0x1800a5128  mov     edx, 369h; void *
0x1800a512d  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a5134  mov     r9d, ebx; char *
0x1800a5137  mov     rcx, [rbp+418h]; this
0x1800a513e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5143  jmp     loc_1800A53AD
0x1800a5148  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800a514e  lea     rcx, aSoftwareMicros_66; "Software\\Microsoft\\EnterpriseResource"...
0x1800a5155  lea     r8, aOsdataSoftware_49; "OSData\\Software\\Microsoft\\Enterprise"...
0x1800a515c  test    al, al
0x1800a515e  cmovz   r8, rcx; unsigned __int16 *
0x1800a5162  mov     r9, r14
0x1800a5165  mov     edx, 104h; unsigned __int64
0x1800a516a  lea     rcx, [rbp+410h+SubKey]; unsigned __int16 *
0x1800a516e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a5173  mov     ebx, eax
0x1800a5175  test    eax, eax
0x1800a5177  jns     short loc_1800A5180
0x1800a5179  mov     edx, 372h
0x1800a517e  jmp     short loc_1800A512D
0x1800a5180  mov     [rsp+510h+hKey], 0
0x1800a5189  xor     edx, edx
0x1800a518b  lea     rcx, [rsp+510h+hKey]
0x1800a5190  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a5195  lea     rax, [rsp+510h+hKey]
0x1800a519a  mov     qword ptr [rsp+510h+phkResult], rax; phkResult
0x1800a519f  mov     r9d, 20119h; samDesired
0x1800a51a5  xor     r8d, r8d; ulOptions
0x1800a51a8  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x1800a51ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a51b3  call    cs:__imp_RegOpenKeyExW
0x1800a51b9  mov     ebx, eax
0x1800a51bb  test    eax, eax
0x1800a51bd  jz      short loc_1800A51D3
0x1800a51bf  jle     loc_1800A53A3
0x1800a51c5  movzx   ebx, ax
0x1800a51c8  or      ebx, 80070000h
0x1800a51ce  jmp     loc_1800A53A3
0x1800a51d3  lea     rcx, [rsp+510h+var_4D0]
0x1800a51d8  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800a51dd  nop
0x1800a51de  lea     rdx, [rsp+510h+var_4D0]
0x1800a51e3  mov     rcx, [rsp+510h+hKey]; hKey
0x1800a51e8  call    ?GetSubkeyNames@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetSubkeyNames(HKEY__ *,std::vector<std::wstring> &)
0x1800a51ed  mov     ebx, eax
0x1800a51ef  test    eax, eax
0x1800a51f1  jns     short loc_1800A51FD
0x1800a51f3  mov     edx, 383h
0x1800a51f8  jmp     loc_1800A5381
0x1800a51fd  mov     rdi, [rsp+510h+var_4D0]
0x1800a5202  mov     r12, [rsp+510h+var_4C8]
0x1800a5207  cmp     rdi, r12
0x1800a520a  jz      loc_1800A5398
0x1800a5210  cmp     qword ptr [rdi+18h], 7
0x1800a5215  jbe     short loc_1800A521C
0x1800a5217  mov     rbx, [rdi]
0x1800a521a  jmp     short loc_1800A521F
0x1800a521c  mov     rbx, rdi
0x1800a521f  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800a5225  lea     rcx, aSoftwareMicros_44; "Software\\Microsoft\\EnterpriseResource"...
0x1800a522c  lea     r8, aOsdataSoftware_36; "OSData\\Software\\Microsoft\\Enterprise"...
0x1800a5233  test    al, al
0x1800a5235  cmovz   r8, rcx; unsigned __int16 *
0x1800a5239  mov     qword ptr [rsp+510h+phkResult], rbx; int
0x1800a523e  mov     r9, r14
0x1800a5241  mov     edx, 104h; unsigned __int64
0x1800a5246  lea     rcx, [rbp+410h+var_250]; unsigned __int16 *
0x1800a524d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a5252  mov     ebx, eax
0x1800a5254  test    eax, eax
0x1800a5256  js      loc_1800A537C
0x1800a525c  mov     [rsp+510h+var_4E0], 0
0x1800a5265  xor     edx, edx
0x1800a5267  lea     rcx, [rsp+510h+var_4E0]
0x1800a526c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a5271  lea     rax, [rsp+510h+var_4E0]
0x1800a5276  mov     qword ptr [rsp+510h+phkResult], rax; int
0x1800a527b  mov     r9d, 20119h; samDesired
0x1800a5281  xor     r8d, r8d; ulOptions
0x1800a5284  lea     rdx, [rbp+410h+var_250]; lpSubKey
0x1800a528b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a5292  call    cs:__imp_RegOpenKeyExW
0x1800a5298  test    eax, eax
0x1800a529a  jnz     loc_1800A533C
0x1800a52a0  cmp     [rsp+510h+var_4E0], 0
0x1800a52a6  jz      loc_1800A534F
0x1800a52ac  lea     rcx, [rsp+510h+var_4B8]
0x1800a52b1  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800a52b6  nop
0x1800a52b7  lea     rdx, [rsp+510h+var_4B8]
0x1800a52bc  mov     rcx, [rsp+510h+var_4E0]; hKey
0x1800a52c1  call    ?EnterpriseResourceManagerStore_GetResourceUris@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; EnterpriseResourceManagerStore_GetResourceUris(HKEY__ *,std::vector<std::wstring> &)
0x1800a52c6  mov     ebx, eax
0x1800a52c8  mov     rsi, [rsp+510h+var_4B8]
0x1800a52cd  mov     r15, [rsp+510h+var_4B0]
0x1800a52d2  jmp     short loc_1800A532C
0x1800a52d4  mov     rdx, rdi
0x1800a52d7  lea     rcx, [rsp+510h+var_4A0]
0x1800a52dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a52e1  nop
0x1800a52e2  mov     rdx, rsi
0x1800a52e5  lea     rcx, [rbp+410h+var_480]
0x1800a52e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a52ee  nop
0x1800a52ef  mov     rax, [r13+8]
0x1800a52f3  cmp     rax, [r13+10h]
0x1800a52f7  jz      short loc_1800A530D
0x1800a52f9  lea     rdx, [rsp+510h+var_4A0]
0x1800a52fe  mov     rcx, rax
0x1800a5301  call    ??0?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@$$QEAV01@@Z; std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(std::tuple<std::wstring,std::wstring> &&)
0x1800a5306  add     qword ptr [r13+8], 40h ; '@'
0x1800a530b  jmp     short loc_1800A531E
0x1800a530d  lea     r8, [rsp+510h+var_4A0]
0x1800a5312  mov     rdx, rax
0x1800a5315  mov     rcx, r13
0x1800a5318  call    ??$_Emplace_reallocate@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<std::wstring,std::wstring>>::_Emplace_reallocate<std::tuple<std::wstring,std::wstring>>(std::tuple<std::wstring,std::wstring> * const,std::tuple<std::wstring,std::wstring> &&)
0x1800a531d  nop
0x1800a531e  lea     rcx, [rsp+510h+var_4A0]
0x1800a5323  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800a5328  add     rsi, 20h ; ' '
0x1800a532c  cmp     rsi, r15
0x1800a532f  jnz     short loc_1800A52D4
0x1800a5331  lea     rcx, [rsp+510h+var_4B8]
0x1800a5336  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a533b  nop
0x1800a533c  lea     rcx, [rsp+510h+var_4E0]
0x1800a5341  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a5346  add     rdi, 20h ; ' '
0x1800a534a  jmp     loc_1800A5207
0x1800a534f  mov     rcx, [rbp+418h]; this
0x1800a5356  mov     ebx, 8000FFFFh
0x1800a535b  mov     r9d, ebx; char *
0x1800a535e  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a5365  mov     edx, 39Dh; void *
0x1800a536a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a536f  nop
0x1800a5370  lea     rcx, [rsp+510h+var_4E0]
0x1800a5375  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a537a  jmp     short loc_1800A5398
0x1800a537c  mov     edx, 38Eh; void *
0x1800a5381  mov     r9d, eax; char *
0x1800a5384  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a538b  mov     rcx, [rbp+418h]; this
0x1800a5392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5397  nop
0x1800a5398  lea     rcx, [rsp+510h+var_4D0]
0x1800a539d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a53a2  nop
0x1800a53a3  lea     rcx, [rsp+510h+hKey]
0x1800a53a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a53ad  mov     eax, ebx
0x1800a53af  mov     rcx, [rbp+410h+var_40]
0x1800a53b6  xor     rcx, rsp; StackCookie
0x1800a53b9  call    __security_check_cookie
0x1800a53be  mov     rbx, [rsp+510h+arg_10]
0x1800a53c6  add     rsp, 4E0h
0x1800a53cd  pop     r15
0x1800a53cf  pop     r14
0x1800a53d1  pop     r13
0x1800a53d3  pop     r12
0x1800a53d5  pop     rdi
0x1800a53d6  pop     rsi
0x1800a53d7  pop     rbp
0x1800a53d8  retn
```
