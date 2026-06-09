# LogDeviceInstallTelemetry

- ea: `0x140016ee8`
- end: `0x14001752b`
- name: `LogDeviceInstallTelemetry`
- size: `1603`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x1400165ac`

## callees

- `0x1400070bc`
- `0x140009794`
- `0x14000bcbc`
- `0x14000c354`
- `0x140016cbc`
- `0x140016ee8`
- `0x140017534`
- `0x1400175fc`
- `0x140023b40`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016f64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400174f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400174f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400173c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400173c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017459`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400174dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400174eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017459`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400174dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400174eb`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001702e`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017088`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017146`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017234`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001728c`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017301`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001702e`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017088`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017146`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017234`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001728c`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140017301`
- `drvstore!DriverStoreFindW` at `0x1400171b3`
- `drvstore!DriverStoreFindW` at `0x1400171b3`
- `drvstore!DriverStoreOpenW` at `0x140016f56`
- `drvstore!DriverStoreOpenW` at `0x140016f56`
- `drvstore!DriverStoreClose` at `0x1400174cf`
- `drvstore!DriverStoreClose` at `0x1400174cf`

## pseudocode

```c
_BOOL8 __fastcall LogDeviceInstallTelemetry(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // r14
  DWORD LastError; // ebx
  __int64 v5; // rdi
  __int64 FileTitle; // rbx
  unsigned __int16 *v7; // rsi
  int v8; // edx
  int v9; // r9d
  unsigned int v10; // r9d
  size_t *v11; // r15
  unsigned __int16 *DriverStorePropertyLogString; // r13
  __int64 v13; // rbx
  int v14; // edx
  int v15; // r9d
  __int64 v16; // rax
  int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // r12d
  HLOCAL v24; // rbx
  const wchar_t *v25; // r8
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // r9
  __int64 v28; // rax
  HLOCAL v29; // r14
  __int64 v31; // [rsp+20h] [rbp-E0h]
  _WORD *v32; // [rsp+28h] [rbp-D8h]
  unsigned int *v33; // [rsp+38h] [rbp-C8h]
  int v34; // [rsp+40h] [rbp-C0h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-ACh] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h]
  __int64 v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h]
  __int64 v41; // [rsp+70h] [rbp-90h]
  __int128 v42; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[28]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v44[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v45[264]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v46[264]; // [rsp+320h] [rbp+220h] BYREF
  _WORD v47[264]; // [rsp+530h] [rbp+430h] BYREF
  __int16 v48[264]; // [rsp+740h] [rbp+640h] BYREF
  unsigned __int16 v49[264]; // [rsp+950h] [rbp+850h] BYREF
  _BYTE v50[528]; // [rsp+B60h] [rbp+A60h] BYREF

  v40 = a2;
  v41 = a1;
  v36 = 0;
  v3 = a2;
  v37 = 0;
  v42 = 0;
  if ( a3 )
  {
    LogFallbackDeviceInstallTelemetry();
    LastError = 0;
  }
  else
  {
    v5 = DriverStoreOpenW(0, 0, 0, 0);
    if ( v5 )
    {
      hMem = 0;
      FileTitle = 0;
      v7 = 0;
      pszDest[0] = 0;
      v46[0] = 0;
      v39 = 0;
      v48[0] = 0;
      if ( *(_WORD *)(v3 + 924)
        && (int)StringCchCopyW(v49, 0x104u, (size_t *)(v3 + 924)) >= 0
        && (unsigned int)pSetupTrimFileTitle(v49) )
      {
        FileTitle = pSetupGetFileTitle(v49);
        v39 = FileTitle;
        DriverStoreGetObjectPropertyW(v5, 2, FileTitle, DEVPKEY_DriverPackage_SubmissionId);
        v48[0] = 0;
        v34 = 0;
        v33 = &v37;
        v32 = v46;
        DriverStoreGetObjectPropertyW(v5, 2, FileTitle, DEVPKEY_DriverPackage_OriginalInfName);
        v46[0] = 0;
        hMem = (HLOCAL)GetDriverStorePropertyLogString(v5, v8, FileTitle, v9, (unsigned int)&v36);
      }
      v10 = *(_DWORD *)(v3 + 1484);
      if ( !v10 && !*(_DWORD *)(v3 + 1480)
        || (LODWORD(v32) = *(unsigned __int16 *)(v3 + 1482),
            LODWORD(v31) = *(unsigned __int16 *)(v3 + 1484),
            StringCchPrintfW(
              pszDest,
              0x18u,
              L"%u.%u.%u.%u",
              HIWORD(v10),
              v31,
              v32,
              *(unsigned __int16 *)(v3 + 1480),
              v33,
              v34) < 0) )
      {
        pszDest[0] = 0;
      }
      if ( !(unsigned int)DriverStoreGetObjectPropertyW(v5, 2, FileTitle, DEVPKEY_DriverPackage_OriginalInfName)
        || v36 != 18 )
      {
        v46[0] = 0;
      }
      v11 = *(size_t **)(v3 + 2920);
      if ( v11 )
      {
        DriverStorePropertyLogString = 0;
        if ( *(_WORD *)v11 )
        {
          do
          {
            if ( (unsigned int)DriverStoreFindW(v5, v11, 9, 0, 1, v50, 260, 0) && (unsigned int)pSetupTrimFileTitle(v50) )
              v13 = pSetupGetFileTitle(v50);
            else
              v13 = 0;
            v45[0] = 0;
            v44[0] = 0;
            if ( !v13 )
              goto LABEL_36;
            if ( !(unsigned int)DriverStoreGetObjectPropertyW(v5, 2, v13, DEVPKEY_DriverPackage_OriginalInfName)
              || v36 != 18
              || v37 < 2 )
            {
              v45[0] = 0;
            }
            if ( (unsigned int)DriverStoreGetObjectPropertyW(v5, 2, v13, DEVPKEY_DriverPackage_ExtensionId)
              && v36 == 13
              && (unsigned int)SpUtilsStringFromGuid(&v42, v44) )
            {
              v44[0] = 0;
            }
            DriverStorePropertyLogString = (unsigned __int16 *)GetDriverStorePropertyLogString(
                                                                 v5,
                                                                 v14,
                                                                 v13,
                                                                 v15,
                                                                 (unsigned int)&v36);
            if ( !(unsigned int)DriverStoreGetObjectPropertyW(v5, 2, v13, DEVPKEY_DriverPackage_SubmissionId)
              || v36 != 18
              || v37 < 2 )
            {
              v47[0] = 0;
            }
            if ( !v45[0] )
            {
LABEL_36:
              if ( (int)StringCchCopyW(v45, 0x104u, v11) < 0 )
                v45[0] = 0;
            }
            if ( v7 )
            {
              v16 = -1;
              do
                ++v16;
              while ( v7[v16] );
              v17 = v16 + 1;
            }
            else
            {
              v17 = 0;
            }
            v18 = -1;
            do
              ++v18;
            while ( v45[v18] );
            v19 = -1;
            do
              ++v19;
            while ( v44[v19] );
            v20 = -1;
            do
              ++v20;
            while ( v47[v20] );
            v21 = (unsigned int)(v18 + v17 + v20 + v19 + 4);
            if ( DriverStorePropertyLogString )
            {
              v22 = -1;
              do
                ++v22;
              while ( DriverStorePropertyLogString[v22] );
              v21 = (unsigned int)(v22 + v21);
            }
            v23 = v21;
            v24 = LocalAlloc(0x40u, 2 * v21);
            if ( v24 )
            {
              v25 = L",";
              v26 = &qword_14004E980;
              if ( DriverStorePropertyLogString )
                v26 = DriverStorePropertyLogString;
              v27 = &qword_14004E980;
              if ( v7 )
                v27 = v7;
              else
                v25 = &qword_14004E980;
              if ( StringCchPrintfW((STRSAFE_LPWSTR)v24, v23, L"%ws%ws%ws:%ws:%ws:%ws", v27, v25, v45, v44, v26, v47) < 0 )
              {
                LocalFree(v24);
              }
              else
              {
                if ( v7 )
                  LocalFree(v7);
                v7 = (unsigned __int16 *)v24;
              }
            }
            if ( DriverStorePropertyLogString )
            {
              LocalFree(DriverStorePropertyLogString);
              DriverStorePropertyLogString = 0;
            }
            v28 = -1;
            do
              ++v28;
            while ( *((_WORD *)v11 + v28) );
            v11 = (size_t *)((char *)v11 + 2 * v28 + 2);
          }
          while ( *(_WORD *)v11 );
          v3 = v40;
        }
      }
      v35 = v3;
      v29 = hMem;
      LastError = 0;
      LogFullDeviceInstallTelemetry(
        v5,
        v41,
        (unsigned int)v46,
        (unsigned int)pszDest,
        v39,
        (__int64)v48,
        (__int64)hMem,
        (__int64)v7,
        v35);
      DriverStoreClose(v5);
      if ( v29 )
        LocalFree(v29);
      if ( v7 )
        LocalFree(v7);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140016ee8  mov     [rsp-8+arg_10], rbx
0x140016eed  push    rbp
0x140016eee  push    rsi
0x140016eef  push    rdi
0x140016ef0  push    r12
0x140016ef2  push    r13
0x140016ef4  push    r14
0x140016ef6  push    r15
0x140016ef8  lea     rbp, [rsp-0C80h]
0x140016f00  sub     rsp, 0D80h
0x140016f07  mov     rax, cs:__security_cookie
0x140016f0e  xor     rax, rsp
0x140016f11  mov     [rbp+0CB0h+var_40], rax
0x140016f18  xor     r12d, r12d
0x140016f1b  mov     [rsp+0DB0h+var_D48], rdx
0x140016f20  mov     [rsp+0DB0h+var_D40], rcx
0x140016f25  xorps   xmm0, xmm0
0x140016f28  mov     [rsp+0DB0h+var_D60], r12d
0x140016f2d  mov     r14, rdx
0x140016f30  mov     [rsp+0DB0h+var_D5C], r12d
0x140016f35  movups  [rsp+0DB0h+var_D38], xmm0
0x140016f3a  test    r8d, r8d
0x140016f3d  jz      short loc_140016F4C
0x140016f3f  call    LogFallbackDeviceInstallTelemetry
0x140016f44  mov     ebx, r12d
0x140016f47  jmp     loc_1400174F1
0x140016f4c  xor     r9d, r9d
0x140016f4f  xor     r8d, r8d
0x140016f52  xor     edx, edx
0x140016f54  xor     ecx, ecx
0x140016f56  call    cs:__imp_DriverStoreOpenW
0x140016f5c  mov     rdi, rax
0x140016f5f  test    rax, rax
0x140016f62  jnz     short loc_140016F71
0x140016f64  call    cs:__imp_GetLastError
0x140016f6a  mov     ebx, eax
0x140016f6c  jmp     loc_1400174F1
0x140016f71  lea     r8, [r14+39Ch]; unsigned __int16 *
0x140016f78  mov     [rsp+0DB0h+hMem], r12
0x140016f7d  mov     rbx, r12
0x140016f80  mov     rsi, r12
0x140016f83  mov     r13d, 208h
0x140016f89  mov     [rbp+0CB0h+pszDest], r12w
0x140016f8e  mov     r15d, 2
0x140016f94  mov     [rbp+0CB0h+var_A90], r12w
0x140016f9c  mov     [rsp+0DB0h+var_D50], rbx
0x140016fa1  mov     [rbp+0CB0h+var_670], r12w
0x140016fa9  cmp     [r8], r12w
0x140016fad  jz      loc_1400170B1
0x140016fb3  mov     edx, 104h; unsigned __int64
0x140016fb8  lea     rcx, [rbp+0CB0h+var_460]; unsigned __int16 *
0x140016fbf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140016fc4  test    eax, eax
0x140016fc6  js      loc_1400170B1
0x140016fcc  lea     rcx, [rbp+0CB0h+var_460]
0x140016fd3  call    pSetupTrimFileTitle
0x140016fd8  test    eax, eax
0x140016fda  jz      loc_1400170B1
0x140016fe0  lea     rcx, [rbp+0CB0h+var_460]
0x140016fe7  call    pSetupGetFileTitle
0x140016fec  mov     rbx, rax
0x140016fef  mov     [rsp+0DB0h+var_D50], rax
0x140016ff4  mov     dword ptr [rsp+0DB0h+var_D70], r12d
0x140016ff9  lea     rax, [rsp+0DB0h+var_D5C]
0x140016ffe  mov     [rsp+0DB0h+var_D78], rax
0x140017003  lea     r9, DEVPKEY_DriverPackage_SubmissionId
0x14001700a  lea     rax, [rbp+0CB0h+var_670]
0x140017011  mov     dword ptr [rsp+0DB0h+var_D80], r13d
0x140017016  mov     [rsp+0DB0h+var_D88], rax
0x14001701b  mov     r8, rbx
0x14001701e  lea     rax, [rsp+0DB0h+var_D60]
0x140017023  mov     edx, r15d
0x140017026  mov     rcx, rdi
0x140017029  mov     [rsp+0DB0h+var_D90], rax
0x14001702e  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140017034  test    eax, eax
0x140017036  jz      short loc_140017046
0x140017038  cmp     [rsp+0DB0h+var_D60], 12h
0x14001703d  jnz     short loc_140017046
0x14001703f  cmp     [rsp+0DB0h+var_D5C], r15d
0x140017044  jnb     short loc_14001704E
0x140017046  mov     [rbp+0CB0h+var_670], r12w
0x14001704e  mov     dword ptr [rsp+0DB0h+var_D70], r12d
0x140017053  lea     rax, [rsp+0DB0h+var_D5C]
0x140017058  mov     [rsp+0DB0h+var_D78], rax
0x14001705d  lea     r9, DEVPKEY_DriverPackage_OriginalInfName
0x140017064  lea     rax, [rbp+0CB0h+var_A90]
0x14001706b  mov     dword ptr [rsp+0DB0h+var_D80], r13d
0x140017070  mov     [rsp+0DB0h+var_D88], rax
0x140017075  mov     r8, rbx
0x140017078  lea     rax, [rsp+0DB0h+var_D60]
0x14001707d  mov     edx, r15d
0x140017080  mov     rcx, rdi
0x140017083  mov     [rsp+0DB0h+var_D90], rax
0x140017088  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14001708e  test    eax, eax
0x140017090  jz      short loc_140017099
0x140017092  cmp     [rsp+0DB0h+var_D60], 12h
0x140017097  jz      short loc_1400170A1
0x140017099  mov     [rbp+0CB0h+var_A90], r12w
0x1400170a1  mov     r8, rbx
0x1400170a4  mov     rcx, rdi
0x1400170a7  call    GetDriverStorePropertyLogString
0x1400170ac  mov     [rsp+0DB0h+hMem], rax
0x1400170b1  mov     r9d, [r14+5CCh]
0x1400170b8  test    r9d, r9d
0x1400170bb  jnz     short loc_1400170C6
0x1400170bd  cmp     [r14+5C8h], r12d
0x1400170c4  jz      short loc_140017107
0x1400170c6  movzx   ecx, word ptr [r14+5C8h]
0x1400170ce  lea     r8, aUUUU; "%u.%u.%u.%u"
0x1400170d5  movzx   edx, word ptr [r14+5CAh]
0x1400170dd  movzx   eax, word ptr [r14+5CCh]
0x1400170e5  mov     dword ptr [rsp+0DB0h+var_D80], ecx
0x1400170e9  lea     rcx, [rbp+0CB0h+pszDest]; pszDest
0x1400170ed  mov     dword ptr [rsp+0DB0h+var_D88], edx
0x1400170f1  mov     edx, 18h; cchDest
0x1400170f6  shr     r9d, 10h
0x1400170fa  mov     dword ptr [rsp+0DB0h+var_D90], eax
0x1400170fe  call    StringCchPrintfW
0x140017103  test    eax, eax
0x140017105  jns     short loc_14001710C
0x140017107  mov     [rbp+0CB0h+pszDest], r12w
0x14001710c  mov     dword ptr [rsp+0DB0h+var_D70], r12d
0x140017111  lea     rax, [rsp+0DB0h+var_D5C]
0x140017116  mov     [rsp+0DB0h+var_D78], rax
0x14001711b  lea     r9, DEVPKEY_DriverPackage_OriginalInfName
0x140017122  lea     rax, [rbp+0CB0h+var_A90]
0x140017129  mov     dword ptr [rsp+0DB0h+var_D80], r13d
0x14001712e  mov     [rsp+0DB0h+var_D88], rax
0x140017133  mov     r8, rbx
0x140017136  lea     rax, [rsp+0DB0h+var_D60]
0x14001713b  mov     edx, r15d
0x14001713e  mov     rcx, rdi
0x140017141  mov     [rsp+0DB0h+var_D90], rax
0x140017146  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14001714c  test    eax, eax
0x14001714e  jz      short loc_140017157
0x140017150  cmp     [rsp+0DB0h+var_D60], 12h
0x140017155  jz      short loc_14001715F
0x140017157  mov     [rbp+0CB0h+var_A90], r12w
0x14001715f  mov     r15, [r14+0B68h]
0x140017166  test    r15, r15
0x140017169  jz      loc_140017487
0x14001716f  mov     r13, r12
0x140017172  cmp     [r15], r12w
0x140017176  jz      loc_140017487
0x14001717c  lea     r14, qword_14004E980
0x140017183  mov     [rsp+0DB0h+var_D78], r12
0x140017188  lea     rax, [rbp+0CB0h+var_250]
0x14001718f  mov     dword ptr [rsp+0DB0h+var_D80], 104h
0x140017197  mov     r8d, 9
0x14001719d  mov     [rsp+0DB0h+var_D88], rax
0x1400171a2  xor     r9d, r9d
0x1400171a5  mov     rdx, r15
0x1400171a8  mov     dword ptr [rsp+0DB0h+var_D90], 1
0x1400171b0  mov     rcx, rdi
0x1400171b3  call    cs:__imp_DriverStoreFindW
0x1400171b9  test    eax, eax
0x1400171bb  jz      short loc_1400171DE
0x1400171bd  lea     rcx, [rbp+0CB0h+var_250]
0x1400171c4  call    pSetupTrimFileTitle
0x1400171c9  test    eax, eax
0x1400171cb  jz      short loc_1400171DE
0x1400171cd  lea     rcx, [rbp+0CB0h+var_250]
0x1400171d4  call    pSetupGetFileTitle
0x1400171d9  mov     rbx, rax
0x1400171dc  jmp     short loc_1400171E1
0x1400171de  mov     rbx, r12
0x1400171e1  mov     [rbp+0CB0h+var_CA0], r12w
0x1400171e6  mov     [rbp+0CB0h+var_CF0], r12w
0x1400171eb  test    rbx, rbx
0x1400171ee  jz      loc_140017328
0x1400171f4  mov     dword ptr [rsp+0DB0h+var_D70], r12d
0x1400171f9  lea     rax, [rsp+0DB0h+var_D5C]
0x1400171fe  mov     [rsp+0DB0h+var_D78], rax
0x140017203  lea     r9, DEVPKEY_DriverPackage_OriginalInfName
0x14001720a  lea     rax, [rbp+0CB0h+var_CA0]
0x14001720e  mov     dword ptr [rsp+0DB0h+var_D80], 208h
0x140017216  mov     [rsp+0DB0h+var_D88], rax
0x14001721b  mov     r13d, 2
0x140017221  lea     rax, [rsp+0DB0h+var_D60]
0x140017226  mov     r8, rbx
0x140017229  mov     edx, r13d
0x14001722c  mov     [rsp+0DB0h+var_D90], rax
0x140017231  mov     rcx, rdi
0x140017234  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14001723a  test    eax, eax
0x14001723c  jz      short loc_14001724C
0x14001723e  cmp     [rsp+0DB0h+var_D60], 12h
0x140017243  jnz     short loc_14001724C
0x140017245  cmp     [rsp+0DB0h+var_D5C], r13d
0x14001724a  jnb     short loc_140017251
0x14001724c  mov     [rbp+0CB0h+var_CA0], r12w
0x140017251  mov     dword ptr [rsp+0DB0h+var_D70], r12d
0x140017256  lea     rax, [rsp+0DB0h+var_D5C]
0x14001725b  mov     [rsp+0DB0h+var_D78], rax
0x140017260  lea     r9, DEVPKEY_DriverPackage_ExtensionId
0x140017267  lea     rax, [rsp+0DB0h+var_D38]
0x14001726c  mov     dword ptr [rsp+0DB0h+var_D80], 10h
0x140017274  mov     [rsp+0DB0h+var_D88], rax
0x140017279  mov     r8, rbx
0x14001727c  lea     rax, [rsp+0DB0h+var_D60]
0x140017281  mov     edx, r13d
0x140017284  mov     rcx, rdi
0x140017287  mov     [rsp+0DB0h+var_D90], rax
0x14001728c  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140017292  test    eax, eax
0x140017294  jz      short loc_1400172B4
0x140017296  cmp     [rsp+0DB0h+var_D60], 0Dh
0x14001729b  jnz     short loc_1400172B4
0x14001729d  lea     rdx, [rbp+0CB0h+var_CF0]
0x1400172a1  lea     rcx, [rsp+0DB0h+var_D38]
0x1400172a6  call    SpUtilsStringFromGuid
0x1400172ab  test    eax, eax
0x1400172ad  jz      short loc_1400172B4
0x1400172af  mov     [rbp+0CB0h+var_CF0], r12w
0x1400172b4  mov     r8, rbx
0x1400172b7  mov     rcx, rdi
0x1400172ba  call    GetDriverStorePropertyLogString
0x1400172bf  mov     r13, rax
0x1400172c2  mov     dword ptr [rsp+0DB0h+var_D70], r12d
0x1400172c7  lea     rax, [rsp+0DB0h+var_D5C]
0x1400172cc  mov     r8, rbx
0x1400172cf  mov     [rsp+0DB0h+var_D78], rax
0x1400172d4  lea     r9, DEVPKEY_DriverPackage_SubmissionId
0x1400172db  lea     rax, [rbp+0CB0h+var_880]
0x1400172e2  mov     dword ptr [rsp+0DB0h+var_D80], 208h
0x1400172ea  mov     [rsp+0DB0h+var_D88], rax
0x1400172ef  mov     edx, 2
0x1400172f4  lea     rax, [rsp+0DB0h+var_D60]
0x1400172f9  mov     rcx, rdi
0x1400172fc  mov     [rsp+0DB0h+var_D90], rax
0x140017301  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140017307  test    eax, eax
0x140017309  jz      short loc_140017319
0x14001730b  cmp     [rsp+0DB0h+var_D60], 12h
0x140017310  jnz     short loc_140017319
0x140017312  cmp     [rsp+0DB0h+var_D5C], 2
0x140017317  jnb     short loc_140017321
0x140017319  mov     [rbp+0CB0h+var_880], r12w
0x140017321  cmp     [rbp+0CB0h+var_CA0], r12w
0x140017326  jnz     short loc_140017342
0x140017328  mov     r8, r15; unsigned __int16 *
0x14001732b  lea     rcx, [rbp+0CB0h+var_CA0]; unsigned __int16 *
0x14001732f  mov     edx, 104h; unsigned __int64
0x140017334  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140017339  test    eax, eax
0x14001733b  jns     short loc_140017342
0x14001733d  mov     [rbp+0CB0h+var_CA0], r12w
0x140017342  or      r10, 0FFFFFFFFFFFFFFFFh
0x140017346  test    rsi, rsi
0x140017349  jz      short loc_14001735E
0x14001734b  mov     rax, r10
0x14001734e  inc     rax
0x140017351  cmp     [rsi+rax*2], r12w
0x140017356  jnz     short loc_14001734E
0x140017358  lea     r8d, [rax+1]
0x14001735c  jmp     short loc_140017361
0x14001735e  mov     r8d, r12d
0x140017361  lea     rax, [rbp+0CB0h+var_CA0]
0x140017365  mov     rdx, r10
0x140017368  inc     rdx
0x14001736b  cmp     [rax+rdx*2], r12w
0x140017370  jnz     short loc_140017368
0x140017372  lea     rax, [rbp+0CB0h+var_CF0]
0x140017376  mov     rcx, r10
0x140017379  inc     rcx
0x14001737c  cmp     [rax+rcx*2], r12w
0x140017381  jnz     short loc_140017379
0x140017383  lea     r9, [rbp+0CB0h+var_880]
0x14001738a  mov     rax, r10
0x14001738d  inc     rax
0x140017390  cmp     [r9+rax*2], r12w
0x140017395  jnz     short loc_14001738D
0x140017397  add     ecx, 4
0x14001739a  add     eax, r8d
0x14001739d  add     ecx, eax
0x14001739f  add     ecx, edx
0x1400173a1  test    r13, r13
0x1400173a4  jz      short loc_1400173B6
0x1400173a6  mov     rax, r10
0x1400173a9  inc     rax
0x1400173ac  cmp     [r13+rax*2+0], r12w
0x1400173b2  jnz     short loc_1400173A9
0x1400173b4  add     ecx, eax
0x1400173b6  mov     r12d, ecx
0x1400173b9  lea     rdx, [rcx+rcx]; uBytes
0x1400173bd  mov     ecx, 40h ; '@'; uFlags
0x1400173c2  call    cs:__imp_LocalAlloc
0x1400173c8  mov     rbx, rax
0x1400173cb  test    rax, rax
0x1400173ce  jz      short loc_14001744E
0x1400173d0  test    r13, r13
0x1400173d3  lea     rax, [rbp+0CB0h+var_880]
0x1400173da  mov     [rsp+0DB0h+var_D70], rax
0x1400173df  lea     r8, asc_14004E9E8; ","
0x1400173e6  lea     rax, [rbp+0CB0h+var_CF0]
0x1400173ea  mov     rcx, r14
0x1400173ed  cmovnz  rcx, r13
  ... truncated ...
```
