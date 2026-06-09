# ShieldProvider::PurgeOldFiles(bool,ushort const *,ushort const *,ulong,void *,ushort const *)

- ea: `0x140006714`
- end: `0x140006b58`
- name: `?PurgeOldFiles@ShieldProvider@@YAJ_NPEBG1KPEAX1@Z`
- size: `1092`
- prototype: `__int64 __fastcall(ShieldProvider *this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HANDLE hHandle, wchar_t *String1)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000329c`

## callees

- `0x1400015d0`
- `0x1400015f4`
- `0x140003640`
- `0x140005394`
- `0x140006714`
- `0x140007018`
- `0x140007098`
- `0x1400071c0`
- `0x14000f3ac`
- `0x140011234`
- `0x140011260`
- `0x140013010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140006964`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140006964`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140006828`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140006828`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000692a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000692a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006976`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006976`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140006949`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140006949`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1400069e0`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1400069e0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400069ee`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400069ee`

## pseudocode

```c
__int64 __fastcall ShieldProvider::PurgeOldFiles(
        ShieldProvider *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HANDLE hHandle,
        wchar_t *String1)
{
  __int64 v7; // r14
  unsigned int v8; // ebx
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  LPCWSTR v14; // rbx
  int v15; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  unsigned __int64 v18; // rdx
  int LastFailure; // eax
  int v20; // r8d
  void *v21; // rdi
  unsigned int v22; // [rsp+20h] [rbp-69h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-29h] BYREF
  void *v24; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int64 v25; // [rsp+70h] [rbp-19h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-11h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+80h] [rbp-9h] BYREF
  FILETIME FileTime1; // [rsp+88h] [rbp-1h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp+7h] BYREF

  v7 = (unsigned int)a4;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, 2147942487LL);
    return v8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2);
  v24 = 0;
  v8 = CommonUtil::NewSprintfW((CommonUtil *)&v24, (unsigned __int16 **)L"%s\\%s", a2, L"SHS-*.etl");
  if ( (v8 & 0x80000000) != 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 21;
LABEL_13:
      WPP_SF_d(v11[2], v12, &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, v8);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *(_QWORD *)&SystemTimeAsFileTime - 10000000 * v7 > *(unsigned __int64 *)&SystemTimeAsFileTime )
  {
    v11 = WPP_GLOBAL_Control;
    v8 = -2147418113;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 22;
      goto LABEL_13;
    }
LABEL_14:
    if ( v24 )
      operator delete(v24, v10);
    return v8;
  }
  FileTime1 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime - 10000000 * v7);
  lpFileName = 0;
  v13 = CommonUtil::UtilEnumFiles(
          (CommonUtil *)&lpFileName,
          (struct CommonUtil::IEnumFiles **)a2,
          L"SHS-*.etl",
          (const unsigned __int16 *)1,
          v22);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
        (unsigned int)v13);
    if ( lpFileName )
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpFileName + 8LL))(lpFileName);
    goto LABEL_14;
  }
  v14 = lpFileName;
  while ( 1 )
  {
    lpFileName = 0;
    v25 = 0;
    v15 = (*(__int64 (__fastcall **)(LPCWSTR, LPCWSTR *, unsigned __int64 *))(*(_QWORD *)v14 + 32LL))(
            v14,
            &lpFileName,
            &v25);
    v17 = v15;
    if ( v15 < 0 )
      break;
    if ( !lpFileName || (v16 = v25) == 0 )
    {
      if ( v14 )
        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v14 + 8LL))(v14);
      if ( v24 )
        operator delete(v24, v16);
      return 0;
    }
    if ( hHandle )
    {
      if ( !WaitForSingleObject(hHandle, 0) )
      {
        v21 = v24;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, v24);
        if ( v14 )
          (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v14 + 8LL))(v14);
        if ( v21 )
          operator delete(v21, v18);
        return 2147500036LL;
      }
      v16 = v25;
    }
    if ( (*(_BYTE *)v16 & 0x10) == 0
      && CompareFileTime(&FileTime1, (const FILETIME *)(v16 + 20)) != -1
      && (!String1 || _wcsicmp(String1, (const wchar_t *)(v25 + 44))) )
    {
      if ( DeleteFileW(lpFileName) || (LastFailure = HrGetLastFailure(), LastFailure >= 0) )
      {
        LocalFileTime = 0;
        SystemTime = 0;
        FileTimeToLocalFileTime((const FILETIME *)(v25 + 20), &LocalFileTime);
        FileTimeToSystemTime(&LocalFileTime, &SystemTime);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SSHHHHHH(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v25 + 44,
            v20,
            (unsigned int)L"file",
            v25 + 44,
            SystemTime.wYear,
            SystemTime.wMonth,
            SystemTime.wDay,
            SystemTime.wHour,
            SystemTime.wMinute,
            SystemTime.wSecond);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
          (_DWORD)lpFileName,
          LastFailure);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
      (unsigned int)v15);
  if ( v14 )
    (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v14 + 8LL))(v14);
  if ( v24 )
    operator delete(v24, v16);
  return v17;
}

```

## disassembly

```asm
0x140006714  mov     [rsp-8+arg_0], rbx
0x140006719  mov     [rsp-8+arg_10], rsi
0x14000671e  push    rbp
0x14000671f  push    rdi
0x140006720  push    r12
0x140006722  push    r14
0x140006724  push    r15
0x140006726  lea     rbp, [rsp-27h]
0x14000672b  sub     rsp, 0B0h
0x140006732  mov     rax, cs:__security_cookie
0x140006739  xor     rax, rsp
0x14000673c  mov     [rbp+47h+var_30], rax
0x140006740  mov     r15, [rbp+47h+hHandle]
0x140006744  mov     rdi, rdx
0x140006747  mov     r12, [rbp+47h+String1]
0x14000674b  mov     r14d, r9d
0x14000674e  test    rdx, rdx
0x140006751  jnz     short loc_14000678E
0x140006753  mov     rcx, cs:WPP_GLOBAL_Control
0x14000675a  lea     rsi, WPP_GLOBAL_Control
0x140006761  mov     ebx, 80070057h
0x140006766  cmp     rcx, rsi
0x140006769  jz      short loc_140006787
0x14000676b  test    byte ptr [rcx+1Ch], 1
0x14000676f  jz      short loc_140006787
0x140006771  mov     rcx, [rcx+10h]
0x140006775  lea     edx, [rdi+13h]
0x140006778  mov     r9d, ebx
0x14000677b  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x140006782  call    WPP_SF_d
0x140006787  mov     eax, ebx
0x140006789  jmp     loc_140006B30
0x14000678e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006795  lea     rsi, WPP_GLOBAL_Control
0x14000679c  cmp     rcx, rsi
0x14000679f  jz      short loc_1400067B3
0x1400067a1  test    byte ptr [rcx+1Ch], 4
0x1400067a5  jz      short loc_1400067B3
0x1400067a7  mov     rcx, [rcx+10h]
0x1400067ab  mov     r9, rdi
0x1400067ae  call    WPP_SF_SS
0x1400067b3  lea     r9, aShsEtl; "SHS-*.etl"
0x1400067ba  mov     [rbp+47h+var_68], 0
0x1400067c2  mov     r8, rdi; unsigned __int16 *
0x1400067c5  lea     rdx, aSS; "%s\\%s"
0x1400067cc  lea     rcx, [rbp+47h+var_68]; this
0x1400067d0  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1400067d5  mov     ebx, eax
0x1400067d7  test    eax, eax
0x1400067d9  jns     short loc_14000681C
0x1400067db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067e2  cmp     rcx, rsi
0x1400067e5  jz      short loc_140006805
0x1400067e7  test    byte ptr [rcx+1Ch], 1
0x1400067eb  jz      short loc_140006805
0x1400067ed  mov     edx, 15h
0x1400067f2  mov     rcx, [rcx+10h]
0x1400067f6  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1400067fd  mov     r9d, ebx
0x140006800  call    WPP_SF_d
0x140006805  mov     rcx, [rbp+47h+var_68]; void *
0x140006809  test    rcx, rcx
0x14000680c  jz      loc_140006787
0x140006812  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006817  jmp     loc_140006787
0x14000681c  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140006820  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140006828  call    cs:__imp_GetSystemTimeAsFileTime
0x14000682e  mov     rax, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x140006832  imul    rcx, r14, 989680h
0x140006839  sub     rax, rcx
0x14000683c  cmp     rax, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x140006840  jbe     short loc_140006860
0x140006842  mov     rcx, cs:WPP_GLOBAL_Control
0x140006849  mov     ebx, 8000FFFFh
0x14000684e  cmp     rcx, rsi
0x140006851  jz      short loc_140006805
0x140006853  test    byte ptr [rcx+1Ch], 1
0x140006857  jz      short loc_140006805
0x140006859  mov     edx, 16h
0x14000685e  jmp     short loc_1400067F2
0x140006860  mov     r9d, 1; unsigned __int16 *
0x140006866  mov     qword ptr [rbp+47h+FileTime1.dwLowDateTime], rax
0x14000686a  lea     r8, aShsEtl; "SHS-*.etl"
0x140006871  mov     [rbp+47h+lpFileName], 0
0x140006879  mov     rdx, rdi; struct CommonUtil::IEnumFiles **
0x14000687c  lea     rcx, [rbp+47h+lpFileName]; this
0x140006880  call    ?UtilEnumFiles@CommonUtil@@YAJPEAPEAUIEnumFiles@1@PEBG1K@Z; CommonUtil::UtilEnumFiles(CommonUtil::IEnumFiles * *,ushort const *,ushort const *,ulong)
0x140006885  mov     ebx, eax
0x140006887  test    eax, eax
0x140006889  jns     short loc_1400068D3
0x14000688b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006892  cmp     rcx, rsi
0x140006895  jz      short loc_1400068B5
0x140006897  test    byte ptr [rcx+1Ch], 1
0x14000689b  jz      short loc_1400068B5
0x14000689d  mov     rcx, [rcx+10h]
0x1400068a1  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1400068a8  mov     edx, 17h
0x1400068ad  mov     r9d, eax
0x1400068b0  call    WPP_SF_d
0x1400068b5  mov     rcx, [rbp+47h+lpFileName]
0x1400068b9  test    rcx, rcx
0x1400068bc  jz      loc_140006805
0x1400068c2  mov     rax, [rcx]
0x1400068c5  mov     rax, [rax+8]
0x1400068c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068ce  jmp     loc_140006805
0x1400068d3  mov     rbx, [rbp+47h+lpFileName]
0x1400068d7  mov     [rbp+47h+lpFileName], 0
0x1400068df  lea     r8, [rbp+47h+var_60]
0x1400068e3  mov     [rbp+47h+var_60], 0
0x1400068eb  lea     rdx, [rbp+47h+lpFileName]
0x1400068ef  mov     rax, [rbx]
0x1400068f2  mov     rcx, rbx
0x1400068f5  mov     rax, [rax+20h]
0x1400068f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068fe  mov     edi, eax
0x140006900  test    eax, eax
0x140006902  js      loc_140006AE2
0x140006908  cmp     [rbp+47h+lpFileName], 0
0x14000690d  jz      loc_140006ABC
0x140006913  mov     rdx, [rbp+47h+var_60]
0x140006917  test    rdx, rdx
0x14000691a  jz      loc_140006ABC
0x140006920  test    r15, r15
0x140006923  jz      short loc_14000693C
0x140006925  xor     edx, edx; dwMilliseconds
0x140006927  mov     rcx, r15; hHandle
0x14000692a  call    cs:__imp_WaitForSingleObject
0x140006930  test    eax, eax
0x140006932  jz      loc_140006A66
0x140006938  mov     rdx, [rbp+47h+var_60]
0x14000693c  test    byte ptr [rdx], 10h
0x14000693f  jnz     short loc_1400068D7
0x140006941  add     rdx, 14h; lpFileTime2
0x140006945  lea     rcx, [rbp+47h+FileTime1]; lpFileTime1
0x140006949  call    cs:__imp_CompareFileTime
0x14000694f  cmp     eax, 0FFFFFFFFh
0x140006952  jz      short loc_1400068D7
0x140006954  test    r12, r12
0x140006957  jz      short loc_140006972
0x140006959  mov     rdx, [rbp+47h+var_60]
0x14000695d  mov     rcx, r12; String1
0x140006960  add     rdx, 2Ch ; ','; String2
0x140006964  call    cs:__imp__wcsicmp
0x14000696a  test    eax, eax
0x14000696c  jz      loc_1400068D7
0x140006972  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x140006976  call    cs:__imp_DeleteFileW
0x14000697c  test    eax, eax
0x14000697e  jnz     short loc_1400069C5
0x140006980  call    HrGetLastFailure
0x140006985  test    eax, eax
0x140006987  jns     short loc_1400069C5
0x140006989  mov     rcx, cs:WPP_GLOBAL_Control
0x140006990  cmp     rcx, rsi
0x140006993  jz      loc_1400068D7
0x140006999  test    byte ptr [rcx+1Ch], 1
0x14000699d  jz      loc_1400068D7
0x1400069a3  mov     r9, [rbp+47h+lpFileName]
0x1400069a7  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x1400069ae  mov     rcx, [rcx+10h]
0x1400069b2  mov     edx, 1Bh
0x1400069b7  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1400069bb  call    WPP_SF_Sd
0x1400069c0  jmp     loc_1400068D7
0x1400069c5  mov     rcx, [rbp+47h+var_60]
0x1400069c9  lea     rdx, [rbp+47h+LocalFileTime]; lpLocalFileTime
0x1400069cd  xorps   xmm0, xmm0
0x1400069d0  mov     qword ptr [rbp+47h+LocalFileTime.dwLowDateTime], 0
0x1400069d8  add     rcx, 14h; lpFileTime
0x1400069dc  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x1400069e0  call    cs:__imp_FileTimeToLocalFileTime
0x1400069e6  lea     rdx, [rbp+47h+SystemTime]; lpSystemTime
0x1400069ea  lea     rcx, [rbp+47h+LocalFileTime]; lpFileTime
0x1400069ee  call    cs:__imp_FileTimeToSystemTime
0x1400069f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069fb  cmp     rcx, rsi
0x1400069fe  jz      loc_1400068D7
0x140006a04  test    byte ptr [rcx+1Ch], 4
0x140006a08  jz      loc_1400068D7
0x140006a0e  movzx   eax, [rbp+47h+SystemTime.wSecond]
0x140006a12  lea     r9, aFile; "file"
0x140006a19  mov     rdx, [rbp+47h+var_60]
0x140006a1d  mov     rcx, [rcx+10h]
0x140006a21  add     rdx, 2Ch ; ','
0x140006a25  mov     [rsp+0D0h+var_80], ax
0x140006a2a  movzx   eax, [rbp+47h+SystemTime.wMinute]
0x140006a2e  mov     [rsp+0D0h+var_88], ax
0x140006a33  movzx   eax, [rbp+47h+SystemTime.wHour]
0x140006a37  mov     [rsp+0D0h+var_90], ax
0x140006a3c  movzx   eax, [rbp+47h+SystemTime.wDay]
0x140006a40  mov     [rsp+0D0h+var_98], ax
0x140006a45  movzx   eax, [rbp+47h+SystemTime.wMonth]
0x140006a49  mov     [rsp+0D0h+var_A0], ax
0x140006a4e  movzx   eax, [rbp+47h+SystemTime.wYear]
0x140006a52  mov     [rsp+0D0h+var_A8], ax
0x140006a57  mov     [rsp+0D0h+var_B0], rdx
0x140006a5c  call    WPP_SF_SSHHHHHH
0x140006a61  jmp     loc_1400068D7
0x140006a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a6d  mov     rdi, [rbp+47h+var_68]
0x140006a71  cmp     rcx, rsi
0x140006a74  jz      short loc_140006A94
0x140006a76  test    byte ptr [rcx+1Ch], 2
0x140006a7a  jz      short loc_140006A94
0x140006a7c  mov     rcx, [rcx+10h]
0x140006a80  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x140006a87  mov     edx, 19h
0x140006a8c  mov     r9, rdi
0x140006a8f  call    WPP_SF_S
0x140006a94  test    rbx, rbx
0x140006a97  jz      short loc_140006AA8
0x140006a99  mov     rax, [rbx]
0x140006a9c  mov     rcx, rbx
0x140006a9f  mov     rax, [rax+8]
0x140006aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006aa8  test    rdi, rdi
0x140006aab  jz      short loc_140006AB5
0x140006aad  mov     rcx, rdi; void *
0x140006ab0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006ab5  mov     eax, 80004004h
0x140006aba  jmp     short loc_140006B30
0x140006abc  test    rbx, rbx
0x140006abf  jz      short loc_140006AD0
0x140006ac1  mov     rax, [rbx]
0x140006ac4  mov     rcx, rbx
0x140006ac7  mov     rax, [rax+8]
0x140006acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ad0  mov     rcx, [rbp+47h+var_68]; void *
0x140006ad4  test    rcx, rcx
0x140006ad7  jz      short loc_140006ADE
0x140006ad9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006ade  xor     eax, eax
0x140006ae0  jmp     short loc_140006B30
0x140006ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ae9  cmp     rcx, rsi
0x140006aec  jz      short loc_140006B0C
0x140006aee  test    byte ptr [rcx+1Ch], 1
0x140006af2  jz      short loc_140006B0C
0x140006af4  mov     rcx, [rcx+10h]
0x140006af8  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x140006aff  mov     edx, 18h
0x140006b04  mov     r9d, edi
0x140006b07  call    WPP_SF_d
0x140006b0c  test    rbx, rbx
0x140006b0f  jz      short loc_140006B20
0x140006b11  mov     rax, [rbx]
0x140006b14  mov     rcx, rbx
0x140006b17  mov     rax, [rax+8]
0x140006b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b20  mov     rcx, [rbp+47h+var_68]; void *
0x140006b24  test    rcx, rcx
0x140006b27  jz      short loc_140006B2E
0x140006b29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006b2e  mov     eax, edi
0x140006b30  mov     rcx, [rbp+47h+var_30]
0x140006b34  xor     rcx, rsp; StackCookie
0x140006b37  call    __security_check_cookie
0x140006b3c  lea     r11, [rsp+0D0h+var_20]
0x140006b44  mov     rbx, [r11+30h]
0x140006b48  mov     rsi, [r11+40h]
0x140006b4c  mov     rsp, r11
0x140006b4f  pop     r15
0x140006b51  pop     r14
0x140006b53  pop     r12
0x140006b55  pop     rdi
0x140006b56  pop     rbp
0x140006b57  retn
```
