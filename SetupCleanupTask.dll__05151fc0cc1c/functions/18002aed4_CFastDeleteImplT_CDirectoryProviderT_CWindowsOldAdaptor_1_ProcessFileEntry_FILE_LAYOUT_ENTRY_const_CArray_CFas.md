# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessFileEntry(_FILE_LAYOUT_ENTRY const *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault> *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,CAdaptorDefault,CPoliciesDefault> *)

- ea: `0x18002aed4`
- end: `0x18002b21c`
- name: `?ProcessFileEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBU_FILE_LAYOUT_ENTRY@@PEAV?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAV?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180026824`

## callees

- `0x180002752`
- `0x1800251c8`
- `0x180025f00`
- `0x180027008`
- `0x1800275b8`
- `0x180029140`
- `0x1800293a4`
- `0x18002aed4`
- `0x18002cb7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b1e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b1e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b1f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b1f8`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessFileEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // edi
  double v7; // xmm1_8
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned int *i; // rsi
  __int64 v11; // r12
  int v12; // eax
  __int64 v13; // rax
  int v14; // edx
  int v15; // eax
  __int64 v16; // rsi
  int v17; // ebx
  int v18; // r15d
  int v19; // ecx
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // edi
  int v23; // ebx
  int v24; // ecx
  int v25; // eax
  int v26; // eax
  int v27; // r8d
  __int64 v28; // rcx
  int v29; // ecx
  __int64 v30; // rbx
  HANDLE ProcessHeap; // rax
  __int128 v33; // [rsp+20h] [rbp-58h]
  __int64 v34; // [rsp+30h] [rbp-48h] BYREF
  __int64 v35; // [rsp+38h] [rbp-40h] BYREF
  __int64 v36; // [rsp+40h] [rbp-38h]
  __int64 v37; // [rsp+48h] [rbp-30h]
  double v38; // [rsp+50h] [rbp-28h]
  __int64 v39; // [rsp+58h] [rbp-20h]
  _QWORD v40[3]; // [rsp+60h] [rbp-18h] BYREF
  int v41; // [rsp+C0h] [rbp+48h] BYREF

  v36 = 0;
  v6 = 0;
  v37 = 0;
  v7 = 0.0;
  v39 = 0;
  v35 = 0;
  v40[0] = 0;
  v40[1] = 0;
  v33 = 0;
  if ( *(_DWORD *)(a1 + 28) )
  {
    v8 = a1 + *(unsigned int *)(a1 + 28);
    v7 = (double)(int)*(_QWORD *)(v8 + 24) + 0.0;
    while ( *(_DWORD *)(v8 + 4) )
    {
      v8 += *(unsigned int *)(v8 + 4);
      v7 = v7 + (double)(int)*(_QWORD *)(v8 + 24);
    }
  }
  v34 = *(_QWORD *)(a1 + 16);
  v38 = v7;
  if ( *(_DWORD *)(a1 + 24) )
  {
    v9 = 0;
    for ( i = (unsigned int *)(a1 + *(unsigned int *)(a1 + 24)); ; i = (unsigned int *)((char *)i + *i) )
    {
      v9 = i[1] & 2
         | ((*(_DWORD *)(a1 + 12) & 0x10) != 0 ? 4 : 0)
         | (((unsigned __int8)v9 ^ (unsigned __int8)i[1]) & 1 ^ v9) & 0xFFFFFFF9;
      LODWORD(v36) = (*(_DWORD *)(a1 + 12) & 0x10) != 0;
      if ( (v9 & 1) != 0 || (v9 & 2) == 0 )
      {
        v11 = i[4] >> 1;
        if ( (unsigned __int64)i[4] >> 1 == v11 )
        {
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v6 = 0;
        }
        else
        {
          LODWORD(v11) = 0;
          v6 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( v6 >= 0 )
        {
          v12 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(i + 6, v11, &v35);
          v6 = v12;
          if ( v12 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
        }
        else
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( v6 < 0 )
          goto LABEL_59;
        v13 = v37;
        v14 = *(_DWORD *)(a2 + 4);
        if ( *(_QWORD *)(a1 + 16) != *((_QWORD *)i + 1) )
          v13 = *((_QWORD *)i + 1);
        v37 = v13;
        v15 = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::Insert(
                a2,
                v14,
                (__int64)&v34);
        v6 = v15;
        if ( v15 < 0 )
          break;
      }
      if ( !*i )
      {
        if ( (v9 & 4) == 0 )
          goto LABEL_61;
        v16 = *(int *)(a3 + 4);
        DWORD2(v33) = *(_DWORD *)(a2 + 4) - 1;
        *(_QWORD *)&v33 = v34;
        if ( (int)v16 < 0 )
        {
          v6 = -2147418113;
          goto LABEL_35;
        }
        v17 = v16 + 1;
        v18 = 0;
        if ( (int)v16 + 1 < (unsigned int)v16 )
        {
          v17 = 0;
          v6 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
        else
        {
          v6 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( v6 < 0 )
        {
          v19 = v6;
          goto LABEL_30;
        }
        if ( v17 >= 0 )
        {
          v18 = v17;
        }
        else
        {
          v19 = -2147024362;
          v6 = -2147024362;
LABEL_30:
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( v6 < 0 )
        {
LABEL_35:
          v21 = v6;
          goto LABEL_36;
        }
        v22 = *(_DWORD *)a3;
        if ( *(int *)a3 < 0 )
        {
          v23 = -2147418113;
          v24 = -2147418113;
          goto LABEL_52;
        }
        if ( v18 > v22 )
        {
          v41 = *(_DWORD *)a3;
          do
          {
            if ( v22 )
            {
              v25 = SafeMul<int>(v22, v20, &v41);
              v23 = v25;
              if ( v25 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v25);
              v22 = v41;
            }
            else
            {
              v22 = 32;
              v23 = 0;
              v41 = 32;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
            if ( v23 < 0 )
            {
              v24 = v23;
              goto LABEL_52;
            }
          }
          while ( v22 < v18 );
          v26 = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(
                  a3,
                  (unsigned int)v22);
          v23 = v26;
          if ( v26 >= 0 )
            goto LABEL_53;
          v24 = v26;
LABEL_52:
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
        }
        else
        {
          v23 = 0;
        }
LABEL_53:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
        if ( v23 >= 0 )
        {
          v27 = *(_DWORD *)(a3 + 4);
          if ( (int)v16 < v27 )
            memmove_0(
              (void *)(*(_QWORD *)(a3 + 8) + 16 * v16 + 16),
              (const void *)(*(_QWORD *)(a3 + 8) + 16 * v16),
              16LL * (v27 - (int)v16));
          v6 = 0;
          v28 = 2 * v16;
          *(_OWORD *)(*(_QWORD *)(a3 + 8) + 8 * v28) = 0;
          *(_OWORD *)(*(_QWORD *)(a3 + 8) + 8 * v28) = v33;
          ++*(_DWORD *)(a3 + 4);
        }
        else
        {
          v6 = v23;
          v21 = v23;
LABEL_36:
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( v6 >= 0 )
          goto LABEL_61;
LABEL_59:
        v29 = v6;
        goto LABEL_60;
      }
    }
    v29 = v15;
LABEL_60:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v29);
  }
LABEL_61:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>((__int64)v40);
  v30 = v35;
  if ( v35 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v30 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002aed4  push    rbp
0x18002aed6  push    rbx
0x18002aed7  push    rsi
0x18002aed8  push    rdi
0x18002aed9  push    r12
0x18002aedb  push    r13
0x18002aedd  push    r14
0x18002aedf  push    r15
0x18002aee1  mov     rbp, rsp
0x18002aee4  sub     rsp, 78h
0x18002aee8  xor     r12d, r12d
0x18002aeeb  xorps   xmm0, xmm0
0x18002aeee  mov     r14, r8
0x18002aef1  mov     r13, rdx
0x18002aef4  mov     r15, rcx
0x18002aef7  mov     [rbp+var_38], r12
0x18002aefb  mov     edi, r12d
0x18002aefe  mov     [rbp+var_30], r12
0x18002af02  xorps   xmm1, xmm1
0x18002af05  mov     [rbp+var_20], r12
0x18002af09  mov     [rbp+var_40], r12
0x18002af0d  mov     [rbp+var_18], r12
0x18002af11  mov     [rbp+var_10], r12
0x18002af15  movups  [rbp+var_58], xmm0
0x18002af19  cmp     [rcx+1Ch], r12d
0x18002af1d  jz      short loc_18002AF4E
0x18002af1f  mov     ecx, [rcx+1Ch]
0x18002af22  add     rcx, r15
0x18002af25  cvtsi2sd xmm1, qword ptr [rcx+18h]
0x18002af2b  addsd   xmm1, cs:__real@0000000000000000
0x18002af33  jmp     short loc_18002AF48
0x18002af35  mov     eax, [rcx+4]
0x18002af38  xorps   xmm0, xmm0
0x18002af3b  add     rcx, rax
0x18002af3e  cvtsi2sd xmm0, qword ptr [rcx+18h]
0x18002af44  addsd   xmm1, xmm0
0x18002af48  cmp     [rcx+4], r12d
0x18002af4c  jnz     short loc_18002AF35
0x18002af4e  mov     rax, [r15+10h]
0x18002af52  mov     [rbp+var_48], rax
0x18002af56  movsd   [rbp+var_28], xmm1
0x18002af5b  cmp     [r15+18h], r12d
0x18002af5f  jz      loc_18002B1D0
0x18002af65  mov     esi, [r15+18h]
0x18002af69  mov     ebx, r12d
0x18002af6c  add     rsi, r15
0x18002af6f  mov     r9d, 80070216h
0x18002af75  mov     edx, [rsi+4]
0x18002af78  mov     eax, edx
0x18002af7a  mov     r8d, [r15+0Ch]
0x18002af7e  xor     eax, ebx
0x18002af80  and     eax, 1
0x18002af83  and     r8d, 10h
0x18002af87  xor     ebx, eax
0x18002af89  mov     eax, r8d
0x18002af8c  and     ebx, 0FFFFFFF9h
0x18002af8f  neg     eax
0x18002af91  mov     eax, r12d
0x18002af94  sbb     ecx, ecx
0x18002af96  and     edx, 2
0x18002af99  and     ecx, 4
0x18002af9c  or      ebx, ecx
0x18002af9e  or      ebx, edx
0x18002afa0  test    r8d, r8d
0x18002afa3  setnz   al
0x18002afa6  mov     dword ptr [rbp+var_38], eax
0x18002afa9  test    bl, 1
0x18002afac  jnz     short loc_18002AFB7
0x18002afae  test    bl, 2
0x18002afb1  jnz     loc_18002B058
0x18002afb7  mov     eax, [rsi+10h]
0x18002afba  shr     rax, 1
0x18002afbd  mov     r12d, eax
0x18002afc0  cmp     rax, r12
0x18002afc3  jz      short loc_18002AFD5
0x18002afc5  xor     r12d, r12d
0x18002afc8  mov     ecx, r9d
0x18002afcb  mov     edi, r9d
0x18002afce  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002afd3  jmp     short loc_18002AFDE
0x18002afd5  xor     ecx, ecx
0x18002afd7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002afdc  xor     edi, edi
0x18002afde  mov     ecx, edi
0x18002afe0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002afe5  test    edi, edi
0x18002afe7  jns     short loc_18002AFF5
0x18002afe9  mov     ecx, edi
0x18002afeb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002aff0  xor     r12d, r12d
0x18002aff3  jmp     short loc_18002B015
0x18002aff5  lea     rcx, [rsi+18h]; Src
0x18002aff9  mov     edx, r12d
0x18002affc  lea     r8, [rbp+var_40]
0x18002b000  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002b005  xor     r12d, r12d
0x18002b008  mov     edi, eax
0x18002b00a  test    eax, eax
0x18002b00c  jns     short loc_18002B015
0x18002b00e  mov     ecx, eax
0x18002b010  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b015  mov     ecx, edi
0x18002b017  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b01c  test    edi, edi
0x18002b01e  js      loc_18002B1C9
0x18002b024  mov     rcx, [rsi+8]
0x18002b028  lea     r8, [rbp+var_48]
0x18002b02c  cmp     [r15+10h], rcx
0x18002b030  mov     rax, [rbp+var_30]
0x18002b034  mov     edx, [r13+4]
0x18002b038  cmovnz  rax, rcx
0x18002b03c  mov     rcx, r13
0x18002b03f  mov     [rbp+var_30], rax
0x18002b043  call    ?Insert@?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHAEBUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::Insert(int,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const &)
0x18002b048  mov     edi, eax
0x18002b04a  test    eax, eax
0x18002b04c  js      loc_18002B218
0x18002b052  mov     r9d, 80070216h
0x18002b058  cmp     [rsi], r12d
0x18002b05b  jz      short loc_18002B067
0x18002b05d  mov     ecx, [rsi]
0x18002b05f  add     rsi, rcx
0x18002b062  jmp     loc_18002AF75
0x18002b067  test    bl, 4
0x18002b06a  jz      loc_18002B1D0
0x18002b070  mov     eax, [r13+4]
0x18002b074  movsxd  rsi, dword ptr [r14+4]
0x18002b078  dec     eax
0x18002b07a  mov     dword ptr [rbp+var_58+8], eax
0x18002b07d  mov     rax, [rbp+var_48]
0x18002b081  mov     qword ptr [rbp+var_58], rax
0x18002b085  test    esi, esi
0x18002b087  jns     short loc_18002B090
0x18002b089  mov     edi, 8000FFFFh
0x18002b08e  jmp     short loc_18002B0DC
0x18002b090  lea     ebx, [rsi+1]
0x18002b093  mov     r15d, r12d
0x18002b096  cmp     ebx, esi
0x18002b098  jb      short loc_18002B09F
0x18002b09a  mov     edi, r12d
0x18002b09d  jmp     short loc_18002B0AD
0x18002b09f  mov     ecx, r9d
0x18002b0a2  mov     ebx, r12d
0x18002b0a5  mov     edi, r9d
0x18002b0a8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b0ad  mov     ecx, edi
0x18002b0af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b0b4  test    edi, edi
0x18002b0b6  jns     short loc_18002B0C1
0x18002b0b8  mov     ecx, edi
0x18002b0ba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b0bf  jmp     short loc_18002B0D1
0x18002b0c1  test    ebx, ebx
0x18002b0c3  jns     short loc_18002B0CE
0x18002b0c5  mov     ecx, 80070216h
0x18002b0ca  mov     edi, ecx
0x18002b0cc  jmp     short loc_18002B0BA
0x18002b0ce  mov     r15d, ebx
0x18002b0d1  mov     ecx, edi
0x18002b0d3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b0d8  test    edi, edi
0x18002b0da  jns     short loc_18002B0E8
0x18002b0dc  mov     ecx, edi
0x18002b0de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b0e3  jmp     loc_18002B1BE
0x18002b0e8  mov     edi, [r14]
0x18002b0eb  test    edi, edi
0x18002b0ed  jns     short loc_18002B0FA
0x18002b0ef  mov     edi, 8000FFFFh
0x18002b0f4  mov     ebx, edi
0x18002b0f6  mov     ecx, edi
0x18002b0f8  jmp     short loc_18002B159
0x18002b0fa  cmp     r15d, edi
0x18002b0fd  jg      short loc_18002B104
0x18002b0ff  mov     ebx, r12d
0x18002b102  jmp     short loc_18002B15E
0x18002b104  mov     [rbp+arg_0], edi
0x18002b107  test    edi, edi
0x18002b109  jnz     short loc_18002B118
0x18002b10b  mov     edi, 20h ; ' '
0x18002b110  mov     ebx, r12d
0x18002b113  mov     [rbp+arg_0], edi
0x18002b116  jmp     short loc_18002B133
0x18002b118  lea     r8, [rbp+arg_0]
0x18002b11c  mov     ecx, edi
0x18002b11e  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x18002b123  mov     ebx, eax
0x18002b125  test    eax, eax
0x18002b127  jns     short loc_18002B130
0x18002b129  mov     ecx, eax
0x18002b12b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b130  mov     edi, [rbp+arg_0]
0x18002b133  mov     ecx, ebx
0x18002b135  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b13a  test    ebx, ebx
0x18002b13c  js      short loc_18002B157
0x18002b13e  cmp     edi, r15d
0x18002b141  jl      short loc_18002B107
0x18002b143  mov     edx, edi
0x18002b145  mov     rcx, r14
0x18002b148  call    ?SetSize@?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18002b14d  mov     ebx, eax
0x18002b14f  test    eax, eax
0x18002b151  jns     short loc_18002B15E
0x18002b153  mov     ecx, eax
0x18002b155  jmp     short loc_18002B159
0x18002b157  mov     ecx, ebx
0x18002b159  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b15e  mov     ecx, ebx
0x18002b160  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b165  test    ebx, ebx
0x18002b167  jns     short loc_18002B172
0x18002b169  mov     edi, ebx
0x18002b16b  mov     ecx, ebx
0x18002b16d  jmp     loc_18002B0DE
0x18002b172  mov     r8d, [r14+4]
0x18002b176  cmp     esi, r8d
0x18002b179  jge     short loc_18002B199
0x18002b17b  sub     r8d, esi
0x18002b17e  mov     rdx, rsi
0x18002b181  shl     rdx, 4
0x18002b185  add     rdx, [r14+8]; Src
0x18002b189  movsxd  r8, r8d
0x18002b18c  shl     r8, 4; Size
0x18002b190  lea     rcx, [rdx+10h]; void *
0x18002b194  call    memmove_0
0x18002b199  mov     rax, [r14+8]
0x18002b19d  xorps   xmm0, xmm0
0x18002b1a0  mov     rcx, rsi
0x18002b1a3  mov     edi, r12d
0x18002b1a6  add     rcx, rcx
0x18002b1a9  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002b1ad  mov     rax, [r14+8]
0x18002b1b1  movups  xmm0, [rbp+var_58]
0x18002b1b5  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18002b1ba  inc     dword ptr [r14+4]
0x18002b1be  mov     ecx, edi
0x18002b1c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b1c5  test    edi, edi
0x18002b1c7  jns     short loc_18002B1D0
0x18002b1c9  mov     ecx, edi
0x18002b1cb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002b1d0  mov     ecx, edi
0x18002b1d2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b1d7  lea     rcx, [rbp+var_18]
0x18002b1db  call    ??1?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(void)
0x18002b1e0  mov     rbx, [rbp+var_40]
0x18002b1e4  test    rbx, rbx
0x18002b1e7  jz      short loc_18002B205
0x18002b1e9  call    cs:__imp_GetProcessHeap
0x18002b1ef  lea     r8, [rbx-4]; lpMem
0x18002b1f3  xor     edx, edx; dwFlags
0x18002b1f5  mov     rcx, rax; hHeap
0x18002b1f8  call    cs:__imp_HeapFree
0x18002b1fe  xor     ecx, ecx
0x18002b200  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002b205  mov     eax, edi
0x18002b207  add     rsp, 78h
0x18002b20b  pop     r15
0x18002b20d  pop     r14
0x18002b20f  pop     r13
0x18002b211  pop     r12
0x18002b213  pop     rdi
0x18002b214  pop     rsi
0x18002b215  pop     rbx
0x18002b216  pop     rbp
0x18002b217  retn
0x18002b218  mov     ecx, eax
0x18002b21a  jmp     short loc_18002B1CB
```
