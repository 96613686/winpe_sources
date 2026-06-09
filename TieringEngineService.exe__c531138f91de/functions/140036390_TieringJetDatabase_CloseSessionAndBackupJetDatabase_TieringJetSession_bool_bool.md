# TieringJetDatabase::CloseSessionAndBackupJetDatabase(TieringJetSession *,bool *,bool *)

- ea: `0x140036390`
- end: `0x1400367ba`
- name: `?CloseSessionAndBackupJetDatabase@TieringJetDatabase@@QEAAJPEAVTieringJetSession@@PEA_N1@Z`
- size: `1066`
- prototype: `__int64 __fastcall(TieringJetDatabase *__hidden this, struct TieringJetSession *, bool *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14002eef0`

## callees

- `0x140002db0`
- `0x140004aa8`
- `0x140009a04`
- `0x140009a64`
- `0x140009c08`
- `0x14000c7e0`
- `0x14000c8f8`
- `0x14000ccc0`
- `0x1400197b0`
- `0x14001cb9c`
- `0x140036390`
- `0x1400367c0`
- `0x1400370f8`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400364ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400364b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400364e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400364ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400364b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400364e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036590`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400366b4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400366b4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400364a2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140036541`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400364a2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140036541`

## pseudocode

```c
__int64 __fastcall TieringJetDatabase::CloseSessionAndBackupJetDatabase(
        TieringJetDatabase *this,
        struct TieringJetSession *a2,
        bool *a3,
        bool *a4)
{
  __int64 result; // rax
  int i; // edi
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  WCHAR *v10; // rax
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  DWORD LastError; // eax
  char v20; // si
  char v21; // al
  DWORD v22; // eax
  char v23; // di
  char v24; // al
  int v25; // eax
  bool v26; // dl
  int v27; // eax
  int v28; // edi
  _QWORD *v29; // rcx
  CTieredVolume *v30; // rcx
  unsigned int v31; // ebx
  WCHAR v34[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR PathName[264]; // [rsp+250h] [rbp+150h] BYREF

  result = TieringJetDatabase::GetBackupDirectoryName(this, 2, v34);
  if ( (int)result < 0 )
    return result;
  CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(*(_QWORD *)this, (__int64)v34, 0, 0, L"*.*");
  for ( i = 1; i > 0; --i )
  {
    v8 = PathName;
    v9 = 4;
    v10 = v34;
    do
    {
      v11 = *(_OWORD *)v10;
      v12 = *((_OWORD *)v10 + 1);
      v10 += 64;
      *(_OWORD *)v8 = v11;
      v13 = *((_OWORD *)v10 - 6);
      *((_OWORD *)v8 + 1) = v12;
      v14 = *((_OWORD *)v10 - 5);
      *((_OWORD *)v8 + 2) = v13;
      v15 = *((_OWORD *)v10 - 4);
      *((_OWORD *)v8 + 3) = v14;
      v16 = *((_OWORD *)v10 - 3);
      *((_OWORD *)v8 + 4) = v15;
      v17 = *((_OWORD *)v10 - 2);
      *((_OWORD *)v8 + 5) = v16;
      v18 = *((_OWORD *)v10 - 1);
      *((_OWORD *)v8 + 6) = v17;
      *((_OWORD *)v8 + 7) = v18;
      v8 += 64;
      --v9;
    }
    while ( v9 );
    *(_QWORD *)v8 = *(_QWORD *)v10;
    if ( (int)TieringJetDatabase::GetBackupDirectoryName(this, i, v34) < 0 )
      break;
    if ( CreateDirectoryW(PathName, 0) || GetLastError() == 183 )
    {
      CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(
        *(_QWORD *)this,
        (__int64)v34,
        (__int64)PathName,
        1u,
        L"*.*");
    }
    else
    {
      LastError = GetLastError();
      v20 = ATL::AtlHresultFromWin32(LastError);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = GetLastError();
        WPP_SF_SDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
          (unsigned int)PathName,
          v21,
          v20);
      }
    }
  }
  if ( !CreateDirectoryW(v34, 0) && GetLastError() != 183 )
  {
    v22 = GetLastError();
    v23 = ATL::AtlHresultFromWin32(v22);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = GetLastError();
      WPP_SF_SDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
        (unsigned int)v34,
        v24,
        v23);
    }
  }
  *(_BYTE *)(*(_QWORD *)this + 164LL) = 1;
  v25 = TieringJetSession::CloseJetTable(a2, 1);
  if ( v25 >= 0 )
  {
    *a4 = 1;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
      (unsigned int)v34,
      v25);
  }
  CTieredVolume::CloseJetDatabases(*(CTieredVolume **)this, 0, 0, 1);
  v27 = TieringJetDatabase::WaitForDatabaseClose(this, v26);
  v28 = v27;
  if ( v27 >= 0 )
    goto LABEL_31;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_32:
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 && *((_BYTE *)v29 + 25) >= 4u )
        WPP_SF_S(v29[2], 38, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v34);
      goto LABEL_36;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
      (unsigned int)v34,
      v27);
LABEL_31:
    v29 = WPP_GLOBAL_Control;
    goto LABEL_32;
  }
LABEL_36:
  CTieredVolume::CloseJetInstance(*(CTieredVolume **)this, 0, 1);
  Sleep(0x7D0u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v34);
  }
  CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(
    *(_QWORD *)this,
    *(_QWORD *)(*(_QWORD *)this + 600LL),
    (__int64)v34,
    2u,
    L"*.*");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v34);
  }
  *(_BYTE *)(*(_QWORD *)this + 164LL) = 0;
  v30 = *(CTieredVolume **)this;
  v31 = *(_DWORD *)(*(_QWORD *)this + 128LL);
  CTieredVolume::DereferenceVolume(v30);
  *a3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v31, v28);
  }
  return 0;
}

```

## disassembly

```asm
0x140036390  push    rbp
0x140036392  push    rbx
0x140036393  push    rsi
0x140036394  push    rdi
0x140036395  push    r12
0x140036397  push    r13
0x140036399  push    r14
0x14003639b  push    r15
0x14003639d  lea     rbp, [rsp-378h]
0x1400363a5  sub     rsp, 478h
0x1400363ac  mov     rax, cs:__security_cookie
0x1400363b3  xor     rax, rsp
0x1400363b6  mov     [rbp+3B0h+var_50], rax
0x1400363bd  mov     [rsp+4B0h+var_478], r8
0x1400363c2  mov     r15, rdx
0x1400363c5  lea     r8, [rsp+4B0h+var_470]; unsigned __int16 *
0x1400363ca  mov     [rsp+4B0h+var_480], r9
0x1400363cf  mov     edx, 2; int
0x1400363d4  mov     rbx, rcx
0x1400363d7  call    ?GetBackupDirectoryName@TieringJetDatabase@@QEAAJHPEAG@Z; TieringJetDatabase::GetBackupDirectoryName(int,ushort *)
0x1400363dc  test    eax, eax
0x1400363de  js      loc_140036797
0x1400363e4  mov     rcx, [rbx]
0x1400363e7  lea     rax, asc_140044A18; "*.*"
0x1400363ee  xor     r9d, r9d
0x1400363f1  mov     [rsp+4B0h+var_490], rax
0x1400363f6  xor     r8d, r8d
0x1400363f9  lea     rdx, [rsp+4B0h+var_470]
0x1400363fe  call    ?TryDeleteMoveCopyFilesForRecoveryOrBackup@CTieredVolume@@QEAAXPEAG0W4RECOVERY_FILE_ACTION@@0@Z; CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(ushort *,ushort *,RECOVERY_FILE_ACTION,ushort *)
0x140036403  mov     r13d, 1
0x140036409  lea     r12, WPP_GLOBAL_Control
0x140036410  mov     edi, r13d
0x140036413  lea     r14, asc_140044A18; "*.*"
0x14003641a  lea     rcx, [rbp+3B0h+PathName]
0x140036421  mov     edx, 4
0x140036426  lea     rax, [rsp+4B0h+var_470]
0x14003642b  movups  xmm0, xmmword ptr [rax]
0x14003642e  movups  xmm1, xmmword ptr [rax+10h]
0x140036432  lea     rax, [rax+80h]
0x140036439  movups  xmmword ptr [rcx], xmm0
0x14003643c  movups  xmm0, xmmword ptr [rax-60h]
0x140036440  movups  xmmword ptr [rcx+10h], xmm1
0x140036444  movups  xmm1, xmmword ptr [rax-50h]
0x140036448  movups  xmmword ptr [rcx+20h], xmm0
0x14003644c  movups  xmm0, xmmword ptr [rax-40h]
0x140036450  movups  xmmword ptr [rcx+30h], xmm1
0x140036454  movups  xmm1, xmmword ptr [rax-30h]
0x140036458  movups  xmmword ptr [rcx+40h], xmm0
0x14003645c  movups  xmm0, xmmword ptr [rax-20h]
0x140036460  movups  xmmword ptr [rcx+50h], xmm1
0x140036464  movups  xmm1, xmmword ptr [rax-10h]
0x140036468  movups  xmmword ptr [rcx+60h], xmm0
0x14003646c  movups  xmmword ptr [rcx+70h], xmm1
0x140036470  lea     rcx, [rcx+80h]
0x140036477  sub     rdx, r13
0x14003647a  jnz     short loc_14003642B
0x14003647c  mov     rax, [rax]
0x14003647f  lea     r8, [rsp+4B0h+var_470]; unsigned __int16 *
0x140036484  mov     [rcx], rax
0x140036487  mov     edx, edi; int
0x140036489  mov     rcx, rbx; this
0x14003648c  call    ?GetBackupDirectoryName@TieringJetDatabase@@QEAAJHPEAG@Z; TieringJetDatabase::GetBackupDirectoryName(int,ushort *)
0x140036491  test    eax, eax
0x140036493  js      loc_14003653A
0x140036499  xor     edx, edx; lpSecurityAttributes
0x14003649b  lea     rcx, [rbp+3B0h+PathName]; lpPathName
0x1400364a2  call    cs:__imp_CreateDirectoryW
0x1400364a8  test    eax, eax
0x1400364aa  jnz     short loc_140036513
0x1400364ac  call    cs:__imp_GetLastError
0x1400364b2  cmp     eax, 0B7h
0x1400364b7  jz      short loc_140036513
0x1400364b9  call    cs:__imp_GetLastError
0x1400364bf  mov     ecx, eax; unsigned int
0x1400364c1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400364c6  mov     esi, eax
0x1400364c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364cf  cmp     rcx, r12
0x1400364d2  jz      short loc_14003652F
0x1400364d4  test    [rcx+1Ch], r13b
0x1400364d8  jz      short loc_14003652F
0x1400364da  cmp     byte ptr [rcx+19h], 2
0x1400364de  jb      short loc_14003652F
0x1400364e0  call    cs:__imp_GetLastError
0x1400364e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364ed  lea     r9, [rbp+3B0h+PathName]
0x1400364f4  mov     edx, 22h ; '"'
0x1400364f9  mov     [rsp+4B0h+var_488], esi
0x1400364fd  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140036504  mov     dword ptr [rsp+4B0h+var_490], eax
0x140036508  mov     rcx, [rcx+10h]
0x14003650c  call    WPP_SF_SDd
0x140036511  jmp     short loc_14003652F
0x140036513  mov     rcx, [rbx]
0x140036516  lea     r8, [rbp+3B0h+PathName]
0x14003651d  mov     r9d, r13d
0x140036520  mov     [rsp+4B0h+var_490], r14
0x140036525  lea     rdx, [rsp+4B0h+var_470]
0x14003652a  call    ?TryDeleteMoveCopyFilesForRecoveryOrBackup@CTieredVolume@@QEAAXPEAG0W4RECOVERY_FILE_ACTION@@0@Z; CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(ushort *,ushort *,RECOVERY_FILE_ACTION,ushort *)
0x14003652f  sub     edi, r13d
0x140036532  test    edi, edi
0x140036534  jg      loc_14003641A
0x14003653a  xor     edx, edx; lpSecurityAttributes
0x14003653c  lea     rcx, [rsp+4B0h+var_470]; lpPathName
0x140036541  call    cs:__imp_CreateDirectoryW
0x140036547  mov     r14, [rsp+4B0h+var_480]
0x14003654c  mov     r12, [rsp+4B0h+var_478]
0x140036551  test    eax, eax
0x140036553  jnz     short loc_1400365C1
0x140036555  call    cs:__imp_GetLastError
0x14003655b  cmp     eax, 0B7h
0x140036560  jz      short loc_1400365C1
0x140036562  call    cs:__imp_GetLastError
0x140036568  mov     ecx, eax; unsigned int
0x14003656a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003656f  mov     edi, eax
0x140036571  mov     rcx, cs:WPP_GLOBAL_Control
0x140036578  lea     rsi, WPP_GLOBAL_Control
0x14003657f  cmp     rcx, rsi
0x140036582  jz      short loc_1400365C8
0x140036584  test    [rcx+1Ch], r13b
0x140036588  jz      short loc_1400365C8
0x14003658a  cmp     byte ptr [rcx+19h], 2
0x14003658e  jb      short loc_1400365C8
0x140036590  call    cs:__imp_GetLastError
0x140036596  mov     rcx, cs:WPP_GLOBAL_Control
0x14003659d  lea     r9, [rsp+4B0h+var_470]
0x1400365a2  mov     edx, 23h ; '#'
0x1400365a7  mov     [rsp+4B0h+var_488], edi
0x1400365ab  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x1400365b2  mov     dword ptr [rsp+4B0h+var_490], eax
0x1400365b6  mov     rcx, [rcx+10h]
0x1400365ba  call    WPP_SF_SDd
0x1400365bf  jmp     short loc_1400365C8
0x1400365c1  lea     rsi, WPP_GLOBAL_Control
0x1400365c8  mov     rax, [rbx]
0x1400365cb  mov     dl, r13b; bool
0x1400365ce  mov     rcx, r15; this
0x1400365d1  mov     [rax+0A4h], r13b
0x1400365d8  call    ?CloseJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::CloseJetTable(bool)
0x1400365dd  test    eax, eax
0x1400365df  jns     short loc_140036619
0x1400365e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400365e8  cmp     rcx, rsi
0x1400365eb  jz      short loc_14003661C
0x1400365ed  test    [rcx+1Ch], r13b
0x1400365f1  jz      short loc_14003661C
0x1400365f3  cmp     byte ptr [rcx+19h], 2
0x1400365f7  jb      short loc_14003661C
0x1400365f9  mov     rcx, [rcx+10h]
0x1400365fd  lea     r9, [rsp+4B0h+var_470]
0x140036602  mov     edx, 24h ; '$'
0x140036607  mov     dword ptr [rsp+4B0h+var_490], eax
0x14003660b  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140036612  call    WPP_SF_Sd
0x140036617  jmp     short loc_14003661C
0x140036619  mov     [r14], r13b
0x14003661c  mov     rcx, [rbx]; this
0x14003661f  mov     r9b, r13b; bool
0x140036622  xor     r8d, r8d; bool
0x140036625  xor     edx, edx; bool
0x140036627  call    ?CloseJetDatabases@CTieredVolume@@QEAAX_N00@Z; CTieredVolume::CloseJetDatabases(bool,bool,bool)
0x14003662c  mov     rcx, rbx; this
0x14003662f  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x140036634  mov     edi, eax
0x140036636  test    eax, eax
0x140036638  jns     short loc_140036670
0x14003663a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036641  cmp     rcx, rsi
0x140036644  jz      short loc_1400366A2
0x140036646  test    [rcx+1Ch], r13b
0x14003664a  jz      short loc_140036677
0x14003664c  cmp     byte ptr [rcx+19h], 2
0x140036650  jb      short loc_140036677
0x140036652  mov     rcx, [rcx+10h]
0x140036656  lea     r9, [rsp+4B0h+var_470]
0x14003665b  mov     edx, 25h ; '%'
0x140036660  mov     dword ptr [rsp+4B0h+var_490], eax
0x140036664  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x14003666b  call    WPP_SF_Sd
0x140036670  mov     rcx, cs:WPP_GLOBAL_Control
0x140036677  cmp     rcx, rsi
0x14003667a  jz      short loc_1400366A2
0x14003667c  test    [rcx+1Ch], r13b
0x140036680  jz      short loc_1400366A2
0x140036682  cmp     byte ptr [rcx+19h], 4
0x140036686  jb      short loc_1400366A2
0x140036688  mov     rcx, [rcx+10h]
0x14003668c  lea     r9, [rsp+4B0h+var_470]
0x140036691  mov     edx, 26h ; '&'
0x140036696  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x14003669d  call    WPP_SF_S
0x1400366a2  mov     rcx, [rbx]; this
0x1400366a5  mov     r8b, r13b; bool
0x1400366a8  xor     edx, edx; bool
0x1400366aa  call    ?CloseJetInstance@CTieredVolume@@QEAAX_N0@Z; CTieredVolume::CloseJetInstance(bool,bool)
0x1400366af  mov     ecx, 7D0h; dwMilliseconds
0x1400366b4  call    cs:__imp_Sleep
0x1400366ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366c1  cmp     rcx, rsi
0x1400366c4  jz      short loc_1400366EC
0x1400366c6  test    [rcx+1Ch], r13b
0x1400366ca  jz      short loc_1400366EC
0x1400366cc  cmp     byte ptr [rcx+19h], 4
0x1400366d0  jb      short loc_1400366EC
0x1400366d2  mov     rcx, [rcx+10h]
0x1400366d6  lea     r9, [rsp+4B0h+var_470]
0x1400366db  mov     edx, 27h ; '''
0x1400366e0  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x1400366e7  call    WPP_SF_S
0x1400366ec  mov     rcx, [rbx]
0x1400366ef  lea     rax, asc_140044A18; "*.*"
0x1400366f6  mov     r9d, 2
0x1400366fc  mov     [rsp+4B0h+var_490], rax
0x140036701  lea     r8, [rsp+4B0h+var_470]
0x140036706  mov     rdx, [rcx+258h]
0x14003670d  call    ?TryDeleteMoveCopyFilesForRecoveryOrBackup@CTieredVolume@@QEAAXPEAG0W4RECOVERY_FILE_ACTION@@0@Z; CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(ushort *,ushort *,RECOVERY_FILE_ACTION,ushort *)
0x140036712  mov     rcx, cs:WPP_GLOBAL_Control
0x140036719  cmp     rcx, rsi
0x14003671c  jz      short loc_140036744
0x14003671e  test    [rcx+1Ch], r13b
0x140036722  jz      short loc_140036744
0x140036724  cmp     byte ptr [rcx+19h], 4
0x140036728  jb      short loc_140036744
0x14003672a  mov     rcx, [rcx+10h]
0x14003672e  lea     r9, [rsp+4B0h+var_470]
0x140036733  mov     edx, 28h ; '('
0x140036738  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x14003673f  call    WPP_SF_S
0x140036744  mov     rax, [rbx]
0x140036747  mov     byte ptr [rax+0A4h], 0
0x14003674e  mov     rcx, [rbx]; this
0x140036751  mov     ebx, [rcx+80h]
0x140036757  call    ?DereferenceVolume@CTieredVolume@@QEAAXXZ; CTieredVolume::DereferenceVolume(void)
0x14003675c  mov     byte ptr [r12], 0
0x140036761  mov     rcx, cs:WPP_GLOBAL_Control
0x140036768  cmp     rcx, rsi
0x14003676b  jz      short loc_140036795
0x14003676d  test    [rcx+1Ch], r13b
0x140036771  jz      short loc_140036795
0x140036773  cmp     byte ptr [rcx+19h], 2
0x140036777  jb      short loc_140036795
0x140036779  mov     rcx, [rcx+10h]
0x14003677d  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140036784  mov     edx, 29h ; ')'
0x140036789  mov     dword ptr [rsp+4B0h+var_490], edi
0x14003678d  mov     r9d, ebx
0x140036790  call    WPP_SF_Dd
0x140036795  xor     eax, eax
0x140036797  mov     rcx, [rbp+3B0h+var_50]
0x14003679e  xor     rcx, rsp; StackCookie
0x1400367a1  call    __security_check_cookie
0x1400367a6  add     rsp, 478h
0x1400367ad  pop     r15
0x1400367af  pop     r14
0x1400367b1  pop     r13
0x1400367b3  pop     r12
0x1400367b5  pop     rdi
0x1400367b6  pop     rsi
0x1400367b7  pop     rbx
0x1400367b8  pop     rbp
0x1400367b9  retn
```
