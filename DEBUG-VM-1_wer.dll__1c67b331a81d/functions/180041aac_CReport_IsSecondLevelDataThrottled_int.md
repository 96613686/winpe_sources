# CReport::IsSecondLevelDataThrottled(int)

- ea: `0x180041aac`
- end: `0x18004212a`
- name: `?IsSecondLevelDataThrottled@CReport@@QEAAHH@Z`
- size: `1662`
- prototype: `__int64 __fastcall(CReport *__hidden this, int)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147b8`
- `0x18001eb2c`

## callees

- `0x180004bb4`
- `0x180008a20`
- `0x180009590`
- `0x180009ad4`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x18001f0d8`
- `0x18001f100`
- `0x18001f274`
- `0x18001fe24`
- `0x180021634`
- `0x18002f34c`
- `0x18003cf38`
- `0x18003eda0`
- `0x180041aac`
- `0x180042130`
- `0x180050db0`
- `0x180071f04`
- `0x1800769f8`
- `0x1800aa000`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180041dc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180041dc2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180041ecb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180041ff5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180041ecb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180041ff5`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CReport::IsSecondLevelDataThrottled(CReport *this, int a2)
{
  unsigned int v4; // esi
  const wchar_t *v5; // rax
  int v6; // r8d
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // r12d
  int v12; // r13d
  int v13; // r14d
  int SignatureParamsHash; // eax
  unsigned int i; // ecx
  unsigned int v16; // r14d
  __int64 v17; // rax
  __int64 v18; // rdx
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  wchar_t *v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v25[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[4]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v27[4]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v28[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v29[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v30[5200]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v31[650]; // [rsp+1560h] [rbp+1460h] BYREF

  CReportArchive::CReportArchive((CReportArchive *)v31);
  CReportQueue::CReportQueue((CReportQueue *)v30);
  v4 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v28);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v27);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v24);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v26);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
  FileTime1 = 0;
  SystemTimeAsFileTime = 0;
  v20 = 0;
  if ( !*((_DWORD *)this + 11670) )
  {
    if ( (*((_DWORD *)this + 1654) & 0x800) != 0
      || (v11 = *((_DWORD *)this + 2277),
          v12 = *((_DWORD *)this + 2276),
          v23 = *((_DWORD *)this + 2275),
          v13 = *((_DWORD *)this + 2274),
          CRegSetting::GetDwordData((CReport *)((char *)this + 48768)) == 1)
      || CRegSetting::GetDwordData((CReport *)((char *)this + 48872)) == 1 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_84;
      v10 = 308;
      goto LABEL_82;
    }
    SignatureParamsHash = CReport::GetSignatureParamsHash(this, v29);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 309;
LABEL_20:
      v9 = (unsigned int)SignatureParamsHash;
      goto LABEL_7;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v25,
                             L"Report") )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 310;
      goto LABEL_6;
    }
    for ( i = 0; i < 6; ++i )
    {
      if ( LODWORD(qword_1800B00D0[2 * i]) == *((_DWORD *)this + 1468) )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          v25,
          qword_1800B00D0[2 * i + 1]);
        break;
      }
    }
    SignatureParamsHash = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            v28,
                            L"%s_*_%s_*_cab_*",
                            v25[0],
                            v29[0]);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 311;
      goto LABEL_20;
    }
    v16 = v11 ^ v12 ^ v23 ^ v13;
    SignatureParamsHash = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            v27,
                            L"*_*_*_%08x_cab_*",
                            v16);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 312;
      goto LABEL_20;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v17 = *(_QWORD *)&SystemTimeAsFileTime - 864000000000LL;
    SystemTimeAsFileTime.dwLowDateTime -= 711573504;
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v17);
    UtilIsCurrentProcessInteractive();
    SignatureParamsHash = CReportArchive::InitMachineStore((CReportArchive *)v31);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 313;
      goto LABEL_20;
    }
    if ( (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v31, v28[0]) < 0 )
    {
      if ( a2
        && v16
        && (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v31, v27[0]) >= 0
        && CReportStore::GetReportCreationDate((CReportStore *)v31, v24[0], &FileTime1) >= 0
        && CompareFileTime(&FileTime1, &SystemTimeAsFileTime) > 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_47;
        v18 = 315;
      }
      else
      {
        SignatureParamsHash = CReportQueue::InitMachineStore((CReportQueue *)v30);
        if ( SignatureParamsHash < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
            goto LABEL_87;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_84;
          v8 = 316;
          goto LABEL_20;
        }
        if ( (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v30, v28[0]) >= 0
          && (int)CReportStore::HasReportFile((CReportStore *)v30, v24[0], &v20) >= 0
          && v20 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_47;
          v18 = 317;
        }
        else
        {
          if ( !a2
            || !v16
            || (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v30, v27[0]) < 0
            || (int)CReportStore::HasReportFile((CReportStore *)v30, v24[0], &v20) < 0
            || !v20
            || CReportStore::GetReportCreationDate((CReportStore *)v30, v24[0], &FileTime1) < 0
            || CompareFileTime(&FileTime1, &SystemTimeAsFileTime) <= 0 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
              goto LABEL_87;
            if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
              goto LABEL_84;
            v10 = 319;
            goto LABEL_82;
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          {
LABEL_47:
            v4 = 1;
            goto LABEL_84;
          }
          v18 = 318;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_47;
      v18 = 314;
    }
    WPP_SF_(*((_QWORD *)v7 + 2), v18, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
    v7 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v5 = UtilPathTail(*((const wchar_t **)this + 5802));
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v26, v5) )
  {
    if ( utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(
           v26[0],
           (__int64)(v26[1] - v26[0]) >> 1,
           v6,
           (unsigned int)L"_cab_",
           5) != -1 )
    {
      v4 = 0;
      goto LABEL_83;
    }
    v4 = 1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
      goto LABEL_87;
    if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_84;
    v10 = 307;
LABEL_82:
    WPP_SF_(*((_QWORD *)v7 + 2), v10, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
    goto LABEL_83;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
    goto LABEL_87;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 306;
LABEL_6:
    v9 = 2147942414LL;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v9);
LABEL_83:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_84:
  if ( v7 != (wchar_t *)&WPP_GLOBAL_Control && (v7[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v7 + 2), 320, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v4);
LABEL_87:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v25);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v26);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v24);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v27);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v28);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
  CReportStore::~CReportStore((CReportStore *)v30);
  v31[0] = &CReportArchive::`vftable';
  CReportStore::~CReportStore((CReportStore *)v31);
  return v4;
}

```

## disassembly

```asm
0x180041aac  push    rbp
0x180041aae  push    rbx
0x180041aaf  push    rsi
0x180041ab0  push    rdi
0x180041ab1  push    r12
0x180041ab3  push    r13
0x180041ab5  push    r14
0x180041ab7  push    r15
0x180041ab9  lea     rbp, [rsp-28C8h]
0x180041ac1  mov     eax, 29C8h
0x180041ac6  call    _alloca_probe
0x180041acb  sub     rsp, rax
0x180041ace  mov     rax, cs:__security_cookie
0x180041ad5  xor     rax, rsp
0x180041ad8  mov     [rbp+2900h+var_50], rax
0x180041adf  mov     r15d, edx
0x180041ae2  mov     rdi, rcx
0x180041ae5  lea     rcx, [rbp+2900h+var_14A0]; this
0x180041aec  call    ??0CReportArchive@@QEAA@XZ; CReportArchive::CReportArchive(void)
0x180041af1  nop
0x180041af2  lea     rcx, [rbp+2900h+var_28F0]; this
0x180041af6  call    ??0CReportQueue@@QEAA@XZ; CReportQueue::CReportQueue(void)
0x180041afb  nop
0x180041afc  xor     ebx, ebx
0x180041afe  mov     esi, ebx
0x180041b00  lea     rcx, [rbp+2900h+var_2910]; void *
0x180041b04  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180041b09  nop
0x180041b0a  lea     rcx, [rbp+2900h+var_2930]; void *
0x180041b0e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180041b13  nop
0x180041b14  lea     rcx, [rbp+2900h+var_2950]; void *
0x180041b18  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180041b1d  nop
0x180041b1e  lea     rcx, [rsp+2A00h+var_29B0]; void *
0x180041b23  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180041b28  nop
0x180041b29  lea     rcx, [rbp+2900h+var_2970]; void *
0x180041b2d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180041b32  nop
0x180041b33  lea     rcx, [rsp+2A00h+var_2990]; void *
0x180041b38  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180041b3d  nop
0x180041b3e  mov     qword ptr [rsp+2A00h+FileTime1.dwLowDateTime], rbx
0x180041b43  mov     qword ptr [rsp+2A00h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180041b48  mov     [rsp+2A00h+var_29D0], ebx
0x180041b4c  cmp     [rdi+0B658h], ebx
0x180041b52  jz      loc_180041C20
0x180041b58  mov     rcx, [rdi+0B550h]; wchar_t *
0x180041b5f  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x180041b64  mov     rdx, rax
0x180041b67  lea     rcx, [rbp+2900h+var_2970]
0x180041b6b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180041b70  test    al, al
0x180041b72  jnz     short loc_180041BB9
0x180041b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b7b  lea     rdi, WPP_GLOBAL_Control
0x180041b82  cmp     rcx, rdi
0x180041b85  jz      loc_1800420A3
0x180041b8b  mov     ebx, 1
0x180041b90  test    [rcx+1Ch], bl
0x180041b93  jz      loc_18004207F
0x180041b99  mov     edx, 132h
0x180041b9e  mov     r9d, 8007000Eh
0x180041ba4  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180041bab  mov     rcx, [rcx+10h]
0x180041baf  call    WPP_SF_d
0x180041bb4  jmp     loc_180042078
0x180041bb9  mov     rcx, [rbp+2900h+var_2970]
0x180041bbd  mov     rdx, [rbp+2900h+var_2968]
0x180041bc1  sub     rdx, rcx
0x180041bc4  sar     rdx, 1
0x180041bc7  mov     [rsp+2A00h+var_29E0], 5
0x180041bd0  lea     r9, aCab; "_cab_"
0x180041bd7  call    ?find@?$_StringTraits@U?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@SA_KPEB_W_K101@Z; utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180041bdc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180041be0  jz      short loc_180041BF0
0x180041be2  mov     esi, ebx
0x180041be4  lea     rdi, WPP_GLOBAL_Control
0x180041beb  jmp     loc_180042078
0x180041bf0  mov     esi, 1
0x180041bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041bfc  lea     rdi, WPP_GLOBAL_Control
0x180041c03  cmp     rcx, rdi
0x180041c06  jz      loc_1800420A3
0x180041c0c  test    byte ptr [rcx+1Ch], 4
0x180041c10  jz      loc_18004207F
0x180041c16  mov     edx, 133h
0x180041c1b  jmp     loc_180042068
0x180041c20  test    dword ptr [rdi+19D8h], 800h
0x180041c2a  jnz     loc_18004204A
0x180041c30  mov     r12d, [rdi+2394h]
0x180041c37  mov     r13d, [rdi+2390h]
0x180041c3e  mov     eax, [rdi+238Ch]
0x180041c44  mov     [rsp+2A00h+var_29B8], eax
0x180041c48  mov     r14d, [rdi+2388h]
0x180041c4f  lea     rcx, [rdi+0BE80h]; this
0x180041c56  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180041c5b  mov     ebx, 1
0x180041c60  cmp     eax, ebx
0x180041c62  jz      loc_18004204A
0x180041c68  lea     rcx, [rdi+0BEE8h]; this
0x180041c6f  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180041c74  cmp     eax, ebx
0x180041c76  jz      loc_18004204A
0x180041c7c  lea     rdx, [rbp+2900h+var_2910]
0x180041c80  mov     rcx, rdi
0x180041c83  call    ?GetSignatureParamsHash@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetSignatureParamsHash(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180041c88  test    eax, eax
0x180041c8a  jns     short loc_180041CB9
0x180041c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c93  lea     rdi, WPP_GLOBAL_Control
0x180041c9a  cmp     rcx, rdi
0x180041c9d  jz      loc_1800420A3
0x180041ca3  test    [rcx+1Ch], bl
0x180041ca6  jz      loc_18004207F
0x180041cac  mov     edx, 135h
0x180041cb1  mov     r9d, eax
0x180041cb4  jmp     loc_180041BA4
0x180041cb9  lea     rdx, aReport; "Report"
0x180041cc0  lea     rcx, [rsp+2A00h+var_2990]
0x180041cc5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180041cca  test    al, al
0x180041ccc  jnz     short loc_180041CF8
0x180041cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180041cd5  lea     rdi, WPP_GLOBAL_Control
0x180041cdc  cmp     rcx, rdi
0x180041cdf  jz      loc_1800420A3
0x180041ce5  test    [rcx+1Ch], bl
0x180041ce8  jz      loc_18004207F
0x180041cee  mov     edx, 136h
0x180041cf3  jmp     loc_180041B9E
0x180041cf8  xor     ecx, ecx
0x180041cfa  lea     r8, qword_1800B00D0
0x180041d01  cmp     ecx, 6
0x180041d04  jnb     short loc_180041D2A
0x180041d06  mov     edx, ecx
0x180041d08  add     rdx, rdx
0x180041d0b  mov     eax, [rdi+16F0h]
0x180041d11  cmp     [r8+rdx*8], eax
0x180041d15  jz      short loc_180041D1B
0x180041d17  add     ecx, ebx
0x180041d19  jmp     short loc_180041D01
0x180041d1b  mov     rdx, [r8+rdx*8+8]
0x180041d20  lea     rcx, [rsp+2A00h+var_2990]
0x180041d25  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180041d2a  mov     r9, [rbp+2900h+var_2910]
0x180041d2e  mov     r8, [rsp+2A00h+var_2990]
0x180041d33  lea     rdx, aSSCab; "%s_*_%s_*_cab_*"
0x180041d3a  lea     rcx, [rbp+2900h+var_2930]
0x180041d3e  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180041d43  test    eax, eax
0x180041d45  jns     short loc_180041D71
0x180041d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d4e  lea     rdi, WPP_GLOBAL_Control
0x180041d55  cmp     rcx, rdi
0x180041d58  jz      loc_1800420A3
0x180041d5e  test    [rcx+1Ch], bl
0x180041d61  jz      loc_18004207F
0x180041d67  mov     edx, 137h
0x180041d6c  jmp     loc_180041CB1
0x180041d71  xor     r14d, [rsp+2A00h+var_29B8]
0x180041d76  xor     r14d, r13d
0x180041d79  xor     r14d, r12d
0x180041d7c  mov     r8d, r14d
0x180041d7f  lea     rdx, a08xCab; "*_*_*_%08x_cab_*"
0x180041d86  lea     rcx, [rbp+2900h+var_2950]
0x180041d8a  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180041d8f  test    eax, eax
0x180041d91  jns     short loc_180041DBD
0x180041d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d9a  lea     rdi, WPP_GLOBAL_Control
0x180041da1  cmp     rcx, rdi
0x180041da4  jz      loc_1800420A3
0x180041daa  test    [rcx+1Ch], bl
0x180041dad  jz      loc_18004207F
0x180041db3  mov     edx, 138h
0x180041db8  jmp     loc_180041CB1
0x180041dbd  lea     rcx, [rsp+2A00h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180041dc2  call    cs:__imp_GetSystemTimeAsFileTime
0x180041dc8  mov     ecx, [rsp+2A00h+SystemTimeAsFileTime.dwHighDateTime]
0x180041dcc  shl     rcx, 20h
0x180041dd0  mov     eax, [rsp+2A00h+SystemTimeAsFileTime.dwLowDateTime]
0x180041dd4  or      rcx, rax
0x180041dd7  mov     rax, 0FFFFFF36D5964000h
0x180041de1  add     rax, rcx
0x180041de4  mov     [rsp+2A00h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180041de8  shr     rax, 20h
0x180041dec  mov     [rsp+2A00h+SystemTimeAsFileTime.dwHighDateTime], eax
0x180041df0  call    ?UtilIsCurrentProcessInteractive@@YAHXZ; UtilIsCurrentProcessInteractive(void)
0x180041df5  lea     rcx, [rbp+2900h+var_14A0]; this
0x180041dfc  call    ?InitMachineStore@CReportArchive@@UEAAJXZ; CReportArchive::InitMachineStore(void)
0x180041e01  test    eax, eax
0x180041e03  jns     short loc_180041E2F
0x180041e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e0c  lea     rdi, WPP_GLOBAL_Control
0x180041e13  cmp     rcx, rdi
0x180041e16  jz      loc_1800420A3
0x180041e1c  test    [rcx+1Ch], bl
0x180041e1f  jz      loc_18004207F
0x180041e25  mov     edx, 139h
0x180041e2a  jmp     loc_180041CB1
0x180041e2f  lea     r8, [rsp+2A00h+var_29B0]
0x180041e34  mov     rdx, [rbp+2900h+var_2930]; wchar_t *
0x180041e38  lea     rcx, [rbp+2900h+var_14A0]; this
0x180041e3f  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180041e44  test    eax, eax
0x180041e46  js      short loc_180041E84
0x180041e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e4f  lea     rdi, WPP_GLOBAL_Control
0x180041e56  cmp     rcx, rdi
0x180041e59  jz      short loc_180041E7D
0x180041e5b  test    byte ptr [rcx+1Ch], 4
0x180041e5f  jz      short loc_180041E7D
0x180041e61  mov     edx, 13Ah
0x180041e66  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180041e6d  mov     rcx, [rcx+10h]
0x180041e71  call    WPP_SF_
0x180041e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e7d  mov     esi, ebx
0x180041e7f  jmp     loc_18004207F
0x180041e84  test    r15d, r15d
0x180041e87  jz      short loc_180041EF8
0x180041e89  test    r14d, r14d
0x180041e8c  jz      short loc_180041EF8
0x180041e8e  lea     r8, [rsp+2A00h+var_29B0]
0x180041e93  mov     rdx, [rbp+2900h+var_2950]; wchar_t *
0x180041e97  lea     rcx, [rbp+2900h+var_14A0]; this
0x180041e9e  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180041ea3  test    eax, eax
0x180041ea5  js      short loc_180041EF8
0x180041ea7  lea     r8, [rsp+2A00h+FileTime1]; struct _FILETIME *
0x180041eac  mov     rdx, [rsp+2A00h+var_29B0]; wchar_t *
0x180041eb1  lea     rcx, [rbp+2900h+var_14A0]; this
0x180041eb8  call    ?GetReportCreationDate@CReportStore@@QEAAJPEB_WPEAU_FILETIME@@@Z; CReportStore::GetReportCreationDate(wchar_t const *,_FILETIME *)
0x180041ebd  test    eax, eax
0x180041ebf  js      short loc_180041EF8
0x180041ec1  lea     rdx, [rsp+2A00h+SystemTimeAsFileTime]; lpFileTime2
0x180041ec6  lea     rcx, [rsp+2A00h+FileTime1]; lpFileTime1
0x180041ecb  call    cs:__imp_CompareFileTime
0x180041ed1  test    eax, eax
0x180041ed3  jle     short loc_180041EF8
0x180041ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041edc  lea     rdi, WPP_GLOBAL_Control
0x180041ee3  cmp     rcx, rdi
0x180041ee6  jz      short loc_180041E7D
0x180041ee8  test    byte ptr [rcx+1Ch], 4
0x180041eec  jz      short loc_180041E7D
0x180041eee  mov     edx, 13Bh
0x180041ef3  jmp     loc_180041E66
0x180041ef8  lea     rcx, [rbp+2900h+var_28F0]; this
0x180041efc  call    ?InitMachineStore@CReportQueue@@UEAAJXZ; CReportQueue::InitMachineStore(void)
0x180041f01  test    eax, eax
0x180041f03  jns     short loc_180041F2F
0x180041f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f0c  lea     rdi, WPP_GLOBAL_Control
0x180041f13  cmp     rcx, rdi
0x180041f16  jz      loc_1800420A3
0x180041f1c  test    [rcx+1Ch], bl
0x180041f1f  jz      loc_18004207F
0x180041f25  mov     edx, 13Ch
0x180041f2a  jmp     loc_180041CB1
0x180041f2f  lea     r8, [rsp+2A00h+var_29B0]
0x180041f34  mov     rdx, [rbp+2900h+var_2930]; wchar_t *
0x180041f38  lea     rcx, [rbp+2900h+var_28F0]; this
0x180041f3c  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180041f41  test    eax, eax
0x180041f43  js      short loc_180041F8E
0x180041f45  lea     r8, [rsp+2A00h+var_29D0]; int *
0x180041f4a  mov     rdx, [rsp+2A00h+var_29B0]; wchar_t *
0x180041f4f  lea     rcx, [rbp+2900h+var_28F0]; this
0x180041f53  call    ?HasReportFile@CReportStore@@QEAAJPEB_WPEAH@Z; CReportStore::HasReportFile(wchar_t const *,int *)
0x180041f58  test    eax, eax
0x180041f5a  js      short loc_180041F8E
0x180041f5c  cmp     [rsp+2A00h+var_29D0], 0
0x180041f61  jz      short loc_180041F8E
0x180041f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f6a  lea     rdi, WPP_GLOBAL_Control
0x180041f71  cmp     rcx, rdi
0x180041f74  jz      loc_180041E7D
0x180041f7a  test    byte ptr [rcx+1Ch], 4
0x180041f7e  jz      loc_180041E7D
0x180041f84  mov     edx, 13Dh
0x180041f89  jmp     loc_180041E66
0x180041f8e  test    r15d, r15d
0x180041f91  jz      loc_18004202A
0x180041f97  test    r14d, r14d
0x180041f9a  jz      loc_18004202A
0x180041fa0  lea     r8, [rsp+2A00h+var_29B0]
0x180041fa5  mov     rdx, [rbp+2900h+var_2950]; wchar_t *
0x180041fa9  lea     rcx, [rbp+2900h+var_28F0]; this
0x180041fad  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180041fb2  test    eax, eax
0x180041fb4  js      short loc_18004202A
0x180041fb6  lea     r8, [rsp+2A00h+var_29D0]; int *
0x180041fbb  mov     rdx, [rsp+2A00h+var_29B0]; wchar_t *
0x180041fc0  lea     rcx, [rbp+2900h+var_28F0]; this
0x180041fc4  call    ?HasReportFile@CReportStore@@QEAAJPEB_WPEAH@Z; CReportStore::HasReportFile(wchar_t const *,int *)
0x180041fc9  test    eax, eax
0x180041fcb  js      short loc_18004202A
  ... truncated ...
```
