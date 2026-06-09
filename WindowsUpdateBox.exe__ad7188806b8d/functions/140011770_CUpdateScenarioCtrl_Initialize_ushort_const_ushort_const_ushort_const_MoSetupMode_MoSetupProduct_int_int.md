# CUpdateScenarioCtrl::Initialize(ushort const *,ushort const *,ushort const *,MoSetupMode,MoSetupProduct,int,int)

- ea: `0x140011770`
- end: `0x140011a9a`
- name: `?Initialize@CUpdateScenarioCtrl@@UEAAJPEBG00W4MoSetupMode@@W4MoSetupProduct@@HH@Z`
- size: `810`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, void *, void *, int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140002116`
- `0x140002a98`
- `0x1400076c8`
- `0x140008434`
- `0x140009f00`
- `0x14000d650`
- `0x140011770`
- `0x1400135b8`
- `0x140016bb4`
- `0x140018a38`
- `0x140080d70`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14001187e`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14001187e`
- `KERNEL32!HeapFree` at `0x1400119b2`
- `KERNEL32!HeapFree` at `0x1400119eb`
- `KERNEL32!HeapFree` at `0x1400119b2`
- `KERNEL32!HeapFree` at `0x1400119eb`
- `KERNEL32!GetProcessHeap` at `0x14001199d`
- `KERNEL32!GetProcessHeap` at `0x1400119d6`
- `KERNEL32!GetProcessHeap` at `0x14001199d`
- `KERNEL32!GetProcessHeap` at `0x1400119d6`
- `KERNEL32!GetLastError` at `0x14001188e`
- `KERNEL32!GetLastError` at `0x14001188e`
- `USER32!CharUpperW` at `0x1400118dd`
- `USER32!CharUpperW` at `0x1400118f0`
- `USER32!CharUpperW` at `0x1400118dd`
- `USER32!CharUpperW` at `0x1400118f0`

## string_xrefs

- `0x140011a3b`: `CUpdateScenarioCtrl::Initialize`

## pseudocode

```c
__int64 __fastcall CUpdateScenarioCtrl::Initialize(
        __int64 a1,
        unsigned __int16 *a2,
        void *a3,
        void *a4,
        int a5,
        unsigned int a6)
{
  HANDLE v6; // rsi
  unsigned int v10; // ebx
  signed int EsdFile; // edi
  signed int LastError; // eax
  WCHAR v13; // r12
  __int16 v14; // r15
  WCHAR *v15; // rbx
  CUpdateScenarioCtrl *v16; // rcx
  int StringCch; // eax
  __int64 v18; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax
  const unsigned __int16 *v22; // rdx
  unsigned __int16 **v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  void *v26; // [rsp+38h] [rbp-C8h]
  _OWORD Src[3]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v28; // [rsp+70h] [rbp-90h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  v6 = 0;
  v26 = a3;
  v28 = aWindowsLsSourc[24];
  Src[0] = *(_OWORD *)L"?:\\$Windows.~LS\\Sources\\";
  Src[1] = *(_OWORD *)L"ows.~LS\\Sources\\";
  Src[2] = *(_OWORD *)L"Sources\\";
  if ( !a2 || !a4 || (unsigned int)(a5 - 1) > 2 || a6 > 4 )
  {
    v10 = -2147024809;
    EsdFile = -2147024809;
    goto LABEL_32;
  }
  EsdFile = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(a2);
  v10 = EsdFile;
  if ( EsdFile < 0 )
    goto LABEL_32;
  EsdFile = CMiscHelpersT<CEmptyType>::ParseFileName(a2, 0);
  v10 = EsdFile;
  if ( EsdFile < 0 )
    goto LABEL_32;
  EsdFile = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(a4);
  v10 = EsdFile;
  if ( EsdFile < 0 )
    goto LABEL_32;
  *(_DWORD *)(a1 + 68) = a5;
  EsdFile = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    v13 = Buffer[0];
  }
  else
  {
    LastError = GetLastError();
    EsdFile = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        EsdFile = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      EsdFile = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)EsdFile);
    v13 = 0;
  }
  v10 = EsdFile;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)EsdFile);
  if ( EsdFile < 0 )
    goto LABEL_32;
  v14 = *a2;
  v15 = CharUpperW((LPWSTR)*a2);
  if ( CharUpperW((LPWSTR)v13) != v15 )
  {
    *(_DWORD *)(a1 + 72) = 1;
    LOWORD(Src[0]) = v14;
    v25 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v25, 0x7FFFFFFF);
    EsdFile = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Src),
          EsdFile = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    v10 = EsdFile;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)EsdFile);
    if ( EsdFile < 0 )
      goto LABEL_32;
  }
  if ( *(_DWORD *)(a1 + 68) == 1 )
    goto LABEL_35;
  if ( v26 )
  {
    EsdFile = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v26);
    v10 = EsdFile;
    if ( EsdFile >= 0 )
    {
      *(_DWORD *)(a1 + 64) = 1;
      v18 = *(_QWORD *)(a1 + 48);
      if ( v18 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v18 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        *(_QWORD *)(a1 + 48) = 0;
      }
      v20 = *(_QWORD *)(a1 + 56);
      if ( v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, (LPVOID)(v20 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        *(_QWORD *)(a1 + 56) = 0;
      }
      goto LABEL_35;
    }
    goto LABEL_32;
  }
  v22 = *(const unsigned __int16 **)(a1 + 32);
  if ( !v22 )
    v22 = 0;
  EsdFile = CUpdateScenarioCtrl::FindEsdFile(
              v16,
              v22,
              (int *)(a1 + 64),
              (unsigned __int16 **)(a1 + 48),
              (unsigned __int16 **)(a1 + 56));
  v10 = EsdFile;
  if ( EsdFile < 0 )
  {
LABEL_32:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    LODWORD(v24) = EsdFile;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v6 = g_shLogFile;
    OutputMsg(v6, g_shLogEvent, L"%s: Error = 0x%X", L"CUpdateScenarioCtrl::Initialize", v24);
  }
LABEL_35:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)EsdFile);
  return (unsigned int)EsdFile;
}

```

## disassembly

```asm
0x140011770  push    rbp
0x140011772  push    rbx
0x140011773  push    rsi
0x140011774  push    rdi
0x140011775  push    r12
0x140011777  push    r13
0x140011779  push    r14
0x14001177b  push    r15
0x14001177d  lea     rbp, [rsp-1A8h]
0x140011785  sub     rsp, 2A8h
0x14001178c  mov     rax, cs:__security_cookie
0x140011793  xor     rax, rsp
0x140011796  mov     [rbp+1E0h+var_50], rax
0x14001179d  movups  xmm0, xmmword ptr cs:aWindowsLsSourc; "?:\\$Windows.~LS\\Sources\\"
0x1400117a4  movzx   eax, word ptr cs:aWindowsLsSourc+30h; ""
0x1400117ab  xor     esi, esi
0x1400117ad  mov     [rsp+2E0h+var_2A8], r8
0x1400117b2  mov     r12, r9
0x1400117b5  mov     [rsp+2E0h+var_270], ax
0x1400117ba  mov     r13, rdx
0x1400117bd  mov     r14, rcx
0x1400117c0  movups  xmm1, xmmword ptr cs:aWindowsLsSourc+10h; "ows.~LS\\Sources\\"
0x1400117c7  movups  [rsp+2E0h+Src], xmm0
0x1400117cc  movups  xmm0, xmmword ptr cs:aWindowsLsSourc+20h; "Sources\\"
0x1400117d3  movups  [rsp+2E0h+var_290], xmm1
0x1400117d8  movups  [rsp+2E0h+var_280], xmm0
0x1400117dd  test    rdx, rdx
0x1400117e0  jnz     short loc_1400117EE
0x1400117e2  mov     ebx, 80070057h
0x1400117e7  mov     edi, ebx
0x1400117e9  jmp     loc_140011A2D
0x1400117ee  test    r12, r12
0x1400117f1  jz      short loc_1400117E2
0x1400117f3  mov     r15d, [rbp+1E0h+arg_20]
0x1400117fa  lea     eax, [r15-1]
0x1400117fe  cmp     eax, 2
0x140011801  ja      short loc_1400117E2
0x140011803  cmp     [rbp+1E0h+arg_28], 4
0x14001180a  ja      short loc_1400117E2
0x14001180c  lea     rdx, [rcx+10h]
0x140011810  mov     rcx, r13; Src
0x140011813  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x140011818  mov     edi, eax
0x14001181a  mov     ebx, eax
0x14001181c  test    eax, eax
0x14001181e  js      loc_140011A2D
0x140011824  lea     r8, [r14+20h]
0x140011828  mov     [rsp+2E0h+var_2C0], rsi; __int64
0x14001182d  xor     r9d, r9d
0x140011830  xor     edx, edx
0x140011832  mov     rcx, r13; Src
0x140011835  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x14001183a  mov     edi, eax
0x14001183c  mov     ebx, eax
0x14001183e  test    eax, eax
0x140011840  js      loc_140011A2D
0x140011846  lea     rdx, [r14+28h]
0x14001184a  mov     rcx, r12; Src
0x14001184d  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x140011852  mov     edi, eax
0x140011854  mov     ebx, eax
0x140011856  test    eax, eax
0x140011858  js      loc_140011A2D
0x14001185e  xor     edx, edx; Val
0x140011860  mov     [r14+44h], r15d
0x140011864  mov     r8d, 208h; Size
0x14001186a  lea     rcx, [rbp+1E0h+Buffer]; void *
0x14001186e  mov     edi, esi
0x140011870  call    memset_0
0x140011875  mov     edx, 104h; uSize
0x14001187a  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x14001187e  call    cs:__imp_GetSystemWindowsDirectoryW
0x140011885  nop     dword ptr [rax+rax+00h]
0x14001188a  test    eax, eax
0x14001188c  jnz     short loc_1400118BF
0x14001188e  call    cs:__imp_GetLastError
0x140011895  nop     dword ptr [rax+rax+00h]
0x14001189a  mov     edi, eax
0x14001189c  test    eax, eax
0x14001189e  jnz     short loc_1400118A7
0x1400118a0  mov     edi, 80004005h
0x1400118a5  jmp     short loc_1400118B2
0x1400118a7  jle     short loc_1400118B2
0x1400118a9  movzx   edi, ax
0x1400118ac  or      edi, 80070000h
0x1400118b2  mov     ecx, edi
0x1400118b4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400118b9  movzx   r12d, si
0x1400118bd  jmp     short loc_1400118C4
0x1400118bf  movzx   r12d, [rbp+1E0h+Buffer]
0x1400118c4  mov     ecx, edi
0x1400118c6  mov     ebx, edi
0x1400118c8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400118cd  test    edi, edi
0x1400118cf  js      loc_140011A2D
0x1400118d5  movzx   r15d, word ptr [r13+0]
0x1400118da  mov     ecx, r15d; lpsz
0x1400118dd  call    cs:__imp_CharUpperW
0x1400118e4  nop     dword ptr [rax+rax+00h]
0x1400118e9  movzx   ecx, r12w; lpsz
0x1400118ed  mov     rbx, rax
0x1400118f0  call    cs:__imp_CharUpperW
0x1400118f7  nop     dword ptr [rax+rax+00h]
0x1400118fc  mov     r12d, 1
0x140011902  cmp     rax, rbx
0x140011905  jz      short loc_140011960
0x140011907  mov     r8d, 7FFFFFFFh
0x14001190d  mov     [r14+48h], r12d
0x140011911  lea     rdx, [rsp+2E0h+var_2B0]
0x140011916  mov     word ptr [rsp+2E0h+Src], r15w
0x14001191c  lea     rcx, [rsp+2E0h+Src]
0x140011921  mov     [rsp+2E0h+var_2B0], esi
0x140011925  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x14001192a  mov     edi, eax
0x14001192c  test    eax, eax
0x14001192e  js      short loc_140011948
0x140011930  mov     edx, [rsp+2E0h+var_2B0]
0x140011934  lea     r8, [r14+50h]
0x140011938  lea     rcx, [rsp+2E0h+Src]; Src
0x14001193d  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x140011942  mov     edi, eax
0x140011944  test    eax, eax
0x140011946  jns     short loc_14001194F
0x140011948  mov     ecx, eax
0x14001194a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001194f  mov     ecx, edi
0x140011951  mov     ebx, edi
0x140011953  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011958  test    edi, edi
0x14001195a  js      loc_140011A2D
0x140011960  cmp     [r14+44h], r12d
0x140011964  jz      loc_140011A6D
0x14001196a  mov     rax, [rsp+2E0h+var_2A8]
0x14001196f  test    rax, rax
0x140011972  jz      loc_140011A04
0x140011978  lea     rdx, [r14+18h]
0x14001197c  mov     rcx, rax; Src
0x14001197f  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x140011984  mov     edi, eax
0x140011986  mov     ebx, eax
0x140011988  test    eax, eax
0x14001198a  js      loc_140011A2D
0x140011990  mov     [r14+40h], r12d
0x140011994  mov     rbx, [r14+30h]
0x140011998  test    rbx, rbx
0x14001199b  jz      short loc_1400119C9
0x14001199d  call    cs:__imp_GetProcessHeap
0x1400119a4  nop     dword ptr [rax+rax+00h]
0x1400119a9  lea     r8, [rbx-4]; lpMem
0x1400119ad  xor     edx, edx; dwFlags
0x1400119af  mov     rcx, rax; hHeap
0x1400119b2  call    cs:__imp_HeapFree
0x1400119b9  nop     dword ptr [rax+rax+00h]
0x1400119be  xor     ecx, ecx
0x1400119c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400119c5  mov     [r14+30h], rsi
0x1400119c9  mov     rbx, [r14+38h]
0x1400119cd  test    rbx, rbx
0x1400119d0  jz      loc_140011A6D
0x1400119d6  call    cs:__imp_GetProcessHeap
0x1400119dd  nop     dword ptr [rax+rax+00h]
0x1400119e2  lea     r8, [rbx-4]; lpMem
0x1400119e6  xor     edx, edx; dwFlags
0x1400119e8  mov     rcx, rax; hHeap
0x1400119eb  call    cs:__imp_HeapFree
0x1400119f2  nop     dword ptr [rax+rax+00h]
0x1400119f7  xor     ecx, ecx
0x1400119f9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400119fe  mov     [r14+38h], rsi
0x140011a02  jmp     short loc_140011A6D
0x140011a04  mov     rdx, [r14+20h]
0x140011a08  lea     rax, [r14+38h]
0x140011a0c  test    rdx, rdx
0x140011a0f  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 **
0x140011a14  lea     r9, [r14+30h]; unsigned __int16 **
0x140011a18  cmovz   rdx, rsi; unsigned __int16 *
0x140011a1c  lea     r8, [r14+40h]; int *
0x140011a20  call    ?FindEsdFile@CUpdateScenarioCtrl@@AEAAJPEBGPEAHPEAPEAG2@Z; CUpdateScenarioCtrl::FindEsdFile(ushort const *,int *,ushort * *,ushort * *)
0x140011a25  mov     edi, eax
0x140011a27  mov     ebx, eax
0x140011a29  test    eax, eax
0x140011a2b  jns     short loc_140011A6D
0x140011a2d  mov     ecx, ebx
0x140011a2f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140011a34  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140011a3b  lea     r9, aCupdatescenari_2; "CUpdateScenarioCtrl::Initialize"
0x140011a42  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140011a49  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x140011a4d  lea     rax, [r8-1]
0x140011a51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011a55  setnbe  al
0x140011a58  test    al, al
0x140011a5a  cmovz   rsi, r8
0x140011a5e  lea     r8, aSError0xX; "%s: Error = 0x%X"
0x140011a65  mov     rcx, rsi; hFile
0x140011a68  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140011a6d  mov     ecx, edi
0x140011a6f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011a74  mov     eax, edi
0x140011a76  mov     rcx, [rbp+1E0h+var_50]
0x140011a7d  xor     rcx, rsp; StackCookie
0x140011a80  call    __security_check_cookie
0x140011a85  add     rsp, 2A8h
0x140011a8c  pop     r15
0x140011a8e  pop     r14
0x140011a90  pop     r13
0x140011a92  pop     r12
0x140011a94  pop     rdi
0x140011a95  pop     rsi
0x140011a96  pop     rbx
0x140011a97  pop     rbp
0x140011a98  retn
```
