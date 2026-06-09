# CUpdateScenarioCtrl::ShouldPreserveWorkingDir(int,int *)

- ea: `0x14001ec90`
- end: `0x14001f282`
- name: `?ShouldPreserveWorkingDir@CUpdateScenarioCtrl@@UEAAJHPEAH@Z`
- size: `1522`
- prototype: `__int64 __fastcall(CUpdateScenarioCtrl *this, unsigned __int16 **, int *)`
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
- `0x14001ec90`
- `0x1400203a8`
- `0x140053ba0`
- `0x140054ac8`
- `0x140054bd4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001f1b9`
- `KERNEL32!HeapFree` at `0x14001f1e7`
- `KERNEL32!HeapFree` at `0x14001f223`
- `KERNEL32!HeapFree` at `0x14001f251`
- `KERNEL32!HeapFree` at `0x14001f1b9`
- `KERNEL32!HeapFree` at `0x14001f1e7`
- `KERNEL32!HeapFree` at `0x14001f223`
- `KERNEL32!HeapFree` at `0x14001f251`
- `KERNEL32!GetProcessHeap` at `0x14001f1a4`
- `KERNEL32!GetProcessHeap` at `0x14001f1d2`
- `KERNEL32!GetProcessHeap` at `0x14001f20e`
- `KERNEL32!GetProcessHeap` at `0x14001f23c`
- `KERNEL32!GetProcessHeap` at `0x14001f1a4`
- `KERNEL32!GetProcessHeap` at `0x14001f1d2`
- `KERNEL32!GetProcessHeap` at `0x14001f20e`
- `KERNEL32!GetProcessHeap` at `0x14001f23c`
- `KERNEL32!GetFileAttributesW` at `0x14001f054`
- `KERNEL32!GetFileAttributesW` at `0x14001f054`
- `KERNEL32!CompareStringW` at `0x14001ee32`
- `KERNEL32!CompareStringW` at `0x14001eedc`
- `KERNEL32!CompareStringW` at `0x14001ee32`
- `KERNEL32!CompareStringW` at `0x14001eedc`

## string_xrefs

- `0x14001ed7f`: `CUpdateScenarioCtrl::ShouldPreserveWorkingDir`
- `0x14001edfe`: `CUpdateScenarioCtrl::ShouldPreserveWorkingDir`
- `0x14001ef1c`: `CUpdateScenarioCtrl::ShouldPreserveWorkingDir`
- `0x14001f0fb`: `CUpdateScenarioCtrl::ShouldPreserveWorkingDir`
- `0x14001f137`: `CUpdateScenarioCtrl::ShouldPreserveWorkingDir`
- `0x14001f17d`: `CUpdateScenarioCtrl::ShouldPreserveWorkingDir`
- `0x14001ef59`: `Opening Box: [%s]`
- `0x14001efb1`: `Reading Box header...`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpdateScenarioCtrl::ShouldPreserveWorkingDir(
        CUpdateScenarioCtrl *this,
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
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v48[16]; // [rsp+60h] [rbp-20h] BYREF
  void *Src[2]; // [rsp+70h] [rbp-10h]
  int v52; // [rsp+D8h] [rbp+58h] BYREF

  lpFileName[1] = (LPCWSTR)-2LL;
  v4 = 0;
  lpString1 = 0;
  v5 = 0;
  v44 = 0;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  v46 = 0;
  v8 = 0;
  lpFileName[0] = 0;
  v52 = 0;
  if ( !a3 )
  {
    Header = -2147024809;
LABEL_67:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Header);
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
        L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir");
    }
    else
    {
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v14 = g_shLogFile;
      OutputMsg(
        v14,
        g_shLogEvent,
        L"%s: Found previously stored file hash.",
        L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir");
    }
    v4 = lpString1;
    if ( *((_DWORD *)this + 17) == 1 )
    {
      v15 = 0;
      v5 = v44;
      if ( !v44 )
        goto LABEL_59;
      v16 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
      if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::ValueExists(v17, v16, L"PreDownloadMode", &v52) >= 0 && v52 )
      {
        v18 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v18 = g_shLogFile;
        OutputMsg(
          v18,
          g_shLogEvent,
          L"%s: PreDownload mode value found.",
          L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir");
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
        OutputMsg(v21, v20, v22, L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir");
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
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v27);
            v6 = v45;
            goto LABEL_68;
          }
          v28 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v28 = g_shLogFile;
          OutputMsg(v28, g_shLogEvent, L"Reading Box header...");
          *(_OWORD *)Src = 0;
          v6 = v45;
          Header = BoxReadHeader(v45, v48);
          if ( Header < 0 )
            goto LABEL_67;
          if ( !Src[1] )
          {
            Header = -2147019873;
            goto LABEL_67;
          }
          Header = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Src[1]);
          if ( Header < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Header);
            v7 = v46;
            goto LABEL_68;
          }
          v7 = v46;
          v29 = *((_QWORD *)this + 5);
          if ( !v29 )
            v29 = 0;
          v30 = CMiscHelpersT<CEmptyType>::CombinePath(v29, v46, 0, lpFileName);
          Header = v30;
          if ( v30 < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v30);
            v8 = lpFileName[0];
            goto LABEL_68;
          }
          v8 = lpFileName[0];
          FileAttributesW = GetFileAttributesW(lpFileName[0]);
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
        *((_DWORD *)this + 22) = v15;
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
        OutputMsg(v35, g_shLogEvent, L"%s: Box file hash is missing.", L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir");
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
          L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir");
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
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)BoxHash);
  v4 = lpString1;
LABEL_68:
  v36 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v36 = g_shLogFile;
  LODWORD(lpString2) = Header;
  OutputMsg(v36, g_shLogEvent, L"%s: Error = 0x%X", L"CUpdateScenarioCtrl::ShouldPreserveWorkingDir", lpString2);
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
0x14001ec90  mov     rax, rsp
0x14001ec93  mov     [rax+18h], r8
0x14001ec97  mov     [rax+8], rcx
0x14001ec9b  push    rbp
0x14001ec9c  push    rsi
0x14001ec9d  push    rdi
0x14001ec9e  push    r12
0x14001eca0  push    r13
0x14001eca2  push    r14
0x14001eca4  push    r15
0x14001eca6  mov     rbp, rsp
0x14001eca9  sub     rsp, 80h
0x14001ecb0  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x14001ecb8  mov     [rax+10h], rbx
0x14001ecbc  mov     rdi, rcx
0x14001ecbf  xor     ecx, ecx
0x14001ecc1  mov     r15d, ecx
0x14001ecc4  mov     [rbp+lpString1], rcx
0x14001ecc8  mov     ebx, ecx
0x14001ecca  mov     [rbp+var_48], rcx
0x14001ecce  mov     r12d, ecx
0x14001ecd1  mov     [rbp+var_40], rcx
0x14001ecd5  mov     r13d, ecx
0x14001ecd8  mov     [rbp+var_38], rcx
0x14001ecdc  mov     r14d, ecx
0x14001ecdf  mov     [rbp+lpFileName], rcx
0x14001ece3  mov     [rbp+arg_18], ecx
0x14001ece6  test    r8, r8
0x14001ece9  jnz     short loc_14001ECF5
0x14001eceb  mov     esi, 80070057h
0x14001ecf0  jmp     loc_14001F156
0x14001ecf5  lea     rcx, [rbp+lpString1]; this
0x14001ecf9  call    ?GenerateBoxHash@ScenarioCtrlHelpers@@YAJPEAPEAG@Z; ScenarioCtrlHelpers::GenerateBoxHash(ushort * *)
0x14001ecfe  mov     esi, eax
0x14001ed00  test    eax, eax
0x14001ed02  jns     short loc_14001ED14
0x14001ed04  mov     ecx, eax
0x14001ed06  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001ed0b  mov     r15, [rbp+lpString1]
0x14001ed0f  jmp     loc_14001F15D
0x14001ed14  mov     ecx, [rdi+8]
0x14001ed17  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001ed1c  mov     rdx, rax
0x14001ed1f  lea     r9, [rbp+var_48]
0x14001ed23  lea     r8, aBoxhash; "BoxHash"
0x14001ed2a  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x14001ed2f  xor     ebx, ebx
0x14001ed31  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001ed38  mov     r10d, ebx
0x14001ed3b  test    eax, eax
0x14001ed3d  js      short loc_14001ED60
0x14001ed3f  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ed46  lea     rax, [rcx-1]
0x14001ed4a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ed4e  setnbe  al
0x14001ed51  test    al, al
0x14001ed53  cmovz   r10, rcx
0x14001ed57  lea     r8, aSFoundPrevious; "%s: Found previously stored file hash."
0x14001ed5e  jmp     short loc_14001ED7F
0x14001ed60  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ed67  lea     rax, [r8-1]
0x14001ed6b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ed6f  setnbe  al
0x14001ed72  test    al, al
0x14001ed74  cmovz   r10, r8
0x14001ed78  lea     r8, aSPreviousFileH; "%s: Previous file hash not found."
0x14001ed7f  lea     r9, aCupdatescenari_0; "CUpdateScenarioCtrl::ShouldPreserveWork"...
0x14001ed86  mov     rcx, r10; hFile
0x14001ed89  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001ed8e  mov     r15, [rbp+lpString1]
0x14001ed92  mov     eax, 1
0x14001ed97  cmp     [rdi+44h], eax
0x14001ed9a  jnz     loc_14001EEB3
0x14001eda0  mov     edi, ebx
0x14001eda2  mov     rbx, [rbp+var_48]
0x14001eda6  test    rbx, rbx
0x14001eda9  jz      loc_14001F0D3
0x14001edaf  mov     rcx, [rbp+arg_0]
0x14001edb3  mov     ecx, [rcx+8]
0x14001edb6  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001edbb  mov     rdx, rax
0x14001edbe  lea     r9, [rbp+arg_18]
0x14001edc2  lea     r8, aPredownloadmod; "PreDownloadMode"
0x14001edc9  call    ?ValueExists@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAH@Z; CRegUtilT<ushort *,CRegType,0,1>::ValueExists(HKEY__ *,ushort const *,ushort const *,int *)
0x14001edce  xor     r11d, r11d
0x14001edd1  test    eax, eax
0x14001edd3  js      loc_14001EE8F
0x14001edd9  cmp     [rbp+arg_18], r11d
0x14001eddd  jz      loc_14001EE8F
0x14001ede3  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001edea  lea     rax, [r8-1]
0x14001edee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001edf2  setnbe  al
0x14001edf5  mov     ecx, r11d
0x14001edf8  test    al, al
0x14001edfa  cmovz   rcx, r8; hFile
0x14001edfe  lea     r9, aCupdatescenari_0; "CUpdateScenarioCtrl::ShouldPreserveWork"...
0x14001ee05  lea     r8, aSPredownloadMo_0; "%s: PreDownload mode value found."
0x14001ee0c  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001ee13  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001ee18  or      r9d, 0FFFFFFFFh; cchCount1
0x14001ee1c  mov     [rsp+80h+cchCount2], r9d; cchCount2
0x14001ee21  mov     [rsp+80h+lpString2], rbx; lpString2
0x14001ee26  mov     r8, r15; lpString1
0x14001ee29  lea     edx, [r9+2]; dwCmpFlags
0x14001ee2d  mov     ecx, 409h; Locale
0x14001ee32  call    cs:__imp_CompareStringW
0x14001ee39  nop     dword ptr [rax+rax+00h]
0x14001ee3e  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; SH_HANDLE g_shLogEvent
0x14001ee45  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ee4c  cmp     eax, 2
0x14001ee4f  lea     rax, [rcx-1]
0x14001ee53  jnz     short loc_14001EE70
0x14001ee55  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ee59  setnbe  al
0x14001ee5c  mov     edi, 1
0x14001ee61  xor     r11d, r11d
0x14001ee64  mov     r10d, r11d
0x14001ee67  lea     r8, aSBoxFileHashMa; "%s: Box file hash matches."
0x14001ee6e  jmp     short loc_14001EE84
0x14001ee70  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ee74  setnbe  al
0x14001ee77  xor     r8d, r8d
0x14001ee7a  mov     r10d, r8d
0x14001ee7d  lea     r8, aSBoxFileHashDo; "%s: Box file hash does not match."
0x14001ee84  test    al, al
0x14001ee86  cmovz   r10, rcx
0x14001ee8a  jmp     loc_14001EF1C
0x14001ee8f  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ee96  lea     rax, [rcx-1]
0x14001ee9a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ee9e  setnbe  al
0x14001eea1  mov     r10, r11
0x14001eea4  test    al, al
0x14001eea6  cmovz   r10, rcx
0x14001eeaa  lea     r8, aSPredownloadMo; "%s: PreDownload mode value not found."
0x14001eeb1  jmp     short loc_14001EF15
0x14001eeb3  mov     edi, eax
0x14001eeb5  mov     rbx, [rbp+var_48]
0x14001eeb9  xor     edx, edx
0x14001eebb  test    rbx, rbx
0x14001eebe  jz      loc_14001F11C
0x14001eec4  or      r9d, 0FFFFFFFFh; cchCount1
0x14001eec8  mov     [rsp+80h+cchCount2], r9d; cchCount2
0x14001eecd  mov     [rsp+80h+lpString2], rbx; lpString2
0x14001eed2  mov     r8, r15; lpString1
0x14001eed5  mov     edx, eax; dwCmpFlags
0x14001eed7  mov     ecx, 409h; Locale
0x14001eedc  call    cs:__imp_CompareStringW
0x14001eee3  nop     dword ptr [rax+rax+00h]
0x14001eee8  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001eeef  cmp     eax, 2
0x14001eef2  lea     rax, [r8-1]
0x14001eef6  jnz     loc_14001F0EA
0x14001eefc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ef00  setnbe  al
0x14001ef03  xor     ecx, ecx
0x14001ef05  mov     r10d, ecx
0x14001ef08  test    al, al
0x14001ef0a  cmovz   r10, r8
0x14001ef0e  lea     r8, aSBoxFileHashMa; "%s: Box file hash matches."
0x14001ef15  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001ef1c  lea     r9, aCupdatescenari_0; "CUpdateScenarioCtrl::ShouldPreserveWork"...
0x14001ef23  mov     rcx, r10; hFile
0x14001ef26  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001ef2b  test    edi, edi
0x14001ef2d  jz      loc_14001F0D3
0x14001ef33  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ef3a  lea     rax, [r8-1]
0x14001ef3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ef42  setnbe  al
0x14001ef45  xor     r12d, r12d
0x14001ef48  mov     ecx, r12d
0x14001ef4b  test    al, al
0x14001ef4d  cmovz   rcx, r8; hFile
0x14001ef51  mov     rdi, [rbp+arg_0]
0x14001ef55  mov     r9, [rdi+10h]
0x14001ef59  lea     r8, aOpeningBoxS; "Opening Box: [%s]"
0x14001ef60  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001ef67  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001ef6c  mov     rcx, [rdi+10h]
0x14001ef70  test    rcx, rcx
0x14001ef73  cmovz   rcx, r12
0x14001ef77  lea     rdx, [rbp+var_40]
0x14001ef7b  call    BoxOpenFromPath
0x14001ef80  mov     esi, eax
0x14001ef82  test    eax, eax
0x14001ef84  jns     short loc_14001EF96
0x14001ef86  mov     ecx, eax
0x14001ef88  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001ef8d  mov     r12, [rbp+var_40]
0x14001ef91  jmp     loc_14001F15D
0x14001ef96  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ef9d  lea     rax, [r8-1]
0x14001efa1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001efa5  setnbe  al
0x14001efa8  mov     rcx, r12
0x14001efab  test    al, al
0x14001efad  cmovz   rcx, r8; hFile
0x14001efb1  lea     r8, aReadingBoxHead; "Reading Box header..."
0x14001efb8  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001efbf  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001efc4  xorps   xmm0, xmm0
0x14001efc7  movups  xmmword ptr [rbp+Src], xmm0
0x14001efcb  mov     r12, [rbp+var_40]
0x14001efcf  lea     rdx, [rbp+var_20]
0x14001efd3  mov     rcx, r12
0x14001efd6  call    BoxReadHeader
0x14001efdb  mov     esi, eax
0x14001efdd  test    eax, eax
0x14001efdf  js      loc_14001F156
0x14001efe5  mov     rcx, [rbp+Src+8]; Src
0x14001efe9  test    rcx, rcx
0x14001efec  jnz     short loc_14001EFF8
0x14001efee  mov     esi, 8007139Fh
0x14001eff3  jmp     loc_14001F156
0x14001eff8  lea     rdx, [rbp+var_38]
0x14001effc  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001f001  mov     esi, eax
0x14001f003  xor     eax, eax
0x14001f005  test    esi, esi
0x14001f007  jns     short loc_14001F019
0x14001f009  mov     ecx, esi
0x14001f00b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001f010  mov     r13, [rbp+var_38]
0x14001f014  jmp     loc_14001F15D
0x14001f019  mov     r13, [rbp+var_38]
0x14001f01d  mov     rcx, [rdi+28h]
0x14001f021  test    rcx, rcx
0x14001f024  cmovz   rcx, rax
0x14001f028  lea     r9, [rbp+lpFileName]
0x14001f02c  xor     r8d, r8d
0x14001f02f  mov     rdx, r13
0x14001f032  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001f037  mov     esi, eax
0x14001f039  test    eax, eax
0x14001f03b  jns     short loc_14001F04D
0x14001f03d  mov     ecx, eax
0x14001f03f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001f044  mov     r14, [rbp+lpFileName]
0x14001f048  jmp     loc_14001F15D
0x14001f04d  mov     r14, [rbp+lpFileName]
0x14001f051  mov     rcx, r14; lpFileName
0x14001f054  call    cs:__imp_GetFileAttributesW
0x14001f05b  nop     dword ptr [rax+rax+00h]
0x14001f060  mov     edi, eax
0x14001f062  cmp     eax, 0FFFFFFFFh
0x14001f065  jz      short loc_14001F071
0x14001f067  shr     edi, 4
0x14001f06a  not     edi
0x14001f06c  and     edi, 1
0x14001f06f  jmp     short loc_14001F075
0x14001f071  xor     eax, eax
0x14001f073  mov     edi, eax
0x14001f075  xor     ecx, ecx
0x14001f077  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001f07c  xor     ecx, ecx
0x14001f07e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001f083  xor     r9d, r9d
0x14001f086  mov     esi, r9d
0x14001f089  lea     rax, aFalse_0; "FALSE"
0x14001f090  lea     rdx, aTrue; "TRUE"
0x14001f097  test    edi, edi
0x14001f099  cmovz   rdx, rax
0x14001f09d  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001f0a4  lea     rax, [r8-1]
0x14001f0a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001f0ac  setnbe  al
0x14001f0af  mov     ecx, r9d
0x14001f0b2  test    al, al
0x14001f0b4  cmovz   rcx, r8; hFile
0x14001f0b8  mov     [rsp+80h+lpString2], rdx
0x14001f0bd  mov     r9, r14
0x14001f0c0  lea     r8, aExecuteFileSEx; "Execute file [%s] exists: [%s]"
0x14001f0c7  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001f0ce  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001f0d3  mov     rax, [rbp+arg_0]
0x14001f0d7  mov     [rax+58h], edi
0x14001f0da  mov     rax, [rbp+arg_10]
0x14001f0de  mov     [rax], edi
0x14001f0e0  test    esi, esi
0x14001f0e2  jns     loc_14001F197
0x14001f0e8  jmp     short loc_14001F15D
0x14001f0ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001f0ee  setnbe  al
0x14001f0f1  xor     edx, edx
0x14001f0f3  mov     ecx, edx
0x14001f0f5  test    al, al
0x14001f0f7  cmovz   rcx, r8; hFile
0x14001f0fb  lea     r9, aCupdatescenari_0; "CUpdateScenarioCtrl::ShouldPreserveWork"...
0x14001f102  lea     r8, aSBoxFileHashDo; "%s: Box file hash does not match."
0x14001f109  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001f110  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001f115  mov     esi, 0C1900131h
0x14001f11a  jmp     short loc_14001F156
0x14001f11c  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001f123  lea     rax, [r8-1]
0x14001f127  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001f12b  setnbe  al
0x14001f12e  mov     rcx, rdx
  ... truncated ...
```
