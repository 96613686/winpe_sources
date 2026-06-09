# ScopeSnapshotHelper::ChangeDiffAreaMaximumSize(long *,unsigned __int64 *,ushort const *,__int64,uchar)

- ea: `0x180048564`
- end: `0x180048966`
- name: `?ChangeDiffAreaMaximumSize@ScopeSnapshotHelper@@SAJPEAJPEA_KPEBG_JE@Z`
- size: `1026`
- prototype: `__int64 __fastcall(int *, unsigned __int64 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18003a550`

## callees

- `0x18000110c`
- `0x18000124c`
- `0x180048564`
- `0x18004896c`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004893b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004893b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048695`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048695`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180048641`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180048641`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180048904`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180048904`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800485c2`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800485c2`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x180048731`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x180048731`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x180048744`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x180048744`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ScopeSnapshotHelper::ChangeDiffAreaMaximumSize(
        int *a1,
        unsigned __int64 *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  const unsigned __int16 *v8; // rax
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  HRESULT v18; // ebx
  bool v19; // r12
  unsigned __int64 v20; // rax
  HRESULT v21; // eax
  __int64 v22; // rax
  int v23; // eax
  ULONGLONG v24; // rax
  int v25; // eax
  __int64 v26; // rax
  REGHANDLE v27; // rcx
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  struct _OSVERSIONINFOEXW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+190h] [rbp+90h] BYREF
  __int128 *v38; // [rsp+1B0h] [rbp+B0h]
  __int64 v39; // [rsp+1B8h] [rbp+B8h]
  WCHAR *v40; // [rsp+1C0h] [rbp+C0h]
  int v41; // [rsp+1C8h] [rbp+C8h]
  int v42; // [rsp+1CCh] [rbp+CCh]
  __int64 *v43; // [rsp+1D0h] [rbp+D0h]
  __int64 v44; // [rsp+1D8h] [rbp+D8h]
  __int64 *v45; // [rsp+1E0h] [rbp+E0h]
  __int64 v46; // [rsp+1E8h] [rbp+E8h]
  __int64 *v47; // [rsp+1F0h] [rbp+F0h]
  __int64 v48; // [rsp+1F8h] [rbp+F8h]
  int *v49; // [rsp+200h] [rbp+100h]
  __int64 v50; // [rsp+208h] [rbp+108h]
  WCHAR szVolumeName[264]; // [rsp+210h] [rbp+110h] BYREF

  ppv = 0;
  v30 = 0;
  v31 = 0;
  v29 = 0;
  if ( !GetVolumeNameForVolumeMountPointW(a3, szVolumeName, 0x32u) )
  {
    v8 = a3;
    v9 = szVolumeName;
    v10 = 4;
    do
    {
      v11 = *((_OWORD *)v8 + 1);
      *(_OWORD *)v9 = *(_OWORD *)v8;
      v12 = *((_OWORD *)v8 + 2);
      *((_OWORD *)v9 + 1) = v11;
      v13 = *((_OWORD *)v8 + 3);
      *((_OWORD *)v9 + 2) = v12;
      v14 = *((_OWORD *)v8 + 4);
      *((_OWORD *)v9 + 3) = v13;
      v15 = *((_OWORD *)v8 + 5);
      *((_OWORD *)v9 + 4) = v14;
      v16 = *((_OWORD *)v8 + 6);
      *((_OWORD *)v9 + 5) = v15;
      v17 = *((_OWORD *)v8 + 7);
      v8 += 64;
      *((_OWORD *)v9 + 6) = v16;
      *((_OWORD *)v9 + 7) = v17;
      v9 += 64;
      --v10;
    }
    while ( v10 );
    *(_QWORD *)v9 = *(_QWORD *)v8;
  }
  ScopeSnapshotHelper::QueryDiffAreaMaxSize(a3, &v31);
  v18 = CoInitializeEx(0, 0);
  v19 = (unsigned int)v18 <= 1;
  if ( (int)(v18 + 0x80000000) >= 0 && v18 != -2147417850 )
  {
    *a1 = v18;
    v20 = 0x1500010A13LL;
LABEL_8:
    *a2 = v20;
    goto LABEL_25;
  }
  v21 = CoCreateInstance(&CLSID_VssSnapshotMgmt, 0, 0x17u, &IID_IVssSnapshotMgmt, &ppv);
  v18 = v21;
  if ( v21 < 0 )
  {
    *a1 = v21;
    v20 = 0x1600010A27LL;
    goto LABEL_8;
  }
  v22 = *(_QWORD *)ppv;
  v35 = xmmword_18006A148;
  v23 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, GUID *, __int64 *))(v22 + 24))(
          ppv,
          &v35,
          &IID_IVssDifferentialSoftwareSnapshotMgmt,
          &v30);
  v18 = v23;
  if ( v23 < 0 )
  {
    *a1 = v23;
    v20 = 0x1700010A39LL;
    goto LABEL_8;
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
  memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
  *(_DWORD *)&VersionInformation.wServicePackMajor = 0;
  *(_DWORD *)&VersionInformation.wSuiteMask = 0x10000;
  v24 = VerSetConditionMask(0, 0x80u, 1u);
  if ( VerifyVersionInfoW(&VersionInformation, 0x80u, v24)
    || (v18 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)v30 + 24LL))(
                v30,
                a3,
                a3,
                a4),
        v18 < 0) )
  {
    v25 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)v30 + 32LL))(
            v30,
            a3,
            a3,
            a4);
    v18 = v25;
    if ( v25 < 0 )
    {
      *a1 = v25;
      *a2 = 0x1800010A73LL;
    }
    ScopeSnapshotHelper::QueryDiffAreaMaxSize(a3, &v29);
    if ( (int)TraceLoggingRegister_EventRegister_2U() >= 0 )
    {
      if ( (unsigned int)dword_18007D038 > 5
        && (qword_18007D048 & 0x400000000000LL) != 0
        && (qword_18007D050 & 0x400000000000LL) == qword_18007D050 )
      {
        v34 = v29;
        v49 = &v32;
        v47 = &v34;
        v45 = &v31;
        v43 = &v29;
        v26 = -1;
        v32 = 1;
        LODWORD(v29) = v18;
        *(_QWORD *)&v35 = 0x1000000;
        v50 = 4;
        v48 = 8;
        v46 = 8;
        v44 = 4;
        do
          ++v26;
        while ( szVolumeName[v26] );
        v39 = 8;
        v41 = 2 * v26 + 2;
        v40 = szVolumeName;
        v38 = &v35;
        v42 = 0;
        tlgWriteTransfer_EventWriteTransfer((int)&dword_18007D038, (int)&byte_1800721BF, 0, 0, 8u, &v37);
      }
      v27 = RegHandle;
      dword_18007D038 = 0;
      RegHandle = 0;
      EventUnregister(v27);
    }
  }
LABEL_25:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v19 )
    CoUninitialize();
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180048564  push    rbp
0x180048566  push    rbx
0x180048567  push    rsi
0x180048568  push    rdi
0x180048569  push    r12
0x18004856b  push    r13
0x18004856d  push    r14
0x18004856f  push    r15
0x180048571  lea     rbp, [rsp-338h]
0x180048579  sub     rsp, 438h
0x180048580  mov     rax, cs:__security_cookie
0x180048587  xor     rax, rsp
0x18004858a  mov     [rbp+370h+var_50], rax
0x180048591  xor     r13d, r13d
0x180048594  mov     rdi, r8
0x180048597  mov     r14, rdx
0x18004859a  mov     [rsp+470h+var_420], r13
0x18004859f  mov     rsi, rcx
0x1800485a2  mov     [rsp+470h+var_438], r13
0x1800485a7  lea     rdx, [rbp+370h+szVolumeName]; lpszVolumeName
0x1800485ae  mov     [rsp+470h+var_430], r13
0x1800485b3  lea     r8d, [r13+32h]; cchBufferLength
0x1800485b7  mov     [rsp+470h+var_440], r13
0x1800485bc  mov     rcx, rdi; lpszVolumeMountPoint
0x1800485bf  mov     r15, r9
0x1800485c2  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800485c8  mov     r8d, 80h
0x1800485ce  test    eax, eax
0x1800485d0  jnz     short loc_180048630
0x1800485d2  mov     rax, rdi
0x1800485d5  lea     rcx, [rbp+370h+szVolumeName]
0x1800485dc  lea     edx, [r13+4]
0x1800485e0  movups  xmm0, xmmword ptr [rax]
0x1800485e3  movups  xmm1, xmmword ptr [rax+10h]
0x1800485e7  movups  xmmword ptr [rcx], xmm0
0x1800485ea  movups  xmm0, xmmword ptr [rax+20h]
0x1800485ee  movups  xmmword ptr [rcx+10h], xmm1
0x1800485f2  movups  xmm1, xmmword ptr [rax+30h]
0x1800485f6  movups  xmmword ptr [rcx+20h], xmm0
0x1800485fa  movups  xmm0, xmmword ptr [rax+40h]
0x1800485fe  movups  xmmword ptr [rcx+30h], xmm1
0x180048602  movups  xmm1, xmmword ptr [rax+50h]
0x180048606  movups  xmmword ptr [rcx+40h], xmm0
0x18004860a  movups  xmm0, xmmword ptr [rax+60h]
0x18004860e  movups  xmmword ptr [rcx+50h], xmm1
0x180048612  movups  xmm1, xmmword ptr [rax+70h]
0x180048616  add     rax, r8
0x180048619  movups  xmmword ptr [rcx+60h], xmm0
0x18004861d  movups  xmmword ptr [rcx+70h], xmm1
0x180048621  add     rcx, r8
0x180048624  sub     rdx, 1
0x180048628  jnz     short loc_1800485E0
0x18004862a  mov     rax, [rax]
0x18004862d  mov     [rcx], rax
0x180048630  lea     rdx, [rsp+470h+var_430]; __int64 *
0x180048635  mov     rcx, rdi; unsigned __int16 *
0x180048638  call    ?QueryDiffAreaMaxSize@ScopeSnapshotHelper@@SAJPEBGPEA_J@Z; ScopeSnapshotHelper::QueryDiffAreaMaxSize(ushort const *,__int64 *)
0x18004863d  xor     edx, edx; dwCoInit
0x18004863f  xor     ecx, ecx; pvReserved
0x180048641  call    cs:__imp_CoInitializeEx
0x180048647  cmp     eax, 1
0x18004864a  mov     ecx, 80000000h
0x18004864f  mov     ebx, eax
0x180048651  setbe   r12b
0x180048655  add     eax, ecx
0x180048657  test    ecx, eax
0x180048659  jnz     short loc_180048677
0x18004865b  cmp     ebx, 80010106h
0x180048661  jz      short loc_180048677
0x180048663  mov     [rsi], ebx
0x180048665  mov     rax, 1500010A13h
0x18004866f  mov     [r14], rax
0x180048672  jmp     loc_18004890A
0x180048677  xor     edx, edx; pUnkOuter
0x180048679  lea     rax, [rsp+470h+var_420]
0x18004867e  lea     r9, IID_IVssSnapshotMgmt; riid
0x180048685  mov     [rsp+470h+ppv], rax; ppv
0x18004868a  lea     rcx, CLSID_VssSnapshotMgmt; rclsid
0x180048691  lea     r8d, [rdx+17h]; dwClsContext
0x180048695  call    cs:__imp_CoCreateInstance
0x18004869b  mov     ebx, eax
0x18004869d  test    eax, eax
0x18004869f  jns     short loc_1800486AF
0x1800486a1  mov     [rsi], eax
0x1800486a3  mov     rax, 1600010A27h
0x1800486ad  jmp     short loc_18004866F
0x1800486af  mov     rcx, [rsp+470h+var_420]
0x1800486b4  lea     r9, [rsp+470h+var_438]
0x1800486b9  movups  xmm0, cs:xmmword_18006A148
0x1800486c0  lea     r8, IID_IVssDifferentialSoftwareSnapshotMgmt
0x1800486c7  lea     rdx, [rsp+470h+var_410]
0x1800486cc  mov     rax, [rcx]
0x1800486cf  movdqu  [rsp+470h+var_410], xmm0
0x1800486d5  mov     rax, [rax+18h]
0x1800486d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486de  mov     ebx, eax
0x1800486e0  test    eax, eax
0x1800486e2  jns     short loc_1800486F5
0x1800486e4  mov     [rsi], eax
0x1800486e6  mov     rax, 1700010A39h
0x1800486f0  jmp     loc_18004866F
0x1800486f5  xorps   xmm0, xmm0
0x1800486f8  mov     [rsp+470h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180048700  xor     edx, edx; Val
0x180048702  lea     rcx, [rbp+370h+VersionInformation.szCSDVersion]; void *
0x180048706  mov     r8d, 100h; Size
0x18004870c  movups  xmmword ptr [rsp+470h+VersionInformation.dwMajorVersion], xmm0
0x180048711  call    memset_0
0x180048716  mov     r8b, 1; Condition
0x180048719  mov     dword ptr [rbp+370h+VersionInformation.wServicePackMajor], r13d
0x180048720  mov     edx, 80h; TypeMask
0x180048725  mov     dword ptr [rbp+370h+VersionInformation.wSuiteMask], 10000h
0x18004872f  xor     ecx, ecx; ConditionMask
0x180048731  call    cs:__imp_VerSetConditionMask
0x180048737  mov     edx, 80h; dwTypeMask
0x18004873c  lea     rcx, [rsp+470h+VersionInformation]; lpVersionInformation
0x180048741  mov     r8, rax; dwlConditionMask
0x180048744  call    cs:__imp_VerifyVersionInfoW
0x18004874a  test    eax, eax
0x18004874c  jnz     short loc_180048772
0x18004874e  mov     rcx, [rsp+470h+var_438]
0x180048753  mov     r9, r15
0x180048756  mov     r8, rdi
0x180048759  mov     rdx, rdi
0x18004875c  mov     rax, [rcx]
0x18004875f  mov     rax, [rax+18h]
0x180048763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048768  mov     ebx, eax
0x18004876a  test    eax, eax
0x18004876c  jns     loc_18004890A
0x180048772  mov     rcx, [rsp+470h+var_438]
0x180048777  mov     r9, r15
0x18004877a  mov     r8, rdi
0x18004877d  mov     rdx, rdi
0x180048780  mov     rax, [rcx]
0x180048783  mov     rax, [rax+20h]
0x180048787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004878c  mov     ebx, eax
0x18004878e  test    eax, eax
0x180048790  jns     short loc_1800487A1
0x180048792  mov     [rsi], eax
0x180048794  mov     rax, 1800010A73h
0x18004879e  mov     [r14], rax
0x1800487a1  lea     rdx, [rsp+470h+var_440]; __int64 *
0x1800487a6  mov     rcx, rdi; unsigned __int16 *
0x1800487a9  call    ?QueryDiffAreaMaxSize@ScopeSnapshotHelper@@SAJPEBGPEA_J@Z; ScopeSnapshotHelper::QueryDiffAreaMaxSize(ushort const *,__int64 *)
0x1800487ae  call    TraceLoggingRegister_EventRegister_2U
0x1800487b3  test    eax, eax
0x1800487b5  js      loc_18004890A
0x1800487bb  mov     eax, cs:dword_18007D038
0x1800487c1  cmp     eax, 5
0x1800487c4  jbe     loc_1800488EF
0x1800487ca  mov     rcx, cs:qword_18007D050
0x1800487d1  mov     rdx, 400000000000h
0x1800487db  mov     rax, cs:qword_18007D048
0x1800487e2  test    rdx, rax
0x1800487e5  jz      loc_1800488EF
0x1800487eb  mov     rax, rcx
0x1800487ee  and     rax, rdx
0x1800487f1  cmp     rax, rcx
0x1800487f4  jnz     loc_1800488EF
0x1800487fa  mov     rax, [rsp+470h+var_440]
0x1800487ff  lea     rcx, [rbp+370h+szVolumeName]
0x180048806  mov     [rsp+470h+var_418], rax
0x18004880b  mov     edx, 8
0x180048810  mov     rax, [rsp+470h+var_430]
0x180048815  mov     [rsp+470h+var_430], rax
0x18004881a  lea     rax, [rsp+470h+var_428]
0x18004881f  mov     [rbp+370h+var_270], rax
0x180048826  lea     rax, [rsp+470h+var_418]
0x18004882b  mov     [rbp+370h+var_280], rax
0x180048832  lea     rax, [rsp+470h+var_430]
0x180048837  mov     [rbp+370h+var_290], rax
0x18004883e  lea     rax, [rsp+470h+var_440]
0x180048843  mov     [rbp+370h+var_2A0], rax
0x18004884a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004884e  mov     [rsp+470h+var_428], 1
0x180048856  mov     dword ptr [rsp+470h+var_440], ebx
0x18004885a  mov     qword ptr [rsp+470h+var_410], 1000000h
0x180048863  mov     [rbp+370h+var_268], 4
0x18004886e  mov     [rbp+370h+var_278], rdx
0x180048875  mov     [rbp+370h+var_288], rdx
0x18004887c  mov     [rbp+370h+var_298], 4
0x180048887  inc     rax
0x18004888a  cmp     [rcx+rax*2], r13w
0x18004888f  jnz     short loc_180048887
0x180048891  lea     eax, ds:2[rax*2]
0x180048898  mov     [rbp+370h+var_2B8], rdx
0x18004889f  mov     [rbp+370h+var_2A8], eax
0x1800488a5  lea     rcx, [rbp+370h+szVolumeName]
0x1800488ac  lea     rax, [rsp+470h+var_410]
0x1800488b1  mov     [rbp+370h+var_2B0], rcx
0x1800488b8  mov     [rbp+370h+var_2C0], rax
0x1800488bf  lea     rcx, dword_18007D038; int
0x1800488c6  lea     rax, [rbp+370h+var_2E0]
0x1800488cd  mov     [rbp+370h+var_2A4], r13d
0x1800488d4  mov     [rsp+470h+var_448], rax; PEVENT_DATA_DESCRIPTOR
0x1800488d9  xor     r9d, r9d; int
0x1800488dc  mov     dword ptr [rsp+470h+ppv], edx; ULONG
0x1800488e0  xor     r8d, r8d; int
0x1800488e3  lea     rdx, byte_1800721BF; int
0x1800488ea  call    _tlgWriteTransfer_EventWriteTransfer
0x1800488ef  mov     rcx, cs:RegHandle; RegHandle
0x1800488f6  mov     cs:dword_18007D038, r13d
0x1800488fd  mov     cs:RegHandle, r13
0x180048904  call    cs:__imp_EventUnregister
0x18004890a  mov     rcx, [rsp+470h+var_420]
0x18004890f  test    rcx, rcx
0x180048912  jz      short loc_180048920
0x180048914  mov     rax, [rcx]
0x180048917  mov     rax, [rax+10h]
0x18004891b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048920  mov     rcx, [rsp+470h+var_438]
0x180048925  test    rcx, rcx
0x180048928  jz      short loc_180048936
0x18004892a  mov     rax, [rcx]
0x18004892d  mov     rax, [rax+10h]
0x180048931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048936  test    r12b, r12b
0x180048939  jz      short loc_180048941
0x18004893b  call    cs:__imp_CoUninitialize
0x180048941  mov     eax, ebx
0x180048943  mov     rcx, [rbp+370h+var_50]
0x18004894a  xor     rcx, rsp; StackCookie
0x18004894d  call    __security_check_cookie
0x180048952  add     rsp, 438h
0x180048959  pop     r15
0x18004895b  pop     r14
0x18004895d  pop     r13
0x18004895f  pop     r12
0x180048961  pop     rdi
0x180048962  pop     rsi
0x180048963  pop     rbx
0x180048964  pop     rbp
0x180048965  retn
```
