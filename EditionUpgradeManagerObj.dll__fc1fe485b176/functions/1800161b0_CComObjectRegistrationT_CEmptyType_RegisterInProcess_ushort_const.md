# CComObjectRegistrationT<CEmptyType>::RegisterInProcess(ushort const *)

- ea: `0x1800161b0`
- end: `0x180016318`
- name: `?RegisterInProcess@?$CComObjectRegistrationT@VCEmptyType@@@@AEAAJPEBG@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015864`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c0cc`
- `0x18000c45c`
- `0x180011e90`
- `0x1800127a0`
- `0x1800142f8`
- `0x1800161b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162ed`

## string_xrefs

- `0x180016293`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall CComObjectRegistrationT<CEmptyType>::RegisterInProcess(__int64 a1, __int64 a2)
{
  void *v3; // rbx
  int CurrentModuleFileName; // eax
  _WORD *v6; // rsi
  int v7; // edi
  int v8; // ecx
  int appended; // eax
  __int64 v10; // rcx
  int PointerDataSize; // eax
  __int64 v12; // rcx
  _WORD *v13; // r14
  int v14; // eax
  __int64 v15; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  LPVOID lpMem[3]; // [rsp+30h] [rbp-18h] BYREF
  _WORD *v20; // [rsp+90h] [rbp+48h] BYREF

  v20 = 0;
  v3 = 0;
  lpMem[0] = 0;
  lpMem[1] = 0;
  CurrentModuleFileName = CComHelpersT<CEmptyType>::GetCurrentModuleFileName(&v20);
  v6 = v20;
  v7 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
    goto LABEL_2;
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)lpMem,
               L"%s\\InprocServer32",
               a2);
  v7 = appended;
  if ( appended < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(appended);
    v3 = lpMem[0];
    goto LABEL_16;
  }
  v3 = lpMem[0];
  CurrentModuleFileName = CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(v10, (const WCHAR *)lpMem[0]);
  v7 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
  {
LABEL_2:
    v8 = CurrentModuleFileName;
LABEL_15:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_16;
  }
  LODWORD(v20) = 0;
  PointerDataSize = CRegType<unsigned short *>::GetPointerDataSize(v6, &v20);
  v7 = PointerDataSize;
  if ( PointerDataSize < 0
    || (PointerDataSize = CRegUtilT<unsigned short *,CRegType,0,0>::SetValue(v12, v3, 0, v6, (_DWORD)v20),
        v7 = PointerDataSize,
        PointerDataSize < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(PointerDataSize);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v7 < 0 )
    goto LABEL_14;
  v13 = *(_WORD **)(a1 + 72);
  LODWORD(v20) = 0;
  v14 = CRegType<unsigned short *>::GetPointerDataSize(v13, &v20);
  v7 = v14;
  if ( v14 < 0
    || (v14 = CRegUtilT<unsigned short *,CRegType,0,0>::SetValue(v15, v3, L"ThreadingModel", v13, (_DWORD)v20),
        v7 = v14,
        v14 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v7 < 0 )
  {
LABEL_14:
    v8 = v7;
    goto LABEL_15;
  }
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  if ( v6 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v6 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800161b0  push    rbp
0x1800161b2  push    rbx
0x1800161b3  push    rsi
0x1800161b4  push    rdi
0x1800161b5  push    r14
0x1800161b7  push    r15
0x1800161b9  mov     rbp, rsp
0x1800161bc  sub     rsp, 48h
0x1800161c0  mov     r15, rcx
0x1800161c3  mov     [rbp+arg_10], 0
0x1800161cb  xor     ebx, ebx
0x1800161cd  lea     rcx, [rbp+arg_10]
0x1800161d1  mov     [rbp+lpMem], rbx
0x1800161d5  mov     r14, rdx
0x1800161d8  mov     [rbp+var_10], rbx
0x1800161dc  call    ?GetCurrentModuleFileName@?$CComHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CComHelpersT<CEmptyType>::GetCurrentModuleFileName(ushort * *)
0x1800161e1  mov     rsi, [rbp+arg_10]
0x1800161e5  mov     edi, eax
0x1800161e7  test    eax, eax
0x1800161e9  jns     short loc_1800161F2
0x1800161eb  mov     ecx, eax
0x1800161ed  jmp     loc_1800162C3
0x1800161f2  mov     r8, r14
0x1800161f5  lea     rdx, aSInprocserver3; "%s\\InprocServer32"
0x1800161fc  lea     rcx, [rbp+lpMem]
0x180016200  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x180016205  mov     edi, eax
0x180016207  test    eax, eax
0x180016209  jns     short loc_18001621B
0x18001620b  mov     ecx, eax
0x18001620d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016212  mov     rbx, [rbp+lpMem]
0x180016216  jmp     loc_1800162C8
0x18001621b  mov     rbx, [rbp+lpMem]
0x18001621f  mov     rdx, rbx
0x180016222  call    ?CreateOrOpenKey@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x180016227  mov     edi, eax
0x180016229  test    eax, eax
0x18001622b  js      short loc_1800161EB
0x18001622d  lea     rdx, [rbp+arg_10]
0x180016231  mov     dword ptr [rbp+arg_10], 0
0x180016238  mov     rcx, rsi
0x18001623b  call    ?GetPointerDataSize@?$CRegType@PEAG@@SAJPEBGPEAK@Z; CRegType<ushort *>::GetPointerDataSize(ushort const *,ulong *)
0x180016240  mov     edi, eax
0x180016242  test    eax, eax
0x180016244  js      short loc_180016261
0x180016246  mov     eax, dword ptr [rbp+arg_10]
0x180016249  mov     r9, rsi
0x18001624c  xor     r8d, r8d
0x18001624f  mov     [rsp+48h+var_28], eax
0x180016253  mov     rdx, rbx
0x180016256  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG11K@Z; CRegUtilT<ushort *,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18001625b  mov     edi, eax
0x18001625d  test    eax, eax
0x18001625f  jns     short loc_180016268
0x180016261  mov     ecx, eax
0x180016263  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016268  mov     ecx, edi
0x18001626a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001626f  test    edi, edi
0x180016271  js      short loc_1800162C1
0x180016273  mov     r14, [r15+48h]
0x180016277  lea     rdx, [rbp+arg_10]
0x18001627b  mov     rcx, r14
0x18001627e  mov     dword ptr [rbp+arg_10], 0
0x180016285  call    ?GetPointerDataSize@?$CRegType@PEAG@@SAJPEBGPEAK@Z; CRegType<ushort *>::GetPointerDataSize(ushort const *,ulong *)
0x18001628a  mov     edi, eax
0x18001628c  test    eax, eax
0x18001628e  js      short loc_1800162AF
0x180016290  mov     eax, dword ptr [rbp+arg_10]
0x180016293  lea     r8, aThreadingmodel; "ThreadingModel"
0x18001629a  mov     r9, r14
0x18001629d  mov     [rsp+48h+var_28], eax
0x1800162a1  mov     rdx, rbx
0x1800162a4  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG11K@Z; CRegUtilT<ushort *,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x1800162a9  mov     edi, eax
0x1800162ab  test    eax, eax
0x1800162ad  jns     short loc_1800162B6
0x1800162af  mov     ecx, eax
0x1800162b1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800162b6  mov     ecx, edi
0x1800162b8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800162bd  test    edi, edi
0x1800162bf  jns     short loc_1800162C8
0x1800162c1  mov     ecx, edi
0x1800162c3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800162c8  mov     ecx, edi
0x1800162ca  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800162cf  test    rbx, rbx
0x1800162d2  jz      short loc_1800162E8
0x1800162d4  call    cs:__imp_GetProcessHeap
0x1800162da  mov     r8, rbx; lpMem
0x1800162dd  xor     edx, edx; dwFlags
0x1800162df  mov     rcx, rax; hHeap
0x1800162e2  call    cs:__imp_HeapFree
0x1800162e8  test    rsi, rsi
0x1800162eb  jz      short loc_180016309
0x1800162ed  call    cs:__imp_GetProcessHeap
0x1800162f3  lea     r8, [rsi-4]; lpMem
0x1800162f7  xor     edx, edx; dwFlags
0x1800162f9  mov     rcx, rax; hHeap
0x1800162fc  call    cs:__imp_HeapFree
0x180016302  xor     ecx, ecx
0x180016304  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016309  mov     eax, edi
0x18001630b  add     rsp, 48h
0x18001630f  pop     r15
0x180016311  pop     r14
0x180016313  pop     rdi
0x180016314  pop     rsi
0x180016315  pop     rbx
0x180016316  pop     rbp
0x180016317  retn
```
