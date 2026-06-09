# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::RetrieveNtfsEntry(CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault> const *,CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault> const *,ushort const * const,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const * *)

- ea: `0x18002b848`
- end: `0x18002bada`
- name: `?RetrieveNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBV?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEBV?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBGPEAPEBUCFastNtfsEntry@1@@Z`
- size: `658`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002b224`

## callees

- `0x180027008`
- `0x1800275b8`
- `0x180027e90`
- `0x1800281cc`
- `0x1800293a4`
- `0x18002b848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002baa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002baa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bab3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bab3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::RetrieveNtfsEntry(
        __int64 a1,
        __int64 a2,
        WCHAR *a3,
        _QWORD *a4)
{
  const WCHAR *v6; // r15
  int FileIdByFileName; // eax
  int v9; // edi
  int v10; // ecx
  unsigned __int64 v11; // rbx
  WCHAR *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r12
  unsigned int v15; // esi
  int v16; // ecx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // r8
  int v20; // r11d
  unsigned int v21; // edx
  _QWORD *v22; // rcx
  HANDLE ProcessHeap; // rax
  int v25; // [rsp+20h] [rbp-20h] BYREF
  const WCHAR *v26; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int64 v27; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-8h] BYREF

  v27 = 0;
  v28 = 0;
  v25 = 0;
  v6 = 0;
  v26 = 0;
  FileIdByFileName = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::GetFileIdByFileName(a3, (DWORD *)&v27);
  v9 = FileIdByFileName;
  if ( FileIdByFileName < 0 )
  {
LABEL_2:
    v10 = FileIdByFileName;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_41;
  }
  v11 = v27;
  if ( CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Find(
         a2,
         v27,
         &v25) )
  {
    v22 = (_QWORD *)(*(_QWORD *)(a1 + 8) + ((__int64)*(int *)(*(_QWORD *)(a2 + 8) + 16LL * v25 + 8) << 6));
    goto LABEL_40;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
LABEL_38:
    v10 = v9;
    goto LABEL_3;
  }
  v12 = a3;
  v13 = 261;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v13;
  }
  while ( v13 );
  v9 = v13 == 0 ? 0x80070057 : 0;
  v14 = (261 - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    goto LABEL_38;
  v15 = 0;
  if ( v14 == (int)v14 )
  {
    v9 = 0;
    if ( (int)v14 < 0 )
    {
      v9 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
    if ( v9 >= 0 )
    {
      v15 = v14;
      goto LABEL_18;
    }
    v16 = v9;
  }
  else
  {
    v9 = -2147024362;
    v16 = -2147024362;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v9 < 0 )
    goto LABEL_38;
  while ( 1 )
  {
    if ( (int)v15 <= 0 )
      goto LABEL_24;
    if ( a3[v15] == 47 || a3[v15] == 92 )
      break;
    --v15;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a3, v15, &v26);
  v9 = v17;
  if ( v17 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
  v6 = v26;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v9 < 0 )
    goto LABEL_38;
  if ( !v6 )
  {
LABEL_24:
    v9 = -2147418113;
    goto LABEL_38;
  }
  FileIdByFileName = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::GetFileIdByFileName(v6, (DWORD *)&v28);
  v9 = FileIdByFileName;
  if ( FileIdByFileName < 0 )
    goto LABEL_2;
  if ( !CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Find(
          a2,
          v28,
          &v25)
    || (v18 = *(_QWORD *)(a1 + 8),
        v19 = (__int64)*(int *)(*(_QWORD *)(a2 + 8) + 16LL * v25 + 8) << 6,
        v20 = *(_DWORD *)(v19 + v18 + 52),
        v20 <= 0) )
  {
LABEL_31:
    v10 = -2147024894;
    v9 = -2147024894;
    goto LABEL_3;
  }
  v21 = 0;
  while ( 1 )
  {
    v22 = *(_QWORD **)(*(_QWORD *)(v19 + v18 + 56) + 8LL * v21);
    if ( *v22 == v11 )
      break;
    if ( (int)++v21 >= v20 )
      goto LABEL_31;
  }
LABEL_40:
  *a4 = v22;
LABEL_41:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b848  mov     rax, rsp
0x18002b84b  mov     [rax+18h], rbx
0x18002b84f  mov     [rax+20h], r9
0x18002b853  mov     [rax+10h], rdx
0x18002b857  mov     [rax+8], rcx
0x18002b85b  push    rbp
0x18002b85c  push    rsi
0x18002b85d  push    rdi
0x18002b85e  push    r12
0x18002b860  push    r13
0x18002b862  push    r14
0x18002b864  push    r15
0x18002b866  mov     rbp, rsp
0x18002b869  sub     rsp, 40h
0x18002b86d  xor     r12d, r12d
0x18002b870  mov     rsi, rdx
0x18002b873  mov     r14, rcx
0x18002b876  mov     [rbp+var_10], r12
0x18002b87a  lea     rdx, [rbp+var_10]
0x18002b87e  mov     [rbp+var_8], r12
0x18002b882  mov     rcx, r8
0x18002b885  mov     [rbp+var_20], r12d
0x18002b889  mov     r15d, r12d
0x18002b88c  mov     [rbp+var_18], r12
0x18002b890  mov     r13, r8
0x18002b893  call    ?GetFileIdByFileName@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJQEBGPEAT_LARGE_INTEGER@@@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::GetFileIdByFileName(ushort const * const,_LARGE_INTEGER *)
0x18002b898  mov     edi, eax
0x18002b89a  test    eax, eax
0x18002b89c  jns     short loc_18002B8AA
0x18002b89e  mov     ecx, eax
0x18002b8a0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b8a5  jmp     loc_18002BA98
0x18002b8aa  mov     rbx, [rbp+var_10]
0x18002b8ae  lea     r8, [rbp+var_20]
0x18002b8b2  mov     rdx, rbx
0x18002b8b5  mov     rcx, rsi
0x18002b8b8  call    ?Find@?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_N_KPEAH@Z; CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Find(unsigned __int64,int *)
0x18002b8bd  test    al, al
0x18002b8bf  jnz     loc_18002BA79
0x18002b8c5  test    r13, r13
0x18002b8c8  jz      loc_18002BA6D
0x18002b8ce  mov     edx, 105h
0x18002b8d3  mov     rax, r13
0x18002b8d6  mov     ecx, edx
0x18002b8d8  cmp     [rax], r12w
0x18002b8dc  jz      short loc_18002B8E8
0x18002b8de  add     rax, 2
0x18002b8e2  sub     rcx, 1
0x18002b8e6  jnz     short loc_18002B8D8
0x18002b8e8  mov     rax, rcx
0x18002b8eb  neg     rax
0x18002b8ee  mov     rax, rcx
0x18002b8f1  sbb     edi, edi
0x18002b8f3  sub     rdx, rcx
0x18002b8f6  not     edi
0x18002b8f8  and     edi, 80070057h
0x18002b8fe  neg     rax
0x18002b901  sbb     r12, r12
0x18002b904  and     r12, rdx
0x18002b907  test    rcx, rcx
0x18002b90a  jz      loc_18002BA72
0x18002b910  xor     esi, esi
0x18002b912  movsxd  rax, r12d
0x18002b915  mov     r14d, 80070216h
0x18002b91b  cmp     r12, rax
0x18002b91e  jz      short loc_18002B92D
0x18002b920  mov     edi, r14d
0x18002b923  mov     ecx, r14d
0x18002b926  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b92b  jmp     short loc_18002B951
0x18002b92d  xor     edi, edi
0x18002b92f  test    r12d, r12d
0x18002b932  jns     short loc_18002B93F
0x18002b934  mov     ecx, r14d
0x18002b937  mov     edi, r14d
0x18002b93a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b93f  mov     ecx, edi
0x18002b941  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b946  test    edi, edi
0x18002b948  jns     short loc_18002B94E
0x18002b94a  mov     ecx, edi
0x18002b94c  jmp     short loc_18002B926
0x18002b94e  mov     esi, r12d
0x18002b951  mov     ecx, edi
0x18002b953  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b958  xor     r12d, r12d
0x18002b95b  test    edi, edi
0x18002b95d  js      loc_18002BA72
0x18002b963  jmp     short loc_18002B97B
0x18002b965  mov     ecx, esi
0x18002b967  cmp     word ptr [r13+rcx*2+0], 2Fh ; '/'
0x18002b96e  jz      short loc_18002B989
0x18002b970  cmp     word ptr [r13+rcx*2+0], 5Ch ; '\'
0x18002b977  jz      short loc_18002B989
0x18002b979  dec     esi
0x18002b97b  test    esi, esi
0x18002b97d  jg      short loc_18002B965
0x18002b97f  mov     edi, 8000FFFFh
0x18002b984  jmp     loc_18002BA72
0x18002b989  mov     eax, esi
0x18002b98b  cmp     rcx, rax
0x18002b98e  jz      short loc_18002B9A0
0x18002b990  mov     ecx, r14d
0x18002b993  mov     esi, r12d
0x18002b996  mov     edi, r14d
0x18002b999  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b99e  jmp     short loc_18002B9AA
0x18002b9a0  xor     ecx, ecx
0x18002b9a2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b9a7  mov     edi, r12d
0x18002b9aa  mov     ecx, edi
0x18002b9ac  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b9b1  test    edi, edi
0x18002b9b3  jns     short loc_18002B9BE
0x18002b9b5  mov     ecx, edi
0x18002b9b7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b9bc  jmp     short loc_18002B9DD
0x18002b9be  lea     r8, [rbp+var_18]
0x18002b9c2  mov     edx, esi
0x18002b9c4  mov     rcx, r13; Src
0x18002b9c7  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002b9cc  mov     edi, eax
0x18002b9ce  test    eax, eax
0x18002b9d0  jns     short loc_18002B9D9
0x18002b9d2  mov     ecx, eax
0x18002b9d4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b9d9  mov     r15, [rbp+var_18]
0x18002b9dd  mov     ecx, edi
0x18002b9df  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b9e4  test    edi, edi
0x18002b9e6  js      loc_18002BA72
0x18002b9ec  test    r15, r15
0x18002b9ef  jz      short loc_18002B97F
0x18002b9f1  lea     rdx, [rbp+var_8]
0x18002b9f5  mov     rcx, r15
0x18002b9f8  call    ?GetFileIdByFileName@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJQEBGPEAT_LARGE_INTEGER@@@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::GetFileIdByFileName(ushort const * const,_LARGE_INTEGER *)
0x18002b9fd  mov     edi, eax
0x18002b9ff  test    eax, eax
0x18002ba01  js      loc_18002B89E
0x18002ba07  mov     rsi, [rbp+arg_8]
0x18002ba0b  lea     r8, [rbp+var_20]
0x18002ba0f  mov     rdx, [rbp+var_8]
0x18002ba13  mov     rcx, rsi
0x18002ba16  call    ?Find@?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_N_KPEAH@Z; CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Find(unsigned __int64,int *)
0x18002ba1b  test    al, al
0x18002ba1d  jnz     short loc_18002BA2B
0x18002ba1f  mov     ecx, 80070002h
0x18002ba24  mov     edi, ecx
0x18002ba26  jmp     loc_18002B8A0
0x18002ba2b  movsxd  rax, [rbp+var_20]
0x18002ba2f  mov     rcx, [rsi+8]
0x18002ba33  add     rax, rax
0x18002ba36  mov     r9, [rbp+arg_0]
0x18002ba3a  movsxd  r8, dword ptr [rcx+rax*8+8]
0x18002ba3f  mov     r9, [r9+8]
0x18002ba43  shl     r8, 6
0x18002ba47  mov     r11d, [r8+r9+34h]
0x18002ba4c  test    r11d, r11d
0x18002ba4f  jle     short loc_18002BA1F
0x18002ba51  mov     r10, [r8+r9+38h]
0x18002ba56  mov     edx, r12d
0x18002ba59  mov     eax, edx
0x18002ba5b  mov     rcx, [r10+rax*8]
0x18002ba5f  cmp     [rcx], rbx
0x18002ba62  jz      short loc_18002BA91
0x18002ba64  inc     edx
0x18002ba66  cmp     edx, r11d
0x18002ba69  jl      short loc_18002BA59
0x18002ba6b  jmp     short loc_18002BA1F
0x18002ba6d  mov     edi, 80070057h
0x18002ba72  mov     ecx, edi
0x18002ba74  jmp     loc_18002B8A0
0x18002ba79  movsxd  rax, [rbp+var_20]
0x18002ba7d  mov     rcx, [rsi+8]
0x18002ba81  add     rax, rax
0x18002ba84  movsxd  rcx, dword ptr [rcx+rax*8+8]
0x18002ba89  shl     rcx, 6
0x18002ba8d  add     rcx, [r14+8]
0x18002ba91  mov     rax, [rbp+arg_18]
0x18002ba95  mov     [rax], rcx
0x18002ba98  mov     ecx, edi
0x18002ba9a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ba9f  test    r15, r15
0x18002baa2  jz      short loc_18002BAC0
0x18002baa4  call    cs:__imp_GetProcessHeap
0x18002baaa  lea     r8, [r15-4]; lpMem
0x18002baae  xor     edx, edx; dwFlags
0x18002bab0  mov     rcx, rax; hHeap
0x18002bab3  call    cs:__imp_HeapFree
0x18002bab9  xor     ecx, ecx
0x18002babb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002bac0  mov     rbx, [rsp+40h+arg_10]
0x18002bac8  mov     eax, edi
0x18002baca  add     rsp, 40h
0x18002bace  pop     r15
0x18002bad0  pop     r14
0x18002bad2  pop     r13
0x18002bad4  pop     r12
0x18002bad6  pop     rdi
0x18002bad7  pop     rsi
0x18002bad8  pop     rbp
0x18002bad9  retn
```
