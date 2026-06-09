# CfReportProviderProgress2

- ea: `0x1800031d0`
- end: `0x1800037e1`
- name: `CfReportProviderProgress2`
- size: `1553`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800031a0`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x1800031d0`
- `0x18000b218`
- `0x18000b6c8`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180003305`
- `ntdll!RtlNtStatusToDosError` at `0x180003399`
- `ntdll!RtlNtStatusToDosError` at `0x180003427`
- `ntdll!RtlNtStatusToDosError` at `0x1800034b5`
- `ntdll!RtlNtStatusToDosError` at `0x180003543`
- `ntdll!RtlNtStatusToDosError` at `0x1800035d1`
- `ntdll!RtlNtStatusToDosError` at `0x18000365f`
- `ntdll!RtlNtStatusToDosError` at `0x1800036f2`
- `ntdll!RtlNtStatusToDosError` at `0x180003305`
- `ntdll!RtlNtStatusToDosError` at `0x180003399`
- `ntdll!RtlNtStatusToDosError` at `0x180003427`
- `ntdll!RtlNtStatusToDosError` at `0x1800034b5`
- `ntdll!RtlNtStatusToDosError` at `0x180003543`
- `ntdll!RtlNtStatusToDosError` at `0x1800035d1`
- `ntdll!RtlNtStatusToDosError` at `0x18000365f`
- `ntdll!RtlNtStatusToDosError` at `0x1800036f2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000322b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000322b`
- `FLTLIB!FilterSendMessage` at `0x180003747`
- `FLTLIB!FilterSendMessage` at `0x180003747`

## string_xrefs

- `0x1800033b9`: `SetCldMsgCommand Failed`
- `0x18000367f`: `SetCldDsMsgProviderProgressCompleted Failed`

## pseudocode

```c
__int64 __fastcall CfReportProviderProgress2(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  int v10; // r12d
  const wchar_t *v11; // rax
  NTSTATUS v12; // r13d
  NTSTATUS v13; // ecx
  DWORD v14; // ecx
  signed int v15; // eax
  NTSTATUS v16; // ecx
  DWORD v17; // eax
  signed int v18; // eax
  NTSTATUS v19; // ecx
  DWORD v20; // eax
  signed int v21; // eax
  NTSTATUS v22; // ecx
  DWORD v23; // eax
  signed int v24; // eax
  NTSTATUS v25; // ecx
  DWORD v26; // eax
  signed int v27; // eax
  NTSTATUS v28; // ecx
  DWORD v29; // eax
  signed int v30; // eax
  NTSTATUS v31; // ecx
  DWORD v32; // eax
  signed int v33; // eax
  DWORD v34; // eax
  signed int v35; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+90h] [rbp-70h]
  __int64 InBuffer; // [rsp+C0h] [rbp-40h] BYREF
  DWORD dwInBufferSize; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  _DWORD v50[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v51; // [rsp+D8h] [rbp-28h]
  DWORD v52; // [rsp+DCh] [rbp-24h]
  int v53; // [rsp+F0h] [rbp-10h]
  DWORD v54; // [rsp+F4h] [rbp-Ch]
  int v55; // [rsp+108h] [rbp+8h]
  DWORD v56; // [rsp+10Ch] [rbp+Ch]
  int v57; // [rsp+130h] [rbp+30h]
  DWORD v58; // [rsp+134h] [rbp+34h]
  int v59; // [rsp+138h] [rbp+38h]
  DWORD v60; // [rsp+13Ch] [rbp+3Ch]
  int v61; // [rsp+140h] [rbp+40h]
  DWORD v62; // [rsp+144h] [rbp+44h]
  int v63; // [rsp+148h] [rbp+48h]
  DWORD v64; // [rsp+14Ch] [rbp+4Ch]

  BytesReturned = 0;
  memset_0(&v40, 0, 0x58u);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v39 = CfpReferenceSyncRoot(a1);
  v10 = v39 == 0 ? 0x57 : 0;
  if ( !v39 )
    v10 |= 0x80070000;
  if ( v10 > -1 )
  {
    memset_0(v50, 0, 0xF0u);
    InBuffer = 1886219331;
    dwInBufferSize = 200;
    v49 = 1507328;
    memset_0(v50, 0, 0xB8u);
    v12 = -1073741811;
    if ( HIWORD(v49) )
    {
      v14 = dwInBufferSize;
      if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0x100 )
      {
        v50[0] = 65543;
        dwInBufferSize = (dwInBufferSize + 3) & 0xFFFFFFFC;
        v50[1] = (v14 + 3) & 0xFFFFFFFC;
        v13 = 0;
        *((_BYTE *)&InBuffer + dwInBufferSize++) = 1;
      }
      else
      {
        v13 = -1073741789;
      }
    }
    else
    {
      v13 = -1073741811;
    }
    v15 = RtlNtStatusToDosError(v13);
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    if ( v10 > -1 )
    {
      if ( HIWORD(v49) > 1u )
      {
        if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0x100 )
        {
          v17 = (dwInBufferSize + 3) & 0xFFFFFFFC;
          dwInBufferSize = v17;
          if ( (_WORD)v51 )
            LOWORD(v49) = v49 | 1;
          v51 = 131080;
          v52 = v17;
          *(_WORD *)((char *)&InBuffer + v17) = 262;
          v16 = 0;
          dwInBufferSize += 2;
        }
        else
        {
          v16 = -1073741789;
        }
      }
      else
      {
        v16 = -1073741811;
      }
      v18 = RtlNtStatusToDosError(v16);
      v10 = v18;
      if ( v18 > 0 )
        v10 = (unsigned __int16)v18 | 0x80070000;
      if ( v10 > -1 )
      {
        if ( HIWORD(v49) > 4u )
        {
          if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
          {
            v20 = (dwInBufferSize + 3) & 0xFFFFFFFC;
            dwInBufferSize = v20;
            if ( (_WORD)v53 )
              LOWORD(v49) = v49 | 1;
            v54 = v20;
            v53 = 524294;
            *(__int64 *)((char *)&InBuffer + v20) = a1;
            v19 = 0;
            dwInBufferSize += 8;
          }
          else
          {
            v19 = -1073741789;
          }
        }
        else
        {
          v19 = -1073741811;
        }
        v21 = RtlNtStatusToDosError(v19);
        v10 = v21;
        if ( v21 > 0 )
          v10 = (unsigned __int16)v21 | 0x80070000;
        if ( v10 > -1 )
        {
          if ( HIWORD(v49) > 7u )
          {
            if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
            {
              v23 = (dwInBufferSize + 3) & 0xFFFFFFFC;
              dwInBufferSize = v23;
              if ( (_WORD)v55 )
                LOWORD(v49) = v49 | 1;
              v56 = v23;
              v55 = 524294;
              *(__int64 *)((char *)&InBuffer + v23) = a2;
              v22 = 0;
              dwInBufferSize += 8;
            }
            else
            {
              v22 = -1073741789;
            }
          }
          else
          {
            v22 = -1073741811;
          }
          v24 = RtlNtStatusToDosError(v22);
          v10 = v24;
          if ( v24 > 0 )
            v10 = (unsigned __int16)v24 | 0x80070000;
          if ( v10 > -1 )
          {
            if ( HIWORD(v49) > 0xCu )
            {
              if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
              {
                v26 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                dwInBufferSize = v26;
                if ( (_WORD)v57 )
                  LOWORD(v49) = v49 | 1;
                v58 = v26;
                v57 = 524294;
                *(__int64 *)((char *)&InBuffer + v26) = a3;
                v25 = 0;
                dwInBufferSize += 8;
              }
              else
              {
                v25 = -1073741789;
              }
            }
            else
            {
              v25 = -1073741811;
            }
            v27 = RtlNtStatusToDosError(v25);
            v10 = v27;
            if ( v27 > 0 )
              v10 = (unsigned __int16)v27 | 0x80070000;
            if ( v10 > -1 )
            {
              if ( HIWORD(v49) > 0xDu )
              {
                if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
                {
                  v29 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                  dwInBufferSize = v29;
                  if ( (_WORD)v59 )
                    LOWORD(v49) = v49 | 1;
                  v60 = v29;
                  v59 = 524294;
                  *(__int64 *)((char *)&InBuffer + v29) = a4;
                  v28 = 0;
                  dwInBufferSize += 8;
                }
                else
                {
                  v28 = -1073741789;
                }
              }
              else
              {
                v28 = -1073741811;
              }
              v30 = RtlNtStatusToDosError(v28);
              v10 = v30;
              if ( v30 > 0 )
                v10 = (unsigned __int16)v30 | 0x80070000;
              if ( v10 > -1 )
              {
                if ( HIWORD(v49) > 0xEu )
                {
                  if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0x100 )
                  {
                    v32 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                    dwInBufferSize = v32;
                    if ( (_WORD)v61 )
                      LOWORD(v49) = v49 | 1;
                    v62 = v32;
                    v61 = 524294;
                    *(__int64 *)((char *)&InBuffer + v32) = a5;
                    v31 = 0;
                    dwInBufferSize += 8;
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
                v33 = RtlNtStatusToDosError(v31);
                v10 = v33;
                if ( v33 > 0 )
                  v10 = (unsigned __int16)v33 | 0x80070000;
                if ( v10 > -1 )
                {
                  if ( HIWORD(v49) > 0xFu )
                  {
                    if ( ((dwInBufferSize + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0x100 )
                    {
                      v34 = (dwInBufferSize + 3) & 0xFFFFFFFC;
                      dwInBufferSize = v34;
                      if ( (_WORD)v63 )
                        LOWORD(v49) = v49 | 1;
                      v12 = 0;
                      v63 = 262154;
                      v64 = v34;
                      *(_DWORD *)((char *)&InBuffer + v34) = a6;
                      dwInBufferSize += 4;
                    }
                    else
                    {
                      v12 = -1073741789;
                    }
                  }
                  v35 = RtlNtStatusToDosError(v12);
                  v10 = v35;
                  if ( v35 > 0 )
                    v10 = (unsigned __int16)v35 | 0x80070000;
                  if ( v10 > -1 )
                  {
                    LOWORD(v49) = v49 & 0xFFFD;
                    HIDWORD(InBuffer) = 0;
                    v10 = FilterSendMessage(hPort, &InBuffer, dwInBufferSize, 0, 0, &BytesReturned);
                    v11 = L"FilterSendMessage failed";
                    if ( v10 > -1 )
                      v11 = 0;
                  }
                  else
                  {
                    v11 = L"SetCldDsMsgRequestorSessionId Failed";
                  }
                }
                else
                {
                  v11 = L"SetCldDsMsgProviderProgressCompleted Failed";
                }
              }
              else
              {
                v11 = L"SetCldDsMsgProviderProgressTotal Failed";
              }
            }
            else
            {
              v11 = L"SetCldDsMsgRequestKey Failed";
            }
          }
          else
          {
            v11 = L"SetCldDsMsgStreamKey Failed";
          }
        }
        else
        {
          v11 = L"SetCldDsMsgSyncRootKey Failed";
        }
      }
      else
      {
        v11 = L"SetCldMsgCommand Failed";
      }
    }
    else
    {
      v11 = L"SetVersion Failed";
    }
  }
  else
  {
    v11 = L"No SyncRoot found with ConnectionKey";
  }
  v41 = v11;
  v42 = a1;
  v43 = a2;
  v44 = a3;
  v45 = a4;
  v46 = a5;
  TlmLogApiReliability(0x21u, 0, 0, 0, 0, UnbiasedTime, &v40, v10);
  if ( v39 )
    CfpReleaseSyncRoot(v39);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800031d0  push    rbp
0x1800031d2  push    rbx
0x1800031d3  push    rsi
0x1800031d4  push    rdi
0x1800031d5  push    r12
0x1800031d7  push    r13
0x1800031d9  push    r14
0x1800031db  push    r15
0x1800031dd  lea     rbp, [rsp-0D8h]
0x1800031e5  sub     rsp, 1D8h
0x1800031ec  mov     rax, cs:__security_cookie
0x1800031f3  xor     rax, rsp
0x1800031f6  mov     [rbp+110h+var_50], rax
0x1800031fd  xor     r15d, r15d
0x180003200  mov     rsi, r8
0x180003203  mov     rdi, rdx
0x180003206  mov     [rsp+210h+BytesReturned], r15d
0x18000320b  mov     rbx, rcx
0x18000320e  xor     edx, edx; Val
0x180003210  lea     rcx, [rsp+210h+var_1B0]; void *
0x180003215  mov     r14, r9
0x180003218  lea     r8d, [r15+58h]; Size
0x18000321c  call    memset_0
0x180003221  lea     rcx, [rsp+210h+UnbiasedTime]; UnbiasedTime
0x180003226  mov     [rsp+210h+UnbiasedTime], r15
0x18000322b  call    cs:__imp_QueryUnbiasedInterruptTime
0x180003231  mov     rcx, rbx
0x180003234  call    CfpReferenceSyncRoot
0x180003239  mov     r15, [rbp+110h+arg_20]
0x180003240  mov     rcx, rax
0x180003243  neg     rcx
0x180003246  mov     [rsp+210h+var_1C0], rax
0x18000324b  sbb     r12d, r12d
0x18000324e  xor     edx, edx; Val
0x180003250  not     r12d
0x180003253  and     r12d, 57h
0x180003257  mov     ecx, r12d
0x18000325a  or      ecx, 80070000h
0x180003260  test    rax, rax
0x180003263  cmovz   r12d, ecx
0x180003267  cmp     r12d, 0FFFFFFFFh
0x18000326b  jg      short loc_180003279
0x18000326d  lea     rax, aNoSyncrootFoun; "No SyncRoot found with ConnectionKey"
0x180003274  jmp     loc_180003761
0x180003279  mov     r8d, 0F0h; Size
0x18000327f  lea     rcx, [rbp+110h+var_140]; void *
0x180003283  call    memset_0
0x180003288  xor     edx, edx; Val
0x18000328a  mov     [rbp+110h+InBuffer], 706D6C43h
0x180003292  mov     r8d, 0B8h; Size
0x180003298  mov     [rbp+110h+dwInBufferSize], 0C8h
0x18000329f  lea     rcx, [rbp+110h+var_140]; void *
0x1800032a3  mov     [rbp+110h+var_144], 170000h
0x1800032aa  xor     r12d, r12d
0x1800032ad  call    memset_0
0x1800032b2  lea     edx, [r12+1]
0x1800032b7  mov     r13d, 0C000000Dh
0x1800032bd  cmp     r12w, word ptr [rbp+110h+var_144+2]
0x1800032c2  jb      short loc_1800032C9
0x1800032c4  mov     ecx, r13d
0x1800032c7  jmp     short loc_180003305
0x1800032c9  mov     ecx, [rbp+110h+dwInBufferSize]
0x1800032cc  lea     rax, [rcx+3]
0x1800032d0  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800032d4  add     rax, rdx
0x1800032d7  cmp     rax, 100h
0x1800032dd  jbe     short loc_1800032E6
0x1800032df  mov     ecx, 0C0000023h
0x1800032e4  jmp     short loc_180003305
0x1800032e6  lea     eax, [rcx+3]
0x1800032e9  mov     [rbp+110h+var_140], 10007h
0x1800032f0  and     eax, 0FFFFFFFCh
0x1800032f3  mov     ecx, eax
0x1800032f5  mov     [rbp+110h+dwInBufferSize], ecx
0x1800032f8  mov     [rbp+110h+var_13C], ecx
0x1800032fb  mov     ecx, r12d; Status
0x1800032fe  mov     byte ptr [rbp+rax+110h+InBuffer], dl
0x180003302  add     [rbp+110h+dwInBufferSize], edx
0x180003305  call    cs:__imp_RtlNtStatusToDosError
0x18000330b  xor     edx, edx
0x18000330d  mov     r12d, eax
0x180003310  test    eax, eax
0x180003312  jle     short loc_18000331F
0x180003314  movzx   r12d, ax
0x180003318  or      r12d, 80070000h
0x18000331f  cmp     r12d, 0FFFFFFFFh
0x180003323  jg      short loc_180003331
0x180003325  lea     rax, aSetversionFail_0; "SetVersion Failed"
0x18000332c  jmp     loc_180003761
0x180003331  mov     r10d, 1
0x180003337  cmp     r10w, word ptr [rbp+110h+var_144+2]
0x18000333c  jb      short loc_180003343
0x18000333e  mov     ecx, r13d
0x180003341  jmp     short loc_180003399
0x180003343  mov     ecx, [rbp+110h+dwInBufferSize]
0x180003346  mov     r8d, 2
0x18000334c  lea     rax, [rcx+3]
0x180003350  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003354  add     rax, r8
0x180003357  cmp     rax, 100h
0x18000335d  jbe     short loc_180003366
0x18000335f  mov     ecx, 0C0000023h
0x180003364  jmp     short loc_180003399
0x180003366  lea     eax, [rcx+3]
0x180003369  and     eax, 0FFFFFFFCh
0x18000336c  mov     ecx, eax
0x18000336e  mov     [rbp+110h+dwInBufferSize], eax
0x180003371  cmp     word ptr [rbp+110h+var_138], dx
0x180003375  jz      short loc_18000337C
0x180003377  or      word ptr [rbp+110h+var_144], r10w
0x18000337c  mov     rax, rcx
0x18000337f  mov     [rbp+110h+var_138], 20008h
0x180003386  mov     ecx, 106h
0x18000338b  mov     [rbp+110h+var_134], eax
0x18000338e  mov     word ptr [rbp+rax+110h+InBuffer], cx
0x180003393  mov     ecx, edx; Status
0x180003395  add     [rbp+110h+dwInBufferSize], r8d
0x180003399  call    cs:__imp_RtlNtStatusToDosError
0x18000339f  xor     edx, edx
0x1800033a1  mov     r12d, eax
0x1800033a4  test    eax, eax
0x1800033a6  jle     short loc_1800033B3
0x1800033a8  movzx   r12d, ax
0x1800033ac  or      r12d, 80070000h
0x1800033b3  cmp     r12d, 0FFFFFFFFh
0x1800033b7  jg      short loc_1800033C5
0x1800033b9  lea     rax, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x1800033c0  jmp     loc_180003761
0x1800033c5  mov     eax, 4
0x1800033ca  cmp     ax, word ptr [rbp+110h+var_144+2]
0x1800033ce  jb      short loc_1800033D5
0x1800033d0  mov     ecx, r13d
0x1800033d3  jmp     short loc_180003427
0x1800033d5  mov     ecx, [rbp+110h+dwInBufferSize]
0x1800033d8  mov     r8d, 8
0x1800033de  lea     rax, [rcx+3]
0x1800033e2  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800033e6  add     rax, r8
0x1800033e9  cmp     rax, 100h
0x1800033ef  jbe     short loc_1800033F8
0x1800033f1  mov     ecx, 0C0000023h
0x1800033f6  jmp     short loc_180003427
0x1800033f8  lea     eax, [rcx+3]
0x1800033fb  and     eax, 0FFFFFFFCh
0x1800033fe  mov     ecx, eax
0x180003400  mov     [rbp+110h+dwInBufferSize], eax
0x180003403  cmp     word ptr [rbp+110h+var_120], dx
0x180003407  jz      short loc_180003412
0x180003409  mov     eax, 1
0x18000340e  or      word ptr [rbp+110h+var_144], ax
0x180003412  mov     [rbp+110h+var_11C], ecx
0x180003415  mov     [rbp+110h+var_120], 80006h
0x18000341c  mov     [rbp+rcx+110h+InBuffer], rbx
0x180003421  mov     ecx, edx; Status
0x180003423  add     [rbp+110h+dwInBufferSize], r8d
0x180003427  call    cs:__imp_RtlNtStatusToDosError
0x18000342d  xor     edx, edx
0x18000342f  mov     r12d, eax
0x180003432  test    eax, eax
0x180003434  jle     short loc_180003441
0x180003436  movzx   r12d, ax
0x18000343a  or      r12d, 80070000h
0x180003441  cmp     r12d, 0FFFFFFFFh
0x180003445  jg      short loc_180003453
0x180003447  lea     rax, aSetclddsmsgsyn; "SetCldDsMsgSyncRootKey Failed"
0x18000344e  jmp     loc_180003761
0x180003453  mov     eax, 7
0x180003458  cmp     ax, word ptr [rbp+110h+var_144+2]
0x18000345c  jb      short loc_180003463
0x18000345e  mov     ecx, r13d
0x180003461  jmp     short loc_1800034B5
0x180003463  mov     ecx, [rbp+110h+dwInBufferSize]
0x180003466  mov     r8d, 8
0x18000346c  lea     rax, [rcx+3]
0x180003470  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003474  add     rax, r8
0x180003477  cmp     rax, 100h
0x18000347d  jbe     short loc_180003486
0x18000347f  mov     ecx, 0C0000023h
0x180003484  jmp     short loc_1800034B5
0x180003486  lea     eax, [rcx+3]
0x180003489  and     eax, 0FFFFFFFCh
0x18000348c  mov     ecx, eax
0x18000348e  mov     [rbp+110h+dwInBufferSize], eax
0x180003491  cmp     word ptr [rbp+110h+var_108], dx
0x180003495  jz      short loc_1800034A0
0x180003497  mov     eax, 1
0x18000349c  or      word ptr [rbp+110h+var_144], ax
0x1800034a0  mov     [rbp+110h+var_104], ecx
0x1800034a3  mov     [rbp+110h+var_108], 80006h
0x1800034aa  mov     [rbp+rcx+110h+InBuffer], rdi
0x1800034af  mov     ecx, edx; Status
0x1800034b1  add     [rbp+110h+dwInBufferSize], r8d
0x1800034b5  call    cs:__imp_RtlNtStatusToDosError
0x1800034bb  xor     edx, edx
0x1800034bd  mov     r12d, eax
0x1800034c0  test    eax, eax
0x1800034c2  jle     short loc_1800034CF
0x1800034c4  movzx   r12d, ax
0x1800034c8  or      r12d, 80070000h
0x1800034cf  cmp     r12d, 0FFFFFFFFh
0x1800034d3  jg      short loc_1800034E1
0x1800034d5  lea     rax, aSetclddsmsgstr; "SetCldDsMsgStreamKey Failed"
0x1800034dc  jmp     loc_180003761
0x1800034e1  mov     eax, 0Ch
0x1800034e6  cmp     ax, word ptr [rbp+110h+var_144+2]
0x1800034ea  jb      short loc_1800034F1
0x1800034ec  mov     ecx, r13d
0x1800034ef  jmp     short loc_180003543
0x1800034f1  mov     ecx, [rbp+110h+dwInBufferSize]
0x1800034f4  mov     r8d, 8
0x1800034fa  lea     rax, [rcx+3]
0x1800034fe  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003502  add     rax, r8
0x180003505  cmp     rax, 100h
0x18000350b  jbe     short loc_180003514
0x18000350d  mov     ecx, 0C0000023h
0x180003512  jmp     short loc_180003543
0x180003514  lea     eax, [rcx+3]
0x180003517  and     eax, 0FFFFFFFCh
0x18000351a  mov     ecx, eax
0x18000351c  mov     [rbp+110h+dwInBufferSize], eax
0x18000351f  cmp     word ptr [rbp+110h+var_E0], dx
0x180003523  jz      short loc_18000352E
0x180003525  mov     eax, 1
0x18000352a  or      word ptr [rbp+110h+var_144], ax
0x18000352e  mov     [rbp+110h+var_DC], ecx
0x180003531  mov     [rbp+110h+var_E0], 80006h
0x180003538  mov     [rbp+rcx+110h+InBuffer], rsi
0x18000353d  mov     ecx, edx; Status
0x18000353f  add     [rbp+110h+dwInBufferSize], r8d
0x180003543  call    cs:__imp_RtlNtStatusToDosError
0x180003549  xor     edx, edx
0x18000354b  mov     r12d, eax
0x18000354e  test    eax, eax
0x180003550  jle     short loc_18000355D
0x180003552  movzx   r12d, ax
0x180003556  or      r12d, 80070000h
0x18000355d  cmp     r12d, 0FFFFFFFFh
0x180003561  jg      short loc_18000356F
0x180003563  lea     rax, aSetclddsmsgreq; "SetCldDsMsgRequestKey Failed"
0x18000356a  jmp     loc_180003761
0x18000356f  mov     eax, 0Dh
0x180003574  cmp     ax, word ptr [rbp+110h+var_144+2]
0x180003578  jb      short loc_18000357F
0x18000357a  mov     ecx, r13d
0x18000357d  jmp     short loc_1800035D1
0x18000357f  mov     ecx, [rbp+110h+dwInBufferSize]
0x180003582  mov     r8d, 8
0x180003588  lea     rax, [rcx+3]
0x18000358c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180003590  add     rax, r8
0x180003593  cmp     rax, 100h
0x180003599  jbe     short loc_1800035A2
0x18000359b  mov     ecx, 0C0000023h
0x1800035a0  jmp     short loc_1800035D1
0x1800035a2  lea     eax, [rcx+3]
0x1800035a5  and     eax, 0FFFFFFFCh
0x1800035a8  mov     ecx, eax
0x1800035aa  mov     [rbp+110h+dwInBufferSize], eax
0x1800035ad  cmp     word ptr [rbp+110h+var_D8], dx
0x1800035b1  jz      short loc_1800035BC
0x1800035b3  mov     eax, 1
0x1800035b8  or      word ptr [rbp+110h+var_144], ax
0x1800035bc  mov     [rbp+110h+var_D4], ecx
0x1800035bf  mov     [rbp+110h+var_D8], 80006h
0x1800035c6  mov     [rbp+rcx+110h+InBuffer], r14
0x1800035cb  mov     ecx, edx; Status
0x1800035cd  add     [rbp+110h+dwInBufferSize], r8d
0x1800035d1  call    cs:__imp_RtlNtStatusToDosError
0x1800035d7  xor     edx, edx
0x1800035d9  mov     r12d, eax
0x1800035dc  test    eax, eax
0x1800035de  jle     short loc_1800035EB
0x1800035e0  movzx   r12d, ax
0x1800035e4  or      r12d, 80070000h
0x1800035eb  cmp     r12d, 0FFFFFFFFh
0x1800035ef  jg      short loc_1800035FD
0x1800035f1  lea     rax, aSetclddsmsgpro; "SetCldDsMsgProviderProgressTotal Failed"
0x1800035f8  jmp     loc_180003761
0x1800035fd  mov     eax, 0Eh
0x180003602  cmp     ax, word ptr [rbp+110h+var_144+2]
0x180003606  jb      short loc_18000360D
0x180003608  mov     ecx, r13d
0x18000360b  jmp     short loc_18000365F
0x18000360d  mov     ecx, [rbp+110h+dwInBufferSize]
0x180003610  mov     r8d, 8
0x180003616  lea     rax, [rcx+3]
0x18000361a  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000361e  add     rax, r8
0x180003621  cmp     rax, 100h
0x180003627  jbe     short loc_180003630
0x180003629  mov     ecx, 0C0000023h
0x18000362e  jmp     short loc_18000365F
0x180003630  lea     eax, [rcx+3]
0x180003633  and     eax, 0FFFFFFFCh
0x180003636  mov     ecx, eax
0x180003638  mov     [rbp+110h+dwInBufferSize], eax
0x18000363b  cmp     word ptr [rbp+110h+var_D0], dx
0x18000363f  jz      short loc_18000364A
  ... truncated ...
```
