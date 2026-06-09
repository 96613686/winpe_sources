# CDiskProtection::VcfWriteChunkMapSectors(CDiskProtection::SCacheFileData *)

- ea: `0x14000dc30`
- end: `0x14000e311`
- name: `?VcfWriteChunkMapSectors@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z`
- size: `1761`
- prototype: `int(CDiskProtection *__hidden this, struct CDiskProtection::SCacheFileData *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000c87c`

## callees

- `0x14000d9c8`
- `0x14000dc30`
- `0x14000e318`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14000e20b`
- `KERNEL32!WriteFile` at `0x14000e20b`
- `KERNEL32!GetLastError` at `0x14000e22e`
- `KERNEL32!GetLastError` at `0x14000e22e`
- `KERNEL32!IsDebuggerPresent` at `0x14000ddcb`
- `KERNEL32!IsDebuggerPresent` at `0x14000df0f`
- `KERNEL32!IsDebuggerPresent` at `0x14000dffd`
- `KERNEL32!IsDebuggerPresent` at `0x14000e0b4`
- `KERNEL32!IsDebuggerPresent` at `0x14000e284`
- `KERNEL32!IsDebuggerPresent` at `0x14000ddcb`
- `KERNEL32!IsDebuggerPresent` at `0x14000df0f`
- `KERNEL32!IsDebuggerPresent` at `0x14000dffd`
- `KERNEL32!IsDebuggerPresent` at `0x14000e0b4`
- `KERNEL32!IsDebuggerPresent` at `0x14000e284`
- `msvcrt!memcpy_s` at `0x14000e1e9`
- `msvcrt!memcpy_s` at `0x14000e1e9`

## string_xrefs

- `0x14000ddb3`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000de01`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000de1e`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000df03`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000df41`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000df5e`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000dfe6`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000e0a0`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000e0e6`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000e103`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000e251`: `CDiskProtection::VcfWriteChunkMapSectors`
- `0x14000dd19`: `CDiskProtection::VcfWriteChunkMapSectors - Bytes Per Sector 0x%8.8lx\n`
- `0x14000dd28`: `CDiskProtection::VcfWriteChunkMapSectors - Bytes Per Cluster 0x%8.8lx\n`
- `0x14000dd3b`: `CDiskProtection::VcfWriteChunkMapSectors - Starting VCN 0x%16.16I64x\n`
- `0x14000de4f`: `CDiskProtection::VcfWriteChunkMapSectors - LCN 0x%16.16I64x\n`
- `0x14000de88`: `CDiskProtection::VcfWriteChunkMapSectors - Next VCN 0x%16.16I64x\n`
- `0x14000de9e`: `CDiskProtection::VcfWriteChunkMapSectors - OffsetToChunkBase 0x%16.16I64x\n`
- `0x14000deaf`: `CDiskProtection::VcfWriteChunkMapSectors - SectorsInChunk 0x%8.8lx\n`

## pseudocode

```c
__int64 __fastcall CDiskProtection::VcfWriteChunkMapSectors(
        CDiskProtection *this,
        struct CDiskProtection::SCacheFileData *a2)
{
  _DWORD *v2; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // r15
  unsigned int v6; // ebx
  unsigned __int64 v7; // rsi
  DWORD *v8; // r12
  const unsigned __int16 *v9; // r9
  unsigned int *v10; // rdx
  __int64 v11; // r13
  __int64 v12; // r14
  __int64 v13; // rbx
  unsigned int v14; // ecx
  DWORD v15; // r8d
  __int64 v16; // r13
  __int64 v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // r9
  DWORD v20; // r10d
  __int64 v21; // r11
  __int64 v22; // rax
  CDiskProtection *v23; // rcx
  int v24; // eax
  unsigned int v25; // edx
  int *p_Source; // r8
  int v27; // r9d
  __int64 v28; // rax
  void *v29; // rcx
  __int64 v30; // r14
  signed int LastError; // eax
  __int64 v33; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v36; // [rsp+50h] [rbp-B0h]
  __int64 v37; // [rsp+58h] [rbp-A8h]
  __int64 v38; // [rsp+60h] [rbp-A0h]
  CDiskProtection *v39; // [rsp+68h] [rbp-98h]
  int Source; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  _DWORD v43[3]; // [rsp+7Ch] [rbp-84h]
  _QWORD v44[60]; // [rsp+88h] [rbp-78h]
  unsigned int v45; // [rsp+26Ch] [rbp+16Ch]

  v2 = (_DWORD *)*((_QWORD *)a2 + 18);
  NumberOfBytesWritten = 0;
  v39 = this;
  v4 = *v2 / 0x1Eu;
  v5 = v4 + 1;
  if ( *v2 == 30 * (_DWORD)v4 )
    v5 = *v2 / 0x1Eu;
  if ( v5 < 0x36 )
  {
    v7 = 0;
    v34 = 0;
    v6 = 0;
    v38 = 0;
    if ( v5 )
    {
      v8 = (DWORD *)((char *)a2 + 48);
      while ( 1 )
      {
        memset_0(&v41, 0, 0x1FCu);
        v10 = (unsigned int *)*((_QWORD *)a2 + 18);
        Source = -808464433;
        v41 = 858993459;
        *(_QWORD *)((char *)&v44[58] + 4) = 1;
        if ( v7 < *v10 )
          break;
LABEL_38:
        v25 = -559038737;
        p_Source = &Source;
        v27 = 508;
        do
        {
          v28 = (unsigned __int8)(*(_BYTE *)p_Source ^ v25);
          p_Source = (int *)((char *)p_Source + 1);
          v25 = dword_1400D78D0[v28] ^ (v25 >> 8);
          --v27;
        }
        while ( v27 );
        v29 = (void *)*((_QWORD *)a2 + 28);
        v30 = v38;
        v45 = v25;
        memcpy_s(v29, *v8, &Source, 0x200u);
        if ( !WriteFile(*(HANDLE *)a2, *((LPCVOID *)a2 + 28), *v8, &NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          if ( (v6 & 0x80000000) == 0 )
            v6 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            0xDF9u,
            L"CDiskProtection::VcfWriteChunkMapSectors",
            L"CBRAEx",
            L"fSuccess",
            v6);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3577,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"CBRAEx",
              L"fSuccess",
              v6);
          }
          else
          {
            LODWORD(v33) = v6;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3577,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"CBRAEx",
              L"fSuccess",
              v33);
          }
          return v6;
        }
        ++v7;
        v38 = v30 + 1;
        if ( v30 + 1 >= v5 )
          return v6;
      }
      v11 = 0;
      v37 = 0;
      while ( 1 )
      {
        ++v42;
        if ( v7 )
        {
          v13 = 16 * v7;
          v12 = *(_QWORD *)&v10[4 * v7 + 4] - *(_QWORD *)&v10[4 * v7];
        }
        else
        {
          DEBUGMSG(L"CDiskProtection::VcfWriteChunkMapSectors - Bytes Per Sector 0x%8.8lx\n", *v8);
          DEBUGMSG(
            L"CDiskProtection::VcfWriteChunkMapSectors - Bytes Per Cluster 0x%8.8lx\n",
            *((unsigned int *)a2 + 13));
          DEBUGMSG(
            L"CDiskProtection::VcfWriteChunkMapSectors - Starting VCN 0x%16.16I64x\n",
            *(_QWORD *)(*((_QWORD *)a2 + 18) + 8LL));
          v10 = (unsigned int *)*((_QWORD *)a2 + 18);
          v12 = *((_QWORD *)v10 + 2) - *((_QWORD *)v10 + 1);
          v13 = 0;
        }
        v14 = *((_DWORD *)a2 + 13);
        v15 = *v8;
        v36 = *(_QWORD *)&v10[(unsigned __int64)v13 / 4 + 6] * (unsigned __int64)v14 / *v8;
        if ( v12 * (unsigned __int64)(v14 / v15) >= 0xFFFFFFFF )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            0xDABu,
            L"CDiskProtection::VcfWriteChunkMapSectors",
            v9,
            L"(numberOfClustersInRun * (pcfd->ntfsVolumeData.BytesPerCluster / pcfd->ntfsVolumeData.BytesPerSector)) < 0xffffffffULL");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3499,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"ASSERT",
              L"(numberOfClustersInRun * (pcfd->ntfsVolumeData.BytesPerCluster / pcfd->ntfsVolumeData.BytesPerSector)) < 0xffffffffULL");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3499,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"ASSERT",
              L"(numberOfClustersInRun * (pcfd->ntfsVolumeData.BytesPerCluster / pcfd->ntfsVolumeData.BytesPerSector)) < 0xffffffffULL");
        }
        v16 = 2 * v11;
        *(_QWORD *)&v43[2 * v16] = v36;
        v17 = *((_QWORD *)a2 + 18);
        v43[2 * v16 + 2] = v12 * (*((_DWORD *)a2 + 13) / *v8);
        DEBUGMSG(L"CDiskProtection::VcfWriteChunkMapSectors - LCN 0x%16.16I64x\n", *(_QWORD *)(v13 + v17 + 24));
        DEBUGMSG(
          L"CDiskProtection::VcfWriteChunkMapSectors - Next VCN 0x%16.16I64x\n",
          *(_QWORD *)(*((_QWORD *)a2 + 18) + v13 + 16));
        DEBUGMSG(L"CDiskProtection::VcfWriteChunkMapSectors - OffsetToChunkBase 0x%16.16I64x\n", v36);
        DEBUGMSG(
          L"CDiskProtection::VcfWriteChunkMapSectors - SectorsInChunk 0x%8.8lx\n",
          (unsigned int)v43[2 * v16 + 2]);
        v18 = *((_QWORD *)a2 + 18);
        v19 = (const unsigned __int16 *)*((unsigned int *)a2 + 13);
        v20 = *v8;
        v21 = *(_QWORD *)&v43[2 * v16];
        if ( v21 * *v8 != *(_QWORD *)(v18 + v13 + 24) * (_QWORD)v19 )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            0xDBDu,
            L"CDiskProtection::VcfWriteChunkMapSectors",
            v19,
            L"chunkMapSector.u.Chunks[idxChunk].OffsetToChunkBase * pcfd->ntfsVolumeData.BytesPerSector == (ULONG64) (pcfd"
             "->pRetrievalPointers->Extents[idxExtent].Lcn.QuadPart * pcfd->ntfsVolumeData.BytesPerCluster)");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3517,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"ASSERT",
              L"chunkMapSector.u.Chunks[idxChunk].OffsetToChunkBase * pcfd->ntfsVolumeData.BytesPerSector == (ULONG64) (pc"
               "fd->pRetrievalPointers->Extents[idxExtent].Lcn.QuadPart * pcfd->ntfsVolumeData.BytesPerCluster)");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3517,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"ASSERT",
              L"chunkMapSector.u.Chunks[idxChunk].OffsetToChunkBase * pcfd->ntfsVolumeData.BytesPerSector == (ULONG64) (pc"
               "fd->pRetrievalPointers->Extents[idxExtent].Lcn.QuadPart * pcfd->ntfsVolumeData.BytesPerCluster)");
          v18 = *((_QWORD *)a2 + 18);
          v19 = (const unsigned __int16 *)*((unsigned int *)a2 + 13);
          v21 = *(_QWORD *)&v43[2 * v16];
          v20 = *v8;
        }
        v22 = 8;
        if ( v7 )
          v22 = v13;
        v23 = (CDiskProtection *)(v20 * (v21 + (unsigned int)v43[2 * v16 + 2]));
        if ( v23 != (CDiskProtection *)((unsigned int)v19
                                      * (*(_QWORD *)(v13 + v18 + 16)
                                       + *(_QWORD *)(v13 + v18 + 24)
                                       - *(_QWORD *)(v22 + v18))) )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            0xDC7u,
            L"CDiskProtection::VcfWriteChunkMapSectors",
            v19,
            L"(chunkMapSector.u.Chunks[idxChunk].OffsetToChunkBase + chunkMapSector.u.Chunks[idxChunk].SectorsInChunk) * p"
             "cfd->ntfsVolumeData.BytesPerSector == (ULONG64) ((pcfd->pRetrievalPointers->Extents[idxExtent].Lcn.QuadPart"
             " + pcfd->pRetrievalPointers->Extents[idxExtent].NextVcn.QuadPart - (idxExtent ? (pcfd->pRetrievalPointers->"
             "Extents[idxExtent - 1].NextVcn.QuadPart) : pcfd->pRetrievalPointers->StartingVcn.QuadPart)) * pcfd->ntfsVol"
             "umeData.BytesPerCluster)");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3527,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"ASSERT",
              L"(chunkMapSector.u.Chunks[idxChunk].OffsetToChunkBase + chunkMapSector.u.Chunks[idxChunk].SectorsInChunk) *"
               " pcfd->ntfsVolumeData.BytesPerSector == (ULONG64) ((pcfd->pRetrievalPointers->Extents[idxExtent].Lcn.Quad"
               "Part + pcfd->pRetrievalPointers->Extents[idxExtent].NextVcn.QuadPart - (idxExtent ? (pcfd->pRetrievalPoin"
               "ters->Extents[idxExtent - 1].NextVcn.QuadPart) : pcfd->pRetrievalPointers->StartingVcn.QuadPart)) * pcfd-"
               ">ntfsVolumeData.BytesPerCluster)");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              3527,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              L"ASSERT",
              L"(chunkMapSector.u.Chunks[idxChunk].OffsetToChunkBase + chunkMapSector.u.Chunks[idxChunk].SectorsInChunk) *"
               " pcfd->ntfsVolumeData.BytesPerSector == (ULONG64) ((pcfd->pRetrievalPointers->Extents[idxExtent].Lcn.Quad"
               "Part + pcfd->pRetrievalPointers->Extents[idxExtent].NextVcn.QuadPart - (idxExtent ? (pcfd->pRetrievalPoin"
               "ters->Extents[idxExtent - 1].NextVcn.QuadPart) : pcfd->pRetrievalPointers->StartingVcn.QuadPart)) * pcfd-"
               ">ntfsVolumeData.BytesPerCluster)");
        }
        if ( v38 || v37 )
        {
          LODWORD(v44[v16]) = 1;
          v24 = CDiskProtection::VcfWriteChunkHeader(v23, a2, v34);
        }
        else
        {
          LODWORD(v44[0]) = 144;
          if ( v34 )
          {
            LOGASSERT(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0xDCEu,
              L"CDiskProtection::VcfWriteChunkMapSectors",
              v19,
              L"nVcfChunkHeaderOffset == 0");
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                3534,
                L"CDiskProtection::VcfWriteChunkMapSectors",
                L"ASSERT",
                L"nVcfChunkHeaderOffset == 0");
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                3534,
                L"CDiskProtection::VcfWriteChunkMapSectors",
                L"ASSERT",
                L"nVcfChunkHeaderOffset == 0");
          }
          v24 = CDiskProtection::VcfWriteTrackedRegKeys(v39, a2, v36);
        }
        v6 = v24;
        if ( v24 < 0 )
          break;
        v34 += (unsigned int)v43[2 * v16 + 2];
        v11 = v37 + 1;
        v37 = v11;
        if ( v11 != 30 )
        {
          v10 = (unsigned int *)*((_QWORD *)a2 + 18);
          if ( ++v7 < *v10 )
            continue;
        }
        goto LABEL_38;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024594;
  }
  return v6;
}

```

## disassembly

```asm
0x14000dc30  mov     [rsp-8+arg_10], rbx
0x14000dc35  push    rbp
0x14000dc36  push    rsi
0x14000dc37  push    rdi
0x14000dc38  push    r12
0x14000dc3a  push    r13
0x14000dc3c  push    r14
0x14000dc3e  push    r15
0x14000dc40  lea     rbp, [rsp-180h]
0x14000dc48  sub     rsp, 280h
0x14000dc4f  mov     rax, cs:__security_cookie
0x14000dc56  xor     rax, rsp
0x14000dc59  mov     [rbp+1B0h+var_40], rax
0x14000dc60  mov     rax, [rdx+90h]
0x14000dc67  mov     rdi, rdx
0x14000dc6a  mov     [rsp+2B0h+NumberOfBytesWritten], 0
0x14000dc72  mov     [rsp+2B0h+var_248], rcx
0x14000dc77  mov     r8d, [rax]
0x14000dc7a  mov     eax, 88888889h
0x14000dc7f  mul     r8d
0x14000dc82  shr     edx, 4
0x14000dc85  imul    eax, edx, 1Eh
0x14000dc88  mov     ecx, edx
0x14000dc8a  lea     r15, [rdx+1]
0x14000dc8e  cmp     r8d, eax
0x14000dc91  cmovz   r15, rcx
0x14000dc95  cmp     r15, 36h ; '6'
0x14000dc99  jb      short loc_14000DCA5
0x14000dc9b  mov     ebx, 8007012Eh
0x14000dca0  jmp     loc_14000E2E5
0x14000dca5  xor     eax, eax
0x14000dca7  xor     r14d, r14d
0x14000dcaa  xor     esi, esi
0x14000dcac  mov     [rsp+2B0h+var_270], rax
0x14000dcb1  xor     ebx, ebx
0x14000dcb3  mov     [rsp+2B0h+var_250], r14
0x14000dcb8  test    r15, r15
0x14000dcbb  jz      loc_14000E2E5
0x14000dcc1  lea     r12, [rdi+30h]
0x14000dcc5  xor     edx, edx; Val
0x14000dcc7  lea     rcx, [rsp+2B0h+var_23C]; void *
0x14000dccc  mov     r8d, 1FCh; Size
0x14000dcd2  call    memset_0
0x14000dcd7  mov     rdx, [rdi+90h]
0x14000dcde  mov     [rsp+2B0h+Source], 0CFCFCFCFh
0x14000dce6  mov     [rsp+2B0h+var_23C], 33333333h
0x14000dcee  mov     [rbp+1B0h+var_54], 1
0x14000dcf9  mov     eax, [rdx]
0x14000dcfb  cmp     rsi, rax
0x14000dcfe  jnb     loc_14000E191
0x14000dd04  xor     r13d, r13d
0x14000dd07  mov     [rsp+2B0h+var_258], r13
0x14000dd0c  inc     [rsp+2B0h+var_238]
0x14000dd10  test    rsi, rsi
0x14000dd13  jnz     short loc_14000DD63
0x14000dd15  mov     edx, [r12]
0x14000dd19  lea     rcx, aCdiskprotectio_89; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000dd20  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000dd25  mov     edx, [rdi+34h]
0x14000dd28  lea     rcx, aCdiskprotectio_46; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000dd2f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000dd34  mov     rdx, [rdi+90h]
0x14000dd3b  lea     rcx, aCdiskprotectio_64; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000dd42  mov     rdx, [rdx+8]
0x14000dd46  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000dd4b  mov     rdx, [rdi+90h]
0x14000dd52  mov     rbx, rsi
0x14000dd55  mov     r14, [rdx+10h]
0x14000dd59  sub     r14, [rdx+8]
0x14000dd5d  shl     rbx, 4
0x14000dd61  jmp     short loc_14000DD73
0x14000dd63  mov     rbx, rsi
0x14000dd66  shl     rbx, 4
0x14000dd6a  mov     r14, [rbx+rdx+10h]
0x14000dd6f  sub     r14, [rbx+rdx]
0x14000dd73  mov     ecx, [rdi+34h]
0x14000dd76  mov     r8d, [r12]
0x14000dd7a  mov     eax, ecx
0x14000dd7c  imul    rax, [rbx+rdx+18h]
0x14000dd82  xor     edx, edx
0x14000dd84  div     r8
0x14000dd87  xor     edx, edx
0x14000dd89  mov     [rsp+2B0h+var_260], rax
0x14000dd8e  mov     eax, ecx
0x14000dd90  div     r8d
0x14000dd93  mov     ecx, eax
0x14000dd95  mov     eax, 0FFFFFFFFh
0x14000dd9a  imul    rcx, r14
0x14000dd9e  cmp     rcx, rax
0x14000dda1  jb      loc_14000DE4A
0x14000dda7  lea     rax, aNumberofcluste; "(numberOfClustersInRun * (pcfd->ntfsVol"...
0x14000ddae  mov     edx, 0DABh; unsigned int
0x14000ddb3  lea     r8, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000ddba  mov     [rsp+2B0h+lpOverlapped], rax; unsigned __int16 *
0x14000ddbf  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000ddc6  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000ddcb  call    cs:__imp_IsDebuggerPresent
0x14000ddd1  test    eax, eax
0x14000ddd3  lea     rax, aNumberofcluste; "(numberOfClustersInRun * (pcfd->ntfsVol"...
0x14000ddda  jz      short loc_14000DE19
0x14000dddc  mov     [rsp+2B0h+var_280], rax
0x14000dde1  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000dde8  lea     rax, aAssert; "ASSERT"
0x14000ddef  mov     r9d, 0DABh
0x14000ddf5  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000ddfa  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000de01  lea     rax, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000de08  mov     ecx, 2; unsigned __int8
0x14000de0d  mov     [rsp+2B0h+lpOverlapped], rax
0x14000de12  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000de17  jmp     short loc_14000DE4A
0x14000de19  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000de1e  lea     r9, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000de25  lea     rax, aAssert; "ASSERT"
0x14000de2c  mov     r8d, 0DABh
0x14000de32  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000de39  mov     [rsp+2B0h+lpOverlapped], rax
0x14000de3e  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000de45  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000de4a  mov     rax, [rsp+2B0h+var_260]
0x14000de4f  lea     rcx, aCdiskprotectio_177; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000de56  xor     edx, edx
0x14000de58  add     r13, r13
0x14000de5b  mov     [rsp+r13*8+2B0h+var_234], rax
0x14000de60  mov     eax, [rdi+34h]
0x14000de63  div     dword ptr [r12]
0x14000de67  mov     rdx, [rdi+90h]
0x14000de6e  imul    eax, r14d
0x14000de72  mov     [rbp+r13*8+1B0h+var_22C], eax
0x14000de77  mov     rdx, [rbx+rdx+18h]
0x14000de7c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000de81  mov     rdx, [rdi+90h]
0x14000de88  lea     rcx, aCdiskprotectio_79; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000de8f  mov     rdx, [rdx+rbx+10h]
0x14000de94  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000de99  mov     rdx, [rsp+2B0h+var_260]
0x14000de9e  lea     rcx, aCdiskprotectio_106; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000dea5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000deaa  mov     edx, [rbp+r13*8+1B0h+var_22C]
0x14000deaf  lea     rcx, aCdiskprotectio_88; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000deb6  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000debb  mov     r8, [rdi+90h]
0x14000dec2  mov     r9d, [rdi+34h]; unsigned __int16 *
0x14000dec6  mov     r10d, [r12]
0x14000deca  mov     ecx, r9d
0x14000decd  mov     r11, [rsp+r13*8+2B0h+var_234]
0x14000ded2  mov     eax, r10d
0x14000ded5  imul    rcx, [r8+rbx+18h]
0x14000dedb  imul    rax, r11
0x14000dedf  cmp     rax, rcx
0x14000dee2  jz      loc_14000DF9A
0x14000dee8  lea     rax, aChunkmapsector; "chunkMapSector.u.Chunks[idxChunk].Offse"...
0x14000deef  mov     edx, 0DBDh; unsigned int
0x14000def4  lea     r14, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000defb  mov     [rsp+2B0h+lpOverlapped], rax; unsigned __int16 *
0x14000df00  mov     rcx, r14; unsigned __int16 *
0x14000df03  lea     r8, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000df0a  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000df0f  call    cs:__imp_IsDebuggerPresent
0x14000df15  test    eax, eax
0x14000df17  lea     rax, aChunkmapsector; "chunkMapSector.u.Chunks[idxChunk].Offse"...
0x14000df1e  jz      short loc_14000DF59
0x14000df20  mov     [rsp+2B0h+var_280], rax
0x14000df25  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000df2c  lea     rax, aAssert; "ASSERT"
0x14000df33  mov     r9d, 0DBDh
0x14000df39  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000df3e  mov     r8, r14
0x14000df41  lea     rax, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000df48  mov     ecx, 2; unsigned __int8
0x14000df4d  mov     [rsp+2B0h+lpOverlapped], rax
0x14000df52  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000df57  jmp     short loc_14000DF86
0x14000df59  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000df5e  lea     r9, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000df65  lea     rax, aAssert; "ASSERT"
0x14000df6c  mov     r8d, 0DBDh
0x14000df72  mov     rdx, r14
0x14000df75  mov     [rsp+2B0h+lpOverlapped], rax
0x14000df7a  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000df81  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000df86  mov     r8, [rdi+90h]
0x14000df8d  mov     r9d, [rdi+34h]; unsigned __int16 *
0x14000df91  mov     r11, [rsp+r13*8+2B0h+var_234]
0x14000df96  mov     r10d, [r12]
0x14000df9a  mov     rdx, [rbx+r8+18h]
0x14000df9f  test    rsi, rsi
0x14000dfa2  mov     ecx, [rbp+r13*8+1B0h+var_22C]
0x14000dfa7  mov     eax, 8
0x14000dfac  cmovnz  rax, rbx
0x14000dfb0  add     rcx, r11
0x14000dfb3  sub     rdx, [rax+r8]
0x14000dfb7  add     rdx, [rbx+r8+10h]
0x14000dfbc  lea     rbx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000dfc3  mov     eax, r9d
0x14000dfc6  imul    rdx, rax
0x14000dfca  mov     eax, r10d
0x14000dfcd  imul    rcx, rax
0x14000dfd1  cmp     rcx, rdx
0x14000dfd4  jz      loc_14000E069
0x14000dfda  lea     rax, aChunkmapsector_0; "(chunkMapSector.u.Chunks[idxChunk].Offs"...
0x14000dfe1  mov     edx, 0DC7h; unsigned int
0x14000dfe6  lea     r14, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000dfed  mov     [rsp+2B0h+lpOverlapped], rax; unsigned __int16 *
0x14000dff2  mov     r8, r14; unsigned __int16 *
0x14000dff5  mov     rcx, rbx; unsigned __int16 *
0x14000dff8  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000dffd  call    cs:__imp_IsDebuggerPresent
0x14000e003  test    eax, eax
0x14000e005  lea     rax, aChunkmapsector_0; "(chunkMapSector.u.Chunks[idxChunk].Offs"...
0x14000e00c  jz      short loc_14000E040
0x14000e00e  mov     [rsp+2B0h+var_280], rax
0x14000e013  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000e01a  lea     rax, aAssert; "ASSERT"
0x14000e021  mov     r9d, 0DC7h
0x14000e027  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000e02c  mov     r8, rbx
0x14000e02f  mov     ecx, 2; unsigned __int8
0x14000e034  mov     [rsp+2B0h+lpOverlapped], r14
0x14000e039  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000e03e  jmp     short loc_14000E069
0x14000e040  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000e045  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000e04c  lea     rax, aAssert; "ASSERT"
0x14000e053  mov     r9, r14
0x14000e056  mov     r8d, 0DC7h
0x14000e05c  mov     [rsp+2B0h+lpOverlapped], rax
0x14000e061  mov     rdx, rbx
0x14000e064  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000e069  cmp     [rsp+2B0h+var_250], 0
0x14000e06f  jnz     loc_14000E13F
0x14000e075  cmp     [rsp+2B0h+var_258], 0
0x14000e07b  jnz     loc_14000E13F
0x14000e081  cmp     [rsp+2B0h+var_270], 0
0x14000e087  mov     [rbp+1B0h+var_228], 90h
0x14000e08e  jz      loc_14000E12B
0x14000e094  lea     rax, aNvcfchunkheade; "nVcfChunkHeaderOffset == 0"
0x14000e09b  mov     edx, 0DCEh; unsigned int
0x14000e0a0  lea     r8, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000e0a7  mov     [rsp+2B0h+lpOverlapped], rax; unsigned __int16 *
0x14000e0ac  mov     rcx, rbx; unsigned __int16 *
0x14000e0af  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000e0b4  call    cs:__imp_IsDebuggerPresent
0x14000e0ba  test    eax, eax
0x14000e0bc  lea     rax, aNvcfchunkheade; "nVcfChunkHeaderOffset == 0"
0x14000e0c3  jz      short loc_14000E0FE
0x14000e0c5  mov     [rsp+2B0h+var_280], rax
0x14000e0ca  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000e0d1  lea     rax, aAssert; "ASSERT"
0x14000e0d8  mov     r9d, 0DCEh
0x14000e0de  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000e0e3  mov     r8, rbx
0x14000e0e6  lea     rax, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000e0ed  mov     ecx, 2; unsigned __int8
0x14000e0f2  mov     [rsp+2B0h+lpOverlapped], rax
0x14000e0f7  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000e0fc  jmp     short loc_14000E12B
0x14000e0fe  mov     qword ptr [rsp+2B0h+var_288], rax
0x14000e103  lea     r9, aCdiskprotectio_99; "CDiskProtection::VcfWriteChunkMapSector"...
0x14000e10a  lea     rax, aAssert; "ASSERT"
0x14000e111  mov     r8d, 0DCEh
0x14000e117  mov     rdx, rbx
0x14000e11a  mov     [rsp+2B0h+lpOverlapped], rax
0x14000e11f  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000e126  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000e12b  mov     r8, [rsp+2B0h+var_260]; unsigned __int64
0x14000e130  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000e133  mov     rcx, [rsp+2B0h+var_248]; this
0x14000e138  call    ?VcfWriteTrackedRegKeys@CDiskProtection@@IEAAJPEAUSCacheFileData@1@_K@Z; CDiskProtection::VcfWriteTrackedRegKeys(CDiskProtection::SCacheFileData *,unsigned __int64)
0x14000e13d  jmp     short loc_14000E155
0x14000e13f  mov     r8, [rsp+2B0h+var_270]; unsigned __int64
0x14000e144  mov     rdx, rdi; struct CDiskProtection::SCacheFileData *
0x14000e147  mov     [rbp+r13*8+1B0h+var_228], 1
0x14000e150  call    ?VcfWriteChunkHeader@CDiskProtection@@IEAAJPEAUSCacheFileData@1@_K@Z; CDiskProtection::VcfWriteChunkHeader(CDiskProtection::SCacheFileData *,unsigned __int64)
0x14000e155  mov     ebx, eax
0x14000e157  test    eax, eax
0x14000e159  js      loc_14000E2E5
0x14000e15f  mov     eax, [rbp+r13*8+1B0h+var_22C]
0x14000e164  mov     r13, [rsp+2B0h+var_258]
0x14000e169  add     [rsp+2B0h+var_270], rax
0x14000e16e  inc     r13
0x14000e171  mov     [rsp+2B0h+var_258], r13
0x14000e176  cmp     r13, 1Eh
0x14000e17a  jz      short loc_14000E191
0x14000e17c  mov     rdx, [rdi+90h]
0x14000e183  inc     rsi
0x14000e186  mov     eax, [rdx]
0x14000e188  cmp     rsi, rax
0x14000e18b  jb      loc_14000DD0C
0x14000e191  mov     edx, 0DEADBEEFh
0x14000e196  lea     r8, [rsp+2B0h+Source]
0x14000e19b  mov     r9d, 1FCh
0x14000e1a1  mov     r14d, 0FFFFFFFFh
0x14000e1a7  movzx   eax, byte ptr [r8]
0x14000e1ab  mov     ecx, edx
0x14000e1ad  xor     rcx, rax
0x14000e1b0  shr     edx, 8
0x14000e1b3  movzx   eax, cl
0x14000e1b6  inc     r8
0x14000e1b9  lea     rcx, dword_1400D78D0
  ... truncated ...
```
