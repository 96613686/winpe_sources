# JobHelper::GetDependency(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_FrameworkDependency &)

- ea: `0x18000e524`
- end: `0x18000e977`
- name: `?GetDependency@JobHelper@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU_FrameworkDependency@@@Z`
- size: `1107`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ea88`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x1800065f8`
- `0x18000702c`
- `0x1800070e4`
- `0x180008b90`
- `0x180008cec`
- `0x180009134`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000bae8`
- `0x18000e524`
- `0x18000f7d4`
- `0x18000fdf8`
- `0x180012fb0`
- `0x18001f3da`
- `0x18001f420`
- `0x18001f4e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e6a7`
- `KERNEL32!EnterCriticalSection` at `0x18000e6a7`
- `KERNEL32!LeaveCriticalSection` at `0x18000e911`
- `KERNEL32!LeaveCriticalSection` at `0x18000e911`

## string_xrefs

- `0x18000e8b0`: `BITSId`
- `0x18000e8ef`: `BITSId`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JobHelper::GetDependency(__int64 a1, const unsigned __int16 **a2, __int64 *a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  int JobDependencyRegPath; // eax
  unsigned int v11; // ebx
  LPCWSTR v12; // rcx
  const unsigned __int16 *v13; // r9
  int v14; // edx
  const WCHAR *v15; // rsi
  LSTATUS Key; // eax
  __int64 v17; // r8
  int v18; // r8d
  int v19; // edx
  __int64 v20; // rax
  const unsigned __int16 *v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  unsigned int *v26; // [rsp+28h] [rbp-D8h]
  unsigned int *v27; // [rsp+28h] [rbp-D8h]
  unsigned int *v28; // [rsp+28h] [rbp-D8h]
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h]
  _BYTE *v33; // [rsp+50h] [rbp-B0h]
  _BYTE v34[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[32]; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 **v36; // [rsp+A0h] [rbp-60h]
  __int64 *v37; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE v39[4096]; // [rsp+D0h] [rbp-30h] BYREF

  v32 = a1;
  v36 = a2;
  v37 = a3;
  std::wstring::wstring(lpSubKey, &dword_180022F6C);
  memset_0(v39, 0, sizeof(v39));
  *(_DWORD *)Data = 0;
  phkResult = 0;
  hKey = 0;
  v33 = v34;
  v8 = std::wstring::wstring(v34, a3);
  v9 = std::wstring::wstring(v35, a2);
  JobDependencyRegPath = JobHelper::GetJobDependencyRegPath(v9, v8, lpSubKey);
  v11 = JobDependencyRegPath;
  if ( JobDependencyRegPath >= 0 )
  {
    v15 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] >= (LPCWSTR)8 )
      v15 = lpSubKey[0];
    std::wstring::operator=(a4, a3);
    Key = CurrentUserRegKeyHelper::GetKey(&phkResult, &hKey);
    v11 = Key;
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)Key);
      goto LABEL_49;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
    JobDependencyRegPath = ReadRegMultiSZValue(hKey, v15, v17, a4 + 32);
    v11 = JobDependencyRegPath;
    if ( JobDependencyRegPath >= 0 )
    {
      JobDependencyRegPath = ReadRegDWORDValue(Data, hKey, v15, L"Status");
      v11 = JobDependencyRegPath;
      if ( JobDependencyRegPath >= 0 )
      {
        v19 = *(_DWORD *)Data;
        *(_DWORD *)(a4 + 160) = *(_DWORD *)Data;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( (unsigned __int64)a3[3] < 8 )
            v20 = (__int64)a3;
          else
            v20 = *a3;
          if ( (unsigned __int64)a2[3] < 8 )
            LODWORD(v21) = (_DWORD)a2;
          else
            v21 = *a2;
          WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v18, (_DWORD)v21, v20, v19);
        }
        JobDependencyRegPath = ReadRegSZValue(v39, 2048, hKey, v15, L"ContentLocation", v26);
        v11 = JobDependencyRegPath;
        if ( JobDependencyRegPath >= 0 )
        {
          std::wstring::assign(a4 + 48, v39);
          JobDependencyRegPath = ReadRegDWORDValue(Data, hKey, v15, L"CurrentDPIndex");
          v11 = JobDependencyRegPath;
          if ( JobDependencyRegPath >= 0 )
          {
            *(_DWORD *)(a4 + 120) = *(_DWORD *)Data;
            JobDependencyRegPath = ReadRegSZValue(v39, 2048, hKey, v15, L"CurrentDPUrl", v27);
            v11 = JobDependencyRegPath;
            if ( JobDependencyRegPath >= 0 )
            {
              std::wstring::assign(a4 + 128, v39);
              JobDependencyRegPath = ReadRegSZValue(v39, 2048, hKey, v15, L"BITSId", v28);
              v11 = JobDependencyRegPath;
              if ( JobDependencyRegPath >= 0 )
              {
                std::wstring::assign(a4 + 88, v39);
                goto LABEL_49;
              }
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
                goto LABEL_49;
              v14 = 74;
              v13 = L"BITSId";
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
                goto LABEL_49;
              v14 = 73;
              v13 = L"CurrentDPUrl";
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
              goto LABEL_49;
            v14 = 72;
            v13 = L"CurrentDPIndex";
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_49;
          v14 = 71;
          v13 = L"ContentLocation";
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_49;
        v14 = 69;
        v13 = L"Status";
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_49;
      v14 = 68;
      v13 = L"UrlList";
    }
LABEL_8:
    WPP_SF_Sd(
      *((_QWORD *)v12 + 2),
      v14,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v13,
      JobDependencyRegPath);
    goto LABEL_49;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    if ( (unsigned __int64)a2[3] < 8 )
      LODWORD(v13) = (_DWORD)a2;
    else
      v13 = *a2;
    v14 = 66;
    goto LABEL_8;
  }
LABEL_49:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 128));
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)&phkResult);
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(lpSubKey, v22, 0);
  LOBYTE(v23) = 1;
  std::wstring::_Tidy(a2, v23, 0);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(a3, v24, 0);
  return v11;
}

```

## disassembly

```asm
0x18000e524  push    rbp
0x18000e526  push    rbx
0x18000e527  push    rsi
0x18000e528  push    rdi
0x18000e529  push    r12
0x18000e52b  push    r13
0x18000e52d  push    r14
0x18000e52f  lea     rbp, [rsp-0FE0h]
0x18000e537  mov     eax, 10E0h
0x18000e53c  call    _alloca_probe
0x18000e541  sub     rsp, rax
0x18000e544  mov     rax, cs:__security_cookie
0x18000e54b  xor     rax, rsp
0x18000e54e  mov     [rbp+1010h+var_40], rax
0x18000e555  mov     r13, r9
0x18000e558  mov     r12, r8
0x18000e55b  mov     r14, rdx
0x18000e55e  mov     rdi, rcx
0x18000e561  mov     [rsp+1110h+var_10C8], rcx
0x18000e566  mov     [rbp+1010h+var_1070], rdx
0x18000e56a  mov     [rbp+1010h+var_1068], r8
0x18000e56e  lea     rdx, dword_180022F6C
0x18000e575  lea     rcx, [rbp+1010h+lpSubKey]
0x18000e579  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e57e  nop
0x18000e57f  xor     edx, edx; Val
0x18000e581  mov     r8d, 1000h; Size
0x18000e587  lea     rcx, [rbp+1010h+var_1040]; void *
0x18000e58b  call    memset_0
0x18000e590  mov     dword ptr [rsp+1110h+Data], 0
0x18000e598  mov     [rsp+1110h+phkResult], 0
0x18000e5a1  mov     [rsp+1110h+hKey], 0
0x18000e5aa  lea     rax, [rsp+1110h+var_10B0]
0x18000e5af  mov     [rsp+1110h+var_10C0], rax
0x18000e5b4  mov     rdx, r12
0x18000e5b7  lea     rcx, [rsp+1110h+var_10B0]
0x18000e5bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e5c1  mov     rbx, rax
0x18000e5c4  mov     rdx, r14
0x18000e5c7  lea     rcx, [rbp+1010h+var_1090]
0x18000e5cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e5d0  nop
0x18000e5d1  lea     r8, [rbp+1010h+lpSubKey]
0x18000e5d5  mov     rdx, rbx
0x18000e5d8  mov     rcx, rax
0x18000e5db  call    ?GetJobDependencyRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobDependencyRegPath(std::wstring,std::wstring,std::wstring &)
0x18000e5e0  mov     ebx, eax
0x18000e5e2  test    eax, eax
0x18000e5e4  jns     short loc_18000E634
0x18000e5e6  lea     rdi, WPP_GLOBAL_Control
0x18000e5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5f4  cmp     rcx, rdi
0x18000e5f7  jz      loc_18000E908
0x18000e5fd  test    byte ptr [rcx+1Ch], 4
0x18000e601  jz      loc_18000E908
0x18000e607  cmp     qword ptr [r14+18h], 8
0x18000e60c  jb      short loc_18000E613
0x18000e60e  mov     r9, [r14]
0x18000e611  jmp     short loc_18000E616
0x18000e613  mov     r9, r14
0x18000e616  mov     edx, 42h ; 'B'
0x18000e61b  mov     dword ptr [rsp+1110h+var_10F0], eax
0x18000e61f  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000e626  mov     rcx, [rcx+10h]
0x18000e62a  call    WPP_SF_Sd
0x18000e62f  jmp     loc_18000E908
0x18000e634  lea     rsi, [rbp+1010h+lpSubKey]
0x18000e638  cmp     [rbp+1010h+var_1048], 8
0x18000e63d  cmovnb  rsi, [rbp+1010h+lpSubKey]
0x18000e642  mov     rdx, r12
0x18000e645  mov     rcx, r13
0x18000e648  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000e64d  lea     rdx, [rsp+1110h+hKey]; HKEY *
0x18000e652  lea     rcx, [rsp+1110h+phkResult]; phkResult
0x18000e657  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x18000e65c  mov     ebx, eax
0x18000e65e  test    eax, eax
0x18000e660  jns     short loc_18000E6A0
0x18000e662  lea     rdi, WPP_GLOBAL_Control
0x18000e669  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e670  cmp     rcx, rdi
0x18000e673  jz      loc_18000E908
0x18000e679  test    byte ptr [rcx+1Ch], 4
0x18000e67d  jz      loc_18000E908
0x18000e683  mov     edx, 43h ; 'C'
0x18000e688  mov     r9d, eax
0x18000e68b  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000e692  mov     rcx, [rcx+10h]
0x18000e696  call    WPP_SF_d
0x18000e69b  jmp     loc_18000E908
0x18000e6a0  lea     rcx, [rdi+80h]; lpCriticalSection
0x18000e6a7  call    cs:__imp_EnterCriticalSection
0x18000e6ae  nop     dword ptr [rax+rax+00h]
0x18000e6b3  lea     r9, [r13+20h]
0x18000e6b7  mov     rdx, rsi; lpSubKey
0x18000e6ba  mov     rcx, [rsp+1110h+hKey]; hKey
0x18000e6bf  call    ?ReadRegMultiSZValue@@YAJPEAUHKEY__@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ReadRegMultiSZValue(HKEY__ *,ushort const *,ushort const *,std::list<std::wstring> &)
0x18000e6c4  mov     ebx, eax
0x18000e6c6  test    eax, eax
0x18000e6c8  jns     short loc_18000E6FC
0x18000e6ca  lea     rdi, WPP_GLOBAL_Control
0x18000e6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d8  cmp     rcx, rdi
0x18000e6db  jz      loc_18000E908
0x18000e6e1  test    byte ptr [rcx+1Ch], 4
0x18000e6e5  jz      loc_18000E908
0x18000e6eb  mov     edx, 44h ; 'D'
0x18000e6f0  lea     r9, ValueName; "UrlList"
0x18000e6f7  jmp     loc_18000E61B
0x18000e6fc  lea     r9, aStatus; "Status"
0x18000e703  mov     r8, rsi; lpSubKey
0x18000e706  mov     rdx, [rsp+1110h+hKey]; hKey
0x18000e70b  lea     rcx, [rsp+1110h+Data]; lpData
0x18000e710  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x18000e715  mov     ebx, eax
0x18000e717  test    eax, eax
0x18000e719  jns     short loc_18000E74D
0x18000e71b  lea     rdi, WPP_GLOBAL_Control
0x18000e722  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e729  cmp     rcx, rdi
0x18000e72c  jz      loc_18000E908
0x18000e732  test    byte ptr [rcx+1Ch], 4
0x18000e736  jz      loc_18000E908
0x18000e73c  mov     edx, 45h ; 'E'
0x18000e741  lea     r9, aStatus; "Status"
0x18000e748  jmp     loc_18000E61B
0x18000e74d  mov     edx, dword ptr [rsp+1110h+Data]
0x18000e751  mov     [r13+0A0h], edx
0x18000e758  lea     rdi, WPP_GLOBAL_Control
0x18000e75f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e766  cmp     rcx, rdi
0x18000e769  jz      short loc_18000E7A3
0x18000e76b  test    byte ptr [rcx+1Ch], 1
0x18000e76f  jz      short loc_18000E7A3
0x18000e771  cmp     qword ptr [r12+18h], 8
0x18000e777  jb      short loc_18000E77F
0x18000e779  mov     rax, [r12]
0x18000e77d  jmp     short loc_18000E782
0x18000e77f  mov     rax, r12
0x18000e782  cmp     qword ptr [r14+18h], 8
0x18000e787  jb      short loc_18000E78E
0x18000e789  mov     r9, [r14]
0x18000e78c  jmp     short loc_18000E791
0x18000e78e  mov     r9, r14
0x18000e791  mov     dword ptr [rsp+1110h+var_10E8], edx; unsigned int *
0x18000e795  mov     [rsp+1110h+var_10F0], rax
0x18000e79a  mov     rcx, [rcx+10h]
0x18000e79e  call    WPP_SF_SSd
0x18000e7a3  lea     rax, aContentlocatio; "ContentLocation"
0x18000e7aa  mov     [rsp+1110h+var_10F0], rax; unsigned __int16 *
0x18000e7af  mov     r9, rsi; unsigned __int16 *
0x18000e7b2  mov     r8, [rsp+1110h+hKey]; HKEY
0x18000e7b7  mov     edx, 800h; unsigned __int64
0x18000e7bc  lea     rcx, [rbp+1010h+var_1040]; lpData
0x18000e7c0  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e7c5  mov     ebx, eax
0x18000e7c7  test    eax, eax
0x18000e7c9  jns     short loc_18000E7F6
0x18000e7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7d2  cmp     rcx, rdi
0x18000e7d5  jz      loc_18000E908
0x18000e7db  test    byte ptr [rcx+1Ch], 4
0x18000e7df  jz      loc_18000E908
0x18000e7e5  mov     edx, 47h ; 'G'
0x18000e7ea  lea     r9, aContentlocatio; "ContentLocation"
0x18000e7f1  jmp     loc_18000E61B
0x18000e7f6  lea     rcx, [r13+30h]
0x18000e7fa  lea     rdx, [rbp+1010h+var_1040]
0x18000e7fe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e803  lea     r9, aCurrentdpindex; "CurrentDPIndex"
0x18000e80a  mov     r8, rsi; lpSubKey
0x18000e80d  mov     rdx, [rsp+1110h+hKey]; hKey
0x18000e812  lea     rcx, [rsp+1110h+Data]; lpData
0x18000e817  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x18000e81c  mov     ebx, eax
0x18000e81e  test    eax, eax
0x18000e820  jns     short loc_18000E84D
0x18000e822  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e829  cmp     rcx, rdi
0x18000e82c  jz      loc_18000E908
0x18000e832  test    byte ptr [rcx+1Ch], 4
0x18000e836  jz      loc_18000E908
0x18000e83c  mov     edx, 48h ; 'H'
0x18000e841  lea     r9, aCurrentdpindex; "CurrentDPIndex"
0x18000e848  jmp     loc_18000E61B
0x18000e84d  mov     eax, dword ptr [rsp+1110h+Data]
0x18000e851  mov     [r13+78h], eax
0x18000e855  lea     rax, aCurrentdpurl; "CurrentDPUrl"
0x18000e85c  mov     [rsp+1110h+var_10F0], rax; unsigned __int16 *
0x18000e861  mov     r9, rsi; unsigned __int16 *
0x18000e864  mov     r8, [rsp+1110h+hKey]; HKEY
0x18000e869  mov     edx, 800h; unsigned __int64
0x18000e86e  lea     rcx, [rbp+1010h+var_1040]; lpData
0x18000e872  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e877  mov     ebx, eax
0x18000e879  test    eax, eax
0x18000e87b  jns     short loc_18000E8A0
0x18000e87d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e884  cmp     rcx, rdi
0x18000e887  jz      short loc_18000E908
0x18000e889  test    byte ptr [rcx+1Ch], 4
0x18000e88d  jz      short loc_18000E908
0x18000e88f  mov     edx, 49h ; 'I'
0x18000e894  lea     r9, aCurrentdpurl; "CurrentDPUrl"
0x18000e89b  jmp     loc_18000E61B
0x18000e8a0  lea     rcx, [r13+80h]
0x18000e8a7  lea     rdx, [rbp+1010h+var_1040]
0x18000e8ab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e8b0  lea     rax, aBitsid; "BITSId"
0x18000e8b7  mov     [rsp+1110h+var_10F0], rax; unsigned __int16 *
0x18000e8bc  mov     r9, rsi; unsigned __int16 *
0x18000e8bf  mov     r8, [rsp+1110h+hKey]; HKEY
0x18000e8c4  mov     edx, 800h; unsigned __int64
0x18000e8c9  lea     rcx, [rbp+1010h+var_1040]; lpData
0x18000e8cd  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e8d2  mov     ebx, eax
0x18000e8d4  test    eax, eax
0x18000e8d6  jns     short loc_18000E8FB
0x18000e8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8df  cmp     rcx, rdi
0x18000e8e2  jz      short loc_18000E908
0x18000e8e4  test    byte ptr [rcx+1Ch], 4
0x18000e8e8  jz      short loc_18000E908
0x18000e8ea  mov     edx, 4Ah ; 'J'
0x18000e8ef  lea     r9, aBitsid; "BITSId"
0x18000e8f6  jmp     loc_18000E61B
0x18000e8fb  lea     rcx, [r13+58h]
0x18000e8ff  lea     rdx, [rbp+1010h+var_1040]
0x18000e903  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000e908  mov     rcx, [rsp+1110h+var_10C8]
0x18000e90d  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18000e911  call    cs:__imp_LeaveCriticalSection
0x18000e918  nop     dword ptr [rax+rax+00h]
0x18000e91d  nop
0x18000e91e  lea     rcx, [rsp+1110h+phkResult]; this
0x18000e923  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18000e928  nop
0x18000e929  xor     r8d, r8d
0x18000e92c  mov     dl, 1
0x18000e92e  lea     rcx, [rbp+1010h+lpSubKey]
0x18000e932  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e937  nop
0x18000e938  xor     r8d, r8d
0x18000e93b  mov     dl, 1
0x18000e93d  mov     rcx, r14
0x18000e940  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e945  nop
0x18000e946  xor     r8d, r8d
0x18000e949  mov     dl, 1
0x18000e94b  mov     rcx, r12
0x18000e94e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e953  mov     eax, ebx
0x18000e955  mov     rcx, [rbp+1010h+var_40]
0x18000e95c  xor     rcx, rsp; StackCookie
0x18000e95f  call    __security_check_cookie
0x18000e964  add     rsp, 10E0h
0x18000e96b  pop     r14
0x18000e96d  pop     r13
0x18000e96f  pop     r12
0x18000e971  pop     rdi
0x18000e972  pop     rsi
0x18000e973  pop     rbx
0x18000e974  pop     rbp
0x18000e975  retn
```
