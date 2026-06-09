# CfReportSyncStatus

- ea: `0x1800073b0`
- end: `0x1800079ba`
- name: `CfReportSyncStatus`
- size: `1546`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x18000446c`
- `0x1800073b0`
- `0x18000f6fc`
- `0x180011338`
- `0x1800118a4`
- `0x180011e18`
- `0x18001be5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800074ae`
- `ntdll!RtlNtStatusToDosError` at `0x180007611`
- `ntdll!RtlNtStatusToDosError` at `0x1800076a1`
- `ntdll!RtlNtStatusToDosError` at `0x180007738`
- `ntdll!RtlNtStatusToDosError` at `0x1800077db`
- `ntdll!RtlNtStatusToDosError` at `0x1800078af`
- `ntdll!RtlNtStatusToDosError` at `0x1800074ae`
- `ntdll!RtlNtStatusToDosError` at `0x180007611`
- `ntdll!RtlNtStatusToDosError` at `0x1800076a1`
- `ntdll!RtlNtStatusToDosError` at `0x180007738`
- `ntdll!RtlNtStatusToDosError` at `0x1800077db`
- `ntdll!RtlNtStatusToDosError` at `0x1800078af`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007439`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007439`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007547`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007969`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007547`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007969`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000755c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000755c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007977`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007977`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007988`
- `FLTLIB!FilterSendMessage` at `0x180007904`
- `FLTLIB!FilterSendMessage` at `0x180007904`

## string_xrefs

- `0x1800076be`: `SetCldMsgCommand Failed`
- `0x1800074c8`: `CfpCreateFile Failed`
- `0x180007463`: `SyncRootPath Can't be NULL`

## pseudocode

```c
__int64 __fastcall CfReportSyncStatus(__int64 a1, char *a2)
{
  char *v2; // r15
  const WCHAR *v4; // rsi
  const WCHAR *v5; // r14
  _DWORD *v6; // rdi
  int SyncRootInfoByHandle; // ebx
  const wchar_t *v8; // rax
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  signed int v11; // eax
  DWORD v12; // r12d
  HANDLE ProcessHeap; // rax
  NTSTATUS v14; // r15d
  NTSTATUS v15; // ecx
  __int64 v16; // rcx
  unsigned int v17; // ecx
  signed int v18; // eax
  NTSTATUS v19; // ecx
  __int64 v20; // rcx
  __int64 v21; // rax
  signed int v22; // eax
  NTSTATUS v23; // ecx
  __int64 v24; // rcx
  HANDLE v25; // rdx
  __int64 v26; // rax
  signed int v27; // eax
  NTSTATUS v28; // ecx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  signed int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  size_t v35; // r8
  __int64 v36; // rcx
  char *v37; // rcx
  signed int v38; // eax
  HANDLE v39; // rax
  __int64 dwOutBufferSize; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+30h] [rbp-D0h]
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  __int64 v47; // [rsp+70h] [rbp-90h]
  unsigned __int64 UnbiasedTime; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  bool v53; // [rsp+A0h] [rbp-60h]
  _BYTE v54[4]; // [rsp+E0h] [rbp-20h] BYREF
  char v55; // [rsp+E4h] [rbp-1Ch] BYREF
  char v56; // [rsp+2E4h] [rbp+1E4h] BYREF

  v2 = a2;
  v47 = a1;
  hObject = (HANDLE)-1LL;
  UnbiasedTime = 0;
  memset_0(v54, 0, 0x404u);
  v46 = 0;
  BytesReturned = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  memset_0(&v49, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  SyncRootInfoByHandle = a1 == 0 ? 0x57 : 0;
  if ( !v47 )
    SyncRootInfoByHandle |= 0x80070000;
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"SyncRootPath Can't be NULL";
    goto LABEL_90;
  }
  SyncRootInfoByHandle = GlobalPortInit(1);
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"GlobalPortInit Failed";
    goto LABEL_90;
  }
  v10 = CfpCreateFile(v47, v9, 0, 7u, dwOutBufferSize, 0x21u, v42, &hObject);
  v11 = RtlNtStatusToDosError(v10);
  SyncRootInfoByHandle = v11;
  if ( v11 > 0 )
    SyncRootInfoByHandle = (unsigned __int16)v11 | 0x80070000;
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"CfpCreateFile Failed";
    goto LABEL_90;
  }
  SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(hObject, 0);
  if ( SyncRootInfoByHandle <= -1 )
  {
    v8 = L"CfpGetSyncRootInfoByHandle Failed";
    goto LABEL_90;
  }
  v5 = (const WCHAR *)&v56;
  v4 = (const WCHAR *)&v55;
  v12 = 224;
  if ( (int)CfpGetSyncRootInfoByHandle(hObject, 0) < 0 )
  {
    v5 = 0;
    v4 = 0;
  }
  if ( v2 )
    v12 = *(_DWORD *)v2 + 224;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, v12);
  SyncRootInfoByHandle = v6 == 0 ? 8 : 0;
  if ( !v6 )
    SyncRootInfoByHandle |= 0x80070000;
  if ( SyncRootInfoByHandle > -1 )
  {
    *(_QWORD *)v6 = 1886219331;
    v6[2] = 200;
    v6[3] = 1507328;
    memset_0(v6 + 4, 0, 0xB8u);
    if ( v12 < 0x18 )
    {
      v14 = -1073741789;
LABEL_23:
      v15 = -1073741789;
      goto LABEL_28;
    }
    v14 = -1073741789;
    if ( *((_WORD *)v6 + 7) )
    {
      v16 = (unsigned int)v6[2];
      if ( ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v12 )
        goto LABEL_23;
      v17 = (v16 + 3) & 0xFFFFFFFC;
      v6[2] = v17;
      v6[5] = v17;
      v6[4] = 65543;
      *((_BYTE *)v6 + v17) = 1;
      ++v6[2];
      v15 = 0;
    }
    else
    {
      v15 = -1073741811;
    }
LABEL_28:
    v18 = RtlNtStatusToDosError(v15);
    SyncRootInfoByHandle = v18;
    if ( v18 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v18 | 0x80070000;
    if ( SyncRootInfoByHandle <= -1 )
    {
      v8 = L"SetVersion Failed";
      goto LABEL_89;
    }
    if ( v12 < 0x18 )
      goto LABEL_33;
    if ( *((_WORD *)v6 + 7) > 1u )
    {
      if ( v12 < 0x20 || (v20 = (unsigned int)v6[2], ((v20 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 > v12) )
      {
LABEL_33:
        v19 = -1073741789;
        goto LABEL_41;
      }
      v21 = ((_DWORD)v20 + 3) & 0xFFFFFFFC;
      v6[2] = v21;
      if ( *((_WORD *)v6 + 12) )
        *((_WORD *)v6 + 6) |= 1u;
      v6[6] = 131080;
      v19 = 0;
      v6[7] = v21;
      *(_WORD *)((char *)v6 + v21) = 7;
      v6[2] += 2;
    }
    else
    {
      v19 = -1073741811;
    }
LABEL_41:
    v22 = RtlNtStatusToDosError(v19);
    SyncRootInfoByHandle = v22;
    if ( v22 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v22 | 0x80070000;
    if ( SyncRootInfoByHandle <= -1 )
    {
      v8 = L"SetCldMsgCommand Failed";
      goto LABEL_89;
    }
    if ( v12 < 0x18 )
      goto LABEL_46;
    if ( *((_WORD *)v6 + 7) > 2u )
    {
      if ( v12 < 0x28 || (v24 = (unsigned int)v6[2], ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > v12) )
      {
LABEL_46:
        v23 = -1073741789;
        goto LABEL_54;
      }
      v25 = hObject;
      v26 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
      v6[2] = v26;
      if ( *((_WORD *)v6 + 16) )
        *((_WORD *)v6 + 6) |= 1u;
      v6[8] = 524299;
      v23 = 0;
      v6[9] = v26;
      *(_QWORD *)((char *)v6 + v26) = v25;
      v6[2] += 8;
    }
    else
    {
      v23 = -1073741811;
    }
LABEL_54:
    v27 = RtlNtStatusToDosError(v23);
    SyncRootInfoByHandle = v27;
    if ( v27 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v27 | 0x80070000;
    if ( SyncRootInfoByHandle <= -1 )
    {
      v8 = L"SetCldDsMsgSyncRoot Failed";
      goto LABEL_89;
    }
    if ( v12 >= 0x18 )
    {
      if ( *((_WORD *)v6 + 7) <= 0x16u )
      {
        v28 = -1073741811;
        goto LABEL_67;
      }
      if ( v12 >= 0xC8 )
      {
        v29 = (unsigned int)v6[2];
        if ( ((v29 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v12 )
        {
          v30 = v46;
          v31 = ((_DWORD)v29 + 3) & 0xFFFFFFFC;
          v6[2] = v31;
          if ( *((_WORD *)v6 + 96) )
            *((_WORD *)v6 + 6) |= 1u;
          v6[48] = 524294;
          v28 = 0;
          v6[49] = v31;
          *(_QWORD *)((char *)v6 + v31) = v30;
          v6[2] += 8;
          goto LABEL_67;
        }
      }
    }
    v28 = -1073741789;
LABEL_67:
    v32 = RtlNtStatusToDosError(v28);
    SyncRootInfoByHandle = v32;
    if ( v32 > 0 )
      SyncRootInfoByHandle = (unsigned __int16)v32 | 0x80070000;
    if ( SyncRootInfoByHandle
      && (TlmChk(v33, 4202, "CfReportSyncStatus", (unsigned int)SyncRootInfoByHandle), SyncRootInfoByHandle < 0) )
    {
      v8 = L"SetCldDsMsgSyncRootFileId Failed";
    }
    else
    {
      v52 = v46;
      if ( !a2 )
        goto LABEL_87;
      if ( v12 >= 0x18 )
      {
        if ( *((_WORD *)v6 + 7) > 9u )
        {
          if ( v12 >= 0x60 )
          {
            v34 = (unsigned int)v6[2];
            v35 = *(unsigned __int16 *)a2;
            if ( v35 + ((v34 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v12 )
            {
              if ( *((_WORD *)v6 + 44) )
                *((_WORD *)v6 + 6) |= 1u;
              v36 = ((_DWORD)v34 + 3) & 0xFFFFFFFC;
              v6[2] = v36;
              v6[23] = v36;
              v37 = (char *)v6 + v36;
              *((_WORD *)v6 + 44) = 17;
              *((_WORD *)v6 + 45) = v35;
              if ( v37 != a2 )
                memcpy_0(v37, a2, v35);
              v14 = 0;
              v6[2] += *((unsigned __int16 *)v6 + 45);
            }
          }
        }
        else
        {
          v14 = -1073741811;
        }
      }
      v38 = RtlNtStatusToDosError(v14);
      SyncRootInfoByHandle = v38;
      if ( v38 > 0 )
        SyncRootInfoByHandle = (unsigned __int16)v38 | 0x80070000;
      if ( SyncRootInfoByHandle <= -1 )
      {
        v8 = L"SetCldDsMsgSyncStatus Failed";
      }
      else
      {
LABEL_87:
        v6[1] = 0;
        *((_WORD *)v6 + 6) &= ~2u;
        SyncRootInfoByHandle = FilterSendMessage(hPort, v6, v12, 0, 0, &BytesReturned);
        v8 = L"FilterSendMessage Failed";
        if ( SyncRootInfoByHandle > -1 )
          v8 = 0;
      }
    }
    goto LABEL_89;
  }
  v8 = L"HeapAlloc CldCmdReportStatus failed";
LABEL_89:
  v2 = a2;
LABEL_90:
  v50 = v8;
  v53 = v2 != 0;
  v51 = v47;
  TlmLogApiReliability(0x1Du, 0, v47, v4, v5, UnbiasedTime, &v49, SyncRootInfoByHandle);
  if ( v6 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v6);
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)SyncRootInfoByHandle;
}

```

## disassembly

```asm
0x1800073b0  mov     [rsp-8+arg_10], rbx
0x1800073b5  push    rbp
0x1800073b6  push    rsi
0x1800073b7  push    rdi
0x1800073b8  push    r12
0x1800073ba  push    r13
0x1800073bc  push    r14
0x1800073be  push    r15
0x1800073c0  lea     rbp, [rsp-400h]
0x1800073c8  sub     rsp, 500h
0x1800073cf  mov     rax, cs:__security_cookie
0x1800073d6  xor     rax, rsp
0x1800073d9  mov     [rbp+430h+var_40], rax
0x1800073e0  mov     r15, rdx
0x1800073e3  mov     [rsp+530h+Src], rdx
0x1800073e8  mov     rbx, rcx
0x1800073eb  mov     [rsp+530h+var_4C0], rcx
0x1800073f0  xor     r13d, r13d
0x1800073f3  mov     [rsp+530h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800073fc  xor     edx, edx; Val
0x1800073fe  mov     [rsp+530h+UnbiasedTime], r13
0x180007403  lea     rcx, [rbp+430h+var_450]; void *
0x180007407  mov     r8d, 404h; Size
0x18000740d  call    memset_0
0x180007412  xor     edx, edx; Val
0x180007414  mov     [rsp+530h+var_4C8], r13
0x180007419  lea     r8d, [r13+58h]; Size
0x18000741d  mov     [rsp+530h+BytesReturned], r13d
0x180007422  lea     rcx, [rbp+430h+var_4B0]; void *
0x180007426  mov     esi, r13d
0x180007429  mov     r14d, r13d
0x18000742c  mov     edi, r13d
0x18000742f  call    memset_0
0x180007434  lea     rcx, [rsp+530h+UnbiasedTime]; UnbiasedTime
0x180007439  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000743f  mov     r12, [rsp+530h+var_4C0]
0x180007444  mov     rax, rbx
0x180007447  neg     rax
0x18000744a  sbb     ebx, ebx
0x18000744c  not     ebx
0x18000744e  and     ebx, 57h
0x180007451  mov     eax, ebx
0x180007453  or      eax, 80070000h
0x180007458  test    r12, r12
0x18000745b  cmovz   ebx, eax
0x18000745e  cmp     ebx, 0FFFFFFFFh
0x180007461  jg      short loc_18000746F
0x180007463  lea     rax, aSyncrootpathCa_0; "SyncRootPath Can't be NULL"
0x18000746a  jmp     loc_180007920
0x18000746f  mov     cl, 1
0x180007471  call    GlobalPortInit
0x180007476  mov     ebx, eax
0x180007478  cmp     eax, 0FFFFFFFFh
0x18000747b  jg      short loc_180007489
0x18000747d  lea     rax, aGlobalportinit; "GlobalPortInit Failed"
0x180007484  jmp     loc_180007920
0x180007489  lea     rax, [rsp+530h+hObject]
0x18000748e  mov     r9d, 7
0x180007494  mov     [rsp+530h+var_4F8], rax
0x180007499  xor     r8d, r8d
0x18000749c  mov     rcx, r12
0x18000749f  mov     dword ptr [rsp+530h+lpBytesReturned], 21h ; '!'
0x1800074a7  call    CfpCreateFile
0x1800074ac  mov     ecx, eax; Status
0x1800074ae  call    cs:__imp_RtlNtStatusToDosError
0x1800074b4  mov     ebx, eax
0x1800074b6  test    eax, eax
0x1800074b8  jle     short loc_1800074C3
0x1800074ba  movzx   ebx, ax
0x1800074bd  or      ebx, 80070000h
0x1800074c3  cmp     ebx, 0FFFFFFFFh
0x1800074c6  jg      short loc_1800074D4
0x1800074c8  lea     rax, aCfpcreatefileF; "CfpCreateFile Failed"
0x1800074cf  jmp     loc_180007920
0x1800074d4  mov     rcx, [rsp+530h+hObject]; hFile
0x1800074d9  lea     r8, [rsp+530h+var_4C8]
0x1800074de  mov     r9d, 8
0x1800074e4  mov     qword ptr [rsp+530h+dwOutBufferSize], r13; __int64
0x1800074e9  xor     edx, edx
0x1800074eb  call    CfpGetSyncRootInfoByHandle
0x1800074f0  mov     ebx, eax
0x1800074f2  cmp     eax, 0FFFFFFFFh
0x1800074f5  jg      short loc_180007503
0x1800074f7  lea     rax, aCfpgetsyncroot; "CfpGetSyncRootInfoByHandle Failed"
0x1800074fe  jmp     loc_180007920
0x180007503  mov     rcx, [rsp+530h+hObject]; hFile
0x180007508  lea     r8, [rbp+430h+var_450]
0x18000750c  mov     r9d, 404h
0x180007512  mov     qword ptr [rsp+530h+dwOutBufferSize], r13; __int64
0x180007517  mov     edx, 2
0x18000751c  call    CfpGetSyncRootInfoByHandle
0x180007521  test    eax, eax
0x180007523  lea     r14, [rbp+430h+var_24C]
0x18000752a  lea     rsi, [rbp+430h+var_44C]
0x18000752e  mov     r12d, 0E0h
0x180007534  cmovs   r14, r13
0x180007538  cmovs   rsi, r13
0x18000753c  test    r15, r15
0x18000753f  jz      short loc_180007544
0x180007541  add     r12d, [r15]
0x180007544  mov     r13d, r12d
0x180007547  call    cs:__imp_GetProcessHeap
0x18000754d  mov     r15d, 8
0x180007553  mov     r8d, r12d; dwBytes
0x180007556  mov     rcx, rax; hHeap
0x180007559  mov     edx, r15d; dwFlags
0x18000755c  call    cs:__imp_HeapAlloc
0x180007562  mov     rdi, rax
0x180007565  neg     rax
0x180007568  sbb     ebx, ebx
0x18000756a  not     ebx
0x18000756c  and     ebx, r15d
0x18000756f  xor     r15d, r15d
0x180007572  mov     eax, ebx
0x180007574  or      eax, 80070000h
0x180007579  test    rdi, rdi
0x18000757c  cmovz   ebx, eax
0x18000757f  cmp     ebx, 0FFFFFFFFh
0x180007582  jg      short loc_180007590
0x180007584  lea     rax, aHeapallocCldcm; "HeapAlloc CldCmdReportStatus failed"
0x18000758b  jmp     loc_18000791B
0x180007590  xor     edx, edx; Val
0x180007592  mov     qword ptr [rdi], 706D6C43h
0x180007599  mov     r8d, 0B8h; Size
0x18000759f  mov     dword ptr [rdi+8], 0C8h
0x1800075a6  lea     rcx, [rdi+10h]; void *
0x1800075aa  mov     dword ptr [rdi+0Ch], 170000h
0x1800075b1  call    memset_0
0x1800075b6  cmp     r12d, 18h
0x1800075ba  jnb     short loc_1800075C7
0x1800075bc  mov     r15d, 0C0000023h
0x1800075c2  mov     ecx, r15d
0x1800075c5  jmp     short loc_180007611
0x1800075c7  mov     eax, r15d
0x1800075ca  mov     r15d, 0C0000023h
0x1800075d0  cmp     ax, [rdi+0Eh]
0x1800075d4  jb      short loc_1800075DC
0x1800075d6  lea     ecx, [r15-16h]
0x1800075da  jmp     short loc_180007611
0x1800075dc  mov     ecx, [rdi+8]
0x1800075df  mov     edx, 1
0x1800075e4  lea     rax, [rcx+3]
0x1800075e8  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800075ec  add     rax, rdx
0x1800075ef  cmp     rax, r13
0x1800075f2  ja      short loc_1800075C2
0x1800075f4  lea     eax, [rcx+3]
0x1800075f7  and     eax, 0FFFFFFFCh
0x1800075fa  mov     ecx, eax
0x1800075fc  mov     [rdi+8], ecx
0x1800075ff  mov     [rdi+14h], ecx
0x180007602  mov     dword ptr [rdi+10h], 10007h
0x180007609  mov     [rax+rdi], dl
0x18000760c  add     [rdi+8], edx
0x18000760f  xor     ecx, ecx; Status
0x180007611  call    cs:__imp_RtlNtStatusToDosError
0x180007617  xor     edx, edx
0x180007619  mov     ebx, eax
0x18000761b  test    eax, eax
0x18000761d  jle     short loc_180007628
0x18000761f  movzx   ebx, ax
0x180007622  or      ebx, 80070000h
0x180007628  cmp     ebx, 0FFFFFFFFh
0x18000762b  jg      short loc_180007639
0x18000762d  lea     rax, aSetversionFail_0; "SetVersion Failed"
0x180007634  jmp     loc_18000791B
0x180007639  cmp     r12d, 18h
0x18000763d  jnb     short loc_180007644
0x18000763f  mov     ecx, r15d
0x180007642  jmp     short loc_1800076A1
0x180007644  mov     r9d, 1
0x18000764a  cmp     r9w, [rdi+0Eh]
0x18000764f  jb      short loc_180007658
0x180007651  mov     ecx, 0C000000Dh
0x180007656  jmp     short loc_1800076A1
0x180007658  cmp     r12d, 20h ; ' '
0x18000765c  jb      short loc_18000763F
0x18000765e  mov     ecx, [rdi+8]
0x180007661  mov     r8d, 2
0x180007667  lea     rax, [rcx+3]
0x18000766b  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000766f  add     rax, r8
0x180007672  cmp     rax, r13
0x180007675  ja      short loc_18000763F
0x180007677  lea     eax, [rcx+3]
0x18000767a  and     eax, 0FFFFFFFCh
0x18000767d  mov     [rdi+8], eax
0x180007680  cmp     [rdi+18h], dx
0x180007684  jz      short loc_18000768B
0x180007686  or      [rdi+0Ch], r9w
0x18000768b  mov     dword ptr [rdi+18h], 20008h
0x180007692  mov     ecx, edx; Status
0x180007694  mov     [rdi+1Ch], eax
0x180007697  mov     word ptr [rax+rdi], 7
0x18000769d  add     [rdi+8], r8d
0x1800076a1  call    cs:__imp_RtlNtStatusToDosError
0x1800076a7  xor     r8d, r8d
0x1800076aa  mov     ebx, eax
0x1800076ac  test    eax, eax
0x1800076ae  jle     short loc_1800076B9
0x1800076b0  movzx   ebx, ax
0x1800076b3  or      ebx, 80070000h
0x1800076b9  cmp     ebx, 0FFFFFFFFh
0x1800076bc  jg      short loc_1800076CA
0x1800076be  lea     rax, aSetcldmsgcomma_0; "SetCldMsgCommand Failed"
0x1800076c5  jmp     loc_18000791B
0x1800076ca  cmp     r12d, 18h
0x1800076ce  jnb     short loc_1800076D5
0x1800076d0  mov     ecx, r15d
0x1800076d3  jmp     short loc_180007738
0x1800076d5  mov     eax, 2
0x1800076da  cmp     ax, [rdi+0Eh]
0x1800076de  jb      short loc_1800076E7
0x1800076e0  mov     ecx, 0C000000Dh
0x1800076e5  jmp     short loc_180007738
0x1800076e7  cmp     r12d, 28h ; '('
0x1800076eb  jb      short loc_1800076D0
0x1800076ed  mov     ecx, [rdi+8]
0x1800076f0  mov     r9d, 8
0x1800076f6  lea     rax, [rcx+3]
0x1800076fa  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800076fe  add     rax, r9
0x180007701  cmp     rax, r13
0x180007704  ja      short loc_1800076D0
0x180007706  mov     rdx, [rsp+530h+hObject]
0x18000770b  lea     eax, [rcx+3]
0x18000770e  and     eax, 0FFFFFFFCh
0x180007711  mov     [rdi+8], eax
0x180007714  cmp     [rdi+20h], r8w
0x180007719  jz      short loc_180007723
0x18000771b  lea     ecx, [r9-7]
0x18000771f  or      [rdi+0Ch], cx
0x180007723  mov     dword ptr [rdi+20h], 8000Bh
0x18000772a  mov     ecx, r8d; Status
0x18000772d  mov     [rdi+24h], eax
0x180007730  mov     [rax+rdi], rdx
0x180007734  add     [rdi+8], r9d
0x180007738  call    cs:__imp_RtlNtStatusToDosError
0x18000773e  xor     r8d, r8d
0x180007741  mov     ebx, eax
0x180007743  test    eax, eax
0x180007745  jle     short loc_180007750
0x180007747  movzx   ebx, ax
0x18000774a  or      ebx, 80070000h
0x180007750  cmp     ebx, 0FFFFFFFFh
0x180007753  jg      short loc_180007761
0x180007755  lea     rax, aSetclddsmsgsyn_0; "SetCldDsMsgSyncRoot Failed"
0x18000775c  jmp     loc_18000791B
0x180007761  cmp     r12d, 18h
0x180007765  jnb     short loc_18000776C
0x180007767  mov     ecx, r15d
0x18000776a  jmp     short loc_1800077DB
0x18000776c  mov     eax, 16h
0x180007771  cmp     ax, [rdi+0Eh]
0x180007775  jb      short loc_18000777E
0x180007777  mov     ecx, 0C000000Dh
0x18000777c  jmp     short loc_1800077DB
0x18000777e  cmp     r12d, 0C8h
0x180007785  jb      short loc_180007767
0x180007787  mov     ecx, [rdi+8]
0x18000778a  mov     r9d, 8
0x180007790  lea     rax, [rcx+3]
0x180007794  and     rax, 0FFFFFFFFFFFFFFFCh
0x180007798  add     rax, r9
0x18000779b  cmp     rax, r13
0x18000779e  ja      short loc_180007767
0x1800077a0  mov     rdx, [rsp+530h+var_4C8]
0x1800077a5  lea     eax, [rcx+3]
0x1800077a8  and     eax, 0FFFFFFFCh
0x1800077ab  mov     [rdi+8], eax
0x1800077ae  cmp     [rdi+0C0h], r8w
0x1800077b6  jz      short loc_1800077C0
0x1800077b8  lea     ecx, [r9-7]
0x1800077bc  or      [rdi+0Ch], cx
0x1800077c0  mov     dword ptr [rdi+0C0h], 80006h
0x1800077ca  mov     ecx, r8d; Status
0x1800077cd  mov     [rdi+0C4h], eax
0x1800077d3  mov     [rax+rdi], rdx
0x1800077d7  add     [rdi+8], r9d
0x1800077db  call    cs:__imp_RtlNtStatusToDosError
0x1800077e1  xor     r9d, r9d
0x1800077e4  mov     ebx, eax
0x1800077e6  test    eax, eax
0x1800077e8  jle     short loc_1800077F3
0x1800077ea  movzx   ebx, ax
0x1800077ed  or      ebx, 80070000h
0x1800077f3  test    ebx, ebx
0x1800077f5  jz      short loc_18000781E
0x1800077f7  mov     r9d, ebx
0x1800077fa  lea     r8, aCfreportsyncst_0; "CfReportSyncStatus"
0x180007801  mov     edx, 106Ah
0x180007806  call    TlmChk
0x18000780b  xor     r9d, r9d
0x18000780e  test    ebx, ebx
0x180007810  jns     short loc_18000781E
0x180007812  lea     rax, aSetclddsmsgsyn_1; "SetCldDsMsgSyncRootFileId Failed"
0x180007819  jmp     loc_18000791B
0x18000781e  mov     rdx, [rsp+530h+Src]; Src
0x180007823  mov     rax, [rsp+530h+var_4C8]
0x180007828  mov     [rbp+430h+var_498], rax
  ... truncated ...
```
