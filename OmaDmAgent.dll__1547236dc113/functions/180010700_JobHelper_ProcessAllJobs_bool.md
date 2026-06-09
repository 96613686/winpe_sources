# JobHelper::ProcessAllJobs(bool &)

- ea: `0x180010700`
- end: `0x180010ea6`
- name: `?ProcessAllJobs@JobHelper@@QEAAJAEA_N@Z`
- size: `1958`
- prototype: `__int64 __fastcall(JobHelper *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, installer_update`

## callers

- `0x180004950`

## callees

- `0x180002a50`
- `0x18000702c`
- `0x1800085d4`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a358`
- `0x18000b2e8`
- `0x18000b468`
- `0x18000b7d8`
- `0x18000b8b4`
- `0x18000ba30`
- `0x18000bb58`
- `0x18000bd00`
- `0x18000bfd4`
- `0x18000c32c`
- `0x18000d2cc`
- `0x18000dcb4`
- `0x18000ea88`
- `0x18000fa44`
- `0x1800102b8`
- `0x180010700`
- `0x180010eac`
- `0x180012338`
- `0x180014680`
- `0x180015298`
- `0x180016814`
- `0x180017b58`
- `0x18001ee24`
- `0x18001f420`

## string_xrefs

- `0x180010985`: `InstallAppLicense failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall JobHelper::ProcessAllJobs(JobHelper *this, bool *a2)
{
  const unsigned __int16 *v4; // rdx
  const unsigned __int16 *v5; // r8
  LPCWSTR v6; // rcx
  int v7; // eax
  int Jobs; // eax
  unsigned int v9; // ebx
  LPCWSTR v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // r15
  _QWORD *i; // rbx
  _QWORD *v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // r8
  const WCHAR *v19; // rax
  int v20; // eax
  int v21; // r14d
  __int64 v22; // rdi
  __int64 v23; // rax
  LPCWSTR v24; // rcx
  _QWORD *v25; // r9
  HSTRING v26; // rax
  int Package; // eax
  __int64 v28; // rdi
  _SwJob *v29; // rax
  int v30; // eax
  bool v31; // al
  HSTRING v32; // rax
  int v33; // eax
  __int64 v34; // rdi
  _SwJob *v35; // rax
  _SwJob *v36; // rax
  bool *v37; // r12
  _QWORD *j; // rbx
  _QWORD *v39; // rax
  int Job; // eax
  _SwJob *v41; // rax
  __int64 v43; // [rsp+28h] [rbp-D8h]
  bool v44; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v45; // [rsp+38h] [rbp-C8h]
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v47; // [rsp+48h] [rbp-B8h]
  _BYTE v48[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v49[2]; // [rsp+70h] [rbp-90h] BYREF
  bool *v50; // [rsp+80h] [rbp-80h]
  _BYTE v51[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v52[328]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v53[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v54; // [rsp+208h] [rbp+108h]
  _BYTE v55[32]; // [rsp+210h] [rbp+110h] BYREF
  unsigned int v56; // [rsp+230h] [rbp+130h]
  unsigned int v57; // [rsp+234h] [rbp+134h]
  unsigned int v58; // [rsp+250h] [rbp+150h]
  _BYTE v59[16]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v60; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v61[320]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v62[304]; // [rsp+470h] [rbp+370h] BYREF

  v50 = a2;
  std::list<_SwJob>::list<_SwJob>(v49);
  PackageInfo::PackageInfo((PackageInfo *)v62);
  *a2 = 0;
  v46 = 0;
  v44 = 0;
  GetRegBoolValue(&v44, v4, v5);
  if ( v44 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    v46 = 1;
    goto LABEL_11;
  }
  v7 = IsLOBEnabled(&v46);
  if ( v7 >= 0 )
    goto LABEL_10;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
    {
LABEL_11:
      if ( v6 != (LPCWSTR)&WPP_GLOBAL_Control && (v6[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)v6 + 2), 150, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
      goto LABEL_14;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      149,
      &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (unsigned int)v7);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
LABEL_14:
  JobHelper::ClearQueue(this);
  Jobs = JobHelper::GetJobs((__int64)this, (__int64)v49);
  v9 = Jobs;
  if ( Jobs < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v11 = 151;
      goto LABEL_18;
    }
    goto LABEL_107;
  }
  v12 = (_QWORD *)v49[0];
  for ( i = *(_QWORD **)v49[0]; i != v12; i = (_QWORD *)*i )
  {
    _SwJob::_SwJob((_SwJob *)v53, (const struct _SwJob *)(i + 2));
    if ( v57 != 1 || v46 )
    {
      if ( !v60 )
        goto LABEL_36;
    }
    else if ( !v60 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v14 = v53;
        if ( v54 >= 8 )
          v14 = (_QWORD *)v53[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v14);
      }
      v47 = v51;
      v15 = std::wstring::wstring(v51, &dword_180022F6C);
      v16 = std::wstring::wstring(v48, v53);
      v43 = v15;
      v17 = 0;
      v18 = 120;
      goto LABEL_58;
    }
    v19 = (const WCHAR *)std::wstring::wstring(v48, v59);
    v20 = InstallAppLicense(v19);
    v21 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)v20);
      v45 = v48;
      v22 = std::wstring::wstring(v48, L"InstallAppLicense failed");
      v23 = std::wstring::wstring(v51, v53);
      JobHelper::UpdateProgress(this, v23, 130, 0, v21, v22);
      goto LABEL_81;
    }
LABEL_36:
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v25 = v53;
        if ( v54 >= 8 )
          v25 = (_QWORD *)v53[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v25);
        v24 = WPP_GLOBAL_Control;
      }
      if ( v24 != (LPCWSTR)&WPP_GLOBAL_Control )
      {
        if ( (v24[14] & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v24 + 2), 155, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v57);
          v24 = WPP_GLOBAL_Control;
        }
        if ( v24 != (LPCWSTR)&WPP_GLOBAL_Control )
        {
          if ( (v24[14] & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v24 + 2), 156, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v56);
            v24 = WPP_GLOBAL_Control;
          }
          if ( v24 != (LPCWSTR)&WPP_GLOBAL_Control && (v24[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)v24 + 2), 157, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v58);
        }
      }
    }
    if ( ((v56 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v56 != 2 )
        goto LABEL_81;
      if ( v58 == 10 || v58 == 70 || v58 == 90 )
        goto LABEL_60;
      if ( v58 != 80 )
        goto LABEL_81;
      v26 = (HSTRING)std::wstring::wstring(v48, v55);
      Package = FindPackage(v62, v26);
      if ( Package == -1879113722 )
      {
        v45 = v48;
        v28 = std::wstring::wstring(v48, &dword_180022F6C);
        v16 = std::wstring::wstring(v51, v53);
        v43 = v28;
        v17 = 100;
        v18 = 100;
LABEL_58:
        JobHelper::UpdateProgress(this, v16, v18, v17, 0, v43);
        goto LABEL_81;
      }
      if ( Package >= 0 )
      {
LABEL_60:
        v29 = _SwJob::_SwJob((_SwJob *)v61, (const struct _SwJob *)v53);
        JobHelper::DoUnInstall(this, v29);
      }
    }
    else
    {
      switch ( v58 )
      {
        case 0xAu:
        case 0x78u:
          v36 = _SwJob::_SwJob((_SwJob *)v61, (const struct _SwJob *)v53);
          JobHelper::ProcessInstallForJob(this, v36);
          break;
        case 0x1Eu:
          break;
        case 0x14u:
          v44 = 1;
          v30 = JobHelper::CheckDownloadStatus(this, (struct _SwJob *)v53, &v44);
          if ( v30 >= 0 )
          {
            v31 = v44;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                158,
                &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
                (unsigned int)v30);
            v31 = 0;
          }
          if ( v31 )
            goto LABEL_79;
          break;
        case 0x28u:
        case 0x3Cu:
          goto LABEL_79;
        case 0x32u:
          v32 = (HSTRING)std::wstring::wstring(v48, v55);
          v33 = FindPackage(v62, v32);
          if ( v33 >= 0 )
          {
            v45 = v48;
            v34 = std::wstring::wstring(v48, &dword_180022F6C);
            v16 = std::wstring::wstring(v51, v53);
            v43 = v34;
            v17 = 100;
            v18 = 70;
            goto LABEL_58;
          }
          if ( v33 == -1879113722 )
          {
LABEL_79:
            v35 = _SwJob::_SwJob((_SwJob *)v61, (const struct _SwJob *)v53);
            JobHelper::DoInstall(this, v35);
          }
          break;
      }
    }
LABEL_81:
    _SwJob::~_SwJob((_SwJob *)v53);
  }
  Jobs = CBitsDownloader::StartDownloads(this);
  v9 = Jobs;
  v37 = v50;
  if ( Jobs >= 0 )
  {
    for ( j = (_QWORD *)*v12; j != v12; j = (_QWORD *)*j )
    {
      _SwJob::_SwJob((_SwJob *)v61, (const struct _SwJob *)(j + 2));
      _SwJob::_SwJob((_SwJob *)v53);
      v39 = (_QWORD *)std::wstring::wstring(v48, v61);
      Job = JobHelper::GetJob((__int64)this, v39, (__int64)v53);
      if ( Job >= 0 )
      {
        if ( v58 == 40 && ((v56 - 1) & 0xFFFFFFFD) == 0 )
        {
          v41 = _SwJob::_SwJob((_SwJob *)v52, (const struct _SwJob *)v53);
          JobHelper::DoInstall(this, v41);
        }
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          160,
          &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)Job);
      }
      _SwJob::~_SwJob((_SwJob *)v53);
      _SwJob::~_SwJob((_SwJob *)v61);
    }
    Jobs = CInstallService::StartDeployments((JobHelper *)((char *)this + 72));
    v9 = Jobs;
    if ( Jobs >= 0 )
    {
      Jobs = JobHelper::IsFinalNotificationNeeded(this, v49, v37);
      v9 = Jobs;
      if ( Jobs >= 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
        goto LABEL_107;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_107;
      v11 = 162;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_107;
      v11 = 161;
    }
LABEL_18:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, (unsigned int)Jobs);
    goto LABEL_107;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v11 = 159;
    goto LABEL_18;
  }
LABEL_107:
  PackageInfo::~PackageInfo((PackageInfo *)v62);
  std::list<_SwJob>::~list<_SwJob>(v49);
  return v9;
}

```

## disassembly

```asm
0x180010700  mov     [rsp-8+arg_10], rbx
0x180010705  mov     [rsp-8+arg_18], rsi
0x18001070a  push    rbp
0x18001070b  push    rdi
0x18001070c  push    r12
0x18001070e  push    r14
0x180010710  push    r15
0x180010712  lea     rbp, [rsp-4B0h]
0x18001071a  sub     rsp, 5B0h
0x180010721  mov     rax, cs:__security_cookie
0x180010728  xor     rax, rsp
0x18001072b  mov     [rbp+4D0h+var_30], rax
0x180010732  mov     r12, rdx
0x180010735  mov     [rbp+4D0h+var_550], rdx
0x180010739  mov     rsi, rcx
0x18001073c  lea     rcx, [rsp+5D0h+var_560]
0x180010741  call    ??0?$list@U_SwJob@@V?$allocator@U_SwJob@@@std@@@std@@QEAA@XZ; std::list<_SwJob>::list<_SwJob>(void)
0x180010746  nop
0x180010747  lea     rcx, [rbp+4D0h+var_160]; this
0x18001074e  call    ??0PackageInfo@@QEAA@XZ; PackageInfo::PackageInfo(void)
0x180010753  nop
0x180010754  mov     byte ptr [r12], 0
0x180010759  mov     [rsp+5D0h+var_590], 0
0x180010761  mov     [rsp+5D0h+var_5A0], 0
0x180010766  lea     rcx, [rsp+5D0h+var_5A0]; bool *
0x18001076b  call    ?GetRegBoolValue@@YAJAEA_NPEBG1@Z; GetRegBoolValue(bool &,ushort const *,ushort const *)
0x180010770  lea     r14, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180010777  lea     rdi, WPP_GLOBAL_Control
0x18001077e  cmp     [rsp+5D0h+var_5A0], 0
0x180010783  jz      short loc_1800107B9
0x180010785  mov     rcx, cs:WPP_GLOBAL_Control
0x18001078c  cmp     rcx, rdi
0x18001078f  jz      short loc_1800107AF
0x180010791  test    byte ptr [rcx+1Ch], 1
0x180010795  jz      short loc_1800107AF
0x180010797  mov     edx, 94h
0x18001079c  mov     r8, r14
0x18001079f  mov     rcx, [rcx+10h]
0x1800107a3  call    WPP_SF_
0x1800107a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107af  mov     [rsp+5D0h+var_590], 1
0x1800107b7  jmp     short loc_1800107F4
0x1800107b9  lea     rcx, [rsp+5D0h+var_590]; int *
0x1800107be  call    ?IsLOBEnabled@@YAJPEAH@Z; IsLOBEnabled(int *)
0x1800107c3  test    eax, eax
0x1800107c5  jns     short loc_1800107ED
0x1800107c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107ce  cmp     rcx, rdi
0x1800107d1  jz      short loc_180010810
0x1800107d3  test    byte ptr [rcx+1Ch], 4
0x1800107d7  jz      short loc_1800107F4
0x1800107d9  mov     edx, 95h
0x1800107de  mov     r9d, eax
0x1800107e1  mov     r8, r14
0x1800107e4  mov     rcx, [rcx+10h]
0x1800107e8  call    WPP_SF_d
0x1800107ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107f4  cmp     rcx, rdi
0x1800107f7  jz      short loc_180010810
0x1800107f9  test    byte ptr [rcx+1Ch], 1
0x1800107fd  jz      short loc_180010810
0x1800107ff  mov     edx, 96h
0x180010804  mov     r8, r14
0x180010807  mov     rcx, [rcx+10h]
0x18001080b  call    WPP_SF_
0x180010810  mov     rcx, rsi; this
0x180010813  call    ?ClearQueue@JobHelper@@AEAAXXZ; JobHelper::ClearQueue(void)
0x180010818  lea     rdx, [rsp+5D0h+var_560]
0x18001081d  mov     rcx, rsi
0x180010820  call    ?GetJobs@JobHelper@@QEAAJAEAV?$list@U_SwJob@@V?$allocator@U_SwJob@@@std@@@std@@@Z; JobHelper::GetJobs(std::list<_SwJob> &)
0x180010825  mov     ebx, eax
0x180010827  test    eax, eax
0x180010829  jns     short loc_18001085E
0x18001082b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010832  cmp     rcx, rdi
0x180010835  jz      loc_180010E61
0x18001083b  test    byte ptr [rcx+1Ch], 4
0x18001083f  jz      loc_180010E61
0x180010845  mov     edx, 97h
0x18001084a  mov     r9d, eax
0x18001084d  mov     r8, r14
0x180010850  mov     rcx, [rcx+10h]
0x180010854  call    WPP_SF_d
0x180010859  jmp     loc_180010E61
0x18001085e  mov     r15, [rsp+5D0h+var_560]
0x180010863  mov     rbx, [r15]
0x180010866  lea     r12, WPP_GLOBAL_Control
0x18001086d  cmp     rbx, r15
0x180010870  jz      loc_180010CCE
0x180010876  lea     rdx, [rbx+10h]; struct _SwJob *
0x18001087a  lea     rcx, [rbp+4D0h+var_3E0]; this
0x180010881  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x180010886  nop
0x180010887  mov     rax, [rbp+4D0h+var_330]
0x18001088e  cmp     [rbp+4D0h+var_39C], 1
0x180010895  jnz     loc_180010928
0x18001089b  cmp     [rsp+5D0h+var_590], 0
0x1800108a0  jnz     loc_180010928
0x1800108a6  test    rax, rax
0x1800108a9  jnz     loc_180010931
0x1800108af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108b6  cmp     rcx, r12
0x1800108b9  jz      short loc_1800108E9
0x1800108bb  test    byte ptr [rcx+1Ch], 2
0x1800108bf  jz      short loc_1800108E9
0x1800108c1  lea     r9, [rbp+4D0h+var_3E0]
0x1800108c8  cmp     [rbp+4D0h+var_3C8], 8
0x1800108d0  cmovnb  r9, [rbp+4D0h+var_3E0]
0x1800108d8  mov     edx, 98h
0x1800108dd  mov     r8, r14
0x1800108e0  mov     rcx, [rcx+10h]
0x1800108e4  call    WPP_SF_S
0x1800108e9  lea     rax, [rbp+4D0h+var_548]
0x1800108ed  mov     [rsp+5D0h+var_588], rax
0x1800108f2  lea     rdx, dword_180022F6C
0x1800108f9  lea     rcx, [rbp+4D0h+var_548]
0x1800108fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180010902  mov     rdi, rax
0x180010905  lea     rdx, [rbp+4D0h+var_3E0]
0x18001090c  lea     rcx, [rsp+5D0h+var_580]
0x180010911  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010916  nop
0x180010917  mov     [rsp+5D0h+var_5A8], rdi
0x18001091c  xor     r9d, r9d
0x18001091f  lea     r8d, [r9+78h]
0x180010923  jmp     loc_180010B32
0x180010928  test    rax, rax
0x18001092b  jz      loc_1800109C9
0x180010931  lea     rdx, [rbp+4D0h+var_340]
0x180010938  lea     rcx, [rsp+5D0h+var_580]
0x18001093d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010942  mov     rcx, rax; lpWideCharStr
0x180010945  call    ?InstallAppLicense@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; InstallAppLicense(std::wstring)
0x18001094a  mov     r14d, eax
0x18001094d  test    eax, eax
0x18001094f  jns     short loc_1800109C2
0x180010951  mov     rcx, cs:WPP_GLOBAL_Control
0x180010958  cmp     rcx, r12
0x18001095b  jz      short loc_18001097B
0x18001095d  test    byte ptr [rcx+1Ch], 4
0x180010961  jz      short loc_18001097B
0x180010963  mov     edx, 99h
0x180010968  mov     r9d, eax
0x18001096b  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180010972  mov     rcx, [rcx+10h]
0x180010976  call    WPP_SF_d
0x18001097b  lea     rax, [rsp+5D0h+var_580]
0x180010980  mov     [rsp+5D0h+var_598], rax
0x180010985  lea     rdx, aInstallapplice; "InstallAppLicense failed"
0x18001098c  lea     rcx, [rsp+5D0h+var_580]
0x180010991  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180010996  mov     rdi, rax
0x180010999  lea     rdx, [rbp+4D0h+var_3E0]
0x1800109a0  lea     rcx, [rbp+4D0h+var_548]
0x1800109a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800109a9  nop
0x1800109aa  mov     [rsp+5D0h+var_5A8], rdi
0x1800109af  mov     [rsp+5D0h+var_5B0], r14d
0x1800109b4  xor     r9d, r9d
0x1800109b7  mov     r8d, 82h
0x1800109bd  jmp     loc_180010B3A
0x1800109c2  lea     r14, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x1800109c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109d0  cmp     rcx, r12
0x1800109d3  jz      loc_180010A85
0x1800109d9  test    byte ptr [rcx+1Ch], 1
0x1800109dd  jz      short loc_180010A0E
0x1800109df  lea     r9, [rbp+4D0h+var_3E0]
0x1800109e6  cmp     [rbp+4D0h+var_3C8], 8
0x1800109ee  cmovnb  r9, [rbp+4D0h+var_3E0]
0x1800109f6  mov     edx, 9Ah
0x1800109fb  mov     r8, r14
0x1800109fe  mov     rcx, [rcx+10h]
0x180010a02  call    WPP_SF_S
0x180010a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a0e  cmp     rcx, r12
0x180010a11  jz      short loc_180010A85
0x180010a13  test    byte ptr [rcx+1Ch], 1
0x180010a17  jz      short loc_180010A38
0x180010a19  mov     edx, 9Bh
0x180010a1e  mov     r9d, [rbp+4D0h+var_39C]
0x180010a25  mov     r8, r14
0x180010a28  mov     rcx, [rcx+10h]
0x180010a2c  call    WPP_SF_d
0x180010a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a38  cmp     rcx, r12
0x180010a3b  jz      short loc_180010A85
0x180010a3d  test    byte ptr [rcx+1Ch], 1
0x180010a41  jz      short loc_180010A62
0x180010a43  mov     edx, 9Ch
0x180010a48  mov     r9d, [rbp+4D0h+var_3A0]
0x180010a4f  mov     r8, r14
0x180010a52  mov     rcx, [rcx+10h]
0x180010a56  call    WPP_SF_d
0x180010a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a62  cmp     rcx, r12
0x180010a65  jz      short loc_180010A85
0x180010a67  test    byte ptr [rcx+1Ch], 1
0x180010a6b  jz      short loc_180010A85
0x180010a6d  mov     edx, 9Dh
0x180010a72  mov     r9d, [rbp+4D0h+var_380]
0x180010a79  mov     r8, r14
0x180010a7c  mov     rcx, [rcx+10h]
0x180010a80  call    WPP_SF_d
0x180010a85  mov     ecx, [rbp+4D0h+var_3A0]
0x180010a8b  lea     eax, [rcx-1]
0x180010a8e  test    eax, 0FFFFFFFDh
0x180010a93  jz      loc_180010B75
0x180010a99  cmp     ecx, 2
0x180010a9c  jnz     loc_180010CB3
0x180010aa2  mov     eax, [rbp+4D0h+var_380]
0x180010aa8  cmp     eax, 0Ah
0x180010aab  jz      loc_180010B52
0x180010ab1  cmp     eax, 46h ; 'F'
0x180010ab4  jz      loc_180010B52
0x180010aba  cmp     eax, 5Ah ; 'Z'
0x180010abd  jz      loc_180010B52
0x180010ac3  cmp     eax, 50h ; 'P'
0x180010ac6  jnz     loc_180010CB3
0x180010acc  lea     rdx, [rbp+4D0h+var_3C0]
0x180010ad3  lea     rcx, [rsp+5D0h+var_580]
0x180010ad8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010add  mov     rdx, rax
0x180010ae0  lea     rcx, [rbp+4D0h+var_160]
0x180010ae7  call    ?FindPackage@@YAJAEAUPackageInfo@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FindPackage(PackageInfo &,std::wstring)
0x180010aec  cmp     eax, 8FFF0006h
0x180010af1  jnz     short loc_180010B4A
0x180010af3  lea     rax, [rsp+5D0h+var_580]
0x180010af8  mov     [rsp+5D0h+var_598], rax
0x180010afd  lea     rdx, dword_180022F6C
0x180010b04  lea     rcx, [rsp+5D0h+var_580]
0x180010b09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180010b0e  mov     rdi, rax
0x180010b11  lea     rdx, [rbp+4D0h+var_3E0]
0x180010b18  lea     rcx, [rbp+4D0h+var_548]
0x180010b1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010b21  nop
0x180010b22  mov     [rsp+5D0h+var_5A8], rdi
0x180010b27  mov     edi, 64h ; 'd'
0x180010b2c  mov     r9d, edi
0x180010b2f  mov     r8d, edi
0x180010b32  mov     [rsp+5D0h+var_5B0], 0
0x180010b3a  mov     rdx, rax
0x180010b3d  mov     rcx, rsi
0x180010b40  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x180010b45  jmp     loc_180010CB3
0x180010b4a  test    eax, eax
0x180010b4c  js      loc_180010CB3
0x180010b52  lea     rdx, [rbp+4D0h+var_3E0]; struct _SwJob *
0x180010b59  lea     rcx, [rbp+4D0h+var_2A0]; this
0x180010b60  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x180010b65  mov     rdx, rax
0x180010b68  mov     rcx, rsi
0x180010b6b  call    ?DoUnInstall@JobHelper@@AEAAJU_SwJob@@@Z; JobHelper::DoUnInstall(_SwJob)
0x180010b70  jmp     loc_180010CB3
0x180010b75  mov     eax, [rbp+4D0h+var_380]
0x180010b7b  cmp     eax, 0Ah
0x180010b7e  jz      loc_180010C94
0x180010b84  cmp     eax, 78h ; 'x'
0x180010b87  jz      loc_180010C94
0x180010b8d  cmp     eax, 1Eh
0x180010b90  jz      loc_180010CB3
0x180010b96  cmp     eax, 14h
0x180010b99  jnz     short loc_180010BF3
0x180010b9b  mov     [rsp+5D0h+var_5A0], 1
0x180010ba0  lea     r8, [rsp+5D0h+var_5A0]; bool *
0x180010ba5  lea     rdx, [rbp+4D0h+var_3E0]; struct _SwJob *
0x180010bac  mov     rcx, rsi; this
0x180010baf  call    ?CheckDownloadStatus@JobHelper@@AEAAJAEAU_SwJob@@AEA_N@Z; JobHelper::CheckDownloadStatus(_SwJob &,bool &)
0x180010bb4  test    eax, eax
0x180010bb6  jns     short loc_180010BE2
0x180010bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bbf  cmp     rcx, r12
0x180010bc2  jz      short loc_180010BDE
0x180010bc4  test    byte ptr [rcx+1Ch], 4
0x180010bc8  jz      short loc_180010BDE
0x180010bca  mov     edx, 9Eh
0x180010bcf  mov     r9d, eax
0x180010bd2  mov     r8, r14
0x180010bd5  mov     rcx, [rcx+10h]
0x180010bd9  call    WPP_SF_d
0x180010bde  xor     al, al
0x180010be0  jmp     short loc_180010BE6
0x180010be2  mov     al, [rsp+5D0h+var_5A0]
0x180010be6  test    al, al
0x180010be8  jz      loc_180010CB3
0x180010bee  jmp     loc_180010C74
0x180010bf3  cmp     eax, 28h ; '('
0x180010bf6  jz      short loc_180010C74
0x180010bf8  cmp     eax, 3Ch ; '<'
0x180010bfb  jz      short loc_180010C74
0x180010bfd  cmp     eax, 32h ; '2'
0x180010c00  jnz     loc_180010CB3
0x180010c06  lea     rdx, [rbp+4D0h+var_3C0]
0x180010c0d  lea     rcx, [rsp+5D0h+var_580]
0x180010c12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010c17  mov     rdx, rax
0x180010c1a  lea     rcx, [rbp+4D0h+var_160]
0x180010c21  call    ?FindPackage@@YAJAEAUPackageInfo@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FindPackage(PackageInfo &,std::wstring)
0x180010c26  test    eax, eax
  ... truncated ...
```
