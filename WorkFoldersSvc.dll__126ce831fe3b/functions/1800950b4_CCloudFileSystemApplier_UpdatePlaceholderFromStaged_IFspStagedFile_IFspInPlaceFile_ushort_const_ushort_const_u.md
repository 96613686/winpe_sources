# CCloudFileSystemApplier::UpdatePlaceholderFromStaged(IFspStagedFile *,IFspInPlaceFile *,ushort const *,ushort const *,ulong,int,IFileConcurrencyBlob * *,IFileConcurrencyBlob * *)

- ea: `0x1800950b4`
- end: `0x180095748`
- name: `?UpdatePlaceholderFromStaged@CCloudFileSystemApplier@@AEAAJPEAUIFspStagedFile@@PEAUIFspInPlaceFile@@PEBG2KHPEAPEAUIFileConcurrencyBlob@@3@Z`
- size: `1684`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IFspStagedFile *, struct IFspInPlaceFile *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, struct IFileConcurrencyBlob **, struct IFileConcurrencyBlob **)`
- caller_count: `5`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008c670`
- `0x18008d7f0`
- `0x18008faa4`
- `0x180094880`
- `0x180094de0`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x18002db48`
- `0x180058d88`
- `0x18008c2d0`
- `0x18008d358`
- `0x180094118`
- `0x1800950b4`
- `0x180095750`
- `0x1800963d0`
- `0x180098914`
- `0x180098eec`
- `0x1800995ec`
- `0x180099e00`
- `0x18009a0e0`
- `0x1800bb594`
- `0x1800bb748`
- `0x1800bb948`
- `0x18013e010`

## import_xrefs

- `ADVAPI32!DecryptFileW` at `0x1800954cf`
- `ADVAPI32!DecryptFileW` at `0x180095503`
- `ADVAPI32!DecryptFileW` at `0x1800954cf`
- `ADVAPI32!DecryptFileW` at `0x180095503`
- `ntdll!NtClose` at `0x1800953fb`
- `ntdll!NtClose` at `0x1800956d7`
- `ntdll!NtClose` at `0x1800956e6`
- `ntdll!NtClose` at `0x1800953fb`
- `ntdll!NtClose` at `0x1800956d7`
- `ntdll!NtClose` at `0x1800956e6`
- `KERNELBASE!ReplaceFileExInternal` at `0x18009558e`
- `KERNELBASE!ReplaceFileExInternal` at `0x18009558e`

## string_xrefs

- `0x180095141`: `CCloudFileSystemApplier::UpdatePlaceholderFromStaged`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CCloudFileSystemApplier::UpdatePlaceholderFromStaged(
        const unsigned __int16 **this,
        struct IFspStagedFile *a2,
        struct IFspInPlaceFile *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        int a7,
        struct IFileConcurrencyBlob **a8,
        struct IFileConcurrencyBlob **a9)
{
  _DWORD *v13; // rax
  char v14; // cl
  struct IFileConcurrencyBlob **v15; // r12
  __int16 v16; // ax
  unsigned int v17; // r8d
  const WCHAR *v18; // r15
  bool v19; // sf
  const WCHAR *v20; // r14
  HANDLE v21; // rbx
  __int16 v22; // ax
  unsigned int v23; // edx
  unsigned int v24; // esi
  int v25; // edx
  CCloudFileSystemApplier *v26; // rcx
  unsigned int v27; // r9d
  __int16 v28; // ax
  unsigned int v29; // ebx
  unsigned int v31; // [rsp+20h] [rbp-91h]
  int AbsoluteFileName; // [rsp+50h] [rbp-61h] BYREF
  int v33; // [rsp+54h] [rbp-5Dh]
  char v34; // [rsp+58h] [rbp-59h]
  const char *v35; // [rsp+60h] [rbp-51h]
  __int64 v36; // [rsp+68h] [rbp-49h]
  PCWSTR SourceString; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int16 *v38; // [rsp+78h] [rbp-39h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-31h] BYREF
  HANDLE v40; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int16 *v41; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int16 *v42; // [rsp+98h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp-11h] BYREF
  void *v44[9]; // [rsp+A8h] [rbp-9h] BYREF

  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
  }
  if ( (v13[17] & 0x100) != 0 && *((_BYTE *)v13 + 65) >= 6u )
  {
    v14 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v14 = 0;
LABEL_9:
  AbsoluteFileName = 0;
  v33 = 1378;
  v34 = v14;
  v35 = "CCloudFileSystemApplier::UpdatePlaceholderFromStaged";
  v36 = 0;
  SourceString = 0;
  lpFileName = 0;
  v42 = 0;
  v41 = 0;
  a6 = 0;
  Handle = 0;
  v40 = 0;
  v44[0] = 0;
  if ( a8 )
    *a8 = 0;
  v15 = a9;
  if ( a9 )
    *a9 = 0;
  v16 = 1393;
  if ( !a2 )
  {
    AbsoluteFileName = -2147024809;
LABEL_15:
    HIWORD(v33) = v16;
    goto LABEL_68;
  }
  AbsoluteFileName = 0;
  LOWORD(v33) = 1393;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[3], a2, &v42);
  v16 = 1396;
  if ( AbsoluteFileName < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1396;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[4], a2, &v41);
  v16 = 1397;
  if ( AbsoluteFileName < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1397;
  if ( a4 )
  {
    AbsoluteFileName = CPathUtilities::GetNormalizedNtPath(a4, (unsigned __int16 **)&SourceString);
    v16 = 1401;
    if ( AbsoluteFileName < 0 )
      goto LABEL_15;
    LOWORD(v33) = 1401;
    v18 = SourceString;
    AbsoluteFileName = CPathUtilities::GetNormalizedWin32Path(a4, (unsigned __int16 **)&lpFileName);
    v19 = AbsoluteFileName < 0;
    v16 = 1403;
  }
  else
  {
    if ( !a3 )
    {
      v18 = v42;
      v20 = v41;
      goto LABEL_27;
    }
    AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[3], a3, (unsigned __int16 **)&SourceString);
    v16 = 1411;
    if ( AbsoluteFileName < 0 )
      goto LABEL_15;
    LOWORD(v33) = 1411;
    v18 = SourceString;
    AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[4], a3, (unsigned __int16 **)&lpFileName);
    v19 = AbsoluteFileName < 0;
    v16 = 1413;
  }
  if ( v19 )
    goto LABEL_15;
  LOWORD(v33) = v16;
  v20 = lpFileName;
LABEL_27:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      32,
      (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
      (_DWORD)SourceString,
      (__int64)v42);
  }
  AbsoluteFileName = CFspCloudFileSystemOperations::CreateFileW(v18, 0x120181u, v17, 0, 0x20u, 1u, 8u, &Handle);
  v21 = Handle;
  v22 = 1435;
  if ( AbsoluteFileName < 0 )
    goto LABEL_32;
  LOWORD(v33) = 1435;
  AbsoluteFileName = CFspCloudFileSystemOperations::GetAttributes(Handle, &a6);
  v22 = 1439;
  if ( AbsoluteFileName < 0 )
    goto LABEL_32;
  LOWORD(v33) = 1439;
  v24 = a6 & 0x186800 | 0x20;
  AbsoluteFileName = CFspCloudFileSystemOperations::GetSecurity(v21, v23, v44);
  v22 = 1448;
  if ( AbsoluteFileName < 0 )
    goto LABEL_32;
  LOWORD(v33) = 1448;
  if ( a3 )
  {
    AbsoluteFileName = CCloudFileSystemApplier::ValidateFileUnchangedAndNotUnderDownload(
                         (CCloudFileSystemApplier *)this,
                         v21,
                         v18,
                         a3);
    v22 = 1454;
    if ( AbsoluteFileName < 0 )
    {
LABEL_32:
      HIWORD(v33) = v22;
LABEL_66:
      if ( v21 )
        NtClose(v21);
      goto LABEL_68;
    }
    LOWORD(v33) = 1454;
  }
  AbsoluteFileName = CFspCloudFileSystemOperations::ClearReadOnly(v21);
  v22 = 1458;
  if ( AbsoluteFileName < 0 )
    goto LABEL_32;
  LOWORD(v33) = 1458;
  NtClose(v21);
  v21 = 0;
  a9 = 0;
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspStagedFile *, struct IFileConcurrencyBlob ***))(*(_QWORD *)a2 + 104LL))(
                       a2,
                       &a9);
  v16 = 1474;
  if ( AbsoluteFileName < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1474;
  a6 = 0;
  v25 = (*(__int64 (__fastcall **)(struct IFspStagedFile *, unsigned int *))(*(_QWORD *)a2 + 40LL))(a2, &a6);
  AbsoluteFileName = v25;
  v16 = 1483;
  if ( v25 < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1483;
  if ( (a6 & 4) != 0 && (v24 & 0x4000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        33,
        (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
        (_DWORD)v20,
        (__int64)a9);
      v25 = AbsoluteFileName;
    }
    AbsoluteFileName = v25;
    if ( !DecryptFileW(v20, 0) )
    {
      AbsoluteFileName = EcsGetLastFailureAsHRESULT();
      v16 = 1494;
      goto LABEL_15;
    }
    LOWORD(v33) = 1494;
    AbsoluteFileName = 0;
    if ( !DecryptFileW((LPCWSTR)a9, 0) )
    {
      AbsoluteFileName = EcsGetLastFailureAsHRESULT();
      v16 = 1495;
      goto LABEL_15;
    }
    v25 = 0;
    AbsoluteFileName = 0;
    LOWORD(v33) = 1495;
    v24 &= ~0x4000u;
  }
  if ( a5 && v15 )
  {
    v25 = CFspCloudFileSystemOperations::OpenFileAttribute(v18, &v40);
    AbsoluteFileName = v25;
    v16 = 1508;
    if ( v25 < 0 )
      goto LABEL_15;
    LOWORD(v33) = 1508;
  }
  AbsoluteFileName = v25;
  if ( !(unsigned int)ReplaceFileExInternal(v20, a9, a5, 0, 8, 8, 0, 0) )
  {
    AbsoluteFileName = EcsGetLastFailureAsHRESULT();
    v16 = 1523;
    goto LABEL_15;
  }
  LOWORD(v33) = 1523;
  AbsoluteFileName = CCloudFileSystemApplier::SetSecurity(v26, v18, v44[0], v27, v31);
  v16 = 1528;
  if ( AbsoluteFileName < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1528;
  AbsoluteFileName = (*((__int64 (__fastcall **)(char *, const WCHAR *, _QWORD, _QWORD, _QWORD))this[2] + 3))(
                       (char *)this + 16,
                       v18,
                       0,
                       v24,
                       0);
  v16 = 1531;
  if ( AbsoluteFileName < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1531;
  AbsoluteFileName = CCloudFileSystemApplier::UpdatePlaceholderInPlace(
                       (CCloudFileSystemApplier *)this,
                       a2,
                       0,
                       v20,
                       v41,
                       v24,
                       8u,
                       a7,
                       a8);
  v16 = 1542;
  if ( AbsoluteFileName < 0 )
    goto LABEL_15;
  LOWORD(v33) = 1542;
  if ( a5 && v15 )
  {
    v38 = 0;
    AbsoluteFileName = CPathUtilities::GetNormalizedNtPath(a5, &v38);
    v28 = 1548;
    if ( AbsoluteFileName < 0
      || (LOWORD(v33) = 1548,
          AbsoluteFileName = CCloudFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(
                               (CCloudFileSystemApplier *)this,
                               &v40,
                               v38,
                               0,
                               v15),
          v28 = 1549,
          AbsoluteFileName < 0) )
    {
      HIWORD(v33) = v28;
      CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v38);
      goto LABEL_68;
    }
    LOWORD(v33) = 1549;
    CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v38);
    goto LABEL_66;
  }
LABEL_68:
  if ( v40 )
  {
    NtClose(v40);
    v40 = 0;
  }
  v29 = AbsoluteFileName;
  CEcsMemPtr<unsigned char,0>::~CEcsMemPtr<unsigned char,0>(v44);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v41);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v42);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&lpFileName);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&AbsoluteFileName);
  return v29;
}

```

## disassembly

```asm
0x1800950b4  mov     [rsp-8+arg_8], rdx
0x1800950b9  push    rbp
0x1800950ba  push    rbx
0x1800950bb  push    rsi
0x1800950bc  push    rdi
0x1800950bd  push    r12
0x1800950bf  push    r13
0x1800950c1  push    r14
0x1800950c3  push    r15
0x1800950c5  lea     rbp, [rsp-7]
0x1800950ca  sub     rsp, 0B8h
0x1800950d1  mov     rbx, r9
0x1800950d4  mov     rdi, r8
0x1800950d7  mov     rsi, rdx
0x1800950da  mov     r13, rcx
0x1800950dd  lea     rcx, WPP_GLOBAL_Control
0x1800950e4  mov     r14d, 100h
0x1800950ea  mov     rax, cs:WPP_GLOBAL_Control
0x1800950f1  cmp     rax, rcx
0x1800950f4  jz      short loc_18009511E
0x1800950f6  test    [rax+44h], r14d
0x1800950fa  jz      short loc_18009512E
0x1800950fc  cmp     byte ptr [rax+41h], 6
0x180095100  jb      short loc_18009511E
0x180095102  mov     edx, 1Fh
0x180095107  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18009510e  mov     rcx, [rax+38h]
0x180095112  call    WPP_SF_
0x180095117  mov     rax, cs:WPP_GLOBAL_Control
0x18009511e  test    [rax+44h], r14d
0x180095122  jz      short loc_18009512E
0x180095124  cmp     byte ptr [rax+41h], 6
0x180095128  jb      short loc_18009512E
0x18009512a  mov     cl, 1
0x18009512c  jmp     short loc_180095130
0x18009512e  xor     cl, cl
0x180095130  mov     [rbp+3Fh+var_A0], 0
0x180095137  mov     [rbp+3Fh+var_9C], 562h
0x18009513e  mov     [rbp+3Fh+var_98], cl
0x180095141  lea     rax, aCcloudfilesyst_6; "CCloudFileSystemApplier::UpdatePlacehol"...
0x180095148  mov     [rbp+3Fh+var_90], rax
0x18009514c  mov     [rbp+3Fh+var_88], 0
0x180095154  mov     [rbp+3Fh+SourceString], 0
0x18009515c  mov     [rbp+3Fh+lpFileName], 0
0x180095164  mov     [rbp+3Fh+var_58], 0
0x18009516c  mov     [rbp+3Fh+var_60], 0
0x180095174  mov     [rbp+3Fh+arg_28], 0
0x18009517b  mov     [rbp+3Fh+Handle], 0
0x180095183  mov     [rbp+3Fh+var_68], 0
0x18009518b  mov     [rbp+3Fh+var_48], 0
0x180095193  mov     rax, [rbp+3Fh+arg_38]
0x18009519a  test    rax, rax
0x18009519d  jz      short loc_1800951A6
0x18009519f  mov     qword ptr [rax], 0
0x1800951a6  mov     r12, [rbp+3Fh+arg_40]
0x1800951ad  test    r12, r12
0x1800951b0  jz      short loc_1800951BA
0x1800951b2  mov     qword ptr [r12], 0
0x1800951ba  mov     eax, [rbp+3Fh+var_A0]
0x1800951bd  mov     [rbp+3Fh+var_A0], eax
0x1800951c0  mov     eax, 571h
0x1800951c5  test    rsi, rsi
0x1800951c8  jnz     short loc_1800951DA
0x1800951ca  mov     [rbp+3Fh+var_A0], 80070057h
0x1800951d1  mov     word ptr [rbp+3Fh+var_9C+2], ax
0x1800951d5  jmp     loc_1800956DD
0x1800951da  mov     [rbp+3Fh+var_A0], 0
0x1800951e1  mov     word ptr [rbp+3Fh+var_9C], ax
0x1800951e5  lea     r8, [rbp+3Fh+var_58]; unsigned __int16 **
0x1800951e9  mov     rdx, rsi; struct IFspFile *
0x1800951ec  mov     rcx, [r13+18h]; unsigned __int16 *
0x1800951f0  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x1800951f5  mov     [rbp+3Fh+var_A0], eax
0x1800951f8  mov     [rbp+3Fh+var_A0], eax
0x1800951fb  test    eax, eax
0x1800951fd  mov     eax, 574h
0x180095202  js      short loc_1800951D1
0x180095204  mov     word ptr [rbp+3Fh+var_9C], ax
0x180095208  lea     r8, [rbp+3Fh+var_60]; unsigned __int16 **
0x18009520c  mov     rdx, rsi; struct IFspFile *
0x18009520f  mov     rcx, [r13+20h]; unsigned __int16 *
0x180095213  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x180095218  mov     [rbp+3Fh+var_A0], eax
0x18009521b  mov     [rbp+3Fh+var_A0], eax
0x18009521e  test    eax, eax
0x180095220  mov     eax, 575h
0x180095225  js      short loc_1800951D1
0x180095227  mov     word ptr [rbp+3Fh+var_9C], ax
0x18009522b  test    rbx, rbx
0x18009522e  jz      short loc_18009527C
0x180095230  lea     rdx, [rbp+3Fh+SourceString]; unsigned __int16 **
0x180095234  mov     rcx, rbx; unsigned __int16 *
0x180095237  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x18009523c  mov     [rbp+3Fh+var_A0], eax
0x18009523f  mov     [rbp+3Fh+var_A0], eax
0x180095242  test    eax, eax
0x180095244  mov     eax, 579h
0x180095249  js      short loc_1800951D1
0x18009524b  mov     word ptr [rbp+3Fh+var_9C], ax
0x18009524f  mov     r15, [rbp+3Fh+SourceString]
0x180095253  lea     rdx, [rbp+3Fh+lpFileName]; unsigned __int16 **
0x180095257  mov     rcx, rbx; FileName
0x18009525a  call    ?GetNormalizedWin32Path@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedWin32Path(ushort const *,ushort * *)
0x18009525f  mov     [rbp+3Fh+var_A0], eax
0x180095262  mov     [rbp+3Fh+var_A0], eax
0x180095265  test    eax, eax
0x180095267  mov     eax, 57Bh
0x18009526c  js      loc_1800951D1
0x180095272  mov     word ptr [rbp+3Fh+var_9C], ax
0x180095276  mov     r14, [rbp+3Fh+lpFileName]
0x18009527a  jmp     short loc_1800952D3
0x18009527c  test    rdi, rdi
0x18009527f  jz      short loc_1800952CB
0x180095281  lea     r8, [rbp+3Fh+SourceString]; unsigned __int16 **
0x180095285  mov     rdx, rdi; struct IFspFile *
0x180095288  mov     rcx, [r13+18h]; unsigned __int16 *
0x18009528c  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x180095291  mov     [rbp+3Fh+var_A0], eax
0x180095294  mov     [rbp+3Fh+var_A0], eax
0x180095297  test    eax, eax
0x180095299  mov     eax, 583h
0x18009529e  js      loc_1800951D1
0x1800952a4  mov     word ptr [rbp+3Fh+var_9C], ax
0x1800952a8  mov     r15, [rbp+3Fh+SourceString]
0x1800952ac  lea     r8, [rbp+3Fh+lpFileName]; unsigned __int16 **
0x1800952b0  mov     rdx, rdi; struct IFspFile *
0x1800952b3  mov     rcx, [r13+20h]; unsigned __int16 *
0x1800952b7  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x1800952bc  mov     [rbp+3Fh+var_A0], eax
0x1800952bf  mov     [rbp+3Fh+var_A0], eax
0x1800952c2  test    eax, eax
0x1800952c4  mov     eax, 585h
0x1800952c9  jmp     short loc_18009526C
0x1800952cb  mov     r15, [rbp+3Fh+var_58]
0x1800952cf  mov     r14, [rbp+3Fh+var_60]
0x1800952d3  mov     ebx, 20h ; ' '
0x1800952d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800952df  lea     rax, WPP_GLOBAL_Control
0x1800952e6  cmp     rcx, rax
0x1800952e9  jz      short loc_180095319
0x1800952eb  test    dword ptr [rcx+44h], 100h
0x1800952f2  jz      short loc_180095319
0x1800952f4  cmp     byte ptr [rcx+41h], 4
0x1800952f8  jb      short loc_180095319
0x1800952fa  mov     edx, ebx
0x1800952fc  mov     rax, [rbp+3Fh+var_58]
0x180095300  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180095305  mov     r9, [rbp+3Fh+SourceString]
0x180095309  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x180095310  mov     rcx, [rcx+38h]
0x180095314  call    WPP_SF_SS
0x180095319  lea     rax, [rbp+3Fh+Handle]
0x18009531d  mov     [rsp+0F0h+var_B8], rax; void **
0x180095322  mov     [rsp+0F0h+var_C0], 8; unsigned int
0x18009532a  mov     [rsp+0F0h+var_C8], 1; ULONG
0x180095332  mov     [rsp+0F0h+var_D0], ebx; ULONG
0x180095336  xor     r9d, r9d; unsigned int
0x180095339  mov     edx, 120181h; DesiredAccess
0x18009533e  mov     rcx, r15; SourceString
0x180095341  call    ?CreateFileW@CFspCloudFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspCloudFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x180095346  mov     [rbp+3Fh+var_A0], eax
0x180095349  mov     [rbp+3Fh+var_A0], eax
0x18009534c  mov     rbx, [rbp+3Fh+Handle]
0x180095350  test    eax, eax
0x180095352  mov     eax, 59Bh
0x180095357  jns     short loc_180095362
0x180095359  mov     word ptr [rbp+3Fh+var_9C+2], ax
0x18009535d  jmp     loc_1800956CF
0x180095362  mov     word ptr [rbp+3Fh+var_9C], ax
0x180095366  lea     rdx, [rbp+3Fh+arg_28]; unsigned int *
0x18009536a  mov     rcx, rbx; FileHandle
0x18009536d  call    ?GetAttributes@CFspCloudFileSystemOperations@@SAJPEAXPEAK@Z; CFspCloudFileSystemOperations::GetAttributes(void *,ulong *)
0x180095372  mov     [rbp+3Fh+var_A0], eax
0x180095375  mov     [rbp+3Fh+var_A0], eax
0x180095378  test    eax, eax
0x18009537a  mov     eax, 59Fh
0x18009537f  js      short loc_180095359
0x180095381  mov     word ptr [rbp+3Fh+var_9C], ax
0x180095385  mov     esi, [rbp+3Fh+arg_28]
0x180095388  and     esi, 186800h
0x18009538e  or      esi, 20h
0x180095391  lea     r8, [rbp+3Fh+var_48]; void **
0x180095395  mov     rcx, rbx; Handle
0x180095398  call    ?GetSecurity@CFspCloudFileSystemOperations@@SAJPEAXKPEAPEAX@Z; CFspCloudFileSystemOperations::GetSecurity(void *,ulong,void * *)
0x18009539d  mov     [rbp+3Fh+var_A0], eax
0x1800953a0  mov     [rbp+3Fh+var_A0], eax
0x1800953a3  test    eax, eax
0x1800953a5  mov     eax, 5A8h
0x1800953aa  js      short loc_180095359
0x1800953ac  mov     word ptr [rbp+3Fh+var_9C], ax
0x1800953b0  test    rdi, rdi
0x1800953b3  jz      short loc_1800953D9
0x1800953b5  mov     r9, rdi; struct IFspInPlaceFile *
0x1800953b8  mov     r8, r15; unsigned __int16 *
0x1800953bb  mov     rdx, rbx; void *
0x1800953be  mov     rcx, r13; this
0x1800953c1  call    ?ValidateFileUnchangedAndNotUnderDownload@CCloudFileSystemApplier@@AEAAJPEAXPEBGPEAUIFspInPlaceFile@@@Z; CCloudFileSystemApplier::ValidateFileUnchangedAndNotUnderDownload(void *,ushort const *,IFspInPlaceFile *)
0x1800953c6  mov     [rbp+3Fh+var_A0], eax
0x1800953c9  mov     [rbp+3Fh+var_A0], eax
0x1800953cc  test    eax, eax
0x1800953ce  mov     eax, 5AEh
0x1800953d3  js      short loc_180095359
0x1800953d5  mov     word ptr [rbp+3Fh+var_9C], ax
0x1800953d9  mov     rcx, rbx; FileHandle
0x1800953dc  call    ?ClearReadOnly@CFspCloudFileSystemOperations@@SAJPEAX@Z; CFspCloudFileSystemOperations::ClearReadOnly(void *)
0x1800953e1  mov     [rbp+3Fh+var_A0], eax
0x1800953e4  mov     [rbp+3Fh+var_A0], eax
0x1800953e7  test    eax, eax
0x1800953e9  mov     eax, 5B2h
0x1800953ee  js      loc_180095359
0x1800953f4  mov     word ptr [rbp+3Fh+var_9C], ax
0x1800953f8  mov     rcx, rbx; Handle
0x1800953fb  call    cs:__imp_NtClose
0x180095401  xor     ebx, ebx
0x180095403  mov     [rbp+3Fh+arg_40], rbx
0x18009540a  mov     rdi, [rbp+3Fh+arg_8]
0x18009540e  mov     rax, [rdi]
0x180095411  lea     rdx, [rbp+3Fh+arg_40]
0x180095418  mov     rcx, rdi
0x18009541b  mov     rax, [rax+68h]
0x18009541f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095424  mov     [rbp+3Fh+var_A0], eax
0x180095427  mov     [rbp+3Fh+var_A0], eax
0x18009542a  test    eax, eax
0x18009542c  mov     eax, 5C2h
0x180095431  js      loc_1800951D1
0x180095437  mov     word ptr [rbp+3Fh+var_9C], ax
0x18009543b  mov     [rbp+3Fh+arg_28], ebx
0x18009543e  mov     rax, [rdi]
0x180095441  lea     rdx, [rbp+3Fh+arg_28]
0x180095445  mov     rcx, rdi
0x180095448  mov     rax, [rax+28h]
0x18009544c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095451  mov     edx, eax
0x180095453  mov     [rbp+3Fh+var_A0], eax
0x180095456  mov     [rbp+3Fh+var_A0], eax
0x180095459  test    eax, eax
0x18009545b  mov     eax, 5CBh
0x180095460  js      loc_1800951D1
0x180095466  mov     word ptr [rbp+3Fh+var_9C], ax
0x18009546a  test    byte ptr [rbp+3Fh+arg_28], 4
0x18009546e  setnz   cl
0x180095471  bt      esi, 0Eh
0x180095475  setb    al
0x180095478  test    al, cl
0x18009547a  jz      loc_180095531
0x180095480  mov     rcx, cs:WPP_GLOBAL_Control
0x180095487  lea     rax, WPP_GLOBAL_Control
0x18009548e  cmp     rcx, rax
0x180095491  jz      short loc_1800954C7
0x180095493  test    dword ptr [rcx+44h], 100h
0x18009549a  jz      short loc_1800954C7
0x18009549c  cmp     byte ptr [rcx+41h], 4
0x1800954a0  jb      short loc_1800954C7
0x1800954a2  lea     edx, [rbx+21h]
0x1800954a5  mov     rax, [rbp+3Fh+arg_40]
0x1800954ac  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800954b1  mov     r9, r14
0x1800954b4  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x1800954bb  mov     rcx, [rcx+38h]
0x1800954bf  call    WPP_SF_SS
0x1800954c4  mov     edx, [rbp+3Fh+var_A0]
0x1800954c7  mov     [rbp+3Fh+var_A0], edx
0x1800954ca  xor     edx, edx; dwReserved
0x1800954cc  mov     rcx, r14; lpFileName
0x1800954cf  call    cs:__imp_DecryptFileW
0x1800954d5  test    eax, eax
0x1800954d7  jnz     short loc_1800954EB
0x1800954d9  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800954de  mov     [rbp+3Fh+var_A0], eax
0x1800954e1  mov     eax, 5D6h
0x1800954e6  jmp     loc_1800951D1
0x1800954eb  mov     [rbp+3Fh+var_A0], ebx
0x1800954ee  mov     eax, 5D6h
0x1800954f3  mov     word ptr [rbp+3Fh+var_9C], ax
0x1800954f7  mov     [rbp+3Fh+var_A0], ebx
0x1800954fa  xor     edx, edx; dwReserved
0x1800954fc  mov     rcx, [rbp+3Fh+arg_40]; lpFileName
0x180095503  call    cs:__imp_DecryptFileW
0x180095509  test    eax, eax
0x18009550b  jnz     short loc_18009551F
0x18009550d  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180095512  mov     [rbp+3Fh+var_A0], eax
0x180095515  mov     eax, 5D7h
0x18009551a  jmp     loc_1800951D1
0x18009551f  xor     edx, edx
0x180095521  mov     [rbp+3Fh+var_A0], edx
0x180095524  mov     eax, 5D7h
0x180095529  mov     word ptr [rbp+3Fh+var_9C], ax
0x18009552d  btr     esi, 0Eh
0x180095531  mov     rdi, [rbp+3Fh+arg_20]
0x180095535  test    rdi, rdi
0x180095538  jz      short loc_180095564
0x18009553a  test    r12, r12
0x18009553d  jz      short loc_180095564
0x18009553f  lea     rdx, [rbp+3Fh+var_68]; void **
0x180095543  mov     rcx, r15; SourceString
0x180095546  call    ?OpenFileAttribute@CFspCloudFileSystemOperations@@SAJPEBGPEAPEAX@Z; CFspCloudFileSystemOperations::OpenFileAttribute(ushort const *,void * *)
0x18009554b  mov     edx, eax
0x18009554d  mov     [rbp+3Fh+var_A0], eax
  ... truncated ...
```
