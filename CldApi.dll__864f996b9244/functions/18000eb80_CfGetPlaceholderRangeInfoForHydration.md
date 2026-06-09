# CfGetPlaceholderRangeInfoForHydration

- ea: `0x18000eb80`
- end: `0x18000f322`
- name: `CfGetPlaceholderRangeInfoForHydration`
- size: `1954`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800022ee`
- `0x18000b218`
- `0x18000b6c8`
- `0x18000eb80`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ecde`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed6f`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee01`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee93`
- `ntdll!RtlNtStatusToDosError` at `0x18000ef25`
- `ntdll!RtlNtStatusToDosError` at `0x18000efc3`
- `ntdll!RtlNtStatusToDosError` at `0x18000f05c`
- `ntdll!RtlNtStatusToDosError` at `0x18000f177`
- `ntdll!RtlNtStatusToDosError` at `0x18000f21a`
- `ntdll!RtlNtStatusToDosError` at `0x18000ecde`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed6f`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee01`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee93`
- `ntdll!RtlNtStatusToDosError` at `0x18000ef25`
- `ntdll!RtlNtStatusToDosError` at `0x18000efc3`
- `ntdll!RtlNtStatusToDosError` at `0x18000f05c`
- `ntdll!RtlNtStatusToDosError` at `0x18000f177`
- `ntdll!RtlNtStatusToDosError` at `0x18000f21a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000ebc8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000ebc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ec28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ec28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f305`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f305`
- `FLTLIB!FilterSendMessage` at `0x18000f276`
- `FLTLIB!FilterSendMessage` at `0x18000f276`

## string_xrefs

- `0x18000ed8f`: `SetCldMsgCommand failed`

## pseudocode

```c
__int64 __fastcall CfGetPlaceholderRangeInfoForHydration(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        _DWORD *a9)
{
  __int64 v12; // r13
  int v13; // r14d
  _DWORD *v14; // r15
  const wchar_t *v15; // rax
  HANDLE ProcessHeap; // rax
  NTSTATUS v17; // r12d
  NTSTATUS v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // ecx
  signed int v22; // eax
  NTSTATUS v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // rax
  signed int v26; // eax
  NTSTATUS v27; // ecx
  __int64 v28; // rcx
  __int64 v29; // rax
  signed int v30; // eax
  NTSTATUS v31; // ecx
  __int64 v32; // rcx
  __int64 v33; // rax
  signed int v34; // eax
  NTSTATUS v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rax
  signed int v38; // eax
  NTSTATUS v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // ecx
  signed int v43; // eax
  NTSTATUS v44; // ecx
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rax
  signed int v49; // eax
  __int64 v50; // rcx
  unsigned int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  NTSTATUS v54; // ecx
  __int64 v55; // rcx
  unsigned int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rax
  signed int v59; // eax
  __int64 v60; // rcx
  unsigned int v61; // eax
  __int64 v62; // rcx
  int v63; // eax
  signed int v64; // eax
  HANDLE v65; // rax
  int v67; // [rsp+40h] [rbp-61h] BYREF
  const wchar_t *v68; // [rsp+48h] [rbp-59h]
  __int64 v69; // [rsp+50h] [rbp-51h]
  __int64 v70; // [rsp+58h] [rbp-49h]
  __int64 v71; // [rsp+60h] [rbp-41h]
  int v72; // [rsp+68h] [rbp-39h]
  int OutBuffer; // [rsp+F0h] [rbp+4Fh] BYREF
  DWORD BytesReturned; // [rsp+F8h] [rbp+57h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+100h] [rbp+5Fh] BYREF
  int v76; // [rsp+108h] [rbp+67h]

  v76 = a4;
  BytesReturned = 0;
  OutBuffer = 0;
  memset_0(&v67, 0, 0x58u);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v12 = CfpReferenceSyncRoot(a1);
  v13 = v12 == 0 ? 0x57 : 0;
  if ( !v12 )
    v13 |= 0x80070000;
  if ( v13 <= -1 )
  {
    v14 = 0;
    v15 = L"Syncroot not found with ConnectionKey";
    goto LABEL_115;
  }
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 8u, 0x108u);
  v13 = v14 == 0 ? 8 : 0;
  if ( !v14 )
    v13 |= 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"Memory alloc failed for CldCmdPlaceholderRangeInfo";
    goto LABEL_115;
  }
  *(_QWORD *)v14 = 1886219331;
  v14[2] = 200;
  v14[3] = 1507328;
  memset_0(v14 + 4, 0, 0xB8u);
  v17 = -1073741811;
  if ( *((_WORD *)v14 + 7) )
  {
    v19 = (unsigned int)v14[2];
    if ( ((v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0x108 )
    {
      v21 = (v19 + 3) & 0xFFFFFFFC;
      v20 = v21;
      v14[2] = v21;
      v14[5] = v21;
      v18 = 0;
      v14[4] = 65543;
      *((_BYTE *)v14 + v20) = 1;
      ++v14[2];
    }
    else
    {
      v18 = -1073741789;
    }
  }
  else
  {
    v18 = -1073741811;
  }
  v22 = RtlNtStatusToDosError(v18);
  v13 = v22;
  if ( v22 > 0 )
    v13 = (unsigned __int16)v22 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetVersion failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 1u )
  {
    v24 = (unsigned int)v14[2];
    if ( ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0x108 )
    {
      v25 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
      v14[2] = v25;
      if ( *((_WORD *)v14 + 12) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[6] = 131080;
      v23 = 0;
      v14[7] = v25;
      *(_WORD *)((char *)v14 + v25) = -12287;
      v14[2] += 2;
    }
    else
    {
      v23 = -1073741789;
    }
  }
  else
  {
    v23 = -1073741811;
  }
  v26 = RtlNtStatusToDosError(v23);
  v13 = v26;
  if ( v26 > 0 )
    v13 = (unsigned __int16)v26 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldMsgCommand failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 4u )
  {
    v28 = (unsigned int)v14[2];
    if ( ((v28 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v29 = ((_DWORD)v28 + 3) & 0xFFFFFFFC;
      v14[2] = v29;
      if ( *((_WORD *)v14 + 24) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[12] = 524294;
      v27 = 0;
      v14[13] = v29;
      *(_QWORD *)((char *)v14 + v29) = a1;
      v14[2] += 8;
    }
    else
    {
      v27 = -1073741789;
    }
  }
  else
  {
    v27 = -1073741811;
  }
  v30 = RtlNtStatusToDosError(v27);
  v13 = v30;
  if ( v30 > 0 )
    v13 = (unsigned __int16)v30 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldDsMsgSyncRootKey failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 7u )
  {
    v32 = (unsigned int)v14[2];
    if ( ((v32 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v33 = ((_DWORD)v32 + 3) & 0xFFFFFFFC;
      v14[2] = v33;
      if ( *((_WORD *)v14 + 36) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[18] = 524294;
      v31 = 0;
      v14[19] = v33;
      *(_QWORD *)((char *)v14 + v33) = a2;
      v14[2] += 8;
    }
    else
    {
      v31 = -1073741789;
    }
  }
  else
  {
    v31 = -1073741811;
  }
  v34 = RtlNtStatusToDosError(v31);
  v13 = v34;
  if ( v34 > 0 )
    v13 = (unsigned __int16)v34 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldDsMsgStreamKey Failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 0xDu )
  {
    v36 = (unsigned int)v14[2];
    if ( ((v36 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v37 = ((_DWORD)v36 + 3) & 0xFFFFFFFC;
      v14[2] = v37;
      if ( *((_WORD *)v14 + 60) )
        *((_WORD *)v14 + 6) |= 1u;
      v14[30] = 524294;
      v35 = 0;
      v14[31] = v37;
      *(_QWORD *)((char *)v14 + v37) = a3;
      v14[2] += 8;
    }
    else
    {
      v35 = -1073741789;
    }
  }
  else
  {
    v35 = -1073741811;
  }
  v38 = RtlNtStatusToDosError(v35);
  v13 = v38;
  if ( v38 > 0 )
    v13 = (unsigned __int16)v38 | 0x80070000;
  if ( v13 <= -1 )
    goto LABEL_61;
  if ( *((_WORD *)v14 + 7) > 0xEu )
  {
    v40 = (unsigned int)v14[2];
    if ( ((v40 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x108 )
    {
      v41 = ((_DWORD)v40 + 3) & 0xFFFFFFFC;
      v14[2] = v41;
      if ( *((_WORD *)v14 + 64) )
        *((_WORD *)v14 + 6) |= 1u;
      v42 = v76;
      v14[32] = 262154;
      v14[33] = v41;
      *(_DWORD *)((char *)v14 + v41) = v42;
      v39 = 0;
      v14[2] += 4;
    }
    else
    {
      v39 = -1073741789;
    }
  }
  else
  {
    v39 = -1073741811;
  }
  v43 = RtlNtStatusToDosError(v39);
  v13 = v43;
  if ( v43 > 0 )
    v13 = (unsigned __int16)v43 | 0x80070000;
  if ( v13 <= -1 )
  {
LABEL_61:
    v15 = L"SetCldDsMsgFileId Failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) > 0xFu )
  {
    v45 = (unsigned int)v14[2];
    if ( ((v45 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v46 = (v45 + 3) & 0xFFFFFFFC;
      v14[2] = v46;
      if ( *((_WORD *)v14 + 68) )
        *((_WORD *)v14 + 6) |= 1u;
      v47 = v46;
      v14[35] = v46;
      v48 = a5;
      v14[34] = 524294;
      *(_QWORD *)((char *)v14 + v47) = v48;
      v44 = 0;
      v14[2] += 8;
    }
    else
    {
      v44 = -1073741789;
    }
  }
  else
  {
    v44 = -1073741811;
  }
  v49 = RtlNtStatusToDosError(v44);
  v13 = v49;
  if ( v49 > 0 )
    v13 = (unsigned __int16)v49 | 0x80070000;
  if ( v13 <= -1 )
  {
    v15 = L"SetCldDsMsgStartingOffset Failed";
    goto LABEL_115;
  }
  if ( *((_WORD *)v14 + 7) <= 0x10u )
  {
    v13 = -1073741811;
LABEL_87:
    v15 = L"SetCldDsMsgRangeLength Failed";
    goto LABEL_115;
  }
  v50 = (unsigned int)v14[2];
  if ( ((v50 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > 0x108 )
  {
    v13 = -1073741789;
    goto LABEL_87;
  }
  v51 = (v50 + 3) & 0xFFFFFFFC;
  v14[2] = v51;
  if ( *((_WORD *)v14 + 72) )
    *((_WORD *)v14 + 6) |= 1u;
  v14[37] = v51;
  v52 = v51;
  v53 = a6;
  v14[36] = 524294;
  *(_QWORD *)((char *)v14 + v52) = v53;
  v14[2] += 8;
  if ( *((_WORD *)v14 + 7) > 0x11u )
  {
    v55 = (unsigned int)v14[2];
    if ( ((v55 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x108 )
    {
      v56 = (v55 + 3) & 0xFFFFFFFC;
      v14[2] = v56;
      if ( *((_WORD *)v14 + 76) )
        *((_WORD *)v14 + 6) |= 1u;
      v57 = v56;
      v14[39] = v56;
      v58 = a7;
      v14[38] = 524299;
      *(_QWORD *)((char *)v14 + v57) = v58;
      v54 = 0;
      v14[2] += 8;
    }
    else
    {
      v54 = -1073741789;
    }
  }
  else
  {
    v54 = -1073741811;
  }
  v59 = RtlNtStatusToDosError(v54);
  v13 = v59;
  if ( v59 > 0 )
    v13 = (unsigned __int16)v59 | 0x80070000;
  if ( v13 > -1 )
  {
    if ( *((_WORD *)v14 + 7) > 0x12u )
    {
      v60 = (unsigned int)v14[2];
      if ( ((v60 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x108 )
      {
        v61 = (v60 + 3) & 0xFFFFFFFC;
        v14[2] = v61;
        if ( *((_WORD *)v14 + 80) )
          *((_WORD *)v14 + 6) |= 1u;
        v14[41] = v61;
        v17 = 0;
        v62 = v61;
        v63 = a8;
        v14[40] = 262154;
        *(_DWORD *)((char *)v14 + v62) = v63;
        v14[2] += 4;
      }
      else
      {
        v17 = -1073741789;
      }
    }
    v64 = RtlNtStatusToDosError(v17);
    v13 = v64;
    if ( v64 > 0 )
      v13 = (unsigned __int16)v64 | 0x80070000;
    if ( v13 > -1 )
    {
      v14[1] = 0;
      *((_WORD *)v14 + 6) &= ~2u;
      v13 = FilterSendMessage(hPort, v14, 0x108u, &OutBuffer, 4u, &BytesReturned);
      if ( a9 )
        *a9 = OutBuffer;
      v15 = L"FilterSendMessage returned failure";
      if ( v13 > -1 )
        v15 = 0;
    }
    else
    {
      v15 = L"SetCldDsMsgInfoBufferLength Failed";
    }
  }
  else
  {
    v15 = L"SetCldDsMsgInfoBuffer Failed";
  }
LABEL_115:
  v68 = v15;
  v72 = v76;
  v69 = a1;
  v70 = a2;
  v71 = a3;
  TlmLogApiReliability(0x1Fu, 0, 0, 0, 0, UnbiasedTime, &v67, v13);
  if ( v12 )
    CfpReleaseSyncRoot(v12);
  if ( v14 )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v14);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000eb80  mov     [rsp-8+arg_18], r9d
0x18000eb85  push    rbp
0x18000eb86  push    rbx
0x18000eb87  push    rsi
0x18000eb88  push    rdi
0x18000eb89  push    r12
0x18000eb8b  push    r13
0x18000eb8d  push    r14
0x18000eb8f  push    r15
0x18000eb91  lea     rbp, [rsp-7]
0x18000eb96  sub     rsp, 0A8h
0x18000eb9d  xor     r14d, r14d
0x18000eba0  mov     rdi, r8
0x18000eba3  mov     rsi, rdx
0x18000eba6  mov     [rbp+3Fh+BytesReturned], r14d
0x18000ebaa  mov     rbx, rcx
0x18000ebad  mov     [rbp+3Fh+OutBuffer], r14d
0x18000ebb1  xor     edx, edx; Val
0x18000ebb3  lea     rcx, [rbp+3Fh+var_A0]; void *
0x18000ebb7  lea     r8d, [r14+58h]; Size
0x18000ebbb  call    memset_0
0x18000ebc0  lea     rcx, [rbp+3Fh+UnbiasedTime]; UnbiasedTime
0x18000ebc4  mov     [rbp+3Fh+UnbiasedTime], r14
0x18000ebc8  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000ebce  mov     rcx, rbx
0x18000ebd1  call    CfpReferenceSyncRoot
0x18000ebd6  mov     rcx, rax
0x18000ebd9  mov     r13, rax
0x18000ebdc  neg     rcx
0x18000ebdf  sbb     r14d, r14d
0x18000ebe2  xor     edx, edx
0x18000ebe4  not     r14d
0x18000ebe7  and     r14d, 57h
0x18000ebeb  mov     ecx, r14d
0x18000ebee  or      ecx, 80070000h
0x18000ebf4  test    rax, rax
0x18000ebf7  cmovz   r14d, ecx
0x18000ebfb  cmp     r14d, 0FFFFFFFFh
0x18000ebff  jg      short loc_18000EC10
0x18000ec01  mov     r15d, edx
0x18000ec04  lea     rax, aSyncrootNotFou_0; "Syncroot not found with ConnectionKey"
0x18000ec0b  jmp     loc_18000F2A1
0x18000ec10  call    cs:__imp_GetProcessHeap
0x18000ec16  mov     r12d, 8
0x18000ec1c  mov     r8d, 108h; dwBytes
0x18000ec22  mov     rcx, rax; hHeap
0x18000ec25  mov     edx, r12d; dwFlags
0x18000ec28  call    cs:__imp_HeapAlloc
0x18000ec2e  mov     r15, rax
0x18000ec31  neg     rax
0x18000ec34  sbb     r14d, r14d
0x18000ec37  xor     edx, edx; Val
0x18000ec39  not     r14d
0x18000ec3c  and     r14d, r12d
0x18000ec3f  mov     eax, r14d
0x18000ec42  or      eax, 80070000h
0x18000ec47  test    r15, r15
0x18000ec4a  cmovz   r14d, eax
0x18000ec4e  cmp     r14d, 0FFFFFFFFh
0x18000ec52  jg      short loc_18000EC60
0x18000ec54  lea     rax, aMemoryAllocFai; "Memory alloc failed for CldCmdPlacehold"...
0x18000ec5b  jmp     loc_18000F2A1
0x18000ec60  mov     r8d, 0B8h; Size
0x18000ec66  mov     qword ptr [r15], 706D6C43h
0x18000ec6d  lea     rcx, [r15+10h]; void *
0x18000ec71  mov     dword ptr [r15+8], 0C8h
0x18000ec79  mov     dword ptr [r15+0Ch], 170000h
0x18000ec81  call    memset_0
0x18000ec86  xor     edx, edx
0x18000ec88  mov     r12d, 0C000000Dh
0x18000ec8e  lea     r9d, [rdx+1]
0x18000ec92  cmp     dx, [r15+0Eh]
0x18000ec97  jb      short loc_18000EC9E
0x18000ec99  mov     ecx, r12d
0x18000ec9c  jmp     short loc_18000ECDE
0x18000ec9e  mov     ecx, [r15+8]
0x18000eca2  lea     rax, [rcx+3]
0x18000eca6  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000ecaa  add     rax, r9
0x18000ecad  cmp     rax, 108h
0x18000ecb3  jbe     short loc_18000ECBC
0x18000ecb5  mov     ecx, 0C0000023h
0x18000ecba  jmp     short loc_18000ECDE
0x18000ecbc  lea     eax, [rcx+3]
0x18000ecbf  and     eax, 0FFFFFFFCh
0x18000ecc2  mov     ecx, eax
0x18000ecc4  mov     [r15+8], ecx
0x18000ecc8  mov     [r15+14h], ecx
0x18000eccc  mov     ecx, edx; Status
0x18000ecce  mov     dword ptr [r15+10h], 10007h
0x18000ecd6  mov     [rax+r15], r9b
0x18000ecda  add     [r15+8], r9d
0x18000ecde  call    cs:__imp_RtlNtStatusToDosError
0x18000ece4  xor     edx, edx
0x18000ece6  mov     r14d, eax
0x18000ece9  test    eax, eax
0x18000eceb  jle     short loc_18000ECF8
0x18000eced  movzx   r14d, ax
0x18000ecf1  or      r14d, 80070000h
0x18000ecf8  cmp     r14d, 0FFFFFFFFh
0x18000ecfc  jg      short loc_18000ED0A
0x18000ecfe  lea     rax, aSetversionFail; "SetVersion failed"
0x18000ed05  jmp     loc_18000F2A1
0x18000ed0a  mov     r9d, 1
0x18000ed10  cmp     r9w, [r15+0Eh]
0x18000ed15  jb      short loc_18000ED1C
0x18000ed17  mov     ecx, r12d
0x18000ed1a  jmp     short loc_18000ED6F
0x18000ed1c  mov     ecx, [r15+8]
0x18000ed20  mov     r8d, 2
0x18000ed26  lea     rax, [rcx+3]
0x18000ed2a  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000ed2e  add     rax, r8
0x18000ed31  cmp     rax, 108h
0x18000ed37  jbe     short loc_18000ED40
0x18000ed39  mov     ecx, 0C0000023h
0x18000ed3e  jmp     short loc_18000ED6F
0x18000ed40  lea     eax, [rcx+3]
0x18000ed43  and     eax, 0FFFFFFFCh
0x18000ed46  mov     [r15+8], eax
0x18000ed4a  cmp     [r15+18h], dx
0x18000ed4f  jz      short loc_18000ED56
0x18000ed51  or      [r15+0Ch], r9w
0x18000ed56  mov     dword ptr [r15+18h], 20008h
0x18000ed5e  mov     ecx, edx; Status
0x18000ed60  mov     [r15+1Ch], eax
0x18000ed64  mov     word ptr [rax+r15], 0D001h
0x18000ed6b  add     [r15+8], r8d
0x18000ed6f  call    cs:__imp_RtlNtStatusToDosError
0x18000ed75  xor     edx, edx
0x18000ed77  mov     r14d, eax
0x18000ed7a  test    eax, eax
0x18000ed7c  jle     short loc_18000ED89
0x18000ed7e  movzx   r14d, ax
0x18000ed82  or      r14d, 80070000h
0x18000ed89  cmp     r14d, 0FFFFFFFFh
0x18000ed8d  jg      short loc_18000ED9B
0x18000ed8f  lea     rax, aSetcldmsgcomma; "SetCldMsgCommand failed"
0x18000ed96  jmp     loc_18000F2A1
0x18000ed9b  mov     eax, 4
0x18000eda0  cmp     ax, [r15+0Eh]
0x18000eda5  jb      short loc_18000EDAC
0x18000eda7  mov     ecx, r12d
0x18000edaa  jmp     short loc_18000EE01
0x18000edac  mov     ecx, [r15+8]
0x18000edb0  mov     r8d, 8
0x18000edb6  lea     rax, [rcx+3]
0x18000edba  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000edbe  add     rax, r8
0x18000edc1  cmp     rax, 108h
0x18000edc7  jbe     short loc_18000EDD0
0x18000edc9  mov     ecx, 0C0000023h
0x18000edce  jmp     short loc_18000EE01
0x18000edd0  lea     eax, [rcx+3]
0x18000edd3  and     eax, 0FFFFFFFCh
0x18000edd6  mov     [r15+8], eax
0x18000edda  cmp     [r15+30h], dx
0x18000eddf  jz      short loc_18000EDEB
0x18000ede1  mov     ecx, 1
0x18000ede6  or      [r15+0Ch], cx
0x18000edeb  mov     dword ptr [r15+30h], 80006h
0x18000edf3  mov     ecx, edx; Status
0x18000edf5  mov     [r15+34h], eax
0x18000edf9  mov     [rax+r15], rbx
0x18000edfd  add     [r15+8], r8d
0x18000ee01  call    cs:__imp_RtlNtStatusToDosError
0x18000ee07  xor     edx, edx
0x18000ee09  mov     r14d, eax
0x18000ee0c  test    eax, eax
0x18000ee0e  jle     short loc_18000EE1B
0x18000ee10  movzx   r14d, ax
0x18000ee14  or      r14d, 80070000h
0x18000ee1b  cmp     r14d, 0FFFFFFFFh
0x18000ee1f  jg      short loc_18000EE2D
0x18000ee21  lea     rax, aSetclddsmsgsyn_2; "SetCldDsMsgSyncRootKey failed"
0x18000ee28  jmp     loc_18000F2A1
0x18000ee2d  mov     eax, 7
0x18000ee32  cmp     ax, [r15+0Eh]
0x18000ee37  jb      short loc_18000EE3E
0x18000ee39  mov     ecx, r12d
0x18000ee3c  jmp     short loc_18000EE93
0x18000ee3e  mov     ecx, [r15+8]
0x18000ee42  mov     r8d, 8
0x18000ee48  lea     rax, [rcx+3]
0x18000ee4c  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000ee50  add     rax, r8
0x18000ee53  cmp     rax, 108h
0x18000ee59  jbe     short loc_18000EE62
0x18000ee5b  mov     ecx, 0C0000023h
0x18000ee60  jmp     short loc_18000EE93
0x18000ee62  lea     eax, [rcx+3]
0x18000ee65  and     eax, 0FFFFFFFCh
0x18000ee68  mov     [r15+8], eax
0x18000ee6c  cmp     [r15+48h], dx
0x18000ee71  jz      short loc_18000EE7D
0x18000ee73  mov     ecx, 1
0x18000ee78  or      [r15+0Ch], cx
0x18000ee7d  mov     dword ptr [r15+48h], 80006h
0x18000ee85  mov     ecx, edx; Status
0x18000ee87  mov     [r15+4Ch], eax
0x18000ee8b  mov     [rax+r15], rsi
0x18000ee8f  add     [r15+8], r8d
0x18000ee93  call    cs:__imp_RtlNtStatusToDosError
0x18000ee99  xor     edx, edx
0x18000ee9b  mov     r14d, eax
0x18000ee9e  test    eax, eax
0x18000eea0  jle     short loc_18000EEAD
0x18000eea2  movzx   r14d, ax
0x18000eea6  or      r14d, 80070000h
0x18000eead  cmp     r14d, 0FFFFFFFFh
0x18000eeb1  jg      short loc_18000EEBF
0x18000eeb3  lea     rax, aSetclddsmsgstr; "SetCldDsMsgStreamKey Failed"
0x18000eeba  jmp     loc_18000F2A1
0x18000eebf  mov     eax, 0Dh
0x18000eec4  cmp     ax, [r15+0Eh]
0x18000eec9  jb      short loc_18000EED0
0x18000eecb  mov     ecx, r12d
0x18000eece  jmp     short loc_18000EF25
0x18000eed0  mov     ecx, [r15+8]
0x18000eed4  mov     r8d, 8
0x18000eeda  lea     rax, [rcx+3]
0x18000eede  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000eee2  add     rax, r8
0x18000eee5  cmp     rax, 108h
0x18000eeeb  jbe     short loc_18000EEF4
0x18000eeed  mov     ecx, 0C0000023h
0x18000eef2  jmp     short loc_18000EF25
0x18000eef4  lea     eax, [rcx+3]
0x18000eef7  and     eax, 0FFFFFFFCh
0x18000eefa  mov     [r15+8], eax
0x18000eefe  cmp     [r15+78h], dx
0x18000ef03  jz      short loc_18000EF0F
0x18000ef05  mov     ecx, 1
0x18000ef0a  or      [r15+0Ch], cx
0x18000ef0f  mov     dword ptr [r15+78h], 80006h
0x18000ef17  mov     ecx, edx; Status
0x18000ef19  mov     [r15+7Ch], eax
0x18000ef1d  mov     [rax+r15], rdi
0x18000ef21  add     [r15+8], r8d
0x18000ef25  call    cs:__imp_RtlNtStatusToDosError
0x18000ef2b  xor     edx, edx
0x18000ef2d  mov     r14d, eax
0x18000ef30  test    eax, eax
0x18000ef32  jle     short loc_18000EF3F
0x18000ef34  movzx   r14d, ax
0x18000ef38  or      r14d, 80070000h
0x18000ef3f  cmp     r14d, 0FFFFFFFFh
0x18000ef43  jg      short loc_18000EF51
0x18000ef45  lea     rax, aSetclddsmsgfil; "SetCldDsMsgFileId Failed"
0x18000ef4c  jmp     loc_18000F2A1
0x18000ef51  mov     eax, 0Eh
0x18000ef56  cmp     ax, [r15+0Eh]
0x18000ef5b  jb      short loc_18000EF62
0x18000ef5d  mov     ecx, r12d
0x18000ef60  jmp     short loc_18000EFC3
0x18000ef62  mov     ecx, [r15+8]
0x18000ef66  mov     r9d, 4
0x18000ef6c  lea     rax, [rcx+3]
0x18000ef70  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000ef74  add     rax, r9
0x18000ef77  cmp     rax, 108h
0x18000ef7d  jbe     short loc_18000EF86
0x18000ef7f  mov     ecx, 0C0000023h
0x18000ef84  jmp     short loc_18000EFC3
0x18000ef86  lea     eax, [rcx+3]
0x18000ef89  and     eax, 0FFFFFFFCh
0x18000ef8c  mov     [r15+8], eax
0x18000ef90  cmp     [r15+80h], dx
0x18000ef98  jz      short loc_18000EFA4
0x18000ef9a  mov     ecx, 1
0x18000ef9f  or      [r15+0Ch], cx
0x18000efa4  mov     ecx, [rbp+3Fh+arg_18]
0x18000efa7  mov     dword ptr [r15+80h], 4000Ah
0x18000efb2  mov     [r15+84h], eax
0x18000efb9  mov     [rax+r15], ecx
0x18000efbd  mov     ecx, edx; Status
0x18000efbf  add     [r15+8], r9d
0x18000efc3  call    cs:__imp_RtlNtStatusToDosError
0x18000efc9  xor     edx, edx
0x18000efcb  mov     r14d, eax
0x18000efce  test    eax, eax
0x18000efd0  jle     short loc_18000EFDD
0x18000efd2  movzx   r14d, ax
0x18000efd6  or      r14d, 80070000h
0x18000efdd  cmp     r14d, 0FFFFFFFFh
0x18000efe1  jle     loc_18000EF45
0x18000efe7  mov     eax, 0Fh
0x18000efec  cmp     ax, [r15+0Eh]
0x18000eff1  jb      short loc_18000EFF8
0x18000eff3  mov     ecx, r12d
0x18000eff6  jmp     short loc_18000F05C
0x18000eff8  mov     ecx, [r15+8]
0x18000effc  mov     r8d, 8
0x18000f002  lea     rax, [rcx+3]
0x18000f006  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000f00a  add     rax, r8
0x18000f00d  cmp     rax, 108h
0x18000f013  jbe     short loc_18000F01C
0x18000f015  mov     ecx, 0C0000023h
0x18000f01a  jmp     short loc_18000F05C
  ... truncated ...
```
