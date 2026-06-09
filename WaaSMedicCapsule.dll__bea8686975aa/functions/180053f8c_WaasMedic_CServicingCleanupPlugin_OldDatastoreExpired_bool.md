# WaasMedic::CServicingCleanupPlugin::OldDatastoreExpired(bool &)

- ea: `0x180053f8c`
- end: `0x18005438a`
- name: `?OldDatastoreExpired@CServicingCleanupPlugin@WaasMedic@@QEAAJAEA_N@Z`
- size: `1022`
- prototype: `__int64 __fastcall(WaasMedic::CServicingCleanupPlugin *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180053240`
- `0x180054390`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18000a5d0`
- `0x18000b308`
- `0x1800250e0`
- `0x18002543c`
- `0x180030954`
- `0x1800309a0`
- `0x180053f8c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005407c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054103`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005407c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054103`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005406e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800540f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005406e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800540f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180054331`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180054331`
- `OLEAUT32!__imp_VariantInit` at `0x1800541f7`
- `OLEAUT32!__imp_VariantInit` at `0x1800541f7`
- `OLEAUT32!__imp_VariantClear` at `0x1800542f0`
- `OLEAUT32!__imp_VariantClear` at `0x180054357`
- `OLEAUT32!__imp_VariantClear` at `0x1800542f0`
- `OLEAUT32!__imp_VariantClear` at `0x180054357`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800540ea`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800540ea`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800540cc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800540cc`

## string_xrefs

- `0x180054217`: `StackDataResetPlugin`
- `0x180054111`: `Unable to find .old data stores, nothing to delete.`
- `0x180054098`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x1800541d6`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x180054246`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x1800542d9`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x18005430c`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CServicingCleanupPlugin::OldDatastoreExpired(
        WaasMedic::CServicingCleanupPlugin *this,
        bool *a2,
        unsigned __int16 **a3)
{
  int v5; // eax
  unsigned int v6; // edi
  void *v7; // rbx
  int v8; // eax
  HANDLE v9; // rax
  char *FirstFileW; // rax
  __int64 v12; // rdi
  bool v13; // r14
  HANDLE ProcessHeap; // rax
  __int64 (__fastcall ***v15)(_QWORD, _BYTE *, _OWORD *, _DWORD *); // rbx
  __int64 (__fastcall *v16)(_QWORD, _BYTE *, _OWORD *, _DWORD *); // r14
  __int64 v17; // rdx
  int v18; // ebx
  unsigned int v19; // edi
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h]
  char *v22; // [rsp+28h] [rbp-D8h]
  char *v23; // [rsp+28h] [rbp-D8h]
  bool v24; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v27; // [rsp+58h] [rbp-A8h]
  struct _FILETIME v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pvarg[32]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v30[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[264]; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  *a2 = 0;
  lpMem = 0;
  v5 = WaasMedic::SafeExpandEnvironmentString(
         L"%windir%\\SoftwareDistribution\\DataStore",
         (const unsigned __int16 *)&lpMem,
         a3);
  v6 = v5;
  if ( v5 >= 0 )
  {
    memset_0(FileName, 0, 0x208u);
    v7 = lpMem;
    v8 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", lpMem);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
        (const char *)(unsigned int)v8,
        (int)L"*.old");
      goto LABEL_5;
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
    v12 = -1;
    v13 = FirstFileW != (char *)-1LL;
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(FirstFileW);
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
    if ( !v13 )
    {
      *a2 = 0;
      LogLevelW(4u, L"Unable to find .old data stores, nothing to delete.");
      return 0;
    }
    v27 = 0;
    v26[0] = 90;
    v26[1] = 2;
    v15 = (__int64 (__fastcall ***)(_QWORD, _BYTE *, _OWORD *, _DWORD *))*((_QWORD *)this + 13);
    v16 = **v15;
    memset(v30, 0, sizeof(v30));
    std::wstring::_Construct<1,unsigned short const *>(v30, L"ThresholdCleanupDSINDays", 24);
    v17 = *((_QWORD *)this + 14);
    memset(pvarg, 0, sizeof(pvarg));
    do
      ++v12;
    while ( *(_WORD *)(v17 + 2 * v12) );
    std::wstring::_Construct<1,unsigned short const *>(pvarg, v17, v12);
    v18 = v16(v15, pvarg, v30, v26);
    std::wstring::~wstring(pvarg);
    std::wstring::~wstring(v30);
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x201,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
        (const char *)(unsigned int)v18,
        (int)L"*.old");
      return (unsigned int)v18;
    }
    v19 = v26[0];
    VariantInit((VARIANTARG *)pvarg);
    *a2 = 0;
    v18 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const char *, _BYTE *))(**((_QWORD **)this + 12) + 16LL))(
            *((_QWORD *)this + 12),
            L"StackDataResetPlugin",
            L"LastRemediationRunTime",
            pvarg);
    if ( v18 < 0 )
    {
      v20 = 530;
LABEL_21:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
        (const char *)(unsigned int)v18,
        (int)"Failed to retrieve %ws for %ws from state provider",
        L"LastRemediationRunTime",
        L"StackDataResetPlugin");
LABEL_28:
      VariantClear((VARIANTARG *)pvarg);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
        (const char *)(unsigned int)v18,
        (int)"Failed to determine if threshold to erase datastore has been passed",
        v23);
      return (unsigned int)v18;
    }
    if ( *(_WORD *)pvarg )
    {
      if ( *(_WORD *)pvarg != 8 )
      {
        v18 = -2147024292;
        v20 = 542;
        goto LABEL_21;
      }
      v28 = 0;
      v18 = WaasMedic::TimeHelper::StringToFileTime(*(const unsigned __int16 **)&pvarg[8], &v28);
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x224,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
          (const char *)(unsigned int)v18,
          (int)"Failed to convert time string %ws to FILETIME",
          *(const char **)&pvarg[8]);
        goto LABEL_28;
      }
      lpMem = 0;
      v24 = 0;
      GetSystemTimeAsFileTime((LPFILETIME)&lpMem);
      *a2 = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v28, (struct _FILETIME)lpMem, &v24) >= v19;
    }
    else
    {
      *a2 = 0;
      LogLevelW(4u, L"variant for last remediation run time is empty");
    }
    VariantClear((VARIANTARG *)pvarg);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x225,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
    (const char *)(unsigned int)v5,
    v21);
  v7 = lpMem;
LABEL_5:
  if ( v7 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x1F7,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
    (const char *)v6,
    (int)"Failed to determine if .old datastore exists",
    v22);
  return v6;
}

```

## disassembly

```asm
0x180053f8c  mov     [rsp-8+arg_10], rbx
0x180053f91  mov     [rsp-8+arg_18], rsi
0x180053f96  push    rbp
0x180053f97  push    rdi
0x180053f98  push    r12
0x180053f9a  push    r14
0x180053f9c  push    r15
0x180053f9e  lea     rbp, [rsp-420h]
0x180053fa6  sub     rsp, 520h
0x180053fad  mov     rax, cs:__security_cookie
0x180053fb4  xor     rax, rsp
0x180053fb7  mov     [rbp+440h+var_30], rax
0x180053fbe  mov     rsi, rdx
0x180053fc1  mov     r15, rcx
0x180053fc4  xor     r12d, r12d
0x180053fc7  mov     [rdx], r12b
0x180053fca  mov     [rsp+540h+lpMem], r12
0x180053fcf  lea     rdx, [rsp+540h+lpMem]; unsigned __int16 *
0x180053fd4  lea     rcx, aWindirSoftware_0; "%windir%\\SoftwareDistribution\\DataSto"...
0x180053fdb  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x180053fe0  mov     edi, eax
0x180053fe2  test    eax, eax
0x180053fe4  jns     short loc_180054008
0x180053fe6  mov     rcx, [rbp+448h]; this
0x180053fed  mov     r9d, eax; char *
0x180053ff0  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180053ff7  mov     edx, 225h; void *
0x180053ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054001  mov     rbx, [rsp+540h+lpMem]
0x180054006  jmp     short loc_180054069
0x180054008  xor     edx, edx; Val
0x18005400a  mov     r8d, 208h; Size
0x180054010  lea     rcx, [rbp+440h+FileName]; void *
0x180054017  call    memset_0
0x18005401c  lea     rax, aOld; "*.old"
0x180054023  mov     qword ptr [rsp+540h+var_520], rax; int
0x180054028  mov     rbx, [rsp+540h+lpMem]
0x18005402d  mov     r9, rbx
0x180054030  lea     r8, aSS; "%s\\%s"
0x180054037  mov     edx, 104h; unsigned __int64
0x18005403c  lea     rcx, [rbp+440h+FileName]; unsigned __int16 *
0x180054043  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054048  mov     edi, eax
0x18005404a  test    eax, eax
0x18005404c  jns     short loc_1800540B0
0x18005404e  mov     rcx, [rbp+448h]; this
0x180054055  mov     r9d, eax; char *
0x180054058  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005405f  mov     edx, 228h; void *
0x180054064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054069  test    rbx, rbx
0x18005406c  jz      short loc_180054082
0x18005406e  call    cs:__imp_GetProcessHeap
0x180054074  mov     r8, rbx; lpMem
0x180054077  xor     edx, edx; dwFlags
0x180054079  mov     rcx, rax; hHeap
0x18005407c  call    cs:__imp_HeapFree
0x180054082  mov     rcx, [rbp+448h]; this
0x180054089  lea     rax, aFailedToDeterm_2; "Failed to determine if .old datastore e"...
0x180054090  mov     qword ptr [rsp+540h+var_520], rax; int
0x180054095  mov     r9d, edi; char *
0x180054098  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18005409f  mov     edx, 1F7h; void *
0x1800540a4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800540a9  mov     eax, edi
0x1800540ab  jmp     loc_18005435F
0x1800540b0  xor     edx, edx; Val
0x1800540b2  mov     r8d, 250h; Size
0x1800540b8  lea     rcx, [rbp+440h+FindFileData]; void *
0x1800540bc  call    memset_0
0x1800540c1  lea     rdx, [rbp+440h+FindFileData]; lpFindFileData
0x1800540c5  lea     rcx, [rbp+440h+FileName]; lpFileName
0x1800540cc  call    cs:__imp_FindFirstFileW
0x1800540d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800540d6  cmp     rax, rdi
0x1800540d9  setnz   r14b
0x1800540dd  lea     rcx, [rax-1]
0x1800540e1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800540e5  ja      short loc_1800540F0
0x1800540e7  mov     rcx, rax; hFindFile
0x1800540ea  call    cs:__imp_FindClose
0x1800540f0  test    rbx, rbx
0x1800540f3  jz      short loc_180054109
0x1800540f5  call    cs:__imp_GetProcessHeap
0x1800540fb  mov     rcx, rax; hHeap
0x1800540fe  mov     r8, rbx; lpMem
0x180054101  xor     edx, edx; dwFlags
0x180054103  call    cs:__imp_HeapFree
0x180054109  test    r14b, r14b
0x18005410c  jnz     short loc_180054127
0x18005410e  mov     [rsi], r12b
0x180054111  lea     rdx, aUnableToFindOl; "Unable to find .old data stores, nothin"...
0x180054118  mov     ecx, 4; unsigned __int8
0x18005411d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180054122  jmp     loc_18005435D
0x180054127  mov     [rsp+540h+var_4E8], r12b
0x18005412c  mov     [rsp+540h+var_4F0], 5Ah ; 'Z'
0x180054134  mov     [rsp+540h+var_4EC], 2
0x18005413c  mov     rbx, [r15+68h]
0x180054140  mov     rax, [rbx]
0x180054143  mov     r14, [rax]
0x180054146  xorps   xmm0, xmm0
0x180054149  movups  [rbp+440h+var_4B8], xmm0
0x18005414d  xorps   xmm1, xmm1
0x180054150  movdqu  [rbp+440h+var_4A8], xmm1
0x180054155  mov     r8d, 18h
0x18005415b  lea     rdx, aThresholdclean; "ThresholdCleanupDSINDays"
0x180054162  lea     rcx, [rbp+440h+var_4B8]
0x180054166  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005416b  nop
0x18005416c  mov     rdx, [r15+70h]
0x180054170  xorps   xmm0, xmm0
0x180054173  movups  xmmword ptr [rsp+540h+pvarg], xmm0
0x180054178  xorps   xmm1, xmm1
0x18005417b  movdqu  xmmword ptr [rsp+540h+pvarg+10h], xmm1
0x180054181  inc     rdi
0x180054184  cmp     [rdx+rdi*2], r12w
0x180054189  jnz     short loc_180054181
0x18005418b  mov     r8, rdi
0x18005418e  lea     rcx, [rsp+540h+pvarg]
0x180054193  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180054198  nop
0x180054199  lea     r9, [rsp+540h+var_4F0]
0x18005419e  lea     r8, [rbp+440h+var_4B8]
0x1800541a2  lea     rdx, [rsp+540h+pvarg]
0x1800541a7  mov     rcx, rbx
0x1800541aa  mov     rax, r14
0x1800541ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541b2  mov     ebx, eax
0x1800541b4  lea     rcx, [rsp+540h+pvarg]; void *
0x1800541b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800541be  nop
0x1800541bf  lea     rcx, [rbp+440h+var_4B8]; void *
0x1800541c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800541c8  test    ebx, ebx
0x1800541ca  jns     short loc_1800541EE
0x1800541cc  mov     rcx, [rbp+448h]; this
0x1800541d3  mov     r9d, ebx; char *
0x1800541d6  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800541dd  mov     edx, 201h; void *
0x1800541e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800541e7  mov     eax, ebx
0x1800541e9  jmp     loc_18005435F
0x1800541ee  mov     edi, [rsp+540h+var_4F0]
0x1800541f2  lea     rcx, [rsp+540h+pvarg]; pvarg
0x1800541f7  call    cs:__imp_VariantInit
0x1800541fd  nop
0x1800541fe  mov     [rsi], r12b
0x180054201  mov     rcx, [r15+60h]
0x180054205  mov     rax, [rcx]
0x180054208  lea     r9, [rsp+540h+pvarg]
0x18005420d  lea     r15, aLastremediatio; "LastRemediationRunTime"
0x180054214  mov     r8, r15
0x180054217  lea     r14, aStackdatareset; "StackDataResetPlugin"
0x18005421e  mov     rdx, r14
0x180054221  mov     rax, [rax+10h]
0x180054225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005422a  mov     ebx, eax
0x18005422c  test    eax, eax
0x18005422e  jns     short loc_180054266
0x180054230  mov     edx, 212h; void *
0x180054235  mov     [rsp+540h+var_510], r14
0x18005423a  mov     [rsp+540h+var_518], r15; char *
0x18005423f  lea     rax, aFailedToRetrie_0; "Failed to retrieve %ws for %ws from sta"...
0x180054246  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18005424d  mov     r9d, ebx; char *
0x180054250  mov     qword ptr [rsp+540h+var_520], rax; int
0x180054255  mov     rcx, [rbp+448h]; this
0x18005425c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054261  jmp     loc_1800542EB
0x180054266  movzx   eax, word ptr [rsp+540h+pvarg]
0x18005426b  test    ax, ax
0x18005426e  jnz     short loc_180054289
0x180054270  mov     [rsi], r12b
0x180054273  lea     rdx, aVariantForLast; "variant for last remediation run time i"...
0x18005427a  mov     ecx, 4; unsigned __int8
0x18005427f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180054284  jmp     loc_180054352
0x180054289  mov     ecx, 8
0x18005428e  cmp     cx, ax
0x180054291  jz      short loc_18005429F
0x180054293  mov     ebx, 8007025Ch
0x180054298  mov     edx, 21Eh
0x18005429d  jmp     short loc_180054235
0x18005429f  mov     qword ptr [rsp+540h+var_4E0.dwLowDateTime], r12
0x1800542a4  lea     rdx, [rsp+540h+var_4E0]; struct _FILETIME *
0x1800542a9  mov     rcx, qword ptr [rsp+540h+pvarg+8]; unsigned __int16 *
0x1800542ae  call    ?StringToFileTime@TimeHelper@WaasMedic@@SAJPEBGPEAU_FILETIME@@@Z; WaasMedic::TimeHelper::StringToFileTime(ushort const *,_FILETIME *)
0x1800542b3  mov     ebx, eax
0x1800542b5  test    eax, eax
0x1800542b7  jns     short loc_180054322
0x1800542b9  mov     rcx, [rbp+448h]; this
0x1800542c0  mov     rax, qword ptr [rsp+540h+pvarg+8]
0x1800542c5  mov     [rsp+540h+var_518], rax; char *
0x1800542ca  lea     rax, aFailedToConver_3; "Failed to convert time string %ws to FI"...
0x1800542d1  mov     qword ptr [rsp+540h+var_520], rax; int
0x1800542d6  mov     r9d, ebx; char *
0x1800542d9  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800542e0  mov     edx, 224h; void *
0x1800542e5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800542ea  nop
0x1800542eb  lea     rcx, [rsp+540h+pvarg]; pvarg
0x1800542f0  call    cs:__imp_VariantClear
0x1800542f6  mov     rcx, [rbp+448h]; this
0x1800542fd  lea     rax, aFailedToDeterm_0; "Failed to determine if threshold to era"...
0x180054304  mov     qword ptr [rsp+540h+var_520], rax; int
0x180054309  mov     r9d, ebx; char *
0x18005430c  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180054313  mov     edx, 205h; void *
0x180054318  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005431d  jmp     loc_1800541E7
0x180054322  mov     [rsp+540h+lpMem], r12
0x180054327  mov     [rsp+540h+var_500], r12b
0x18005432c  lea     rcx, [rsp+540h+lpMem]; lpSystemTimeAsFileTime
0x180054331  call    cs:__imp_GetSystemTimeAsFileTime
0x180054337  lea     r8, [rsp+540h+var_500]; bool *
0x18005433c  mov     rdx, [rsp+540h+lpMem]; struct _FILETIME
0x180054341  mov     rcx, qword ptr [rsp+540h+var_4E0.dwLowDateTime]; struct _FILETIME
0x180054346  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x18005434b  cmp     eax, edi
0x18005434d  setnb   al
0x180054350  mov     [rsi], al
0x180054352  lea     rcx, [rsp+540h+pvarg]; pvarg
0x180054357  call    cs:__imp_VariantClear
0x18005435d  xor     eax, eax
0x18005435f  mov     rcx, [rbp+440h+var_30]
0x180054366  xor     rcx, rsp; StackCookie
0x180054369  call    __security_check_cookie
0x18005436e  lea     r11, [rsp+540h+var_20]
0x180054376  mov     rbx, [r11+40h]
0x18005437a  mov     rsi, [r11+48h]
0x18005437e  mov     rsp, r11
0x180054381  pop     r15
0x180054383  pop     r14
0x180054385  pop     r12
0x180054387  pop     rdi
0x180054388  pop     rbp
0x180054389  retn
```
