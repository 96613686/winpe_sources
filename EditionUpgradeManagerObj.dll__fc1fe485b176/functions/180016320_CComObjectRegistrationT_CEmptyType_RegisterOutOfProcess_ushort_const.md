# CComObjectRegistrationT<CEmptyType>::RegisterOutOfProcess(ushort const *)

- ea: `0x180016320`
- end: `0x180016444`
- name: `?RegisterOutOfProcess@?$CComObjectRegistrationT@VCEmptyType@@@@AEAAJPEBG@Z`
- size: `292`
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
- `0x180016320`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016422`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016413`

## pseudocode

```c
__int64 __fastcall CComObjectRegistrationT<CEmptyType>::RegisterOutOfProcess(__int64 a1, __int64 a2)
{
  void *v2; // rbx
  int CurrentModuleFileName; // eax
  _WORD *v5; // rsi
  int v6; // edi
  int v7; // ecx
  int appended; // eax
  __int64 v9; // rcx
  int PointerDataSize; // eax
  __int64 v11; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  LPVOID lpMem[2]; // [rsp+30h] [rbp-10h] BYREF
  _WORD *v16; // [rsp+60h] [rbp+20h] BYREF

  v2 = 0;
  v16 = 0;
  lpMem[0] = 0;
  lpMem[1] = 0;
  CurrentModuleFileName = CComHelpersT<CEmptyType>::GetCurrentModuleFileName(&v16);
  v5 = v16;
  v6 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
    goto LABEL_2;
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)lpMem,
               L"%s\\LocalServer32",
               a2);
  v6 = appended;
  if ( appended < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(appended);
    v2 = lpMem[0];
    goto LABEL_12;
  }
  v2 = lpMem[0];
  CurrentModuleFileName = CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(v9, (const WCHAR *)lpMem[0]);
  v6 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
  {
LABEL_2:
    v7 = CurrentModuleFileName;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_12;
  }
  LODWORD(v16) = 0;
  PointerDataSize = CRegType<unsigned short *>::GetPointerDataSize(v5, &v16);
  v6 = PointerDataSize;
  if ( PointerDataSize < 0
    || (PointerDataSize = CRegUtilT<unsigned short *,CRegType,0,0>::SetValue(v11, v2, 0, v5, (_DWORD)v16),
        v6 = PointerDataSize,
        PointerDataSize < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(PointerDataSize);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v6 < 0 )
  {
    v7 = v6;
    goto LABEL_11;
  }
LABEL_12:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  if ( v5 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v5 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016320  mov     [rsp-18h+arg_8], rbx
0x180016325  mov     [rsp-18h+arg_10], rsi
0x18001632a  mov     [rsp-18h+arg_0], rcx
0x18001632f  push    rbp
0x180016330  push    rdi
0x180016331  push    r14
0x180016333  mov     rbp, rsp
0x180016336  sub     rsp, 40h
0x18001633a  xor     ebx, ebx
0x18001633c  mov     [rbp+arg_0], 0
0x180016344  lea     rcx, [rbp+arg_0]
0x180016348  mov     [rbp+lpMem], rbx
0x18001634c  mov     [rbp+var_8], rbx
0x180016350  mov     r14, rdx
0x180016353  call    ?GetCurrentModuleFileName@?$CComHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CComHelpersT<CEmptyType>::GetCurrentModuleFileName(ushort * *)
0x180016358  mov     rsi, [rbp+arg_0]
0x18001635c  mov     edi, eax
0x18001635e  test    eax, eax
0x180016360  jns     short loc_180016369
0x180016362  mov     ecx, eax
0x180016364  jmp     loc_1800163E9
0x180016369  mov     r8, r14
0x18001636c  lea     rdx, aSLocalserver32; "%s\\LocalServer32"
0x180016373  lea     rcx, [rbp+lpMem]
0x180016377  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x18001637c  mov     edi, eax
0x18001637e  test    eax, eax
0x180016380  jns     short loc_18001638F
0x180016382  mov     ecx, eax
0x180016384  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016389  mov     rbx, [rbp+lpMem]
0x18001638d  jmp     short loc_1800163EE
0x18001638f  mov     rbx, [rbp+lpMem]
0x180016393  mov     rdx, rbx
0x180016396  call    ?CreateOrOpenKey@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x18001639b  mov     edi, eax
0x18001639d  test    eax, eax
0x18001639f  js      short loc_180016362
0x1800163a1  lea     rdx, [rbp+arg_0]
0x1800163a5  mov     dword ptr [rbp+arg_0], 0
0x1800163ac  mov     rcx, rsi
0x1800163af  call    ?GetPointerDataSize@?$CRegType@PEAG@@SAJPEBGPEAK@Z; CRegType<ushort *>::GetPointerDataSize(ushort const *,ulong *)
0x1800163b4  mov     edi, eax
0x1800163b6  test    eax, eax
0x1800163b8  js      short loc_1800163D5
0x1800163ba  mov     eax, dword ptr [rbp+arg_0]
0x1800163bd  mov     r9, rsi
0x1800163c0  xor     r8d, r8d
0x1800163c3  mov     [rsp+40h+var_20], eax
0x1800163c7  mov     rdx, rbx
0x1800163ca  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG11K@Z; CRegUtilT<ushort *,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x1800163cf  mov     edi, eax
0x1800163d1  test    eax, eax
0x1800163d3  jns     short loc_1800163DC
0x1800163d5  mov     ecx, eax
0x1800163d7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800163dc  mov     ecx, edi
0x1800163de  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800163e3  test    edi, edi
0x1800163e5  jns     short loc_1800163EE
0x1800163e7  mov     ecx, edi
0x1800163e9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800163ee  mov     ecx, edi
0x1800163f0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800163f5  test    rbx, rbx
0x1800163f8  jz      short loc_18001640E
0x1800163fa  call    cs:__imp_GetProcessHeap
0x180016400  mov     r8, rbx; lpMem
0x180016403  xor     edx, edx; dwFlags
0x180016405  mov     rcx, rax; hHeap
0x180016408  call    cs:__imp_HeapFree
0x18001640e  test    rsi, rsi
0x180016411  jz      short loc_18001642F
0x180016413  call    cs:__imp_GetProcessHeap
0x180016419  lea     r8, [rsi-4]; lpMem
0x18001641d  xor     edx, edx; dwFlags
0x18001641f  mov     rcx, rax; hHeap
0x180016422  call    cs:__imp_HeapFree
0x180016428  xor     ecx, ecx
0x18001642a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001642f  mov     rbx, [rsp+40h+arg_8]
0x180016434  mov     eax, edi
0x180016436  mov     rsi, [rsp+40h+arg_10]
0x18001643b  add     rsp, 40h
0x18001643f  pop     r14
0x180016441  pop     rdi
0x180016442  pop     rbp
0x180016443  retn
```
