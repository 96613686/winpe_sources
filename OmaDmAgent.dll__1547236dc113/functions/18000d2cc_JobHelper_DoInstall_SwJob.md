# JobHelper::DoInstall(_SwJob)

- ea: `0x18000d2cc`
- end: `0x18000da0a`
- name: `?DoInstall@JobHelper@@AEAAJU_SwJob@@@Z`
- size: `1854`
- prototype: `int __high(struct _SwJob)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180010700`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x1800070e4`
- `0x18000a290`
- `0x18000a3c0`
- `0x18000a440`
- `0x18000a4f4`
- `0x18000aab0`
- `0x18000b51c`
- `0x18000b588`
- `0x18000b6f4`
- `0x18000bbf8`
- `0x18000bccc`
- `0x18000bd00`
- `0x18000d2cc`
- `0x18000e980`
- `0x180011a44`
- `0x180012338`
- `0x180012914`
- `0x180015a2c`
- `0x180017aac`
- `0x18001f420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d4f6`
- `msvcrt!_wcsicmp` at `0x18000d606`
- `msvcrt!_wcsicmp` at `0x18000d4f6`
- `msvcrt!_wcsicmp` at `0x18000d606`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall JobHelper::DoInstall(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdx
  unsigned int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // rdi
  int v9; // ebx
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  int PackageFullNameFromManifest; // r15d
  JobHelper *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdx
  const wchar_t **v18; // rbx
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  wchar_t **v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rbx
  const WCHAR *v25; // rcx
  const wchar_t *v26; // rdx
  const wchar_t *v27; // rcx
  __int64 i; // rax
  wchar_t **v29; // rax
  wchar_t **v30; // r9
  __int64 v31; // rbx
  __int64 v32; // rax
  JobHelper *v33; // rcx
  wchar_t **v34; // rax
  __int64 v35; // r9
  __int64 v36; // rbx
  __int64 v37; // rax
  unsigned int v38; // ebx
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rbx
  __int64 j; // rax
  _DeployJob *v44; // rax
  JobHelper *v45; // rcx
  __int64 v46; // r9
  __int64 v47; // rsi
  int v48; // ebx
  unsigned int v49; // edi
  __int64 v50; // rax
  _BYTE v51[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v52[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v53; // [rsp+80h] [rbp-80h]
  wchar_t *String1[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v55; // [rsp+A0h] [rbp-60h]
  wchar_t *String2[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v57; // [rsp+C8h] [rbp-38h]
  _QWORD v58[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v59[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v60[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v61; // [rsp+1C0h] [rbp+C0h]
  int v62; // [rsp+1C4h] [rbp+C4h]
  __int64 v63; // [rsp+1C8h] [rbp+C8h] BYREF
  int v64; // [rsp+1D8h] [rbp+D8h]
  _BYTE v65[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v66[128]; // [rsp+210h] [rbp+110h] BYREF

  v53 = a2;
  std::wstring::wstring(String1, &dword_180022F6C);
  if ( *((_DWORD *)a2 + 17) != 1 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
LABEL_5:
    LOBYTE(v4) = 1;
    std::wstring::_Tidy(String1, v4, 0);
    _SwJob::~_SwJob((_SwJob *)a2);
    return 0;
  }
  v6 = *(_DWORD *)(a1 + 104);
  if ( *((_DWORD *)a2 + 56) >= v6 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      if ( (unsigned __int64)a2[3] < 8 )
        LODWORD(v7) = (_DWORD)a2;
      else
        v7 = *a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        179,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v7,
        v6);
    }
    v8 = std::wstring::wstring(v52, a2 + 14);
    v9 = *((_DWORD *)a2 + 26);
    v10 = std::wstring::wstring(v51, a2);
    JobHelper::UpdateProgress(a1, v10, 60, 0, v9, v8);
    goto LABEL_5;
  }
  if ( (unsigned __int64)a2[27] < 8 )
    v11 = (const WCHAR *)(a2 + 24);
  else
    v11 = (const WCHAR *)a2[24];
  PackageFullNameFromManifest = GetPackageFullNameFromManifest(v11, (__int64)String1, *((_BYTE *)a2 + 76));
  if ( PackageFullNameFromManifest >= 0 )
  {
    v18 = (const wchar_t **)(a2 + 4);
    if ( (unsigned __int64)a2[7] < 8 )
      v19 = (const wchar_t *)(a2 + 4);
    else
      v19 = *v18;
    v20 = (const wchar_t *)String1;
    if ( v55 >= 8 )
      v20 = String1[0];
    if ( _wcsicmp(v20, v19) )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v21 = String1;
        if ( v55 >= 8 )
          v21 = (wchar_t **)String1[0];
        if ( (unsigned __int64)a2[7] >= 8 )
          v18 = (const wchar_t **)*v18;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          181,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (_DWORD)v18,
          (__int64)v21);
      }
      v22 = std::wstring::wstring(v51, L"Package is tampered");
      v23 = std::wstring::wstring(v52, a2);
      JobHelper::UpdateProgress(a1, v23, 110, 100, -2147467259, v22);
      goto LABEL_5;
    }
    v24 = *(_QWORD *)a2[38];
    while ( v24 != a2[38] )
    {
      _FrameworkDependency::_FrameworkDependency(
        (_FrameworkDependency *)String2,
        (const struct _FrameworkDependency *)(v24 + 64));
      v25 = (const WCHAR *)v58;
      if ( v58[3] >= 8u )
        v25 = (const WCHAR *)v58[0];
      PackageFullNameFromManifest = GetPackageFullNameFromManifest(v25, (__int64)String1, 0);
      if ( PackageFullNameFromManifest < 0 )
      {
        v33 = (JobHelper *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v34 = String2;
          if ( v57 >= 8 )
            v34 = (wchar_t **)String2[0];
          if ( (unsigned __int64)a2[3] < 8 )
            LODWORD(v35) = (_DWORD)a2;
          else
            v35 = *a2;
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            182,
            (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
            v35,
            (__int64)v34,
            PackageFullNameFromManifest);
        }
        *((_DWORD *)a2 + 26) = PackageFullNameFromManifest;
        JobHelper::GetErrorMessage(v33, (struct _SwJob *)a2);
        v36 = std::wstring::wstring(v51, a2 + 14);
        v37 = std::wstring::wstring(v52, a2);
        JobHelper::UpdateProgress(a1, v37, 110, 100, PackageFullNameFromManifest, v36);
        _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)String2);
        goto LABEL_94;
      }
      v26 = (const wchar_t *)String2;
      if ( v57 >= 8 )
        v26 = String2[0];
      v27 = (const wchar_t *)String1;
      if ( v55 >= 8 )
        v27 = String1[0];
      if ( _wcsicmp(v27, v26) )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v29 = String1;
          if ( v55 >= 8 )
            v29 = (wchar_t **)String1[0];
          v30 = String2;
          if ( v57 >= 8 )
            LODWORD(v30) = String2[0];
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            183,
            (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
            (_DWORD)v30,
            (__int64)v29);
        }
        v31 = std::wstring::wstring(v51, L"Dependant package is tampered");
        v32 = std::wstring::wstring(v52, a2);
        JobHelper::UpdateProgress(a1, v32, 110, 100, -2147467259, v31);
        _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)String2);
        PackageFullNameFromManifest = 0;
        goto LABEL_94;
      }
      _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)String2);
      if ( !*(_BYTE *)(v24 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v24 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(v24 + 8); !*(_BYTE *)(i + 25) && v24 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v24 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min();
        }
        v24 = i;
      }
    }
    v38 = ++*((_DWORD *)a2 + 56);
    v39 = std::wstring::wstring(v51, a2);
    JobHelper::UpdateDeployRetry(a1, v39, v38);
    v40 = std::wstring::wstring(v51, &dword_180022F6C);
    v41 = std::wstring::wstring(v52, a2);
    JobHelper::UpdateProgress(a1, v41, 50, 0, 0, v40);
    _DeployJob::_DeployJob((_DeployJob *)v59);
    std::wstring::operator=(v59, a2);
    std::wstring::operator=(v60, a2 + 24);
    v61 = 1;
    v62 = *((_DWORD *)a2 + 18);
    v64 = *(_DWORD *)(a1 + 108);
    v42 = *(_QWORD *)a2[38];
    while ( v42 != a2[38] )
    {
      _FrameworkDependency::_FrameworkDependency(
        (_FrameworkDependency *)v65,
        (const struct _FrameworkDependency *)(v42 + 64));
      std::list<std::wstring>::_Insert<std::wstring const &>(&v63, v63, v66);
      _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)v65);
      if ( !*(_BYTE *)(v42 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v42 + 16) + 25LL) )
        {
          for ( j = *(_QWORD *)(v42 + 8); !*(_BYTE *)(j + 25) && v42 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            v42 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min();
        }
        v42 = j;
      }
    }
    v44 = _DeployJob::_DeployJob((_DeployJob *)v65, (const struct _DeployJob *)v59);
    PackageFullNameFromManifest = CInstallService::AddJob(a1 + 72, v44);
    if ( PackageFullNameFromManifest < 0 )
    {
      v45 = (JobHelper *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        if ( (unsigned __int64)a2[3] < 8 )
          LODWORD(v46) = (_DWORD)a2;
        else
          v46 = *a2;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          184,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          v46,
          PackageFullNameFromManifest);
      }
      *((_DWORD *)a2 + 24) = 60;
      *((_DWORD *)a2 + 26) = PackageFullNameFromManifest;
      JobHelper::GetErrorMessage(v45, (struct _SwJob *)a2);
      v47 = std::wstring::wstring(v51, a2 + 14);
      v48 = *((_DWORD *)a2 + 26);
      v49 = *((_DWORD *)a2 + 24);
      v50 = std::wstring::wstring(v52, a2);
      JobHelper::UpdateProgress(a1, v50, v49, 0, v48, v47);
    }
    _DeployJob::~_DeployJob((_DeployJob *)v59);
  }
  else
  {
    v13 = (JobHelper *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( (unsigned __int64)a2[3] < 8 )
        LODWORD(v14) = (_DWORD)a2;
      else
        v14 = *a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v14,
        PackageFullNameFromManifest);
    }
    *((_DWORD *)a2 + 26) = PackageFullNameFromManifest;
    JobHelper::GetErrorMessage(v13, (struct _SwJob *)a2);
    v15 = std::wstring::wstring(v51, a2 + 14);
    v16 = std::wstring::wstring(v52, a2);
    JobHelper::UpdateProgress(a1, v16, 110, 100, PackageFullNameFromManifest, v15);
  }
LABEL_94:
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(String1, v17, 0);
  _SwJob::~_SwJob((_SwJob *)a2);
  return (unsigned int)PackageFullNameFromManifest;
}

```

## disassembly

```asm
0x18000d2cc  mov     [rsp-8+arg_10], rbx
0x18000d2d1  mov     [rsp-8+arg_18], rsi
0x18000d2d6  push    rbp
0x18000d2d7  push    rdi
0x18000d2d8  push    r13
0x18000d2da  push    r14
0x18000d2dc  push    r15
0x18000d2de  lea     rbp, [rsp-1A0h]
0x18000d2e6  sub     rsp, 2A0h
0x18000d2ed  mov     rax, cs:__security_cookie
0x18000d2f4  xor     rax, rsp
0x18000d2f7  mov     [rbp+1C0h+var_30], rax
0x18000d2fe  mov     r14, rdx
0x18000d301  mov     r13, rcx
0x18000d304  mov     [rbp+1C0h+var_240], rdx
0x18000d308  lea     rdx, dword_180022F6C
0x18000d30f  lea     rcx, [rbp+1C0h+String1]
0x18000d313  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000d318  nop
0x18000d319  cmp     dword ptr [r14+44h], 1
0x18000d31e  jz      short loc_18000D36D
0x18000d320  lea     rax, WPP_GLOBAL_Control
0x18000d327  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d32e  cmp     rcx, rax
0x18000d331  jz      short loc_18000D34F
0x18000d333  test    byte ptr [rcx+1Ch], 2
0x18000d337  jz      short loc_18000D34F
0x18000d339  mov     edx, 0B2h
0x18000d33e  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000d345  mov     rcx, [rcx+10h]
0x18000d349  call    WPP_SF_
0x18000d34e  nop
0x18000d34f  xor     r8d, r8d
0x18000d352  mov     dl, 1
0x18000d354  lea     rcx, [rbp+1C0h+String1]
0x18000d358  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d35d  nop
0x18000d35e  mov     rcx, r14; this
0x18000d361  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18000d366  xor     eax, eax
0x18000d368  jmp     loc_18000D9DE
0x18000d36d  mov     r8d, [r13+68h]
0x18000d371  lea     rdi, [r14+0C0h]
0x18000d378  cmp     [rdi+20h], r8d
0x18000d37c  jb      loc_18000D411
0x18000d382  lea     rax, WPP_GLOBAL_Control
0x18000d389  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d390  cmp     rcx, rax
0x18000d393  jz      short loc_18000D3C4
0x18000d395  test    byte ptr [rcx+1Ch], 1
0x18000d399  jz      short loc_18000D3C4
0x18000d39b  cmp     qword ptr [r14+18h], 8
0x18000d3a0  jb      short loc_18000D3A7
0x18000d3a2  mov     r9, [r14]
0x18000d3a5  jmp     short loc_18000D3AA
0x18000d3a7  mov     r9, r14
0x18000d3aa  mov     edx, 0B3h
0x18000d3af  mov     dword ptr [rsp+2C0h+var_2A0], r8d
0x18000d3b4  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000d3bb  mov     rcx, [rcx+10h]
0x18000d3bf  call    WPP_SF_Sd
0x18000d3c4  lea     rax, [rsp+2C0h+var_260]
0x18000d3c9  mov     [rsp+2C0h+var_288], rax
0x18000d3ce  lea     rdx, [r14+70h]
0x18000d3d2  lea     rcx, [rsp+2C0h+var_260]
0x18000d3d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d3dc  mov     rdi, rax
0x18000d3df  mov     ebx, [r14+68h]
0x18000d3e3  mov     rdx, r14
0x18000d3e6  lea     rcx, [rsp+2C0h+var_280]
0x18000d3eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d3f0  nop
0x18000d3f1  mov     [rsp+2C0h+var_298], rdi
0x18000d3f6  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x18000d3fa  xor     r9d, r9d
0x18000d3fd  lea     r8d, [r9+3Ch]
0x18000d401  mov     rdx, rax
0x18000d404  mov     rcx, r13
0x18000d407  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000d40c  jmp     loc_18000D34F
0x18000d411  cmp     qword ptr [rdi+18h], 8
0x18000d416  jb      short loc_18000D41D
0x18000d418  mov     rcx, [rdi]
0x18000d41b  jmp     short loc_18000D420
0x18000d41d  mov     rcx, rdi
0x18000d420  mov     r8b, [r14+4Ch]
0x18000d424  lea     rdx, [rbp+1C0h+String1]
0x18000d428  call    ?GetPackageFullNameFromManifest@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; GetPackageFullNameFromManifest(ushort const *,std::wstring &,bool)
0x18000d42d  mov     r15d, eax
0x18000d430  xor     esi, esi
0x18000d432  test    eax, eax
0x18000d434  jns     loc_18000D4D5
0x18000d43a  lea     rax, WPP_GLOBAL_Control
0x18000d441  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d448  cmp     rcx, rax
0x18000d44b  jz      short loc_18000D47C
0x18000d44d  test    byte ptr [rcx+1Ch], 4
0x18000d451  jz      short loc_18000D47C
0x18000d453  cmp     qword ptr [r14+18h], 8
0x18000d458  jb      short loc_18000D45F
0x18000d45a  mov     r9, [r14]
0x18000d45d  jmp     short loc_18000D462
0x18000d45f  mov     r9, r14
0x18000d462  mov     edx, 0B4h
0x18000d467  mov     dword ptr [rsp+2C0h+var_2A0], r15d
0x18000d46c  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000d473  mov     rcx, [rcx+10h]
0x18000d477  call    WPP_SF_Sd
0x18000d47c  mov     [r14+68h], r15d
0x18000d480  mov     rdx, r14; struct _SwJob *
0x18000d483  call    ?GetErrorMessage@JobHelper@@AEAAXAEAU_SwJob@@@Z; JobHelper::GetErrorMessage(_SwJob &)
0x18000d488  lea     rax, [rsp+2C0h+var_280]
0x18000d48d  mov     [rsp+2C0h+var_290], rax
0x18000d492  lea     rdx, [r14+70h]
0x18000d496  lea     rcx, [rsp+2C0h+var_280]
0x18000d49b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d4a0  mov     rbx, rax
0x18000d4a3  mov     rdx, r14
0x18000d4a6  lea     rcx, [rsp+2C0h+var_260]
0x18000d4ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d4b0  nop
0x18000d4b1  mov     [rsp+2C0h+var_298], rbx
0x18000d4b6  mov     dword ptr [rsp+2C0h+var_2A0], r15d
0x18000d4bb  mov     r9d, 64h ; 'd'
0x18000d4c1  lea     r8d, [r9+0Ah]
0x18000d4c5  mov     rdx, rax
0x18000d4c8  mov     rcx, r13
0x18000d4cb  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000d4d0  jmp     loc_18000D9C4
0x18000d4d5  lea     rbx, [r14+20h]
0x18000d4d9  cmp     qword ptr [rbx+18h], 8
0x18000d4de  jb      short loc_18000D4E5
0x18000d4e0  mov     rdx, [rbx]
0x18000d4e3  jmp     short loc_18000D4E8
0x18000d4e5  mov     rdx, rbx; String2
0x18000d4e8  lea     rcx, [rbp+1C0h+String1]
0x18000d4ec  cmp     [rbp+1C0h+var_220], 8
0x18000d4f1  cmovnb  rcx, [rbp+1C0h+String1]; String1
0x18000d4f6  call    cs:__imp__wcsicmp
0x18000d4fd  nop     dword ptr [rax+rax+00h]
0x18000d502  test    eax, eax
0x18000d504  jz      loc_18000D5A0
0x18000d50a  lea     rax, WPP_GLOBAL_Control
0x18000d511  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d518  cmp     rcx, rax
0x18000d51b  jz      short loc_18000D558
0x18000d51d  test    byte ptr [rcx+1Ch], 4
0x18000d521  jz      short loc_18000D558
0x18000d523  lea     rax, [rbp+1C0h+String1]
0x18000d527  cmp     [rbp+1C0h+var_220], 8
0x18000d52c  cmovnb  rax, [rbp+1C0h+String1]
0x18000d531  cmp     qword ptr [rbx+18h], 8
0x18000d536  jb      short loc_18000D53B
0x18000d538  mov     rbx, [rbx]
0x18000d53b  mov     edx, 0B5h
0x18000d540  mov     [rsp+2C0h+var_2A0], rax
0x18000d545  mov     r9, rbx
0x18000d548  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000d54f  mov     rcx, [rcx+10h]
0x18000d553  call    WPP_SF_SS
0x18000d558  lea     rax, [rsp+2C0h+var_280]
0x18000d55d  mov     [rsp+2C0h+var_290], rax
0x18000d562  lea     rdx, aPackageIsTampe; "Package is tampered"
0x18000d569  lea     rcx, [rsp+2C0h+var_280]
0x18000d56e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000d573  mov     rbx, rax
0x18000d576  mov     rdx, r14
0x18000d579  lea     rcx, [rsp+2C0h+var_260]
0x18000d57e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d583  nop
0x18000d584  mov     [rsp+2C0h+var_298], rbx
0x18000d589  mov     dword ptr [rsp+2C0h+var_2A0], 80004005h
0x18000d591  mov     r9d, 64h ; 'd'
0x18000d597  lea     r8d, [r9+0Ah]
0x18000d59b  jmp     loc_18000D401
0x18000d5a0  mov     rbx, [r14+130h]
0x18000d5a7  mov     rbx, [rbx]
0x18000d5aa  cmp     rbx, [r14+130h]
0x18000d5b1  jz      loc_18000D7BE
0x18000d5b7  lea     rdx, [rbx+40h]; struct _FrameworkDependency *
0x18000d5bb  lea     rcx, [rbp+1C0h+String2]; this
0x18000d5bf  call    ??0_FrameworkDependency@@QEAA@AEBU0@@Z; _FrameworkDependency::_FrameworkDependency(_FrameworkDependency const &)
0x18000d5c4  nop
0x18000d5c5  lea     rcx, [rbp+1C0h+var_1E0]
0x18000d5c9  cmp     [rbp+1C0h+var_1C8], 8
0x18000d5ce  cmovnb  rcx, [rbp+1C0h+var_1E0]
0x18000d5d3  xor     r8d, r8d
0x18000d5d6  lea     rdx, [rbp+1C0h+String1]
0x18000d5da  call    ?GetPackageFullNameFromManifest@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; GetPackageFullNameFromManifest(ushort const *,std::wstring &,bool)
0x18000d5df  mov     r15d, eax
0x18000d5e2  test    eax, eax
0x18000d5e4  js      loc_18000D706
0x18000d5ea  lea     rdx, [rbp+1C0h+String2]
0x18000d5ee  cmp     [rbp+1C0h+var_1F8], 8
0x18000d5f3  cmovnb  rdx, [rbp+1C0h+String2]; String2
0x18000d5f8  lea     rcx, [rbp+1C0h+String1]
0x18000d5fc  cmp     [rbp+1C0h+var_220], 8
0x18000d601  cmovnb  rcx, [rbp+1C0h+String1]; String1
0x18000d606  call    cs:__imp__wcsicmp
0x18000d60d  nop     dword ptr [rax+rax+00h]
0x18000d612  test    eax, eax
0x18000d614  jnz     short loc_18000D657
0x18000d616  lea     rcx, [rbp+1C0h+String2]; this
0x18000d61a  call    ??1_FrameworkDependency@@QEAA@XZ; _FrameworkDependency::~_FrameworkDependency(void)
0x18000d61f  cmp     [rbx+19h], sil
0x18000d623  jnz     short loc_18000D5AA
0x18000d625  mov     rcx, [rbx+10h]
0x18000d629  cmp     [rcx+19h], sil
0x18000d62d  jnz     short loc_18000D636
0x18000d62f  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min(std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *)
0x18000d634  jmp     short loc_18000D64F
0x18000d636  mov     rax, [rbx+8]
0x18000d63a  jmp     short loc_18000D649
0x18000d63c  cmp     rbx, [rax+10h]
0x18000d640  jnz     short loc_18000D64F
0x18000d642  mov     rbx, rax
0x18000d645  mov     rax, [rax+8]
0x18000d649  cmp     [rax+19h], sil
0x18000d64d  jz      short loc_18000D63C
0x18000d64f  mov     rbx, rax
0x18000d652  jmp     loc_18000D5AA
0x18000d657  lea     rax, WPP_GLOBAL_Control
0x18000d65e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d665  cmp     rcx, rax
0x18000d668  jz      short loc_18000D6A6
0x18000d66a  test    byte ptr [rcx+1Ch], 4
0x18000d66e  jz      short loc_18000D6A6
0x18000d670  lea     rax, [rbp+1C0h+String1]
0x18000d674  cmp     [rbp+1C0h+var_220], 8
0x18000d679  cmovnb  rax, [rbp+1C0h+String1]
0x18000d67e  lea     r9, [rbp+1C0h+String2]
0x18000d682  cmp     [rbp+1C0h+var_1F8], 8
0x18000d687  cmovnb  r9, [rbp+1C0h+String2]
0x18000d68c  mov     edx, 0B7h
0x18000d691  mov     [rsp+2C0h+var_2A0], rax
0x18000d696  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000d69d  mov     rcx, [rcx+10h]
0x18000d6a1  call    WPP_SF_SS
0x18000d6a6  lea     rax, [rsp+2C0h+var_280]
0x18000d6ab  mov     [rsp+2C0h+var_290], rax
0x18000d6b0  lea     rdx, aDependantPacka; "Dependant package is tampered"
0x18000d6b7  lea     rcx, [rsp+2C0h+var_280]
0x18000d6bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000d6c1  mov     rbx, rax
0x18000d6c4  mov     rdx, r14
0x18000d6c7  lea     rcx, [rsp+2C0h+var_260]
0x18000d6cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d6d1  nop
0x18000d6d2  mov     [rsp+2C0h+var_298], rbx
0x18000d6d7  mov     dword ptr [rsp+2C0h+var_2A0], 80004005h
0x18000d6df  mov     r9d, 64h ; 'd'
0x18000d6e5  lea     r8d, [r9+0Ah]
0x18000d6e9  mov     rdx, rax
0x18000d6ec  mov     rcx, r13
0x18000d6ef  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000d6f4  nop
0x18000d6f5  lea     rcx, [rbp+1C0h+String2]; this
0x18000d6f9  call    ??1_FrameworkDependency@@QEAA@XZ; _FrameworkDependency::~_FrameworkDependency(void)
0x18000d6fe  mov     r15d, esi
0x18000d701  jmp     loc_18000D9C4
0x18000d706  lea     rax, WPP_GLOBAL_Control
0x18000d70d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d714  cmp     rcx, rax
0x18000d717  jz      short loc_18000D75B
0x18000d719  test    byte ptr [rcx+1Ch], 4
0x18000d71d  jz      short loc_18000D75B
0x18000d71f  lea     rax, [rbp+1C0h+String2]
0x18000d723  cmp     [rbp+1C0h+var_1F8], 8
0x18000d728  cmovnb  rax, [rbp+1C0h+String2]
0x18000d72d  cmp     qword ptr [r14+18h], 8
0x18000d732  jb      short loc_18000D739
0x18000d734  mov     r9, [r14]
0x18000d737  jmp     short loc_18000D73C
0x18000d739  mov     r9, r14
0x18000d73c  mov     edx, 0B6h
0x18000d741  mov     dword ptr [rsp+2C0h+var_298], r15d
0x18000d746  mov     [rsp+2C0h+var_2A0], rax
0x18000d74b  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000d752  mov     rcx, [rcx+10h]
0x18000d756  call    WPP_SF_SSD
0x18000d75b  mov     [r14+68h], r15d
0x18000d75f  mov     rdx, r14; struct _SwJob *
0x18000d762  call    ?GetErrorMessage@JobHelper@@AEAAXAEAU_SwJob@@@Z; JobHelper::GetErrorMessage(_SwJob &)
0x18000d767  lea     rax, [rsp+2C0h+var_280]
0x18000d76c  mov     [rsp+2C0h+var_290], rax
0x18000d771  lea     rdx, [r14+70h]
0x18000d775  lea     rcx, [rsp+2C0h+var_280]
0x18000d77a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d77f  mov     rbx, rax
0x18000d782  mov     rdx, r14
0x18000d785  lea     rcx, [rsp+2C0h+var_260]
0x18000d78a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d78f  nop
0x18000d790  mov     [rsp+2C0h+var_298], rbx
0x18000d795  mov     dword ptr [rsp+2C0h+var_2A0], r15d
0x18000d79a  mov     r9d, 64h ; 'd'
0x18000d7a0  lea     r8d, [r9+0Ah]
0x18000d7a4  mov     rdx, rax
0x18000d7a7  mov     rcx, r13
0x18000d7aa  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
  ... truncated ...
```
