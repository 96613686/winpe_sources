# CUpdateScenarioCtrl::PopulateWorkingDir(ushort * *,ushort * *)

- ea: `0x14001a670`
- end: `0x14001ac57`
- name: `?PopulateWorkingDir@CUpdateScenarioCtrl@@UEAAJPEAPEAG0@Z`
- size: `1511`
- prototype: `__int64 __fastcall(CUpdateScenarioCtrl *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140008434`
- `0x14000a564`
- `0x14000ba6c`
- `0x14000e2a0`
- `0x14000e878`
- `0x140010148`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001a41c`
- `0x14001a670`
- `0x14001b310`
- `0x14001dedc`
- `0x14001dfc8`
- `0x140053ba0`
- `0x140054ac8`
- `0x140054bd4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001ab95`
- `KERNEL32!HeapFree` at `0x14001abc3`
- `KERNEL32!HeapFree` at `0x14001abf8`
- `KERNEL32!HeapFree` at `0x14001ac26`
- `KERNEL32!HeapFree` at `0x14001ab95`
- `KERNEL32!HeapFree` at `0x14001abc3`
- `KERNEL32!HeapFree` at `0x14001abf8`
- `KERNEL32!HeapFree` at `0x14001ac26`
- `KERNEL32!GetProcessHeap` at `0x14001ab80`
- `KERNEL32!GetProcessHeap` at `0x14001abae`
- `KERNEL32!GetProcessHeap` at `0x14001abe4`
- `KERNEL32!GetProcessHeap` at `0x14001ac11`
- `KERNEL32!GetProcessHeap` at `0x14001ab80`
- `KERNEL32!GetProcessHeap` at `0x14001abae`
- `KERNEL32!GetProcessHeap` at `0x14001abe4`
- `KERNEL32!GetProcessHeap` at `0x14001ac11`
- `KERNEL32!GetFileAttributesW` at `0x14001a7e9`
- `KERNEL32!GetFileAttributesW` at `0x14001aa65`
- `KERNEL32!GetFileAttributesW` at `0x14001a7e9`
- `KERNEL32!GetFileAttributesW` at `0x14001aa65`

## string_xrefs

- `0x14001a6fe`: `Opening Box: [%s]`
- `0x14001a756`: `Reading Box header...`
- `0x14001a85c`: `CUpdateScenarioCtrl::PopulateWorkingDir`
- `0x14001a891`: `CUpdateScenarioCtrl::PopulateWorkingDir`
- `0x14001a97b`: `CUpdateScenarioCtrl::PopulateWorkingDir`
- `0x14001a9b5`: `CUpdateScenarioCtrl::PopulateWorkingDir`
- `0x14001ab4b`: `CUpdateScenarioCtrl::PopulateWorkingDir`
- `0x14001a863`: `%s: Working directory was preserved so it is already populated.`
- `0x14001aa26`: `Install`

## pseudocode

```c
__int64 __fastcall CUpdateScenarioCtrl::PopulateWorkingDir(
        CUpdateScenarioCtrl *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 *v4; // r14
  LPCWSTR v5; // r15
  __int64 v6; // r13
  void *v7; // r12
  __int64 v8; // rcx
  int v9; // edi
  HANDLE v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  HANDLE v13; // rcx
  int Header; // eax
  __int64 v15; // rcx
  int v16; // eax
  DWORD FileAttributesW; // eax
  BOOL v18; // esi
  HANDLE v19; // rcx
  HANDLE v20; // rcx
  __int64 SetupVolatileRegKey; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int16 **v27; // rdx
  int BoxHash; // eax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rcx
  HANDLE v34; // rcx
  HANDLE v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  DWORD v42; // eax
  BOOL v43; // esi
  HANDLE v44; // rcx
  const wchar_t *v45; // rdx
  const unsigned __int16 *v46; // rdx
  unsigned __int16 *v47; // rax
  unsigned __int16 *v48; // rax
  HANDLE v49; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v51; // rax
  void *v52; // rbx
  HANDLE v53; // rax
  HANDLE v54; // rax
  __int64 v56; // [rsp+20h] [rbp-60h]
  LPVOID lpMem; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-48h] BYREF
  __int64 v59; // [rsp+40h] [rbp-40h] BYREF
  __int64 v60; // [rsp+48h] [rbp-38h]
  __int64 v61; // [rsp+50h] [rbp-30h]
  _BYTE v62[16]; // [rsp+58h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+68h] [rbp-18h]
  LPCWSTR v66; // [rsp+D8h] [rbp+58h] BYREF

  v61 = -2;
  v4 = 0;
  v66 = 0;
  v60 = 0;
  v5 = 0;
  lpFileName = 0;
  v6 = 0;
  v59 = 0;
  v7 = 0;
  lpMem = 0;
  if ( a2 && a3 )
  {
    v10 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v10 = g_shLogFile;
    OutputMsg(v10, g_shLogEvent, L"Opening Box: [%s]", *((_QWORD *)this + 2));
    v11 = *((_QWORD *)this + 2);
    if ( !v11 )
      v11 = 0;
    v12 = BoxOpenFromPath(v11, &lpMem);
    v9 = v12;
    if ( v12 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
      v7 = lpMem;
      goto LABEL_71;
    }
    v13 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v13 = g_shLogFile;
    OutputMsg(v13, g_shLogEvent, L"Reading Box header...");
    *(_OWORD *)Src = 0;
    v7 = lpMem;
    Header = BoxReadHeader(lpMem, v62);
    v9 = Header;
    if ( Header < 0 )
      goto LABEL_14;
    if ( !Src[1] )
    {
      v9 = -2147019873;
      v8 = 2147947423LL;
      goto LABEL_3;
    }
    Header = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Src[1]);
    v9 = Header;
    if ( Header < 0 )
      goto LABEL_14;
    v15 = *((_QWORD *)this + 5);
    if ( !v15 )
      v15 = 0;
    v16 = CMiscHelpersT<CEmptyType>::CombinePath(v15, v60, 0, &lpFileName);
    v9 = v16;
    if ( v16 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
      v5 = lpFileName;
      goto LABEL_71;
    }
    v5 = lpFileName;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v18 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( *((_DWORD *)this + 17) == 1 )
    {
      if ( *((_DWORD *)this + 22) )
      {
        v19 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v19 = g_shLogFile;
        OutputMsg(
          v19,
          g_shLogEvent,
          L"%s: Working directory was preserved so it is already populated.",
          L"CUpdateScenarioCtrl::PopulateWorkingDir");
      }
      else
      {
        Header = CUpdateScenarioCtrl::PopulateWorkingDir(this, v7);
        v9 = Header;
        if ( Header < 0 )
        {
LABEL_14:
          v8 = (unsigned int)Header;
          goto LABEL_3;
        }
      }
      v20 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v20 = g_shLogFile;
      OutputMsg(v20, g_shLogEvent, L"%s: Setting PreDownload mode...", L"CUpdateScenarioCtrl::PopulateWorkingDir");
      SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v22, SetupVolatileRegKey);
      v9 = Header;
      if ( Header < 0 )
        goto LABEL_14;
      v23 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v24, v23, L"PreDownloadMode", 1);
      v9 = Header;
      if ( Header < 0 )
        goto LABEL_14;
      v25 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v26, v25);
      v9 = Header;
      if ( Header < 0 )
        goto LABEL_14;
      BoxHash = ScenarioCtrlHelpers::GenerateBoxHash((ScenarioCtrlHelpers *)&v59, v27);
      v9 = BoxHash;
      if ( BoxHash < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)BoxHash);
        v6 = v59;
        goto LABEL_71;
      }
      v6 = v59;
      v29 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CRegUtilT<unsigned short *,CRegType,0,1>::SetValue(v30, v29, v31, v6);
      v9 = Header;
      if ( Header < 0 )
        goto LABEL_14;
      v32 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      Header = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v33, v32);
      v9 = Header;
      if ( Header < 0 )
        goto LABEL_14;
      v34 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v34 = g_shLogFile;
      OutputMsg(v34, g_shLogEvent, L"%s: File hash stored!", L"CUpdateScenarioCtrl::PopulateWorkingDir");
LABEL_70:
      v47 = (unsigned __int16 *)v5;
      v5 = 0;
      *a2 = v47;
      v48 = (unsigned __int16 *)v4;
      v4 = 0;
      *a3 = v48;
      if ( v9 >= 0 )
        goto LABEL_74;
      goto LABEL_71;
    }
    v35 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v35 = g_shLogFile;
    OutputMsg(v35, g_shLogEvent, L"%s: Clearing PreDownload mode...", L"CUpdateScenarioCtrl::PopulateWorkingDir");
    v36 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
    v9 = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v37, v36, L"PreDownloadMode");
    if ( v9 >= 0 )
    {
      v38 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      v9 = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v39, v38);
      if ( v9 >= 0 )
      {
        if ( v18 )
        {
          if ( *((_DWORD *)this + 18) )
            v40 = *((_QWORD *)this + 10);
          else
            v40 = *((_QWORD *)this + 5);
          if ( !v40 )
            v40 = 0;
          v41 = CMiscHelpersT<CEmptyType>::CombinePath(v40, L"Install", L"esd", &v66);
          v9 = v41;
          if ( v41 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v41);
            v4 = v66;
            goto LABEL_71;
          }
          v4 = v66;
          v42 = GetFileAttributesW(v66);
          v43 = v42 != -1 && (v42 & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v44 = 0;
          v9 = 0;
          v45 = L"does";
          if ( !v43 )
            v45 = L"does not";
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v44 = g_shLogFile;
          OutputMsg(v44, g_shLogEvent, L"Working file [%s] %s exist.", v4, v45);
          if ( *((_DWORD *)this + 16) )
          {
            v46 = (const unsigned __int16 *)*((_QWORD *)this + 3);
            if ( v46 || (v46 = (const unsigned __int16 *)*((_QWORD *)this + 6)) != 0 )
            {
              Header = CUpdateScenarioCtrl::ProjectEsdFile(this, v46, v4);
              v9 = Header;
              if ( Header < 0 )
                goto LABEL_14;
            }
          }
          goto LABEL_70;
        }
        v9 = -2145116147;
      }
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    goto LABEL_71;
  }
  v8 = 2147942487LL;
  v9 = -2147024809;
LABEL_3:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_71:
  v49 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v49 = g_shLogFile;
  LODWORD(v56) = v9;
  OutputMsg(v49, g_shLogEvent, L"%s: Error = 0x%X", L"CUpdateScenarioCtrl::PopulateWorkingDir", v56);
LABEL_74:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  if ( v7 )
    FreeBoxFileHandle(v7);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v60 )
  {
    v52 = (void *)(v60 - 4);
    v53 = GetProcessHeap();
    HeapFree(v53, 0, v52);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v54 = GetProcessHeap();
    HeapFree(v54, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001a670  mov     rax, rsp
0x14001a673  mov     [rax+18h], r8
0x14001a677  mov     [rax+10h], rdx
0x14001a67b  push    rbp
0x14001a67c  push    rsi
0x14001a67d  push    rdi
0x14001a67e  push    r12
0x14001a680  push    r13
0x14001a682  push    r14
0x14001a684  push    r15
0x14001a686  mov     rbp, rsp
0x14001a689  sub     rsp, 80h
0x14001a690  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x14001a698  mov     [rax+8], rbx
0x14001a69c  mov     rax, r8
0x14001a69f  mov     rbx, rcx
0x14001a6a2  xor     esi, esi
0x14001a6a4  mov     r14d, esi
0x14001a6a7  mov     [rbp+arg_18], rsi
0x14001a6ab  mov     [rbp+var_38], rsi
0x14001a6af  mov     r15d, esi
0x14001a6b2  mov     [rbp+lpFileName], rsi
0x14001a6b6  mov     r13d, esi
0x14001a6b9  mov     [rbp+var_40], rsi
0x14001a6bd  mov     r12d, esi
0x14001a6c0  mov     [rbp+lpMem], rsi
0x14001a6c4  test    rdx, rdx
0x14001a6c7  jnz     short loc_14001A6DA
0x14001a6c9  mov     ecx, 80070057h
0x14001a6ce  mov     edi, ecx
0x14001a6d0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001a6d5  jmp     loc_14001AB2C
0x14001a6da  test    rax, rax
0x14001a6dd  jz      short loc_14001A6C9
0x14001a6df  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a6e6  lea     rax, [r8-1]
0x14001a6ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a6ee  setnbe  al
0x14001a6f1  mov     rcx, rsi
0x14001a6f4  test    al, al
0x14001a6f6  cmovz   rcx, r8; hFile
0x14001a6fa  mov     r9, [rbx+10h]
0x14001a6fe  lea     r8, aOpeningBoxS; "Opening Box: [%s]"
0x14001a705  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a70c  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a711  mov     rcx, [rbx+10h]
0x14001a715  test    rcx, rcx
0x14001a718  cmovz   rcx, rsi
0x14001a71c  lea     rdx, [rbp+lpMem]
0x14001a720  call    BoxOpenFromPath
0x14001a725  mov     edi, eax
0x14001a727  test    eax, eax
0x14001a729  jns     short loc_14001A73B
0x14001a72b  mov     ecx, eax
0x14001a72d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001a732  mov     r12, [rbp+lpMem]
0x14001a736  jmp     loc_14001AB2C
0x14001a73b  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a742  lea     rax, [r8-1]
0x14001a746  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a74a  setnbe  al
0x14001a74d  mov     rcx, rsi
0x14001a750  test    al, al
0x14001a752  cmovz   rcx, r8; hFile
0x14001a756  lea     r8, aReadingBoxHead; "Reading Box header..."
0x14001a75d  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a764  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a769  xorps   xmm0, xmm0
0x14001a76c  movups  xmmword ptr [rbp+Src], xmm0
0x14001a770  mov     r12, [rbp+lpMem]
0x14001a774  lea     rdx, [rbp+var_28]
0x14001a778  mov     rcx, r12
0x14001a77b  call    BoxReadHeader
0x14001a780  mov     edi, eax
0x14001a782  test    eax, eax
0x14001a784  jns     short loc_14001A78D
0x14001a786  mov     ecx, eax
0x14001a788  jmp     loc_14001A6D0
0x14001a78d  mov     rcx, [rbp+Src+8]; Src
0x14001a791  test    rcx, rcx
0x14001a794  jnz     short loc_14001A7A2
0x14001a796  mov     edi, 8007139Fh
0x14001a79b  mov     ecx, edi
0x14001a79d  jmp     loc_14001A6D0
0x14001a7a2  lea     rdx, [rbp+var_38]
0x14001a7a6  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001a7ab  mov     edi, eax
0x14001a7ad  test    eax, eax
0x14001a7af  js      short loc_14001A786
0x14001a7b1  mov     rcx, [rbx+28h]
0x14001a7b5  test    rcx, rcx
0x14001a7b8  cmovz   rcx, rsi
0x14001a7bc  lea     r9, [rbp+lpFileName]
0x14001a7c0  xor     r8d, r8d
0x14001a7c3  mov     rdx, [rbp+var_38]
0x14001a7c7  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001a7cc  mov     edi, eax
0x14001a7ce  test    eax, eax
0x14001a7d0  jns     short loc_14001A7E2
0x14001a7d2  mov     ecx, eax
0x14001a7d4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001a7d9  mov     r15, [rbp+lpFileName]
0x14001a7dd  jmp     loc_14001AB2C
0x14001a7e2  mov     r15, [rbp+lpFileName]
0x14001a7e6  mov     rcx, r15; lpFileName
0x14001a7e9  call    cs:__imp_GetFileAttributesW
0x14001a7f0  nop     dword ptr [rax+rax+00h]
0x14001a7f5  mov     esi, eax
0x14001a7f7  cmp     eax, 0FFFFFFFFh
0x14001a7fa  jz      short loc_14001A808
0x14001a7fc  shr     esi, 4
0x14001a7ff  not     esi
0x14001a801  and     esi, 1
0x14001a804  xor     edi, edi
0x14001a806  jmp     short loc_14001A80C
0x14001a808  xor     edi, edi
0x14001a80a  mov     esi, edi
0x14001a80c  xor     ecx, ecx
0x14001a80e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a813  xor     ecx, ecx
0x14001a815  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001a81a  cmp     dword ptr [rbx+44h], 1
0x14001a81e  jnz     loc_14001A99A
0x14001a824  xor     esi, esi
0x14001a826  cmp     [rbx+58h], esi
0x14001a829  jnz     short loc_14001A841
0x14001a82b  mov     rdx, r12; void *
0x14001a82e  mov     rcx, rbx; this
0x14001a831  call    ?PopulateWorkingDir@CUpdateScenarioCtrl@@AEAAJPEAX@Z; CUpdateScenarioCtrl::PopulateWorkingDir(void *)
0x14001a836  mov     edi, eax
0x14001a838  test    eax, eax
0x14001a83a  jns     short loc_14001A876
0x14001a83c  jmp     loc_14001A786
0x14001a841  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a848  lea     rax, [r8-1]
0x14001a84c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a850  setnbe  al
0x14001a853  mov     rcx, rsi
0x14001a856  test    al, al
0x14001a858  cmovz   rcx, r8; hFile
0x14001a85c  lea     r9, aCupdatescenari; "CUpdateScenarioCtrl::PopulateWorkingDir"
0x14001a863  lea     r8, aSWorkingDirect; "%s: Working directory was preserved so "...
0x14001a86a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a871  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a876  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a87d  lea     rax, [r8-1]
0x14001a881  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a885  setnbe  al
0x14001a888  mov     rcx, rsi
0x14001a88b  test    al, al
0x14001a88d  cmovz   rcx, r8; hFile
0x14001a891  lea     r9, aCupdatescenari; "CUpdateScenarioCtrl::PopulateWorkingDir"
0x14001a898  lea     r8, aSSettingPredow; "%s: Setting PreDownload mode..."
0x14001a89f  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a8a6  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a8ab  mov     ecx, [rbx+8]
0x14001a8ae  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a8b3  mov     rdx, rax
0x14001a8b6  call    ?CreateOrOpenKey@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<ulong,CRegType,0,1>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x14001a8bb  mov     edi, eax
0x14001a8bd  test    eax, eax
0x14001a8bf  js      loc_14001A786
0x14001a8c5  mov     ecx, [rbx+8]
0x14001a8c8  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a8cd  mov     rdx, rax
0x14001a8d0  mov     r9d, 1
0x14001a8d6  lea     r8, aPredownloadmod; "PreDownloadMode"
0x14001a8dd  call    ?SetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1K@Z; CRegUtilT<ulong,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x14001a8e2  mov     edi, eax
0x14001a8e4  test    eax, eax
0x14001a8e6  js      loc_14001A786
0x14001a8ec  mov     ecx, [rbx+8]
0x14001a8ef  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a8f4  mov     rdx, rax
0x14001a8f7  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x14001a8fc  mov     edi, eax
0x14001a8fe  test    eax, eax
0x14001a900  js      loc_14001A786
0x14001a906  lea     rcx, [rbp+var_40]; this
0x14001a90a  call    ?GenerateBoxHash@ScenarioCtrlHelpers@@YAJPEAPEAG@Z; ScenarioCtrlHelpers::GenerateBoxHash(ushort * *)
0x14001a90f  mov     edi, eax
0x14001a911  test    eax, eax
0x14001a913  jns     short loc_14001A925
0x14001a915  mov     ecx, eax
0x14001a917  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001a91c  mov     r13, [rbp+var_40]
0x14001a920  jmp     loc_14001AB2C
0x14001a925  mov     r13, [rbp+var_40]
0x14001a929  mov     ecx, [rbx+8]
0x14001a92c  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a931  mov     rdx, rax
0x14001a934  mov     r9, r13
0x14001a937  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG11@Z; CRegUtilT<ushort *,CRegType,0,1>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14001a93c  mov     edi, eax
0x14001a93e  test    eax, eax
0x14001a940  js      loc_14001A786
0x14001a946  mov     ecx, [rbx+8]
0x14001a949  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a94e  mov     rdx, rax
0x14001a951  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x14001a956  mov     edi, eax
0x14001a958  test    eax, eax
0x14001a95a  js      loc_14001A786
0x14001a960  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a967  lea     rax, [r8-1]
0x14001a96b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a96f  setnbe  al
0x14001a972  mov     rcx, rsi
0x14001a975  test    al, al
0x14001a977  cmovz   rcx, r8; hFile
0x14001a97b  lea     r9, aCupdatescenari; "CUpdateScenarioCtrl::PopulateWorkingDir"
0x14001a982  lea     r8, aSFileHashStore; "%s: File hash stored!"
0x14001a989  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a990  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a995  jmp     loc_14001AB0E
0x14001a99a  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001a9a1  lea     rax, [r8-1]
0x14001a9a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a9a9  setnbe  al
0x14001a9ac  mov     rcx, rdi
0x14001a9af  test    al, al
0x14001a9b1  cmovz   rcx, r8; hFile
0x14001a9b5  lea     r9, aCupdatescenari; "CUpdateScenarioCtrl::PopulateWorkingDir"
0x14001a9bc  lea     r8, aSClearingPredo; "%s: Clearing PreDownload mode..."
0x14001a9c3  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001a9ca  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001a9cf  mov     ecx, [rbx+8]
0x14001a9d2  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a9d7  mov     rdx, rax
0x14001a9da  lea     r8, aPredownloadmod; "PreDownloadMode"
0x14001a9e1  call    ?DeleteValueIfExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1@Z; CRegUtilT<ulong,CRegType,0,1>::DeleteValueIfExists(HKEY__ *,ushort const *,ushort const *)
0x14001a9e6  mov     edi, eax
0x14001a9e8  test    eax, eax
0x14001a9ea  js      short loc_14001AA0B
0x14001a9ec  mov     ecx, [rbx+8]
0x14001a9ef  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001a9f4  mov     rdx, rax
0x14001a9f7  call    ?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z; CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)
0x14001a9fc  mov     edi, eax
0x14001a9fe  test    eax, eax
0x14001aa00  js      short loc_14001AA0B
0x14001aa02  test    esi, esi
0x14001aa04  jnz     short loc_14001AA19
0x14001aa06  mov     edi, 8024200Dh
0x14001aa0b  mov     ecx, edi
0x14001aa0d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001aa12  xor     esi, esi
0x14001aa14  jmp     loc_14001AB2C
0x14001aa19  xor     esi, esi
0x14001aa1b  lea     r9, [rbp+arg_18]
0x14001aa1f  lea     r8, aEsd; "esd"
0x14001aa26  lea     rdx, aInstall_0; "Install"
0x14001aa2d  cmp     [rbx+48h], esi
0x14001aa30  jz      short loc_14001AA58
0x14001aa32  mov     rcx, [rbx+50h]
0x14001aa36  test    rcx, rcx
0x14001aa39  cmovz   rcx, rsi
0x14001aa3d  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001aa42  mov     edi, eax
0x14001aa44  test    eax, eax
0x14001aa46  jns     short loc_14001AA5E
0x14001aa48  mov     ecx, eax
0x14001aa4a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001aa4f  mov     r14, [rbp+arg_18]
0x14001aa53  jmp     loc_14001AB2C
0x14001aa58  mov     rcx, [rbx+28h]
0x14001aa5c  jmp     short loc_14001AA36
0x14001aa5e  mov     r14, [rbp+arg_18]
0x14001aa62  mov     rcx, r14; lpFileName
0x14001aa65  call    cs:__imp_GetFileAttributesW
0x14001aa6c  nop     dword ptr [rax+rax+00h]
0x14001aa71  mov     esi, eax
0x14001aa73  cmp     eax, 0FFFFFFFFh
0x14001aa76  jz      short loc_14001AA82
0x14001aa78  shr     esi, 4
0x14001aa7b  not     esi
0x14001aa7d  and     esi, 1
0x14001aa80  jmp     short loc_14001AA86
0x14001aa82  xor     eax, eax
0x14001aa84  mov     esi, eax
0x14001aa86  xor     ecx, ecx
0x14001aa88  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001aa8d  xor     ecx, ecx
0x14001aa8f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001aa94  xor     ecx, ecx
0x14001aa96  mov     edi, ecx
0x14001aa98  lea     rax, aDoesNot; "does not"
0x14001aa9f  lea     rdx, aDoes; "does"
0x14001aaa6  test    esi, esi
0x14001aaa8  cmovz   rdx, rax
0x14001aaac  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001aab3  lea     rax, [r8-1]
0x14001aab7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001aabb  setnbe  al
0x14001aabe  xor     esi, esi
0x14001aac0  test    al, al
0x14001aac2  cmovz   rcx, r8; hFile
0x14001aac6  mov     [rsp+80h+var_60], rdx
0x14001aacb  mov     r9, r14
0x14001aace  lea     r8, aWorkingFileSSE; "Working file [%s] %s exist."
  ... truncated ...
```
