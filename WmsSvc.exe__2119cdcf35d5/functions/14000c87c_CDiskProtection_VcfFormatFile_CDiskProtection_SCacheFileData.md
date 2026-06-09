# CDiskProtection::VcfFormatFile(CDiskProtection::SCacheFileData *)

- ea: `0x14000c87c`
- end: `0x14000ce0d`
- name: `?VcfFormatFile@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z`
- size: `1425`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this, struct CDiskProtection::SCacheFileData *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1400087b0`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400090dc`
- `0x14000c87c`
- `0x14000d22c`
- `0x14000d458`
- `0x14000d770`
- `0x14000dc30`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x14000ca31`
- `KERNEL32!SetFilePointerEx` at `0x14000cb2f`
- `KERNEL32!SetFilePointerEx` at `0x14000ca31`
- `KERNEL32!SetFilePointerEx` at `0x14000cb2f`
- `KERNEL32!WriteFile` at `0x14000cd0d`
- `KERNEL32!WriteFile` at `0x14000cd0d`
- `KERNEL32!GetLastError` at `0x14000ca3f`
- `KERNEL32!GetLastError` at `0x14000cb3d`
- `KERNEL32!GetLastError` at `0x14000cd1b`
- `KERNEL32!GetLastError` at `0x14000ca3f`
- `KERNEL32!GetLastError` at `0x14000cb3d`
- `KERNEL32!GetLastError` at `0x14000cd1b`
- `KERNEL32!IsDebuggerPresent` at `0x14000c947`
- `KERNEL32!IsDebuggerPresent` at `0x14000ca96`
- `KERNEL32!IsDebuggerPresent` at `0x14000cb94`
- `KERNEL32!IsDebuggerPresent` at `0x14000cd72`
- `KERNEL32!IsDebuggerPresent` at `0x14000c947`
- `KERNEL32!IsDebuggerPresent` at `0x14000ca96`
- `KERNEL32!IsDebuggerPresent` at `0x14000cb94`
- `KERNEL32!IsDebuggerPresent` at `0x14000cd72`
- `msvcrt!memcpy_s` at `0x14000cceb`
- `msvcrt!memcpy_s` at `0x14000cceb`

## pseudocode

```c
__int64 __fastcall CDiskProtection::VcfFormatFile(CDiskProtection *this, struct CDiskProtection::SCacheFileData *a2)
{
  int v4; // r14d
  void *v5; // rax
  CDiskProtection *v6; // rcx
  signed int PartitionInfo; // ebx
  CDiskProtection *v8; // rcx
  LARGE_INTEGER v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  void *v12; // rcx
  CDiskProtection *v13; // rcx
  signed int LastError; // eax
  __int64 v15; // r8
  CDiskProtection *v16; // rcx
  CDiskProtection *v17; // rcx
  signed int v18; // eax
  rsize_t v19; // r10
  __int64 v20; // xmm0_8
  int v21; // ecx
  unsigned __int64 v22; // rtt
  unsigned int v23; // r8d
  int *p_Source; // r9
  __int64 v25; // rax
  void *v26; // rcx
  signed int v27; // eax
  LARGE_INTEGER liDistanceToMove; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  int Source; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+64h] [rbp-9Ch] BYREF
  int v35; // [rsp+6Ch] [rbp-94h]
  int v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+74h] [rbp-8Ch]
  __int64 v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  rsize_t v41; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v42; // [rsp+B8h] [rbp-48h]
  __int64 v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E4h] [rbp-1Ch]
  int v49; // [rsp+E8h] [rbp-18h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  int v52; // [rsp+100h] [rbp+0h]
  int v53; // [rsp+104h] [rbp+4h]
  rsize_t v54; // [rsp+10Ch] [rbp+Ch]
  __int64 v55; // [rsp+11Dh] [rbp+1Dh]
  __int64 v56; // [rsp+125h] [rbp+25h]
  int v57; // [rsp+12Dh] [rbp+2Dh]
  unsigned int v58; // [rsp+135h] [rbp+35h]
  unsigned int v59; // [rsp+25Ch] [rbp+15Ch]

  v4 = 508;
  v32 = 0;
  v31 = 0;
  Source = 0;
  memset_0(&v34, 0, 0x1FCu);
  NumberOfBytesWritten = 0;
  DEBUGMSG(L"CDiskProtection::VcfFormatFile\n");
  v5 = operator new(*((unsigned int *)a2 + 12));
  *((_QWORD *)a2 + 28) = v5;
  if ( !v5 )
  {
    PartitionInfo = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0xE23u,
      L"CDiskProtection::VcfFormatFile",
      L"CPR",
      L"pcfd->pbSectorBuffer",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        3619,
        L"CDiskProtection::VcfFormatFile",
        L"CPR",
        L"pcfd->pbSectorBuffer",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        3619,
        L"CDiskProtection::VcfFormatFile",
        L"CPR",
        L"pcfd->pbSectorBuffer",
        -2147024882);
    goto LABEL_41;
  }
  PartitionInfo = CDiskProtection::VcfGetPartitionInfo(v6, a2, &v50, &v51);
  if ( PartitionInfo >= 0 )
  {
    PartitionInfo = CDiskProtection::GetNtfsVolumeData(
                      v8,
                      *(void **)a2,
                      (struct NTFS_VOLUME_DATA_BUFFER *)((char *)a2 + 8));
    if ( PartitionInfo >= 0 )
    {
      v9.QuadPart = *((unsigned int *)a2 + 12);
      liDistanceToMove = v9;
      *((_QWORD *)a2 + 17) = *((_DWORD *)a2 + 13) / v9.LowPart;
      v10 = *((_QWORD *)a2 + 18);
      *((_QWORD *)a2 + 20) = *(_QWORD *)(v10 + 8);
      v11 = (unsigned int)(*(_DWORD *)(v10 + 16 * (*((_QWORD *)a2 + 13) + 1LL)) - *(_DWORD *)(v10 + 8));
      v12 = *(void **)a2;
      *((_QWORD *)a2 + 16) = v11;
      *((_QWORD *)a2 + 19) = *((_QWORD *)a2 + 23) / v9.QuadPart;
      if ( !SetFilePointerEx(v12, v9, 0, 0) )
      {
        LastError = GetLastError();
        PartitionInfo = LastError;
        if ( LastError > 0 )
          PartitionInfo = (unsigned __int16)LastError | 0x80070000;
        if ( PartitionInfo >= 0 )
          PartitionInfo = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          0xE55u,
          L"CDiskProtection::VcfFormatFile",
          L"CBRAEx",
          L"fSuccess",
          PartitionInfo);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            3669,
            L"CDiskProtection::VcfFormatFile",
            L"CBRAEx",
            L"fSuccess",
            PartitionInfo);
          goto LABEL_41;
        }
        v15 = 3669;
LABEL_40:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v15,
          L"CDiskProtection::VcfFormatFile",
          L"CBRAEx",
          L"fSuccess",
          PartitionInfo);
        goto LABEL_41;
      }
      PartitionInfo = CDiskProtection::VcfGetNextBlockNumber(v13, a2, &v32);
      if ( PartitionInfo >= 0 )
      {
        PartitionInfo = CDiskProtection::VcfGetNextBlockNumber(v16, a2, &v31);
        if ( PartitionInfo >= 0 )
        {
          PartitionInfo = CDiskProtection::VcfWriteBaseMapSector(v17, a2);
          if ( PartitionInfo >= 0 )
          {
            PartitionInfo = CDiskProtection::VcfWriteChunkMapSectors(this, a2);
            if ( PartitionInfo >= 0 )
            {
              liDistanceToMove.LowPart = 0;
              if ( !SetFilePointerEx(*(HANDLE *)a2, liDistanceToMove, 0, 0) )
              {
                v18 = GetLastError();
                PartitionInfo = v18;
                if ( v18 > 0 )
                  PartitionInfo = (unsigned __int16)v18 | 0x80070000;
                if ( PartitionInfo >= 0 )
                  PartitionInfo = -2147467259;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                  0xE77u,
                  L"CDiskProtection::VcfFormatFile",
                  L"CBRAEx",
                  L"fSuccess",
                  PartitionInfo);
                if ( IsDebuggerPresent() )
                {
                  DEBUGMSGLEVEL(
                    2u,
                    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                    3703,
                    L"CDiskProtection::VcfFormatFile",
                    L"CBRAEx",
                    L"fSuccess",
                    PartitionInfo);
                  goto LABEL_41;
                }
                v15 = 3703;
                goto LABEL_40;
              }
              v19 = *((unsigned int *)a2 + 12);
              v20 = *((_QWORD *)a2 + 26);
              v21 = *((_DWORD *)a2 + 50);
              Source = *((_DWORD *)a2 + 51);
              v35 = *((_DWORD *)a2 + 54);
              v22 = *((_QWORD *)a2 + 23);
              v34 = v20;
              v41 = v22 / v19;
              v54 = v22 / v19;
              v36 = -808464433;
              v42 = v31 * (unsigned int)v19;
              v43 = *((_QWORD *)a2 + 14);
              v46 = *((_QWORD *)a2 + 1);
              v47 = *((_DWORD *)a2 + 13);
              v48 = *((_DWORD *)a2 + 14);
              v49 = *((_DWORD *)a2 + 15);
              v37 = 286331153;
              v58 = 0x100000 / (unsigned int)v19;
              v38 = 33947648;
              v39 = 0;
              v44 = 144;
              v52 = 1000;
              v53 = 500;
              v40 = -1;
              v45 = 1;
              if ( v21 )
              {
                v55 = *((_QWORD *)a2 + 24);
                v56 = 56;
                v57 = v21;
              }
              v23 = -559038737;
              p_Source = &Source;
              do
              {
                v25 = (unsigned __int8)(*(_BYTE *)p_Source ^ v23);
                p_Source = (int *)((char *)p_Source + 1);
                v23 = dword_1400D78D0[v25] ^ (v23 >> 8);
                --v4;
              }
              while ( v4 );
              v26 = (void *)*((_QWORD *)a2 + 28);
              v59 = v23;
              memcpy_s(v26, v19, &Source, 0x200u);
              if ( !WriteFile(*(HANDLE *)a2, *((LPCVOID *)a2 + 28), *((_DWORD *)a2 + 12), &NumberOfBytesWritten, 0) )
              {
                v27 = GetLastError();
                PartitionInfo = v27;
                if ( v27 > 0 )
                  PartitionInfo = (unsigned __int16)v27 | 0x80070000;
                if ( PartitionInfo >= 0 )
                  PartitionInfo = -2147467259;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                  0xEABu,
                  L"CDiskProtection::VcfFormatFile",
                  L"CBRAEx",
                  L"fSuccess",
                  PartitionInfo);
                if ( IsDebuggerPresent() )
                {
                  DEBUGMSGLEVEL(
                    2u,
                    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                    3755,
                    L"CDiskProtection::VcfFormatFile",
                    L"CBRAEx",
                    L"fSuccess",
                    PartitionInfo);
                  goto LABEL_41;
                }
                v15 = 3755;
                goto LABEL_40;
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  operator delete(*((void **)a2 + 28));
  *((_QWORD *)a2 + 28) = 0;
  DEBUGMSG(L"CDiskProtection::VcfFormatFile - exiting, hr = 0x%08X\n", (unsigned int)PartitionInfo);
  return (unsigned int)PartitionInfo;
}

```

## disassembly

```asm
0x14000c87c  mov     [rsp-8+arg_10], rbx
0x14000c881  mov     [rsp-8+arg_18], rsi
0x14000c886  push    rbp
0x14000c887  push    rdi
0x14000c888  push    r12
0x14000c88a  push    r14
0x14000c88c  push    r15
0x14000c88e  lea     rbp, [rsp-170h]
0x14000c896  sub     rsp, 270h
0x14000c89d  mov     rax, cs:__security_cookie
0x14000c8a4  xor     rax, rsp
0x14000c8a7  mov     [rbp+190h+var_30], rax
0x14000c8ae  xor     eax, eax
0x14000c8b0  mov     rdi, rdx
0x14000c8b3  mov     r15, rcx
0x14000c8b6  mov     dword ptr [rsp+290h+liDistanceToMove+4], eax
0x14000c8ba  mov     r14d, 1FCh
0x14000c8c0  mov     [rsp+290h+var_238], rax
0x14000c8c5  mov     r8d, r14d; Size
0x14000c8c8  mov     [rsp+290h+var_240], rax
0x14000c8cd  xor     edx, edx; Val
0x14000c8cf  mov     [rsp+290h+Source], eax
0x14000c8d3  lea     rcx, [rsp+290h+var_22C]; void *
0x14000c8d8  call    memset_0
0x14000c8dd  lea     rcx, aCdiskprotectio_182; "CDiskProtection::VcfFormatFile\n"
0x14000c8e4  mov     [rsp+290h+NumberOfBytesWritten], 0
0x14000c8ec  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000c8f1  mov     ecx, [rdi+30h]; Size
0x14000c8f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c8f9  mov     [rdi+0E0h], rax
0x14000c900  test    rax, rax
0x14000c903  jnz     loc_14000C99D
0x14000c909  mov     ebx, 8007000Eh
0x14000c90e  lea     r14, aCdiskprotectio_23; "CDiskProtection::VcfFormatFile"
0x14000c915  mov     r15d, 0E23h
0x14000c91b  mov     [rsp+290h+var_268], ebx; int
0x14000c91f  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000c926  mov     r8, r14; unsigned __int16 *
0x14000c929  lea     r12, aPcfdPbsectorbu; "pcfd->pbSectorBuffer"
0x14000c930  mov     edx, r15d; unsigned int
0x14000c933  mov     rcx, rsi; unsigned __int16 *
0x14000c936  mov     [rsp+290h+lpOverlapped], r12; unsigned __int16 *
0x14000c93b  lea     r9, aCpr; "CPR"
0x14000c942  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000c947  call    cs:__imp_IsDebuggerPresent
0x14000c94d  test    eax, eax
0x14000c94f  lea     rax, aCpr; "CPR"
0x14000c956  jz      short loc_14000C987
0x14000c958  mov     [rsp+290h+var_258], ebx
0x14000c95c  mov     r9d, r15d
0x14000c95f  mov     [rsp+290h+var_260], r12
0x14000c964  mov     qword ptr [rsp+290h+var_268], rax
0x14000c969  mov     r8, rsi
0x14000c96c  mov     [rsp+290h+lpOverlapped], r14
0x14000c971  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000c978  mov     ecx, 2; unsigned __int8
0x14000c97d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000c982  jmp     loc_14000CDBB
0x14000c987  mov     dword ptr [rsp+290h+var_260], ebx
0x14000c98b  mov     r8d, r15d
0x14000c98e  mov     qword ptr [rsp+290h+var_268], r12
0x14000c993  mov     [rsp+290h+lpOverlapped], rax
0x14000c998  jmp     loc_14000CDA9
0x14000c99d  lea     r9, [rbp+190h+var_198]; __int64 *
0x14000c9a1  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000c9a4  lea     r8, [rbp+190h+var_1A0]; __int64 *
0x14000c9a8  call    ?VcfGetPartitionInfo@CDiskProtection@@IEAAJPEBUSCacheFileData@1@PEA_J1@Z; CDiskProtection::VcfGetPartitionInfo(CDiskProtection::SCacheFileData const *,__int64 *,__int64 *)
0x14000c9ad  mov     ebx, eax
0x14000c9af  test    eax, eax
0x14000c9b1  js      loc_14000CDBB
0x14000c9b7  mov     rdx, [rdi]; void *
0x14000c9ba  lea     r8, [rdi+8]; struct NTFS_VOLUME_DATA_BUFFER *
0x14000c9be  call    ?GetNtfsVolumeData@CDiskProtection@@IEAAJPEAXPEAUNTFS_VOLUME_DATA_BUFFER@@@Z; CDiskProtection::GetNtfsVolumeData(void *,NTFS_VOLUME_DATA_BUFFER *)
0x14000c9c3  mov     ebx, eax
0x14000c9c5  test    eax, eax
0x14000c9c7  js      loc_14000CDBB
0x14000c9cd  mov     r8d, [rdi+30h]
0x14000c9d1  xor     edx, edx
0x14000c9d3  mov     eax, [rdi+34h]
0x14000c9d6  xor     r9d, r9d; dwMoveMethod
0x14000c9d9  div     r8d
0x14000c9dc  xor     edx, edx
0x14000c9de  mov     dword ptr [rsp+290h+liDistanceToMove], r8d
0x14000c9e3  mov     ecx, eax
0x14000c9e5  mov     [rdi+88h], rcx
0x14000c9ec  mov     rcx, [rdi+90h]
0x14000c9f3  mov     rax, [rcx+8]
0x14000c9f7  mov     [rdi+0A0h], rax
0x14000c9fe  mov     rax, [rdi+68h]
0x14000ca02  inc     rax
0x14000ca05  add     rax, rax
0x14000ca08  mov     eax, [rcx+rax*8]
0x14000ca0b  sub     eax, [rcx+8]
0x14000ca0e  mov     rcx, [rdi]; hFile
0x14000ca11  mov     [rdi+80h], rax
0x14000ca18  mov     rax, [rdi+0B8h]
0x14000ca1f  div     r8
0x14000ca22  mov     rdx, qword ptr [rsp+290h+liDistanceToMove]; liDistanceToMove
0x14000ca27  xor     r8d, r8d; lpNewFilePointer
0x14000ca2a  mov     [rdi+98h], rax
0x14000ca31  call    cs:__imp_SetFilePointerEx
0x14000ca37  test    eax, eax
0x14000ca39  jnz     loc_14000CAC4
0x14000ca3f  call    cs:__imp_GetLastError
0x14000ca45  mov     ebx, eax
0x14000ca47  test    eax, eax
0x14000ca49  jle     short loc_14000CA54
0x14000ca4b  movzx   ebx, ax
0x14000ca4e  or      ebx, 80070000h
0x14000ca54  mov     eax, 80004005h
0x14000ca59  lea     r12, aCbraex; "CBRAEx"
0x14000ca60  test    ebx, ebx
0x14000ca62  lea     r14, aCdiskprotectio_23; "CDiskProtection::VcfFormatFile"
0x14000ca69  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000ca70  mov     r9, r12; unsigned __int16 *
0x14000ca73  cmovns  ebx, eax
0x14000ca76  lea     r15, aFsuccess; "fSuccess"
0x14000ca7d  mov     [rsp+290h+var_268], ebx; int
0x14000ca81  mov     r8, r14; unsigned __int16 *
0x14000ca84  mov     edx, 0E55h; unsigned int
0x14000ca89  mov     [rsp+290h+lpOverlapped], r15; unsigned __int16 *
0x14000ca8e  mov     rcx, rsi; unsigned __int16 *
0x14000ca91  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000ca96  call    cs:__imp_IsDebuggerPresent
0x14000ca9c  test    eax, eax
0x14000ca9e  jz      short loc_14000CAB9
0x14000caa0  mov     [rsp+290h+var_258], ebx
0x14000caa4  mov     r9d, 0E55h
0x14000caaa  mov     [rsp+290h+var_260], r15
0x14000caaf  mov     qword ptr [rsp+290h+var_268], r12
0x14000cab4  jmp     loc_14000C969
0x14000cab9  mov     r8d, 0E55h
0x14000cabf  jmp     loc_14000CD9B
0x14000cac4  lea     r8, [rsp+290h+var_238]; unsigned __int64 *
0x14000cac9  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000cacc  call    ?VcfGetNextBlockNumber@CDiskProtection@@IEAAJPEAUSCacheFileData@1@PEA_K@Z; CDiskProtection::VcfGetNextBlockNumber(CDiskProtection::SCacheFileData *,unsigned __int64 *)
0x14000cad1  mov     ebx, eax
0x14000cad3  test    eax, eax
0x14000cad5  js      loc_14000CDBB
0x14000cadb  lea     r8, [rsp+290h+var_240]; unsigned __int64 *
0x14000cae0  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000cae3  call    ?VcfGetNextBlockNumber@CDiskProtection@@IEAAJPEAUSCacheFileData@1@PEA_K@Z; CDiskProtection::VcfGetNextBlockNumber(CDiskProtection::SCacheFileData *,unsigned __int64 *)
0x14000cae8  mov     ebx, eax
0x14000caea  test    eax, eax
0x14000caec  js      loc_14000CDBB
0x14000caf2  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000caf5  call    ?VcfWriteBaseMapSector@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z; CDiskProtection::VcfWriteBaseMapSector(CDiskProtection::SCacheFileData *)
0x14000cafa  mov     ebx, eax
0x14000cafc  test    eax, eax
0x14000cafe  js      loc_14000CDBB
0x14000cb04  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000cb07  mov     rcx, r15; this
0x14000cb0a  call    ?VcfWriteChunkMapSectors@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z; CDiskProtection::VcfWriteChunkMapSectors(CDiskProtection::SCacheFileData *)
0x14000cb0f  mov     ebx, eax
0x14000cb11  test    eax, eax
0x14000cb13  js      loc_14000CDBB
0x14000cb19  mov     rcx, [rdi]; hFile
0x14000cb1c  xor     r9d, r9d; dwMoveMethod
0x14000cb1f  mov     dword ptr [rsp+290h+liDistanceToMove], 0
0x14000cb27  xor     r8d, r8d; lpNewFilePointer
0x14000cb2a  mov     rdx, qword ptr [rsp+290h+liDistanceToMove]; liDistanceToMove
0x14000cb2f  call    cs:__imp_SetFilePointerEx
0x14000cb35  test    eax, eax
0x14000cb37  jnz     loc_14000CBC2
0x14000cb3d  call    cs:__imp_GetLastError
0x14000cb43  mov     ebx, eax
0x14000cb45  test    eax, eax
0x14000cb47  jle     short loc_14000CB52
0x14000cb49  movzx   ebx, ax
0x14000cb4c  or      ebx, 80070000h
0x14000cb52  mov     eax, 80004005h
0x14000cb57  lea     r12, aCbraex; "CBRAEx"
0x14000cb5e  test    ebx, ebx
0x14000cb60  lea     r14, aCdiskprotectio_23; "CDiskProtection::VcfFormatFile"
0x14000cb67  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000cb6e  mov     r9, r12; unsigned __int16 *
0x14000cb71  cmovns  ebx, eax
0x14000cb74  lea     r15, aFsuccess; "fSuccess"
0x14000cb7b  mov     [rsp+290h+var_268], ebx; int
0x14000cb7f  mov     r8, r14; unsigned __int16 *
0x14000cb82  mov     edx, 0E77h; unsigned int
0x14000cb87  mov     [rsp+290h+lpOverlapped], r15; unsigned __int16 *
0x14000cb8c  mov     rcx, rsi; unsigned __int16 *
0x14000cb8f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000cb94  call    cs:__imp_IsDebuggerPresent
0x14000cb9a  test    eax, eax
0x14000cb9c  jz      short loc_14000CBB7
0x14000cb9e  mov     [rsp+290h+var_258], ebx
0x14000cba2  mov     r9d, 0E77h
0x14000cba8  mov     [rsp+290h+var_260], r15
0x14000cbad  mov     qword ptr [rsp+290h+var_268], r12
0x14000cbb2  jmp     loc_14000C969
0x14000cbb7  mov     r8d, 0E77h
0x14000cbbd  jmp     loc_14000CD9B
0x14000cbc2  mov     eax, [rdi+0CCh]
0x14000cbc8  xor     edx, edx
0x14000cbca  mov     r10d, [rdi+30h]
0x14000cbce  movsd   xmm0, qword ptr [rdi+0D0h]
0x14000cbd6  mov     ecx, [rdi+0C8h]
0x14000cbdc  mov     [rsp+290h+Source], eax
0x14000cbe0  mov     eax, [rdi+0D8h]
0x14000cbe6  mov     [rsp+290h+var_224], eax
0x14000cbea  mov     rax, [rdi+0B8h]
0x14000cbf1  div     r10
0x14000cbf4  xor     edx, edx
0x14000cbf6  movsd   [rsp+290h+var_22C], xmm0
0x14000cbfc  mov     [rbp+190h+var_1F0], rax
0x14000cc00  mov     [rbp+190h+var_184], rax
0x14000cc04  mov     eax, r10d
0x14000cc07  imul    rax, [rsp+290h+var_240]
0x14000cc0d  mov     [rsp+290h+var_220], 0CFCFCFCFh
0x14000cc15  mov     [rbp+190h+var_1D8], rax
0x14000cc19  mov     rax, [rdi+70h]
0x14000cc1d  mov     [rbp+190h+var_1D0], rax
0x14000cc21  mov     rax, [rdi+8]
0x14000cc25  mov     [rbp+190h+var_1B8], rax
0x14000cc29  mov     eax, [rdi+34h]
0x14000cc2c  mov     [rbp+190h+var_1B0], eax
0x14000cc2f  mov     eax, [rdi+38h]
0x14000cc32  mov     [rbp+190h+var_1AC], eax
0x14000cc35  mov     eax, [rdi+3Ch]
0x14000cc38  mov     [rbp+190h+var_1A8], eax
0x14000cc3b  mov     eax, 100000h
0x14000cc40  div     r10d
0x14000cc43  mov     [rsp+290h+var_21C], 11111111h
0x14000cc4b  mov     [rbp+190h+var_15B], eax
0x14000cc4e  mov     [rsp+290h+var_218], 2060000h
0x14000cc57  mov     [rbp+190h+var_210], 0
0x14000cc5f  mov     [rbp+190h+var_1C8], 90h
0x14000cc67  mov     [rbp+190h+var_190], 3E8h
0x14000cc6e  mov     [rbp+190h+var_18C], 1F4h
0x14000cc75  mov     [rbp+190h+var_208], 0FFFFFFFFFFFFFFFFh
0x14000cc7d  mov     [rbp+190h+var_1C0], 1
0x14000cc85  test    ecx, ecx
0x14000cc87  jz      short loc_14000CC9F
0x14000cc89  mov     rax, [rdi+0C0h]
0x14000cc90  mov     [rbp+190h+var_173], rax
0x14000cc94  mov     [rbp+190h+var_16B], 38h ; '8'
0x14000cc9c  mov     [rbp+190h+var_163], ecx
0x14000cc9f  mov     r8d, 0DEADBEEFh
0x14000cca5  lea     r9, [rsp+290h+Source]
0x14000ccaa  movzx   eax, byte ptr [r9]
0x14000ccae  mov     ecx, r8d
0x14000ccb1  xor     rcx, rax
0x14000ccb4  shr     r8d, 8
0x14000ccb8  movzx   eax, cl
0x14000ccbb  inc     r9
0x14000ccbe  lea     rcx, dword_1400D78D0
0x14000ccc5  xor     r8d, [rcx+rax*4]
0x14000ccc9  add     r14d, 0FFFFFFFFh
0x14000cccd  jnz     short loc_14000CCAA
0x14000cccf  mov     rcx, [rdi+0E0h]; Destination
0x14000ccd6  mov     r9d, 200h; SourceSize
0x14000ccdc  mov     [rbp+190h+var_34], r8d
0x14000cce3  mov     rdx, r10; DestinationSize
0x14000cce6  lea     r8, [rsp+290h+Source]; Source
0x14000cceb  call    cs:__imp_memcpy_s
0x14000ccf1  mov     r8d, [rdi+30h]; nNumberOfBytesToWrite
0x14000ccf5  lea     r9, [rsp+290h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000ccfa  mov     rdx, [rdi+0E0h]; lpBuffer
0x14000cd01  mov     rcx, [rdi]; hFile
0x14000cd04  mov     [rsp+290h+lpOverlapped], 0; lpOverlapped
0x14000cd0d  call    cs:__imp_WriteFile
0x14000cd13  test    eax, eax
0x14000cd15  jnz     loc_14000CDBB
0x14000cd1b  call    cs:__imp_GetLastError
0x14000cd21  mov     ebx, eax
0x14000cd23  test    eax, eax
0x14000cd25  jle     short loc_14000CD30
0x14000cd27  movzx   ebx, ax
0x14000cd2a  or      ebx, 80070000h
0x14000cd30  mov     eax, 80004005h
0x14000cd35  lea     r12, aCbraex; "CBRAEx"
0x14000cd3c  test    ebx, ebx
0x14000cd3e  lea     r14, aCdiskprotectio_23; "CDiskProtection::VcfFormatFile"
0x14000cd45  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000cd4c  mov     r9, r12; unsigned __int16 *
0x14000cd4f  cmovns  ebx, eax
0x14000cd52  lea     r15, aFsuccess; "fSuccess"
0x14000cd59  mov     [rsp+290h+var_268], ebx; int
0x14000cd5d  mov     r8, r14; unsigned __int16 *
0x14000cd60  mov     edx, 0EABh; unsigned int
0x14000cd65  mov     [rsp+290h+lpOverlapped], r15; unsigned __int16 *
0x14000cd6a  mov     rcx, rsi; unsigned __int16 *
0x14000cd6d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000cd72  call    cs:__imp_IsDebuggerPresent
0x14000cd78  test    eax, eax
0x14000cd7a  jz      short loc_14000CD95
0x14000cd7c  mov     [rsp+290h+var_258], ebx
0x14000cd80  mov     r9d, 0EABh
0x14000cd86  mov     [rsp+290h+var_260], r15
0x14000cd8b  mov     qword ptr [rsp+290h+var_268], r12
0x14000cd90  jmp     loc_14000C969
0x14000cd95  mov     r8d, 0EABh
0x14000cd9b  mov     dword ptr [rsp+290h+var_260], ebx
0x14000cd9f  mov     qword ptr [rsp+290h+var_268], r15
0x14000cda4  mov     [rsp+290h+lpOverlapped], r12
0x14000cda9  mov     r9, r14
0x14000cdac  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000cdb3  mov     rdx, rsi
  ... truncated ...
```
