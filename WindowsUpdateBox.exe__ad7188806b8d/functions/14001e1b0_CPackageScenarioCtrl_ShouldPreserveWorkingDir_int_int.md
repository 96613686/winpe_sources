# CPackageScenarioCtrl::ShouldPreserveWorkingDir(int,int *)

- ea: `0x14001e1b0`
- end: `0x14001e7a2`
- name: `?ShouldPreserveWorkingDir@CPackageScenarioCtrl@@UEAAJHPEAH@Z`
- size: `1522`
- prototype: `__int64 __fastcall(CPackageScenarioCtrl *__hidden this, int, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140008434`
- `0x14000e878`
- `0x140010148`
- `0x140010a14`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001e1b0`
- `0x1400203a8`
- `0x140053ba0`
- `0x140054ac8`
- `0x140054bd4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001e6d9`
- `KERNEL32!HeapFree` at `0x14001e707`
- `KERNEL32!HeapFree` at `0x14001e743`
- `KERNEL32!HeapFree` at `0x14001e771`
- `KERNEL32!HeapFree` at `0x14001e6d9`
- `KERNEL32!HeapFree` at `0x14001e707`
- `KERNEL32!HeapFree` at `0x14001e743`
- `KERNEL32!HeapFree` at `0x14001e771`
- `KERNEL32!GetProcessHeap` at `0x14001e6c4`
- `KERNEL32!GetProcessHeap` at `0x14001e6f2`
- `KERNEL32!GetProcessHeap` at `0x14001e72e`
- `KERNEL32!GetProcessHeap` at `0x14001e75c`
- `KERNEL32!GetProcessHeap` at `0x14001e6c4`
- `KERNEL32!GetProcessHeap` at `0x14001e6f2`
- `KERNEL32!GetProcessHeap` at `0x14001e72e`
- `KERNEL32!GetProcessHeap` at `0x14001e75c`
- `KERNEL32!GetFileAttributesW` at `0x14001e574`
- `KERNEL32!GetFileAttributesW` at `0x14001e574`
- `KERNEL32!CompareStringW` at `0x14001e352`
- `KERNEL32!CompareStringW` at `0x14001e3fc`
- `KERNEL32!CompareStringW` at `0x14001e352`
- `KERNEL32!CompareStringW` at `0x14001e3fc`

## string_xrefs

- `0x14001e479`: `Opening Box: [%s]`
- `0x14001e4d1`: `Reading Box header...`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPackageScenarioCtrl::ShouldPreserveWorkingDir(
        CPackageScenarioCtrl *this,
        unsigned __int16 **a2,
        int *a3)
{
  const WCHAR *v4; // r15
  const WCHAR *v5; // rbx
  void *v6; // r12
  __int64 v7; // r13
  LPCWSTR v8; // r14
  int Header; // esi
  int BoxHash; // eax
  __int64 SetupVolatileRegKey; // rax
  __int64 v12; // rcx
  int Value; // eax
  HANDLE v14; // r10
  BOOL v15; // edi
  __int64 v16; // rax
  __int64 v17; // rcx
  HANDLE v18; // rcx
  int v19; // eax
  HANDLE v20; // rdx
  HANDLE v21; // r10
  const unsigned __int16 *v22; // r8
  bool v23; // zf
  char *v24; // rax
  HANDLE v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  HANDLE v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  DWORD FileAttributesW; // eax
  const wchar_t *v32; // rdx
  HANDLE v33; // rcx
  HANDLE v34; // rcx
  HANDLE v35; // rcx
  HANDLE v36; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  HANDLE v40; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-60h]
  PCNZWCH lpString1; // [rsp+30h] [rbp-50h] BYREF
  PCNZWCH v44; // [rsp+38h] [rbp-48h] BYREF
  void *v45; // [rsp+40h] [rbp-40h] BYREF
  __int64 v46; // [rsp+48h] [rbp-38h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-30h]
  __int64 v48; // [rsp+58h] [rbp-28h]
  _BYTE v49[16]; // [rsp+60h] [rbp-20h] BYREF
  void *Src[2]; // [rsp+70h] [rbp-10h]
  int v53; // [rsp+D8h] [rbp+58h] BYREF

  v48 = -2;
  v4 = 0;
  lpString1 = 0;
  v5 = 0;
  v44 = 0;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  v46 = 0;
  v8 = 0;
  lpFileName = 0;
  v53 = 0;
  if ( !a3 )
  {
    Header = -2147024809;
LABEL_67:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Header);
    goto LABEL_68;
  }
  BoxHash = ScenarioCtrlHelpers::GenerateBoxHash((ScenarioCtrlHelpers *)&lpString1, a2);
  Header = BoxHash;
  if ( BoxHash >= 0 )
  {
    SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
    Value = CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(v12, SetupVolatileRegKey, L"BoxHash", &v44);
    v14 = 0;
    if ( Value < 0 )
    {
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v14 = g_shLogFile;
      OutputMsg(
        v14,
        g_shLogEvent,
        L"%s: Previous file hash not found.",
        L"CPackageScenarioCtrl::ShouldPreserveWorkingDir");
    }
    else
    {
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v14 = g_shLogFile;
      OutputMsg(
        v14,
        g_shLogEvent,
        L"%s: Found previously stored file hash.",
        L"CPackageScenarioCtrl::ShouldPreserveWorkingDir");
    }
    v4 = lpString1;
    if ( *((_DWORD *)this + 10) == 1 )
    {
      v15 = 0;
      v5 = v44;
      if ( !v44 )
        goto LABEL_59;
      v16 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::ValueExists(v17, v16, L"PreDownloadMode", &v53) >= 0 && v53 )
      {
        v18 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v18 = g_shLogFile;
        OutputMsg(
          v18,
          g_shLogEvent,
          L"%s: PreDownload mode value found.",
          L"CPackageScenarioCtrl::ShouldPreserveWorkingDir");
        v19 = CompareStringW(0x409u, 1u, v4, -1, v5, -1);
        v20 = g_shLogEvent;
        if ( v19 == 2 )
        {
          v15 = 1;
          v21 = 0;
          v22 = L"%s: Box file hash matches.";
        }
        else
        {
          v21 = 0;
          v22 = L"%s: Box file hash does not match.";
        }
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v21 = g_shLogFile;
LABEL_33:
        OutputMsg(v21, v20, v22, L"CPackageScenarioCtrl::ShouldPreserveWorkingDir");
        if ( v15 )
        {
          v25 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v25 = g_shLogFile;
          OutputMsg(v25, g_shLogEvent, L"Opening Box: [%s]", *((_QWORD *)this + 2));
          v26 = *((_QWORD *)this + 2);
          if ( !v26 )
            v26 = 0;
          v27 = BoxOpenFromPath(v26, &v45);
          Header = v27;
          if ( v27 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27);
            v6 = v45;
            goto LABEL_68;
          }
          v28 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v28 = g_shLogFile;
          OutputMsg(v28, g_shLogEvent, L"Reading Box header...");
          *(_OWORD *)Src = 0;
          v6 = v45;
          Header = BoxReadHeader(v45, v49);
          if ( Header < 0 )
            goto LABEL_67;
          if ( !Src[1] )
          {
            Header = -2147019873;
            goto LABEL_67;
          }
          Header = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create((_WORD *)Src[1]);
          if ( Header < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Header);
            v7 = v46;
            goto LABEL_68;
          }
          v7 = v46;
          v29 = *((_QWORD *)this + 4);
          if ( !v29 )
            v29 = 0;
          v30 = CMiscHelpersT<CEmptyType>::CombinePath(v29, v46, 0);
          Header = v30;
          if ( v30 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30);
            v8 = lpFileName;
            goto LABEL_68;
          }
          v8 = lpFileName;
          FileAttributesW = GetFileAttributesW(lpFileName);
          v15 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          Header = 0;
          v32 = L"TRUE";
          if ( !v15 )
            v32 = L"FALSE";
          v33 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v33 = g_shLogFile;
          OutputMsg(v33, g_shLogEvent, L"Execute file [%s] exists: [%s]", v8, v32);
        }
LABEL_59:
        *((_DWORD *)this + 14) = v15;
        *a3 = v15;
        if ( Header >= 0 )
          goto LABEL_71;
        goto LABEL_68;
      }
      v21 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v21 = g_shLogFile;
      v22 = L"%s: PreDownload mode value not found.";
    }
    else
    {
      v15 = 1;
      v5 = v44;
      if ( !v44 )
      {
        v35 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v35 = g_shLogFile;
        OutputMsg(
          v35,
          g_shLogEvent,
          L"%s: Box file hash is missing.",
          L"CPackageScenarioCtrl::ShouldPreserveWorkingDir");
        Header = -1047527120;
        goto LABEL_67;
      }
      v23 = CompareStringW(0x409u, 1u, lpString1, -1, v44, -1) == 2;
      v24 = (char *)g_shLogFile - 1;
      if ( !v23 )
      {
        v34 = 0;
        if ( (unsigned __int64)v24 <= 0xFFFFFFFFFFFFFFFDuLL )
          v34 = g_shLogFile;
        OutputMsg(
          v34,
          g_shLogEvent,
          L"%s: Box file hash does not match.",
          L"CPackageScenarioCtrl::ShouldPreserveWorkingDir");
        Header = -1047527119;
        goto LABEL_67;
      }
      v21 = 0;
      if ( (unsigned __int64)v24 <= 0xFFFFFFFFFFFFFFFDuLL )
        v21 = g_shLogFile;
      v22 = L"%s: Box file hash matches.";
    }
    v20 = g_shLogEvent;
    goto LABEL_33;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(BoxHash);
  v4 = lpString1;
LABEL_68:
  v36 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v36 = g_shLogFile;
  LODWORD(lpString2) = Header;
  OutputMsg(v36, g_shLogEvent, L"%s: Error = 0x%X", L"CPackageScenarioCtrl::ShouldPreserveWorkingDir", lpString2);
LABEL_71:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Header);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v8 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v7 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
    FreeBoxFileHandle(v6);
  if ( v5 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x14001e1b0  mov     rax, rsp
0x14001e1b3  mov     [rax+18h], r8
0x14001e1b7  mov     [rax+8], rcx
0x14001e1bb  push    rbp
0x14001e1bc  push    rsi
0x14001e1bd  push    rdi
0x14001e1be  push    r12
0x14001e1c0  push    r13
0x14001e1c2  push    r14
0x14001e1c4  push    r15
0x14001e1c6  mov     rbp, rsp
0x14001e1c9  sub     rsp, 80h
0x14001e1d0  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x14001e1d8  mov     [rax+10h], rbx
0x14001e1dc  mov     rdi, rcx
0x14001e1df  xor     ecx, ecx
0x14001e1e1  mov     r15d, ecx
0x14001e1e4  mov     [rbp+lpString1], rcx
0x14001e1e8  mov     ebx, ecx
0x14001e1ea  mov     [rbp+var_48], rcx
0x14001e1ee  mov     r12d, ecx
0x14001e1f1  mov     [rbp+var_40], rcx
0x14001e1f5  mov     r13d, ecx
0x14001e1f8  mov     [rbp+var_38], rcx
0x14001e1fc  mov     r14d, ecx
0x14001e1ff  mov     [rbp+lpFileName], rcx
0x14001e203  mov     [rbp+arg_18], ecx
0x14001e206  test    r8, r8
0x14001e209  jnz     short loc_14001E215
0x14001e20b  mov     esi, 80070057h
0x14001e210  jmp     loc_14001E676
0x14001e215  lea     rcx, [rbp+lpString1]; this
0x14001e219  call    ?GenerateBoxHash@ScenarioCtrlHelpers@@YAJPEAPEAG@Z; ScenarioCtrlHelpers::GenerateBoxHash(ushort * *)
0x14001e21e  mov     esi, eax
0x14001e220  test    eax, eax
0x14001e222  jns     short loc_14001E234
0x14001e224  mov     ecx, eax
0x14001e226  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e22b  mov     r15, [rbp+lpString1]
0x14001e22f  jmp     loc_14001E67D
0x14001e234  mov     ecx, [rdi+8]
0x14001e237  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001e23c  mov     rdx, rax
0x14001e23f  lea     r9, [rbp+var_48]
0x14001e243  lea     r8, aBoxhash; "BoxHash"
0x14001e24a  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x14001e24f  xor     ebx, ebx
0x14001e251  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e258  mov     r10d, ebx
0x14001e25b  test    eax, eax
0x14001e25d  js      short loc_14001E280
0x14001e25f  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e266  lea     rax, [rcx-1]
0x14001e26a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e26e  setnbe  al
0x14001e271  test    al, al
0x14001e273  cmovz   r10, rcx
0x14001e277  lea     r8, aSFoundPrevious; "%s: Found previously stored file hash."
0x14001e27e  jmp     short loc_14001E29F
0x14001e280  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e287  lea     rax, [r8-1]
0x14001e28b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e28f  setnbe  al
0x14001e292  test    al, al
0x14001e294  cmovz   r10, r8
0x14001e298  lea     r8, aSPreviousFileH; "%s: Previous file hash not found."
0x14001e29f  lea     r9, aCpackagescenar_2; "CPackageScenarioCtrl::ShouldPreserveWor"...
0x14001e2a6  mov     rcx, r10; hFile
0x14001e2a9  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e2ae  mov     r15, [rbp+lpString1]
0x14001e2b2  mov     eax, 1
0x14001e2b7  cmp     [rdi+28h], eax
0x14001e2ba  jnz     loc_14001E3D3
0x14001e2c0  mov     edi, ebx
0x14001e2c2  mov     rbx, [rbp+var_48]
0x14001e2c6  test    rbx, rbx
0x14001e2c9  jz      loc_14001E5F3
0x14001e2cf  mov     rcx, [rbp+arg_0]
0x14001e2d3  mov     ecx, [rcx+8]
0x14001e2d6  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001e2db  mov     rdx, rax
0x14001e2de  lea     r9, [rbp+arg_18]
0x14001e2e2  lea     r8, aPredownloadmod; "PreDownloadMode"
0x14001e2e9  call    ?ValueExists@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAH@Z; CRegUtilT<ushort *,CRegType,0,1>::ValueExists(HKEY__ *,ushort const *,ushort const *,int *)
0x14001e2ee  xor     r11d, r11d
0x14001e2f1  test    eax, eax
0x14001e2f3  js      loc_14001E3AF
0x14001e2f9  cmp     [rbp+arg_18], r11d
0x14001e2fd  jz      loc_14001E3AF
0x14001e303  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e30a  lea     rax, [r8-1]
0x14001e30e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e312  setnbe  al
0x14001e315  mov     ecx, r11d
0x14001e318  test    al, al
0x14001e31a  cmovz   rcx, r8; hFile
0x14001e31e  lea     r9, aCpackagescenar_2; "CPackageScenarioCtrl::ShouldPreserveWor"...
0x14001e325  lea     r8, aSPredownloadMo_0; "%s: PreDownload mode value found."
0x14001e32c  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e333  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e338  or      r9d, 0FFFFFFFFh; cchCount1
0x14001e33c  mov     [rsp+80h+cchCount2], r9d; cchCount2
0x14001e341  mov     [rsp+80h+lpString2], rbx; lpString2
0x14001e346  mov     r8, r15; lpString1
0x14001e349  lea     edx, [r9+2]; dwCmpFlags
0x14001e34d  mov     ecx, 409h; Locale
0x14001e352  call    cs:__imp_CompareStringW
0x14001e359  nop     dword ptr [rax+rax+00h]
0x14001e35e  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; SH_HANDLE g_shLogEvent
0x14001e365  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e36c  cmp     eax, 2
0x14001e36f  lea     rax, [rcx-1]
0x14001e373  jnz     short loc_14001E390
0x14001e375  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e379  setnbe  al
0x14001e37c  mov     edi, 1
0x14001e381  xor     r11d, r11d
0x14001e384  mov     r10d, r11d
0x14001e387  lea     r8, aSBoxFileHashMa; "%s: Box file hash matches."
0x14001e38e  jmp     short loc_14001E3A4
0x14001e390  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e394  setnbe  al
0x14001e397  xor     r8d, r8d
0x14001e39a  mov     r10d, r8d
0x14001e39d  lea     r8, aSBoxFileHashDo; "%s: Box file hash does not match."
0x14001e3a4  test    al, al
0x14001e3a6  cmovz   r10, rcx
0x14001e3aa  jmp     loc_14001E43C
0x14001e3af  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e3b6  lea     rax, [rcx-1]
0x14001e3ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e3be  setnbe  al
0x14001e3c1  mov     r10, r11
0x14001e3c4  test    al, al
0x14001e3c6  cmovz   r10, rcx
0x14001e3ca  lea     r8, aSPredownloadMo; "%s: PreDownload mode value not found."
0x14001e3d1  jmp     short loc_14001E435
0x14001e3d3  mov     edi, eax
0x14001e3d5  mov     rbx, [rbp+var_48]
0x14001e3d9  xor     edx, edx
0x14001e3db  test    rbx, rbx
0x14001e3de  jz      loc_14001E63C
0x14001e3e4  or      r9d, 0FFFFFFFFh; cchCount1
0x14001e3e8  mov     [rsp+80h+cchCount2], r9d; cchCount2
0x14001e3ed  mov     [rsp+80h+lpString2], rbx; lpString2
0x14001e3f2  mov     r8, r15; lpString1
0x14001e3f5  mov     edx, eax; dwCmpFlags
0x14001e3f7  mov     ecx, 409h; Locale
0x14001e3fc  call    cs:__imp_CompareStringW
0x14001e403  nop     dword ptr [rax+rax+00h]
0x14001e408  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e40f  cmp     eax, 2
0x14001e412  lea     rax, [r8-1]
0x14001e416  jnz     loc_14001E60A
0x14001e41c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e420  setnbe  al
0x14001e423  xor     ecx, ecx
0x14001e425  mov     r10d, ecx
0x14001e428  test    al, al
0x14001e42a  cmovz   r10, r8
0x14001e42e  lea     r8, aSBoxFileHashMa; "%s: Box file hash matches."
0x14001e435  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e43c  lea     r9, aCpackagescenar_2; "CPackageScenarioCtrl::ShouldPreserveWor"...
0x14001e443  mov     rcx, r10; hFile
0x14001e446  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e44b  test    edi, edi
0x14001e44d  jz      loc_14001E5F3
0x14001e453  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e45a  lea     rax, [r8-1]
0x14001e45e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e462  setnbe  al
0x14001e465  xor     r12d, r12d
0x14001e468  mov     ecx, r12d
0x14001e46b  test    al, al
0x14001e46d  cmovz   rcx, r8; hFile
0x14001e471  mov     rdi, [rbp+arg_0]
0x14001e475  mov     r9, [rdi+10h]
0x14001e479  lea     r8, aOpeningBoxS; "Opening Box: [%s]"
0x14001e480  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e487  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e48c  mov     rcx, [rdi+10h]
0x14001e490  test    rcx, rcx
0x14001e493  cmovz   rcx, r12
0x14001e497  lea     rdx, [rbp+var_40]
0x14001e49b  call    BoxOpenFromPath
0x14001e4a0  mov     esi, eax
0x14001e4a2  test    eax, eax
0x14001e4a4  jns     short loc_14001E4B6
0x14001e4a6  mov     ecx, eax
0x14001e4a8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e4ad  mov     r12, [rbp+var_40]
0x14001e4b1  jmp     loc_14001E67D
0x14001e4b6  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e4bd  lea     rax, [r8-1]
0x14001e4c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e4c5  setnbe  al
0x14001e4c8  mov     rcx, r12
0x14001e4cb  test    al, al
0x14001e4cd  cmovz   rcx, r8; hFile
0x14001e4d1  lea     r8, aReadingBoxHead; "Reading Box header..."
0x14001e4d8  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e4df  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e4e4  xorps   xmm0, xmm0
0x14001e4e7  movups  xmmword ptr [rbp+Src], xmm0
0x14001e4eb  mov     r12, [rbp+var_40]
0x14001e4ef  lea     rdx, [rbp+var_20]
0x14001e4f3  mov     rcx, r12
0x14001e4f6  call    BoxReadHeader
0x14001e4fb  mov     esi, eax
0x14001e4fd  test    eax, eax
0x14001e4ff  js      loc_14001E676
0x14001e505  mov     rcx, [rbp+Src+8]; Src
0x14001e509  test    rcx, rcx
0x14001e50c  jnz     short loc_14001E518
0x14001e50e  mov     esi, 8007139Fh
0x14001e513  jmp     loc_14001E676
0x14001e518  lea     rdx, [rbp+var_38]
0x14001e51c  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001e521  mov     esi, eax
0x14001e523  xor     eax, eax
0x14001e525  test    esi, esi
0x14001e527  jns     short loc_14001E539
0x14001e529  mov     ecx, esi
0x14001e52b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e530  mov     r13, [rbp+var_38]
0x14001e534  jmp     loc_14001E67D
0x14001e539  mov     r13, [rbp+var_38]
0x14001e53d  mov     rcx, [rdi+20h]
0x14001e541  test    rcx, rcx
0x14001e544  cmovz   rcx, rax
0x14001e548  lea     r9, [rbp+lpFileName]
0x14001e54c  xor     r8d, r8d
0x14001e54f  mov     rdx, r13
0x14001e552  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001e557  mov     esi, eax
0x14001e559  test    eax, eax
0x14001e55b  jns     short loc_14001E56D
0x14001e55d  mov     ecx, eax
0x14001e55f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e564  mov     r14, [rbp+lpFileName]
0x14001e568  jmp     loc_14001E67D
0x14001e56d  mov     r14, [rbp+lpFileName]
0x14001e571  mov     rcx, r14; lpFileName
0x14001e574  call    cs:__imp_GetFileAttributesW
0x14001e57b  nop     dword ptr [rax+rax+00h]
0x14001e580  mov     edi, eax
0x14001e582  cmp     eax, 0FFFFFFFFh
0x14001e585  jz      short loc_14001E591
0x14001e587  shr     edi, 4
0x14001e58a  not     edi
0x14001e58c  and     edi, 1
0x14001e58f  jmp     short loc_14001E595
0x14001e591  xor     eax, eax
0x14001e593  mov     edi, eax
0x14001e595  xor     ecx, ecx
0x14001e597  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001e59c  xor     ecx, ecx
0x14001e59e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001e5a3  xor     r9d, r9d
0x14001e5a6  mov     esi, r9d
0x14001e5a9  lea     rax, aFalse_0; "FALSE"
0x14001e5b0  lea     rdx, aTrue; "TRUE"
0x14001e5b7  test    edi, edi
0x14001e5b9  cmovz   rdx, rax
0x14001e5bd  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e5c4  lea     rax, [r8-1]
0x14001e5c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e5cc  setnbe  al
0x14001e5cf  mov     ecx, r9d
0x14001e5d2  test    al, al
0x14001e5d4  cmovz   rcx, r8; hFile
0x14001e5d8  mov     [rsp+80h+lpString2], rdx
0x14001e5dd  mov     r9, r14
0x14001e5e0  lea     r8, aExecuteFileSEx; "Execute file [%s] exists: [%s]"
0x14001e5e7  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e5ee  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e5f3  mov     rax, [rbp+arg_0]
0x14001e5f7  mov     [rax+38h], edi
0x14001e5fa  mov     rax, [rbp+arg_10]
0x14001e5fe  mov     [rax], edi
0x14001e600  test    esi, esi
0x14001e602  jns     loc_14001E6B7
0x14001e608  jmp     short loc_14001E67D
0x14001e60a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e60e  setnbe  al
0x14001e611  xor     edx, edx
0x14001e613  mov     ecx, edx
0x14001e615  test    al, al
0x14001e617  cmovz   rcx, r8; hFile
0x14001e61b  lea     r9, aCpackagescenar_2; "CPackageScenarioCtrl::ShouldPreserveWor"...
0x14001e622  lea     r8, aSBoxFileHashDo; "%s: Box file hash does not match."
0x14001e629  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e630  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e635  mov     esi, 0C1900131h
0x14001e63a  jmp     short loc_14001E676
0x14001e63c  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e643  lea     rax, [r8-1]
0x14001e647  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e64b  setnbe  al
0x14001e64e  mov     rcx, rdx
  ... truncated ...
```
