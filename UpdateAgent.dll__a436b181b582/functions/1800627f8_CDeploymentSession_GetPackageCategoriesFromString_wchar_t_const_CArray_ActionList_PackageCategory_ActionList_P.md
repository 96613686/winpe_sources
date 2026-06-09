# CDeploymentSession::GetPackageCategoriesFromString(wchar_t const *,CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault> *)

- ea: `0x1800627f8`
- end: `0x180062d1d`
- name: `?GetPackageCategoriesFromString@CDeploymentSession@@QEAAJPEB_WPEAV?$CArray@W4PackageCategory@ActionList@@W412@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z`
- size: `1317`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002c0c4`

## callees

- `0x180035720`
- `0x180039f90`
- `0x1800627f8`
- `0x180077664`
- `0x180078b9c`
- `0x180090e44`
- `0x180091364`
- `0x1800948f8`
- `0x180094e1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006295d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800629a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800629df`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062a22`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062a65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062aa8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062aeb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062b6e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062bae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006295d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800629a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800629df`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062a22`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062a65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062aa8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062aeb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062b6e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062bae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062ca1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062cd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062ca1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062cd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062cb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062cee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062cb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062cee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeploymentSession::GetPackageCategoriesFromString(__int64 a1, void *a2, __int64 a3)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 updated; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  const char *v11; // r9
  HANDLE v12; // rax
  __int64 result; // rax
  int lpString2; // [rsp+20h] [rbp-58h]
  int cchCount2; // [rsp+28h] [rbp-50h]
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-38h]
  __int64 v18; // [rsp+48h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v22; // [rsp+90h] [rbp+18h]

  v22 = a3;
  try
  {
    v16 = 0;
    v17 = 0;
    v18 = 0;
    lpMem = 0;
    if ( a2 )
    {
      if ( a3 )
      {
        v9 = CMiscHelpersT<CEmptyType>::TokenizeString(a2);
        v5 = v9;
        v8 = *(_QWORD *)(a1 + 600);
        if ( v9 >= 0 )
        {
          if ( v8 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v8,
              2,
              L"GetPackageCategoriesFromString: Found [%d] categories.",
              HIDWORD(v16));
          CArray<enum ActionList::PackageCategory,enum ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::Swap(
            v22,
            &v18);
          goto LABEL_19;
        }
        if ( !v8 )
          goto LABEL_4;
        cchCount2 = v9;
        lpString2 = 5967;
      }
      else
      {
        v8 = *(_QWORD *)(a1 + 600);
        v5 = -2147024809;
        if ( !v8 )
          goto LABEL_4;
        cchCount2 = -2147024809;
        lpString2 = 5965;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v8,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GetPackageCategoriesFromString",
                                lpString2,
                                cchCount2,
                                -2,
                                v16);
    }
    else
    {
      v4 = *(_QWORD *)(a1 + 600);
      v5 = -2147024809;
      if ( !v4 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_19:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
        CArray<enum ActionList::PackageCategory,enum ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::SetSize(
          &v18,
          0);
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, lpMem);
        }
        CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v16, 0);
        if ( v17 )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v17);
        }
        return v5;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v4,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GetPackageCategoriesFromString",
                                5964,
                                -2147024809,
                                -2,
                                v16);
    }
    if ( (int)updated < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v7);
    goto LABEL_8;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x178B,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800627f8  mov     r11, rsp
0x1800627fb  mov     [r11+18h], r8
0x1800627ff  push    r12
0x180062801  push    r13
0x180062803  push    r15
0x180062805  sub     rsp, 60h
0x180062809  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180062811  mov     [r11+8], rbx
0x180062815  mov     [r11+20h], rsi
0x180062819  mov     rax, rdx
0x18006281c  mov     rsi, rcx
0x18006281f  mov     qword ptr [r11-40h], 0
0x180062827  mov     qword ptr [r11-38h], 0
0x18006282f  mov     qword ptr [r11-30h], 0
0x180062837  mov     qword ptr [r11-28h], 0
0x18006283f  test    rax, rax
0x180062842  jnz     short loc_180062892
0x180062844  mov     rcx, [rcx+258h]
0x18006284b  mov     ebx, 80070057h
0x180062850  test    rcx, rcx
0x180062853  jnz     short loc_180062859
0x180062855  xor     ecx, ecx
0x180062857  jmp     short loc_180062888
0x180062859  mov     [rsp+78h+cchCount2], ebx
0x18006285d  mov     dword ptr [rsp+78h+lpString2], 174Ch
0x180062865  lea     r9, aCdeploymentses_5; "CDeploymentSession::GetPackageCategorie"...
0x18006286c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180062873  mov     edx, 4
0x180062878  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006287d  mov     ecx, eax
0x18006287f  test    ecx, ecx
0x180062881  jns     short loc_180062888
0x180062883  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180062888  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006288d  jmp     loc_180062C85
0x180062892  test    r8, r8
0x180062895  jnz     short loc_1800628D0
0x180062897  mov     rcx, [rcx+258h]
0x18006289e  mov     ebx, 80070057h
0x1800628a3  test    rcx, rcx
0x1800628a6  jz      short loc_180062855
0x1800628a8  mov     [rsp+78h+cchCount2], ebx
0x1800628ac  mov     dword ptr [rsp+78h+lpString2], 174Dh
0x1800628b4  lea     r9, aCdeploymentses_5; "CDeploymentSession::GetPackageCategorie"...
0x1800628bb  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800628c2  mov     edx, 4
0x1800628c7  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800628cc  mov     ecx, eax
0x1800628ce  jmp     short loc_18006287F
0x1800628d0  mov     edx, 3Bh ; ';'
0x1800628d5  lea     r8, [rsp+78h+var_40]
0x1800628da  mov     rcx, rax; Src
0x1800628dd  call    ?TokenizeString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W_WPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@H@Z; CMiscHelpersT<CEmptyType>::TokenizeString(wchar_t const *,wchar_t,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int)
0x1800628e2  mov     ebx, eax
0x1800628e4  mov     rcx, [rsi+258h]
0x1800628eb  test    eax, eax
0x1800628ed  jns     short loc_180062906
0x1800628ef  test    rcx, rcx
0x1800628f2  jz      loc_180062855
0x1800628f8  mov     [rsp+78h+cchCount2], eax
0x1800628fc  mov     dword ptr [rsp+78h+lpString2], 174Fh
0x180062904  jmp     short loc_1800628B4
0x180062906  mov     r13d, [rsp+78h+var_3C]
0x18006290b  test    rcx, rcx
0x18006290e  jz      short loc_180062924
0x180062910  mov     r9d, r13d
0x180062913  lea     r8, aGetpackagecate; "GetPackageCategoriesFromString: Found ["...
0x18006291a  mov     edx, 2
0x18006291f  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180062924  xor     r12d, r12d
0x180062927  mov     r15, [rsp+78h+var_38]
0x18006292c  cmp     r12d, r13d
0x18006292f  jnb     loc_180062C73
0x180062935  movsxd  rbx, r12d
0x180062938  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x180062940  lea     rax, aSetupdu_0; "SETUPDU"
0x180062947  mov     [rsp+78h+lpString2], rax; lpString2
0x18006294c  or      r9d, 0FFFFFFFFh; cchCount1
0x180062950  mov     r8, [r15+rbx*8]; lpString1
0x180062954  lea     edx, [r9+2]; dwCmpFlags
0x180062958  mov     ecx, 409h; Locale
0x18006295d  call    cs:__imp_CompareStringW
0x180062964  nop     dword ptr [rax+rax+00h]
0x180062969  cmp     eax, 2
0x18006296c  jnz     short loc_18006297E
0x18006296e  mov     [rsp+78h+arg_8], 0Fh
0x180062979  jmp     loc_180062BCA
0x18006297e  or      r9d, 0FFFFFFFFh; cchCount1
0x180062982  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180062987  lea     rax, aOndemand; "ONDEMAND"
0x18006298e  mov     [rsp+78h+lpString2], rax; lpString2
0x180062993  mov     r8, [r15+rbx*8]; lpString1
0x180062997  lea     edx, [r9+2]; dwCmpFlags
0x18006299b  mov     ecx, 409h; Locale
0x1800629a0  call    cs:__imp_CompareStringW
0x1800629a7  nop     dword ptr [rax+rax+00h]
0x1800629ac  cmp     eax, 2
0x1800629af  jnz     short loc_1800629BD
0x1800629b1  mov     [rsp+78h+arg_8], eax
0x1800629b8  jmp     loc_180062BCA
0x1800629bd  or      ecx, 0FFFFFFFFh
0x1800629c0  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x1800629c4  lea     rax, aSatellite_1; "SATELLITE"
0x1800629cb  mov     [rsp+78h+lpString2], rax; lpString2
0x1800629d0  mov     r9d, ecx; cchCount1
0x1800629d3  mov     r8, [r15+rbx*8]; lpString1
0x1800629d7  lea     edx, [rcx+2]; dwCmpFlags
0x1800629da  mov     ecx, 409h; Locale
0x1800629df  call    cs:__imp_CompareStringW
0x1800629e6  nop     dword ptr [rax+rax+00h]
0x1800629eb  cmp     eax, 2
0x1800629ee  jnz     short loc_180062A00
0x1800629f0  mov     [rsp+78h+arg_8], 3
0x1800629fb  jmp     loc_180062BCA
0x180062a00  or      ecx, 0FFFFFFFFh
0x180062a03  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062a07  lea     rax, aLanguagePack; "LANGUAGE_PACK"
0x180062a0e  mov     [rsp+78h+lpString2], rax; lpString2
0x180062a13  mov     r9d, ecx; cchCount1
0x180062a16  mov     r8, [r15+rbx*8]; lpString1
0x180062a1a  lea     edx, [rcx+2]; dwCmpFlags
0x180062a1d  mov     ecx, 409h; Locale
0x180062a22  call    cs:__imp_CompareStringW
0x180062a29  nop     dword ptr [rax+rax+00h]
0x180062a2e  cmp     eax, 2
0x180062a31  jnz     short loc_180062A43
0x180062a33  mov     [rsp+78h+arg_8], 4
0x180062a3e  jmp     loc_180062BCA
0x180062a43  or      ecx, 0FFFFFFFFh
0x180062a46  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062a4a  lea     rax, aLxp_0; "LXP"
0x180062a51  mov     [rsp+78h+lpString2], rax; lpString2
0x180062a56  mov     r9d, ecx; cchCount1
0x180062a59  mov     r8, [r15+rbx*8]; lpString1
0x180062a5d  lea     edx, [rcx+2]; dwCmpFlags
0x180062a60  mov     ecx, 409h; Locale
0x180062a65  call    cs:__imp_CompareStringW
0x180062a6c  nop     dword ptr [rax+rax+00h]
0x180062a71  cmp     eax, 2
0x180062a74  jnz     short loc_180062A86
0x180062a76  mov     [rsp+78h+arg_8], 11h
0x180062a81  jmp     loc_180062BCA
0x180062a86  or      ecx, 0FFFFFFFFh
0x180062a89  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062a8d  lea     rax, aCritdu_0; "CRITDU"
0x180062a94  mov     [rsp+78h+lpString2], rax; lpString2
0x180062a99  mov     r9d, ecx; cchCount1
0x180062a9c  mov     r8, [r15+rbx*8]; lpString1
0x180062aa0  lea     edx, [rcx+2]; dwCmpFlags
0x180062aa3  mov     ecx, 409h; Locale
0x180062aa8  call    cs:__imp_CompareStringW
0x180062aaf  nop     dword ptr [rax+rax+00h]
0x180062ab4  cmp     eax, 2
0x180062ab7  jnz     short loc_180062AC9
0x180062ab9  mov     [rsp+78h+arg_8], 0Dh
0x180062ac4  jmp     loc_180062BCA
0x180062ac9  or      ecx, 0FFFFFFFFh
0x180062acc  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062ad0  lea     rax, aSsu; "SSU"
0x180062ad7  mov     [rsp+78h+lpString2], rax; lpString2
0x180062adc  mov     r9d, ecx; cchCount1
0x180062adf  mov     r8, [r15+rbx*8]; lpString1
0x180062ae3  lea     edx, [rcx+2]; dwCmpFlags
0x180062ae6  mov     ecx, 409h; Locale
0x180062aeb  call    cs:__imp_CompareStringW
0x180062af2  nop     dword ptr [rax+rax+00h]
0x180062af7  cmp     eax, 2
0x180062afa  jnz     short loc_180062B0C
0x180062afc  mov     [rsp+78h+arg_8], 7
0x180062b07  jmp     loc_180062BCA
0x180062b0c  or      ecx, 0FFFFFFFFh
0x180062b0f  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062b13  lea     rax, aSafeosdu; "SAFEOSDU"
0x180062b1a  mov     [rsp+78h+lpString2], rax; lpString2
0x180062b1f  mov     r9d, ecx; cchCount1
0x180062b22  mov     r8, [r15+rbx*8]; lpString1
0x180062b26  lea     edx, [rcx+2]; dwCmpFlags
0x180062b29  mov     ecx, 409h; Locale
0x180062b2e  call    cs:__imp_CompareStringW
0x180062b35  nop     dword ptr [rax+rax+00h]
0x180062b3a  cmp     eax, 2
0x180062b3d  jnz     short loc_180062B4C
0x180062b3f  mov     [rsp+78h+arg_8], 0Eh
0x180062b4a  jmp     short loc_180062BCA
0x180062b4c  or      ecx, 0FFFFFFFFh
0x180062b4f  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062b53  lea     rax, aGdr; "GDR"
0x180062b5a  mov     [rsp+78h+lpString2], rax; lpString2
0x180062b5f  mov     r9d, ecx; cchCount1
0x180062b62  mov     r8, [r15+rbx*8]; lpString1
0x180062b66  lea     edx, [rcx+2]; dwCmpFlags
0x180062b69  mov     ecx, 409h; Locale
0x180062b6e  call    cs:__imp_CompareStringW
0x180062b75  nop     dword ptr [rax+rax+00h]
0x180062b7a  cmp     eax, 2
0x180062b7d  jnz     short loc_180062B8C
0x180062b7f  mov     [rsp+78h+arg_8], 5
0x180062b8a  jmp     short loc_180062BCA
0x180062b8c  or      ecx, 0FFFFFFFFh
0x180062b8f  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180062b93  lea     rax, String1; "LCU"
0x180062b9a  mov     [rsp+78h+lpString2], rax; lpString2
0x180062b9f  mov     r9d, ecx; cchCount1
0x180062ba2  mov     r8, [r15+rbx*8]; lpString1
0x180062ba6  lea     edx, [rcx+2]; dwCmpFlags
0x180062ba9  mov     ecx, 409h; Locale
0x180062bae  call    cs:__imp_CompareStringW
0x180062bb5  nop     dword ptr [rax+rax+00h]
0x180062bba  cmp     eax, 2
0x180062bbd  jnz     short loc_180062C2C
0x180062bbf  mov     [rsp+78h+arg_8], 6
0x180062bca  mov     rcx, [rsi+258h]
0x180062bd1  test    rcx, rcx
0x180062bd4  jz      short loc_180062BEB
0x180062bd6  mov     r9, [r15+rbx*8]
0x180062bda  lea     r8, aGetpackagecate_0; "GetPackageCategoriesFromString: Adding "...
0x180062be1  mov     edx, 2
0x180062be6  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180062beb  lea     rdx, [rsp+78h+arg_8]
0x180062bf3  lea     rcx, [rsp+78h+var_30]
0x180062bf8  call    ?Append@?$CArray@W4PackageCategory@ActionList@@W412@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBW4PackageCategory@ActionList@@@Z; CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::Append(ActionList::PackageCategory const &)
0x180062bfd  mov     ebx, eax
0x180062bff  test    eax, eax
0x180062c01  jns     short loc_180062C24
0x180062c03  mov     rcx, [rsi+258h]
0x180062c0a  test    rcx, rcx
0x180062c0d  jz      loc_180062855
0x180062c13  mov     [rsp+78h+cchCount2], eax
0x180062c17  mov     dword ptr [rsp+78h+lpString2], 1782h
0x180062c1f  jmp     loc_1800628B4
0x180062c24  inc     r12d
0x180062c27  jmp     loc_18006292C
0x180062c2c  mov     rcx, [rsi+258h]
0x180062c33  test    rcx, rcx
0x180062c36  jz      short loc_180062C4D
0x180062c38  mov     r9, [r15+rbx*8]
0x180062c3c  lea     r8, aGetpackagecate_1; "GetPackageCategoriesFromString: Unexpec"...
0x180062c43  mov     edx, 4
0x180062c48  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180062c4d  mov     rcx, [rsi+258h]
0x180062c54  mov     ebx, 8000FFFFh
0x180062c59  test    rcx, rcx
0x180062c5c  jz      loc_180062855
0x180062c62  mov     [rsp+78h+cchCount2], ebx
0x180062c66  mov     dword ptr [rsp+78h+lpString2], 177Eh
0x180062c6e  jmp     loc_1800628B4
0x180062c73  lea     rdx, [rsp+78h+var_30]
0x180062c78  mov     rcx, [rsp+78h+arg_10]
0x180062c80  call    ?Swap@?$CArray@W4PackageCategory@ActionList@@W412@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAXPEAV1@@Z; CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::Swap(CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault> *)
0x180062c85  mov     ecx, ebx
0x180062c87  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180062c8c  nop
0x180062c8d  xor     edx, edx
0x180062c8f  lea     rcx, [rsp+78h+var_30]
0x180062c94  call    ?SetSize@?$CArray@W4PackageCategory@ActionList@@W412@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180062c99  cmp     [rsp+78h+lpMem], 0
0x180062c9f  jz      short loc_180062CC4
0x180062ca1  call    cs:__imp_GetProcessHeap
0x180062ca8  nop     dword ptr [rax+rax+00h]
0x180062cad  mov     rcx, rax; hHeap
0x180062cb0  mov     r8, [rsp+78h+lpMem]; lpMem
0x180062cb5  xor     edx, edx; dwFlags
0x180062cb7  call    cs:__imp_HeapFree
0x180062cbe  nop     dword ptr [rax+rax+00h]
0x180062cc3  nop
0x180062cc4  xor     edx, edx
0x180062cc6  lea     rcx, [rsp+78h+var_40]
0x180062ccb  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180062cd0  cmp     [rsp+78h+var_38], 0
0x180062cd6  jz      short loc_180062CFA
0x180062cd8  call    cs:__imp_GetProcessHeap
0x180062cdf  nop     dword ptr [rax+rax+00h]
0x180062ce4  mov     rcx, rax; hHeap
0x180062ce7  mov     r8, [rsp+78h+var_38]; lpMem
0x180062cec  xor     edx, edx; dwFlags
0x180062cee  call    cs:__imp_HeapFree
0x180062cf5  nop     dword ptr [rax+rax+00h]
0x180062cfa  mov     eax, ebx
0x180062cfc  jmp     short loc_180062D05
0x180062cfe  mov     eax, [rsp+78h+arg_8]
0x180062d05  lea     r11, [rsp+78h+var_18]
0x180062d0a  mov     rbx, [r11+20h]
0x180062d0e  mov     rsi, [r11+38h]
0x180062d12  mov     rsp, r11
0x180062d15  pop     r15
0x180062d17  pop     r13
0x180062d19  pop     r12
0x180062d1b  retn
```
