# CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::Insert(int,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const &)

- ea: `0x180029140`
- end: `0x180029343`
- name: `?Insert@?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHAEBUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002aed4`

## callees

- `0x180002752`
- `0x1800251c8`
- `0x180025f00`
- `0x180027008`
- `0x180029140`
- `0x1800293a4`
- `0x18002c9fc`
- `0x18002d43c`
- `0x1800322d2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800292a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800292a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800292b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800292b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::Insert(
        __int64 a1,
        int a2,
        __int64 a3)
{
  int v3; // eax
  __int64 v5; // r14
  int v7; // ebx
  int v8; // ebp
  int v9; // edi
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // ebx
  int v13; // edi
  int v14; // ecx
  int v15; // eax
  int v16; // eax
  int v17; // r8d
  __int64 v18; // rdi
  __int64 v19; // rbp
  __int64 v20; // r14
  __int64 v21; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD v24[9]; // [rsp+20h] [rbp-48h] BYREF
  int v25; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a1 + 4);
  v5 = a2;
  if ( v3 < 0 )
  {
    v7 = -2147418113;
LABEL_12:
    v11 = v7;
LABEL_13:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    goto LABEL_37;
  }
  v8 = 0;
  v9 = v3 + 1;
  if ( v3 + 1 < (unsigned int)v3 )
  {
    v7 = -2147024362;
    v9 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  else
  {
    v7 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_7;
  if ( v9 < 0 )
  {
    v7 = -2147024362;
LABEL_7:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_11;
  }
  v8 = v9;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_12;
  v12 = *(_DWORD *)a1;
  if ( *(int *)a1 >= 0 )
  {
    if ( v8 <= v12 )
    {
      v13 = 0;
      goto LABEL_30;
    }
    v25 = *(_DWORD *)a1;
    do
    {
      if ( v12 )
      {
        v15 = SafeMul<int>(v12, v10, &v25);
        v13 = v15;
        if ( v15 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
        v12 = v25;
      }
      else
      {
        v12 = 32;
        v13 = 0;
        v25 = 32;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
      if ( v13 < 0 )
      {
        v14 = v13;
        goto LABEL_29;
      }
    }
    while ( v12 < v8 );
    v16 = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::SetSize(
            a1,
            (unsigned int)v12);
    v13 = v16;
    if ( v16 >= 0 )
      goto LABEL_30;
    v14 = v16;
  }
  else
  {
    v13 = -2147418113;
    v14 = -2147418113;
  }
LABEL_29:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
LABEL_30:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
  if ( v13 < 0 )
  {
    v7 = v13;
    v11 = v13;
    goto LABEL_13;
  }
  v17 = *(_DWORD *)(a1 + 4);
  if ( (int)v5 < v17 )
    memmove_0(
      (void *)(*(_QWORD *)(a1 + 8) + (v5 << 6) + 64),
      (const void *)(*(_QWORD *)(a1 + 8) + (v5 << 6)),
      (__int64)(v17 - (int)v5) << 6);
  v18 = v5 << 6;
  memset_0((void *)((v5 << 6) + *(_QWORD *)(a1 + 8)), 0, 0x40u);
  v19 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(v18 + v19) = *(_QWORD *)a3;
  v20 = *(_QWORD *)(a3 + 8);
  *(_QWORD *)(a3 + 8) = 0;
  v21 = *(_QWORD *)(v18 + v19 + 8);
  if ( v21 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v21 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  *(_QWORD *)(v18 + v19 + 8) = v20;
  *(_DWORD *)(v18 + v19 + 16) = *(_DWORD *)(a3 + 16);
  *(_QWORD *)(v18 + v19 + 24) = *(_QWORD *)(a3 + 24);
  *(_QWORD *)(v18 + v19 + 24) = *(_QWORD *)(a3 + 24);
  *(_QWORD *)(v18 + v19 + 32) = *(_QWORD *)(a3 + 32);
  *(_DWORD *)(v18 + v19 + 40) = *(_DWORD *)(a3 + 40);
  v24[0] = 0;
  v24[1] = 0;
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Swap(
    v24,
    a3 + 48);
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Swap(
    v24,
    v18 + v19 + 48);
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>((__int64)v24);
  ++*(_DWORD *)(a1 + 4);
  v7 = 0;
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029140  push    rbx
0x180029142  push    rbp
0x180029143  push    rsi
0x180029144  push    rdi
0x180029145  push    r14
0x180029147  push    r15
0x180029149  sub     rsp, 38h
0x18002914d  mov     eax, [rcx+4]
0x180029150  mov     r15, r8
0x180029153  movsxd  r14, edx
0x180029156  mov     rsi, rcx
0x180029159  test    eax, eax
0x18002915b  jns     short loc_180029164
0x18002915d  mov     ebx, 8000FFFFh
0x180029162  jmp     short loc_1800291AB
0x180029164  xor     ebp, ebp
0x180029166  lea     edi, [rax+1]
0x180029169  cmp     edi, eax
0x18002916b  jb      short loc_180029171
0x18002916d  xor     ebx, ebx
0x18002916f  jmp     short loc_18002917F
0x180029171  mov     ebx, 80070216h
0x180029176  xor     edi, edi
0x180029178  mov     ecx, ebx
0x18002917a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002917f  mov     ecx, ebx
0x180029181  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029186  test    ebx, ebx
0x180029188  jns     short loc_180029193
0x18002918a  mov     ecx, ebx
0x18002918c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029191  jmp     short loc_1800291A0
0x180029193  test    edi, edi
0x180029195  jns     short loc_18002919E
0x180029197  mov     ebx, 80070216h
0x18002919c  jmp     short loc_18002918A
0x18002919e  mov     ebp, edi
0x1800291a0  mov     ecx, ebx
0x1800291a2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800291a7  test    ebx, ebx
0x1800291a9  jns     short loc_1800291B7
0x1800291ab  mov     ecx, ebx
0x1800291ad  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800291b2  jmp     loc_18002932D
0x1800291b7  mov     ebx, [rsi]
0x1800291b9  test    ebx, ebx
0x1800291bb  jns     short loc_1800291C8
0x1800291bd  mov     ebx, 8000FFFFh
0x1800291c2  mov     edi, ebx
0x1800291c4  mov     ecx, ebx
0x1800291c6  jmp     short loc_180029227
0x1800291c8  cmp     ebp, ebx
0x1800291ca  jg      short loc_1800291D0
0x1800291cc  xor     edi, edi
0x1800291ce  jmp     short loc_18002922C
0x1800291d0  mov     [rsp+68h+arg_0], ebx
0x1800291d4  test    ebx, ebx
0x1800291d6  jnz     short loc_1800291E5
0x1800291d8  mov     ebx, 20h ; ' '
0x1800291dd  xor     edi, edi
0x1800291df  mov     [rsp+68h+arg_0], ebx
0x1800291e3  jmp     short loc_180029202
0x1800291e5  lea     r8, [rsp+68h+arg_0]
0x1800291ea  mov     ecx, ebx
0x1800291ec  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x1800291f1  mov     edi, eax
0x1800291f3  test    eax, eax
0x1800291f5  jns     short loc_1800291FE
0x1800291f7  mov     ecx, eax
0x1800291f9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800291fe  mov     ebx, [rsp+68h+arg_0]
0x180029202  mov     ecx, edi
0x180029204  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029209  test    edi, edi
0x18002920b  js      short loc_180029225
0x18002920d  cmp     ebx, ebp
0x18002920f  jl      short loc_1800291D4
0x180029211  mov     edx, ebx
0x180029213  mov     rcx, rsi
0x180029216  call    ?SetSize@?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18002921b  mov     edi, eax
0x18002921d  test    eax, eax
0x18002921f  jns     short loc_18002922C
0x180029221  mov     ecx, eax
0x180029223  jmp     short loc_180029227
0x180029225  mov     ecx, edi
0x180029227  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002922c  mov     ecx, edi
0x18002922e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029233  test    edi, edi
0x180029235  jns     short loc_180029240
0x180029237  mov     ebx, edi
0x180029239  mov     ecx, edi
0x18002923b  jmp     loc_1800291AD
0x180029240  mov     r8d, [rsi+4]
0x180029244  mov     rdi, r14
0x180029247  cmp     r14d, r8d
0x18002924a  jge     short loc_18002926A
0x18002924c  sub     r8d, r14d
0x18002924f  mov     rdx, r14
0x180029252  shl     rdx, 6
0x180029256  add     rdx, [rsi+8]; Src
0x18002925a  movsxd  r8, r8d
0x18002925d  shl     r8, 6; Size
0x180029261  lea     rcx, [rdx+40h]; void *
0x180029265  call    memmove_0
0x18002926a  mov     rcx, [rsi+8]
0x18002926e  xor     edx, edx; Val
0x180029270  shl     rdi, 6
0x180029274  add     rcx, rdi; void *
0x180029277  lea     r8d, [rdx+40h]; Size
0x18002927b  call    memset_0
0x180029280  mov     rbp, [rsi+8]
0x180029284  mov     rax, [r15]
0x180029287  mov     [rdi+rbp], rax
0x18002928b  mov     r14, [r15+8]
0x18002928f  mov     qword ptr [r15+8], 0
0x180029297  mov     rbx, [rdi+rbp+8]
0x18002929c  test    rbx, rbx
0x18002929f  jz      short loc_1800292BD
0x1800292a1  call    cs:__imp_GetProcessHeap
0x1800292a7  lea     r8, [rbx-4]; lpMem
0x1800292ab  xor     edx, edx; dwFlags
0x1800292ad  mov     rcx, rax; hHeap
0x1800292b0  call    cs:__imp_HeapFree
0x1800292b6  xor     ecx, ecx
0x1800292b8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800292bd  mov     [rdi+rbp+8], r14
0x1800292c2  lea     rdx, [r15+30h]
0x1800292c6  mov     eax, [r15+10h]
0x1800292ca  lea     rcx, [rsp+68h+var_48]
0x1800292cf  mov     [rdi+rbp+10h], eax
0x1800292d3  mov     rax, [r15+18h]
0x1800292d7  mov     [rdi+rbp+18h], rax
0x1800292dc  mov     rax, [r15+18h]
0x1800292e0  mov     [rdi+rbp+18h], rax
0x1800292e5  mov     rax, [r15+20h]
0x1800292e9  mov     [rdi+rbp+20h], rax
0x1800292ee  mov     eax, [r15+28h]
0x1800292f2  mov     [rdi+rbp+28h], eax
0x1800292f6  mov     [rsp+68h+var_48], 0
0x1800292ff  mov     [rsp+68h+var_40], 0
0x180029308  call    ?Swap@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAXPEAV1@@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Swap(CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> *)
0x18002930d  lea     rdx, [rbp+30h]
0x180029311  add     rdx, rdi
0x180029314  lea     rcx, [rsp+68h+var_48]
0x180029319  call    ?Swap@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAXPEAV1@@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Swap(CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> *)
0x18002931e  lea     rcx, [rsp+68h+var_48]
0x180029323  call    ??1?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(void)
0x180029328  inc     dword ptr [rsi+4]
0x18002932b  xor     ebx, ebx
0x18002932d  mov     ecx, ebx
0x18002932f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029334  mov     eax, ebx
0x180029336  add     rsp, 38h
0x18002933a  pop     r15
0x18002933c  pop     r14
0x18002933e  pop     rdi
0x18002933f  pop     rsi
0x180029340  pop     rbp
0x180029341  pop     rbx
0x180029342  retn
```
