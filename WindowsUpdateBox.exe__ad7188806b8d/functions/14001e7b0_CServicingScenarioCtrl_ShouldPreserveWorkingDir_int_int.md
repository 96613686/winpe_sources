# CServicingScenarioCtrl::ShouldPreserveWorkingDir(int,int *)

- ea: `0x14001e7b0`
- end: `0x14001ec80`
- name: `?ShouldPreserveWorkingDir@CServicingScenarioCtrl@@UEAAJHPEAH@Z`
- size: `1232`
- prototype: `__int64 __fastcall(CServicingScenarioCtrl *__hidden this, int, int *)`
- caller_count: `0`
- callee_count: `12`
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
- `0x14001e7b0`
- `0x140053ba0`
- `0x140054ac8`
- `0x140054bd4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001eb36`
- `KERNEL32!HeapFree` at `0x14001eb64`
- `KERNEL32!HeapFree` at `0x14001eba0`
- `KERNEL32!HeapFree` at `0x14001ebce`
- `KERNEL32!HeapFree` at `0x14001eb36`
- `KERNEL32!HeapFree` at `0x14001eb64`
- `KERNEL32!HeapFree` at `0x14001eba0`
- `KERNEL32!HeapFree` at `0x14001ebce`
- `KERNEL32!GetProcessHeap` at `0x14001eb21`
- `KERNEL32!GetProcessHeap` at `0x14001eb4f`
- `KERNEL32!GetProcessHeap` at `0x14001eb8b`
- `KERNEL32!GetProcessHeap` at `0x14001ebb9`
- `KERNEL32!GetProcessHeap` at `0x14001eb21`
- `KERNEL32!GetProcessHeap` at `0x14001eb4f`
- `KERNEL32!GetProcessHeap` at `0x14001eb8b`
- `KERNEL32!GetProcessHeap` at `0x14001ebb9`
- `KERNEL32!GetFileAttributesW` at `0x14001ea4e`
- `KERNEL32!GetFileAttributesW` at `0x14001ea4e`
- `KERNEL32!CompareStringW` at `0x14001e8e3`
- `KERNEL32!CompareStringW` at `0x14001e8e3`

## string_xrefs

- `0x14001e953`: `Opening Box: [%s]`
- `0x14001e9ab`: `Reading Box header...`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CServicingScenarioCtrl::ShouldPreserveWorkingDir(
        CServicingScenarioCtrl *this,
        unsigned __int16 **a2,
        int *a3)
{
  PCNZWCH v3; // r15
  PCNZWCH v4; // rbx
  void *v5; // r12
  __int64 v6; // r13
  LPCWSTR v7; // r14
  int Header; // esi
  BOOL v9; // edi
  int BoxHash; // eax
  __int64 SetupVolatileRegKey; // rax
  __int64 v12; // rcx
  int Value; // eax
  HANDLE v14; // r10
  bool v15; // zf
  char *v16; // rax
  HANDLE v17; // rcx
  HANDLE v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  HANDLE v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  DWORD FileAttributesW; // eax
  const wchar_t *v25; // rdx
  HANDLE v26; // rcx
  CServicingScenarioCtrl *v27; // rax
  HANDLE v28; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v30; // rax
  HANDLE v31; // rax
  HANDLE v32; // rax
  HANDLE v34; // rcx
  HANDLE v35; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-60h]
  LPVOID lpMem; // [rsp+30h] [rbp-50h] BYREF
  __int64 v38; // [rsp+38h] [rbp-48h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-40h]
  PCNZWCH v40[2]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v41[16]; // [rsp+58h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+68h] [rbp-18h]
  PCNZWCH lpString1; // [rsp+D8h] [rbp+58h] BYREF

  v40[1] = (PCNZWCH)-2LL;
  v3 = 0;
  lpString1 = 0;
  v4 = 0;
  v40[0] = 0;
  v5 = 0;
  lpMem = 0;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  lpFileName = 0;
  if ( a3 )
  {
    v9 = 0;
    BoxHash = ScenarioCtrlHelpers::GenerateBoxHash((ScenarioCtrlHelpers *)&lpString1, a2);
    Header = BoxHash;
    if ( BoxHash < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(BoxHash);
      v3 = lpString1;
      goto LABEL_43;
    }
    SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)this + 2));
    Value = CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(v12, SetupVolatileRegKey, L"BoxHash", v40);
    v14 = 0;
    if ( Value < 0 )
    {
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v14 = g_shLogFile;
      OutputMsg(
        v14,
        g_shLogEvent,
        L"%s: Previous file hash not found.",
        L"CServicingScenarioCtrl::ShouldPreserveWorkingDir");
    }
    else
    {
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v14 = g_shLogFile;
      OutputMsg(
        v14,
        g_shLogEvent,
        L"%s: Found previously stored file hash.",
        L"CServicingScenarioCtrl::ShouldPreserveWorkingDir");
    }
    v3 = lpString1;
    v4 = v40[0];
    if ( v40[0] )
    {
      v15 = CompareStringW(0x409u, 1u, lpString1, -1, v40[0], -1) == 2;
      v16 = (char *)g_shLogFile - 1;
      if ( v15 )
      {
        v17 = 0;
        if ( (unsigned __int64)v16 <= 0xFFFFFFFFFFFFFFFDuLL )
          v17 = g_shLogFile;
        OutputMsg(v17, g_shLogEvent, L"%s: Box file hash matches.", L"CServicingScenarioCtrl::ShouldPreserveWorkingDir");
        v18 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v18 = g_shLogFile;
        OutputMsg(v18, g_shLogEvent, L"Opening Box: [%s]", *((_QWORD *)this + 2));
        v19 = *((_QWORD *)this + 2);
        if ( !v19 )
          v19 = 0;
        v20 = BoxOpenFromPath(v19, &lpMem);
        Header = v20;
        if ( v20 < 0 )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
          v5 = lpMem;
          goto LABEL_43;
        }
        v21 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v21 = g_shLogFile;
        OutputMsg(v21, g_shLogEvent, L"Reading Box header...");
        *(_OWORD *)Src = 0;
        v5 = lpMem;
        Header = BoxReadHeader(lpMem, v41);
        if ( Header < 0 )
          goto LABEL_3;
        if ( !Src[1] )
        {
          Header = -2147019873;
          goto LABEL_3;
        }
        Header = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create((_WORD *)Src[1]);
        if ( Header < 0 )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Header);
          v6 = v38;
          goto LABEL_43;
        }
        v6 = v38;
        v22 = *((_QWORD *)this + 4);
        if ( !v22 )
          v22 = 0;
        v23 = CMiscHelpersT<CEmptyType>::CombinePath(v22, v38, 0);
        Header = v23;
        if ( v23 < 0 )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
          v7 = lpFileName;
          goto LABEL_43;
        }
        v7 = lpFileName;
        FileAttributesW = GetFileAttributesW(lpFileName);
        v9 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        Header = 0;
        v25 = L"TRUE";
        if ( !v9 )
          v25 = L"FALSE";
        v26 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v26 = g_shLogFile;
        OutputMsg(v26, g_shLogEvent, L"Execute file [%s] exists: [%s]", v7, v25);
        v27 = this;
      }
      else
      {
        v34 = 0;
        if ( (unsigned __int64)v16 <= 0xFFFFFFFFFFFFFFFDuLL )
          v34 = g_shLogFile;
        OutputMsg(
          v34,
          g_shLogEvent,
          L"%s: Box file hash does not match.",
          L"CServicingScenarioCtrl::ShouldPreserveWorkingDir");
        v27 = this;
        if ( *((_DWORD *)this + 10) == 3 )
        {
          Header = -1047527119;
          goto LABEL_3;
        }
      }
    }
    else
    {
      v35 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v35 = g_shLogFile;
      OutputMsg(
        v35,
        g_shLogEvent,
        L"%s: Box file hash is missing.",
        L"CServicingScenarioCtrl::ShouldPreserveWorkingDir");
      v27 = this;
      if ( *((_DWORD *)this + 10) == 3 )
      {
        Header = -1047527120;
        goto LABEL_3;
      }
    }
    *((_DWORD *)v27 + 3) = v9;
    *a3 = v9;
    if ( Header >= 0 )
      goto LABEL_46;
    goto LABEL_43;
  }
  Header = -2147024809;
LABEL_3:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Header);
LABEL_43:
  v28 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v28 = g_shLogFile;
  LODWORD(lpString2) = Header;
  OutputMsg(v28, g_shLogEvent, L"%s: Error = 0x%X", L"CServicingScenarioCtrl::ShouldPreserveWorkingDir", lpString2);
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Header);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
    FreeBoxFileHandle(v5);
  if ( v4 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x14001e7b0  mov     rax, rsp
0x14001e7b3  mov     [rax+18h], r8
0x14001e7b7  mov     [rax+8], rcx
0x14001e7bb  push    rbp
0x14001e7bc  push    rsi
0x14001e7bd  push    rdi
0x14001e7be  push    r12
0x14001e7c0  push    r13
0x14001e7c2  push    r14
0x14001e7c4  push    r15
0x14001e7c6  mov     rbp, rsp
0x14001e7c9  sub     rsp, 80h
0x14001e7d0  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x14001e7d8  mov     [rax+10h], rbx
0x14001e7dc  xor     ecx, ecx
0x14001e7de  mov     r15d, ecx
0x14001e7e1  mov     [rbp+lpString1], rcx
0x14001e7e5  mov     ebx, ecx
0x14001e7e7  mov     [rbp+var_38], rcx
0x14001e7eb  mov     r12d, ecx
0x14001e7ee  mov     [rbp+lpMem], rcx
0x14001e7f2  mov     r13d, ecx
0x14001e7f5  mov     [rbp+var_48], rcx
0x14001e7f9  mov     r14d, ecx
0x14001e7fc  mov     [rbp+lpFileName], rcx
0x14001e800  test    r8, r8
0x14001e803  jnz     short loc_14001E816
0x14001e805  mov     esi, 80070057h
0x14001e80a  mov     ecx, esi
0x14001e80c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e811  jmp     loc_14001EADC
0x14001e816  mov     edi, ecx
0x14001e818  lea     rcx, [rbp+lpString1]; this
0x14001e81c  call    ?GenerateBoxHash@ScenarioCtrlHelpers@@YAJPEAPEAG@Z; ScenarioCtrlHelpers::GenerateBoxHash(ushort * *)
0x14001e821  mov     esi, eax
0x14001e823  xor     r15d, r15d
0x14001e826  test    eax, eax
0x14001e828  jns     short loc_14001E83A
0x14001e82a  mov     ecx, eax
0x14001e82c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e831  mov     r15, [rbp+lpString1]
0x14001e835  jmp     loc_14001EADC
0x14001e83a  mov     rax, [rbp+arg_0]
0x14001e83e  mov     ecx, [rax+8]
0x14001e841  call    ?GetSetupVolatileRegKey@MoSetupReg@@YAPEBGW4MoSetupScenario@@@Z; MoSetupReg::GetSetupVolatileRegKey(MoSetupScenario)
0x14001e846  mov     rdx, rax
0x14001e849  lea     r9, [rbp+var_38]
0x14001e84d  lea     r8, aBoxhash; "BoxHash"
0x14001e854  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x14001e859  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e860  mov     r10, r15
0x14001e863  test    eax, eax
0x14001e865  js      short loc_14001E888
0x14001e867  mov     rcx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e86e  lea     rax, [rcx-1]
0x14001e872  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e876  setnbe  al
0x14001e879  test    al, al
0x14001e87b  cmovz   r10, rcx
0x14001e87f  lea     r8, aSFoundPrevious; "%s: Found previously stored file hash."
0x14001e886  jmp     short loc_14001E8A7
0x14001e888  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e88f  lea     rax, [r8-1]
0x14001e893  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e897  setnbe  al
0x14001e89a  test    al, al
0x14001e89c  cmovz   r10, r8
0x14001e8a0  lea     r8, aSPreviousFileH; "%s: Previous file hash not found."
0x14001e8a7  lea     r9, aCservicingscen_0; "CServicingScenarioCtrl::ShouldPreserveW"...
0x14001e8ae  mov     rcx, r10; hFile
0x14001e8b1  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e8b6  mov     r15, [rbp+lpString1]
0x14001e8ba  mov     rbx, [rbp+var_38]
0x14001e8be  xor     edx, edx
0x14001e8c0  test    rbx, rbx
0x14001e8c3  jz      loc_14001EC32
0x14001e8c9  or      r9d, 0FFFFFFFFh; cchCount1
0x14001e8cd  mov     [rsp+80h+cchCount2], r9d; cchCount2
0x14001e8d2  mov     [rsp+80h+lpString2], rbx; lpString2
0x14001e8d7  mov     r8, r15; lpString1
0x14001e8da  lea     edx, [r9+2]; dwCmpFlags
0x14001e8de  mov     ecx, 409h; Locale
0x14001e8e3  call    cs:__imp_CompareStringW
0x14001e8ea  nop     dword ptr [rax+rax+00h]
0x14001e8ef  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e8f6  lea     r9, aCservicingscen_0; "CServicingScenarioCtrl::ShouldPreserveW"...
0x14001e8fd  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e904  cmp     eax, 2
0x14001e907  lea     rax, [r8-1]
0x14001e90b  jnz     loc_14001EBFF
0x14001e911  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e915  setnbe  al
0x14001e918  xor     r12d, r12d
0x14001e91b  mov     ecx, r12d
0x14001e91e  test    al, al
0x14001e920  cmovz   rcx, r8; hFile
0x14001e924  lea     r8, aSBoxFileHashMa; "%s: Box file hash matches."
0x14001e92b  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e930  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e937  lea     rax, [r8-1]
0x14001e93b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e93f  setnbe  al
0x14001e942  mov     ecx, r12d
0x14001e945  test    al, al
0x14001e947  cmovz   rcx, r8; hFile
0x14001e94b  mov     rdi, [rbp+arg_0]
0x14001e94f  mov     r9, [rdi+10h]
0x14001e953  lea     r8, aOpeningBoxS; "Opening Box: [%s]"
0x14001e95a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e961  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e966  mov     rcx, [rdi+10h]
0x14001e96a  test    rcx, rcx
0x14001e96d  cmovz   rcx, r12
0x14001e971  lea     rdx, [rbp+lpMem]
0x14001e975  call    BoxOpenFromPath
0x14001e97a  mov     esi, eax
0x14001e97c  test    eax, eax
0x14001e97e  jns     short loc_14001E990
0x14001e980  mov     ecx, eax
0x14001e982  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001e987  mov     r12, [rbp+lpMem]
0x14001e98b  jmp     loc_14001EADC
0x14001e990  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001e997  lea     rax, [r8-1]
0x14001e99b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001e99f  setnbe  al
0x14001e9a2  mov     rcx, r12
0x14001e9a5  test    al, al
0x14001e9a7  cmovz   rcx, r8; hFile
0x14001e9ab  lea     r8, aReadingBoxHead; "Reading Box header..."
0x14001e9b2  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001e9b9  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001e9be  xorps   xmm0, xmm0
0x14001e9c1  movups  xmmword ptr [rbp+Src], xmm0
0x14001e9c5  mov     r12, [rbp+lpMem]
0x14001e9c9  lea     rdx, [rbp+var_28]
0x14001e9cd  mov     rcx, r12
0x14001e9d0  call    BoxReadHeader
0x14001e9d5  mov     esi, eax
0x14001e9d7  test    eax, eax
0x14001e9d9  js      loc_14001E80A
0x14001e9df  mov     rcx, [rbp+Src+8]; Src
0x14001e9e3  test    rcx, rcx
0x14001e9e6  jnz     short loc_14001E9F2
0x14001e9e8  mov     esi, 8007139Fh
0x14001e9ed  jmp     loc_14001E80A
0x14001e9f2  lea     rdx, [rbp+var_48]
0x14001e9f6  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001e9fb  mov     esi, eax
0x14001e9fd  xor     eax, eax
0x14001e9ff  test    esi, esi
0x14001ea01  jns     short loc_14001EA13
0x14001ea03  mov     ecx, esi
0x14001ea05  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001ea0a  mov     r13, [rbp+var_48]
0x14001ea0e  jmp     loc_14001EADC
0x14001ea13  mov     r13, [rbp+var_48]
0x14001ea17  mov     rcx, [rdi+20h]
0x14001ea1b  test    rcx, rcx
0x14001ea1e  cmovz   rcx, rax
0x14001ea22  lea     r9, [rbp+lpFileName]
0x14001ea26  xor     r8d, r8d
0x14001ea29  mov     rdx, r13
0x14001ea2c  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14001ea31  mov     esi, eax
0x14001ea33  test    eax, eax
0x14001ea35  jns     short loc_14001EA47
0x14001ea37  mov     ecx, eax
0x14001ea39  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001ea3e  mov     r14, [rbp+lpFileName]
0x14001ea42  jmp     loc_14001EADC
0x14001ea47  mov     r14, [rbp+lpFileName]
0x14001ea4b  mov     rcx, r14; lpFileName
0x14001ea4e  call    cs:__imp_GetFileAttributesW
0x14001ea55  nop     dword ptr [rax+rax+00h]
0x14001ea5a  mov     edi, eax
0x14001ea5c  cmp     eax, 0FFFFFFFFh
0x14001ea5f  jz      short loc_14001EA6B
0x14001ea61  shr     edi, 4
0x14001ea64  not     edi
0x14001ea66  and     edi, 1
0x14001ea69  jmp     short loc_14001EA6D
0x14001ea6b  xor     edi, edi
0x14001ea6d  xor     ecx, ecx
0x14001ea6f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ea74  xor     ecx, ecx
0x14001ea76  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ea7b  xor     r9d, r9d
0x14001ea7e  mov     esi, r9d
0x14001ea81  lea     rax, aFalse_0; "FALSE"
0x14001ea88  lea     rdx, aTrue; "TRUE"
0x14001ea8f  test    edi, edi
0x14001ea91  cmovz   rdx, rax
0x14001ea95  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ea9c  lea     rax, [r8-1]
0x14001eaa0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001eaa4  setnbe  al
0x14001eaa7  mov     ecx, r9d
0x14001eaaa  test    al, al
0x14001eaac  cmovz   rcx, r8; hFile
0x14001eab0  mov     [rsp+80h+lpString2], rdx
0x14001eab5  mov     r9, r14
0x14001eab8  lea     r8, aExecuteFileSEx; "Execute file [%s] exists: [%s]"
0x14001eabf  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001eac6  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001eacb  mov     rax, [rbp+arg_0]
0x14001eacf  mov     [rax+0Ch], edi
0x14001ead2  mov     rax, [rbp+arg_10]
0x14001ead6  mov     [rax], edi
0x14001ead8  test    esi, esi
0x14001eada  jns     short loc_14001EB14
0x14001eadc  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001eae3  lea     rax, [r8-1]
0x14001eae7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001eaeb  setnbe  al
0x14001eaee  xor     ecx, ecx
0x14001eaf0  test    al, al
0x14001eaf2  cmovz   rcx, r8; hFile
0x14001eaf6  mov     dword ptr [rsp+80h+lpString2], esi
0x14001eafa  lea     r9, aCservicingscen_0; "CServicingScenarioCtrl::ShouldPreserveW"...
0x14001eb01  lea     r8, aSError0xX; "%s: Error = 0x%X"
0x14001eb08  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001eb0f  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001eb14  mov     ecx, esi
0x14001eb16  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001eb1b  nop
0x14001eb1c  test    r14, r14
0x14001eb1f  jz      short loc_14001EB4A
0x14001eb21  call    cs:__imp_GetProcessHeap
0x14001eb28  nop     dword ptr [rax+rax+00h]
0x14001eb2d  mov     rcx, rax; hHeap
0x14001eb30  lea     r8, [r14-4]; lpMem
0x14001eb34  xor     edx, edx; dwFlags
0x14001eb36  call    cs:__imp_HeapFree
0x14001eb3d  nop     dword ptr [rax+rax+00h]
0x14001eb42  xor     ecx, ecx
0x14001eb44  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001eb49  nop
0x14001eb4a  test    r13, r13
0x14001eb4d  jz      short loc_14001EB78
0x14001eb4f  call    cs:__imp_GetProcessHeap
0x14001eb56  nop     dword ptr [rax+rax+00h]
0x14001eb5b  mov     rcx, rax; hHeap
0x14001eb5e  lea     r8, [r13-4]; lpMem
0x14001eb62  xor     edx, edx; dwFlags
0x14001eb64  call    cs:__imp_HeapFree
0x14001eb6b  nop     dword ptr [rax+rax+00h]
0x14001eb70  xor     ecx, ecx
0x14001eb72  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001eb77  nop
0x14001eb78  test    r12, r12
0x14001eb7b  jz      short loc_14001EB86
0x14001eb7d  mov     rcx, r12; lpMem
0x14001eb80  call    FreeBoxFileHandle
0x14001eb85  nop
0x14001eb86  test    rbx, rbx
0x14001eb89  jz      short loc_14001EBB4
0x14001eb8b  call    cs:__imp_GetProcessHeap
0x14001eb92  nop     dword ptr [rax+rax+00h]
0x14001eb97  mov     rcx, rax; hHeap
0x14001eb9a  lea     r8, [rbx-4]; lpMem
0x14001eb9e  xor     edx, edx; dwFlags
0x14001eba0  call    cs:__imp_HeapFree
0x14001eba7  nop     dword ptr [rax+rax+00h]
0x14001ebac  xor     ecx, ecx
0x14001ebae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ebb3  nop
0x14001ebb4  test    r15, r15
0x14001ebb7  jz      short loc_14001EBE1
0x14001ebb9  call    cs:__imp_GetProcessHeap
0x14001ebc0  nop     dword ptr [rax+rax+00h]
0x14001ebc5  mov     rcx, rax; hHeap
0x14001ebc8  lea     r8, [r15-4]; lpMem
0x14001ebcc  xor     edx, edx; dwFlags
0x14001ebce  call    cs:__imp_HeapFree
0x14001ebd5  nop     dword ptr [rax+rax+00h]
0x14001ebda  xor     ecx, ecx
0x14001ebdc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001ebe1  mov     eax, esi
0x14001ebe3  mov     rbx, [rsp+80h+arg_8]
0x14001ebeb  add     rsp, 80h
0x14001ebf2  pop     r15
0x14001ebf4  pop     r14
0x14001ebf6  pop     r13
0x14001ebf8  pop     r12
0x14001ebfa  pop     rdi
0x14001ebfb  pop     rsi
0x14001ebfc  pop     rbp
0x14001ebfd  retn
0x14001ebff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ec03  setnbe  al
0x14001ec06  xor     ecx, ecx
0x14001ec08  test    al, al
0x14001ec0a  cmovz   rcx, r8; hFile
0x14001ec0e  lea     r8, aSBoxFileHashDo; "%s: Box file hash does not match."
0x14001ec15  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001ec1a  mov     rax, [rbp+arg_0]
0x14001ec1e  cmp     dword ptr [rax+28h], 3
0x14001ec22  jnz     loc_14001EACF
0x14001ec28  mov     esi, 0C1900131h
  ... truncated ...
```
