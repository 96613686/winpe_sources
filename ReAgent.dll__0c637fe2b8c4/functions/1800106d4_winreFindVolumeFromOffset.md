# winreFindVolumeFromOffset

- ea: `0x1800106d4`
- end: `0x1800109c7`
- name: `winreFindVolumeFromOffset`
- size: `755`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x180011974`
- `0x180017960`
- `0x180036c38`

## callees

- `0x180002786`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6f0`
- `0x18000edec`
- `0x18000ee80`
- `0x18000ffcc`
- `0x1800106d4`
- `0x180011208`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x180010879`
- `KERNEL32!GetFileAttributesExW` at `0x180010879`
- `ole32!CoTaskMemFree` at `0x180010997`
- `ole32!CoTaskMemFree` at `0x180010997`

## string_xrefs

- `0x180010737`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x1800107a6`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18001095d`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18001074e`: `failed to allocate path`
- `0x180010956`: `failed to create target path`
- `0x1800108fb`: `failed to copy target path`

## pseudocode

```c
__int64 __fastcall winreFindVolumeFromOffset(__int64 a1, unsigned __int16 *a2, void *a3, int a4, int a5)
{
  int v6; // ebx
  __int64 **v7; // r15
  unsigned int PartitionList; // edi
  __int64 v9; // rax
  BOOL v10; // r14d
  int v11; // r13d
  int v12; // ecx
  __int64 **i; // rbx
  bool v14; // zf
  __int64 v15; // rax
  int v16; // r14d
  unsigned __int16 *v17; // r14
  const char *v18; // r8
  int v20; // [rsp+28h] [rbp-49h]
  int v21; // [rsp+34h] [rbp-3Dh]
  LPCWSTR lpFileName; // [rsp+38h] [rbp-39h] BYREF
  BOOL v23; // [rsp+40h] [rbp-31h]
  int v24; // [rsp+44h] [rbp-2Dh]
  __int64 **v25; // [rsp+48h] [rbp-29h]
  unsigned __int16 *v26; // [rsp+50h] [rbp-21h]
  void *v27; // [rsp+58h] [rbp-19h]
  _OWORD FileInformation[2]; // [rsp+60h] [rbp-11h] BYREF
  int v29; // [rsp+80h] [rbp+Fh]

  v24 = a4;
  v27 = a3;
  v6 = 0;
  v26 = a2;
  v7 = 0;
  lpFileName = 0;
  v25 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v29 = 0;
  PartitionList = winreAllocPath(&lpFileName);
  if ( PartitionList )
  {
    UnattendLogW(
      2,
      L"winreFindVolumeFromOffset %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      PartitionList,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
      1475);
    goto LABEL_41;
  }
  v9 = *(_QWORD *)&ZeroGuid.Data1 - *(_QWORD *)(a1 + 1212);
  if ( *(_QWORD *)&ZeroGuid.Data1 == *(_QWORD *)(a1 + 1212) )
    v9 = *(_QWORD *)ZeroGuid.Data4 - *(_QWORD *)(a1 + 1220);
  v10 = v9 == 0;
  v23 = v10;
  PartitionList = PrivateGetPartitionList(0);
  if ( PartitionList )
  {
    UnattendLogW(
      2,
      L"winreFindVolumeFromOffset %s (0x%x) in file %S line %d",
      L"failed to get partition list",
      PartitionList,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
      1487);
    v7 = v25;
    goto LABEL_41;
  }
  v7 = v25;
  v11 = 0;
  v12 = 0;
LABEL_8:
  v21 = v12;
LABEL_9:
  for ( i = (__int64 **)*v7; ; i = (__int64 **)*i )
  {
    if ( i == v7 )
    {
      if ( !v11 )
      {
LABEL_26:
        v11 = 1;
        goto LABEL_9;
      }
      if ( a5 && !v12 )
      {
        v12 = 1;
        goto LABEL_8;
      }
      goto LABEL_40;
    }
    if ( !v11 )
    {
      if ( v10 )
      {
        v14 = *((_DWORD *)i + 8) == *(_DWORD *)(a1 + 1208);
      }
      else
      {
        v15 = *(_QWORD *)(a1 + 1212) - *(_QWORD *)((char *)i + 36);
        if ( !v15 )
          v15 = *(_QWORD *)(a1 + 1220) - *(_QWORD *)((char *)i + 44);
        v14 = v15 == 0;
      }
      if ( !v14 )
        continue;
    }
    if ( !v12 && i[158] != *(__int64 **)(a1 + 1232) )
      continue;
    v16 = StringCchPrintfW((unsigned __int16 *)lpFileName, 0x12Eu, L"%s%s", i + 82, a1 + 604);
    if ( v16 < 0 )
    {
      v20 = 1550;
      v18 = "failed to create target path";
LABEL_39:
      UnattendLogW(
        2,
        L"winreFindVolumeFromOffset %s (0x%x) in file %S line %d",
        v18,
        (unsigned int)v16,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        v20);
      PartitionList = (unsigned __int16)v16;
LABEL_40:
      v6 = 0;
      goto LABEL_41;
    }
    if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, FileInformation) && (FileInformation[0] & 0x10) != 0 )
      break;
    v12 = v21;
    v10 = v23;
    if ( !v11 )
      goto LABEL_26;
  }
  v17 = v26;
  if ( v26 )
  {
    winreRemoveTrailingBackslash(lpFileName);
    v16 = StringCchCopyW(v17, 0x12Eu, lpFileName);
    if ( v16 < 0 )
    {
      v20 = 1578;
      v18 = (const char *)L"failed to copy target path";
      goto LABEL_39;
    }
  }
  if ( v27 )
    memcpy_0(v27, i, 0x530u);
  if ( v24 )
  {
    *(_DWORD *)(a1 + 1208) = *((_DWORD *)i + 8);
    *(_QWORD *)(a1 + 1232) = i[158];
    *(_OWORD *)(a1 + 1212) = *(_OWORD *)((char *)i + 36);
  }
  v6 = 1;
LABEL_41:
  PrivateFreePartitionList(v7);
  if ( lpFileName )
    CoTaskMemFree((LPVOID)lpFileName);
  if ( !v6 )
    return 3;
  return PartitionList;
}

```

## disassembly

```asm
0x1800106d4  push    rbp
0x1800106d6  push    rbx
0x1800106d7  push    rsi
0x1800106d8  push    rdi
0x1800106d9  push    r13
0x1800106db  push    r14
0x1800106dd  push    r15
0x1800106df  lea     rbp, [rsp-1Fh]
0x1800106e4  sub     rsp, 90h
0x1800106eb  mov     rax, cs:__security_cookie
0x1800106f2  xor     rax, rsp
0x1800106f5  mov     [rbp+4Fh+var_38], rax
0x1800106f9  xorps   xmm0, xmm0
0x1800106fc  mov     [rbp+4Fh+var_7C], r9d
0x180010700  mov     rsi, rcx
0x180010703  mov     [rbp+4Fh+var_68], r8
0x180010707  xor     ebx, ebx
0x180010709  mov     [rbp+4Fh+var_70], rdx
0x18001070d  xor     eax, eax
0x18001070f  mov     [rbp+4Fh+var_90], ebx
0x180010712  xor     r15d, r15d
0x180010715  mov     [rbp+4Fh+lpFileName], rbx
0x180010719  lea     rcx, [rbp+4Fh+lpFileName]
0x18001071d  mov     [rbp+4Fh+var_78], r15
0x180010721  movups  [rbp+4Fh+FileInformation], xmm0
0x180010725  mov     [rbp+4Fh+var_40], eax
0x180010728  movups  [rbp+4Fh+var_50], xmm0
0x18001072c  call    winreAllocPath
0x180010731  mov     edi, eax
0x180010733  test    eax, eax
0x180010735  jz      short loc_180010769
0x180010737  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18001073e  mov     [rsp+0C0h+var_98], 5C3h
0x180010746  mov     r9d, edi
0x180010749  mov     [rsp+0C0h+var_A0], rax
0x18001074e  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180010755  lea     rdx, aWinrefindvolum; "winreFindVolumeFromOffset %s (0x%x) in "...
0x18001075c  lea     ecx, [rbx+2]
0x18001075f  call    UnattendLogW
0x180010764  jmp     loc_180010984
0x180010769  mov     rax, qword ptr cs:ZeroGuid.Data1
0x180010770  sub     rax, [rsi+4BCh]
0x180010777  jnz     short loc_180010787
0x180010779  mov     rax, qword ptr cs:ZeroGuid.Data4
0x180010780  sub     rax, [rsi+4C4h]
0x180010787  xor     r14d, r14d
0x18001078a  lea     rdx, [rbp+4Fh+var_78]
0x18001078e  test    rax, rax
0x180010791  setz    r14b
0x180010795  xor     ecx, ecx; struct _GUID *
0x180010797  mov     [rbp+4Fh+var_80], r14d
0x18001079b  call    PrivateGetPartitionList
0x1800107a0  mov     edi, eax
0x1800107a2  test    eax, eax
0x1800107a4  jz      short loc_1800107DE
0x1800107a6  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x1800107ad  mov     [rsp+0C0h+var_98], 5CFh
0x1800107b5  mov     r9d, edi
0x1800107b8  mov     [rsp+0C0h+var_A0], rax
0x1800107bd  lea     r8, aFailedToGetPar; "failed to get partition list"
0x1800107c4  mov     ecx, 2
0x1800107c9  lea     rdx, aWinrefindvolum; "winreFindVolumeFromOffset %s (0x%x) in "...
0x1800107d0  call    UnattendLogW
0x1800107d5  mov     r15, [rbp+4Fh+var_78]
0x1800107d9  jmp     loc_180010984
0x1800107de  mov     r15, [rbp+4Fh+var_78]
0x1800107e2  xor     r13d, r13d
0x1800107e5  xor     ecx, ecx
0x1800107e7  mov     [rbp+4Fh+var_8C], ecx
0x1800107ea  mov     rbx, [r15]
0x1800107ed  cmp     rbx, r15
0x1800107f0  jz      loc_18001089D
0x1800107f6  test    r13d, r13d
0x1800107f9  jnz     short loc_180010828
0x1800107fb  test    r14d, r14d
0x1800107fe  jz      short loc_18001080B
0x180010800  mov     eax, [rsi+4B8h]
0x180010806  cmp     [rbx+20h], eax
0x180010809  jmp     short loc_180010826
0x18001080b  mov     rax, [rsi+4BCh]
0x180010812  sub     rax, [rbx+24h]
0x180010816  jnz     short loc_180010823
0x180010818  mov     rax, [rsi+4C4h]
0x18001081f  sub     rax, [rbx+2Ch]
0x180010823  test    rax, rax
0x180010826  jnz     short loc_180010895
0x180010828  test    ecx, ecx
0x18001082a  jnz     short loc_18001083C
0x18001082c  mov     rax, [rsi+4D0h]
0x180010833  cmp     [rbx+4F0h], rax
0x18001083a  jnz     short loc_180010895
0x18001083c  mov     rcx, [rbp+4Fh+lpFileName]; unsigned __int16 *
0x180010840  lea     rax, [rsi+25Ch]
0x180010847  lea     r9, [rbx+290h]
0x18001084e  mov     [rsp+0C0h+var_A0], rax
0x180010853  lea     r8, aSS_2; "%s%s"
0x18001085a  mov     edx, 12Eh; unsigned __int64
0x18001085f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010864  mov     r14d, eax
0x180010867  test    eax, eax
0x180010869  js      loc_18001094E
0x18001086f  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x180010873  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x180010877  xor     edx, edx; fInfoLevelId
0x180010879  call    cs:__imp_GetFileAttributesExW
0x18001087f  test    eax, eax
0x180010881  jz      short loc_180010889
0x180010883  test    byte ptr [rbp+4Fh+FileInformation], 10h
0x180010887  jnz     short loc_1800108C9
0x180010889  mov     ecx, [rbp+4Fh+var_8C]
0x18001088c  mov     r14d, [rbp+4Fh+var_80]
0x180010890  test    r13d, r13d
0x180010893  jz      short loc_1800108A2
0x180010895  mov     rbx, [rbx]
0x180010898  jmp     loc_1800107ED
0x18001089d  test    r13d, r13d
0x1800108a0  jnz     short loc_1800108AD
0x1800108a2  mov     r13d, 1
0x1800108a8  jmp     loc_1800107EA
0x1800108ad  cmp     [rbp+4Fh+arg_20], 0
0x1800108b1  jz      loc_180010981
0x1800108b7  test    ecx, ecx
0x1800108b9  jnz     loc_180010981
0x1800108bf  mov     ecx, 1
0x1800108c4  jmp     loc_1800107E7
0x1800108c9  mov     r14, [rbp+4Fh+var_70]
0x1800108cd  test    r14, r14
0x1800108d0  jz      short loc_180010904
0x1800108d2  mov     rcx, [rbp+4Fh+lpFileName]
0x1800108d6  call    winreRemoveTrailingBackslash
0x1800108db  mov     r8, [rbp+4Fh+lpFileName]; unsigned __int16 *
0x1800108df  mov     edx, 12Eh; unsigned __int64
0x1800108e4  mov     rcx, r14; unsigned __int16 *
0x1800108e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800108ec  mov     r14d, eax
0x1800108ef  test    eax, eax
0x1800108f1  jns     short loc_180010904
0x1800108f3  mov     [rsp+0C0h+var_98], 62Ah
0x1800108fb  lea     r8, aFailedToCopyTa_0; "failed to copy target path"
0x180010902  jmp     short loc_18001095D
0x180010904  mov     rax, [rbp+4Fh+var_68]
0x180010908  test    rax, rax
0x18001090b  jz      short loc_18001091E
0x18001090d  mov     rcx, rax; void *
0x180010910  mov     rdx, rbx; Src
0x180010913  mov     r8d, 530h; Size
0x180010919  call    memcpy_0
0x18001091e  cmp     [rbp+4Fh+var_7C], 0
0x180010922  jz      short loc_180010947
0x180010924  mov     eax, [rbx+20h]
0x180010927  mov     [rsi+4B8h], eax
0x18001092d  mov     rax, [rbx+4F0h]
0x180010934  mov     [rsi+4D0h], rax
0x18001093b  movups  xmm0, xmmword ptr [rbx+24h]
0x18001093f  movdqu  xmmword ptr [rsi+4BCh], xmm0
0x180010947  mov     ebx, 1
0x18001094c  jmp     short loc_180010984
0x18001094e  mov     [rsp+0C0h+var_98], 60Eh
0x180010956  lea     r8, aFailedToCreate_24; "failed to create target path"
0x18001095d  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010964  mov     r9d, r14d
0x180010967  lea     rdx, aWinrefindvolum; "winreFindVolumeFromOffset %s (0x%x) in "...
0x18001096e  mov     [rsp+0C0h+var_A0], rax
0x180010973  mov     ecx, 2
0x180010978  call    UnattendLogW
0x18001097d  movzx   edi, r14w
0x180010981  mov     ebx, [rbp+4Fh+var_90]
0x180010984  mov     rcx, r15; pv
0x180010987  call    PrivateFreePartitionList
0x18001098c  cmp     [rbp+4Fh+lpFileName], 0
0x180010991  jz      short loc_18001099D
0x180010993  mov     rcx, [rbp+4Fh+lpFileName]; pv
0x180010997  call    cs:__imp_CoTaskMemFree
0x18001099d  mov     eax, 3
0x1800109a2  test    ebx, ebx
0x1800109a4  cmovz   edi, eax
0x1800109a7  mov     eax, edi
0x1800109a9  mov     rcx, [rbp+4Fh+var_38]
0x1800109ad  xor     rcx, rsp; StackCookie
0x1800109b0  call    __security_check_cookie
0x1800109b5  add     rsp, 90h
0x1800109bc  pop     r15
0x1800109be  pop     r14
0x1800109c0  pop     r13
0x1800109c2  pop     rdi
0x1800109c3  pop     rsi
0x1800109c4  pop     rbx
0x1800109c5  pop     rbp
0x1800109c6  retn
```
