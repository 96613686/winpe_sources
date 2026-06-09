# BCryptVerifySignature

- ea: `0x180010680`
- end: `0x180010ecb`
- name: `BCryptVerifySignature`
- size: `2123`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, void *pPaddingInfo, PUCHAR pbHash, ULONG cbHash, PUCHAR pbSignature, ULONG cbSignature, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a7c`
- `0x18000cae4`
- `0x180010680`
- `0x180011104`
- `0x1800159dc`
- `0x180017420`
- `0x18001b785`
- `0x18001b7a9`
- `0x18001b7e0`
- `0x18001c010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180010963`
- `ntdll!NtQueryInformationProcess` at `0x180010bc8`
- `ntdll!NtQueryInformationProcess` at `0x180010963`
- `ntdll!NtQueryInformationProcess` at `0x180010bc8`
- `ntdll!RtlDllShutdownInProgress` at `0x180010bf6`
- `ntdll!RtlDllShutdownInProgress` at `0x180010bf6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010e7a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010e7a`

## string_xrefs

- `0x180010778`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800108ef`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800109c4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180010a42`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180010af2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180010b32`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180010b6b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptVerifySignature(
        BCRYPT_KEY_HANDLE hKey,
        void *pPaddingInfo,
        PUCHAR pbHash,
        ULONG cbHash,
        PUCHAR pbSignature,
        ULONG cbSignature,
        ULONG dwFlags)
{
  ULONG *v7; // r14
  int *v8; // r13
  __int64 v9; // r10
  _BYTE *v11; // rcx
  NTSTATUS v12; // edi
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, __int64); // rax
  int v15; // edx
  __int64 (__fastcall *v16)(_QWORD, PUCHAR, _QWORD, _QWORD, _QWORD, _DWORD, ULONG *, ULONG, int *, _DWORD); // r14
  ULONG *v17; // rbx
  ULONG v18; // edx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  ULONG *v23; // rax
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rax
  bool v28; // zf
  int v29; // ebx
  unsigned __int8 v30; // r8
  char *v31; // r9
  char *v32; // rax
  char v33; // cl
  __int64 v36; // rcx
  int v37; // edx
  __int64 v38; // rcx
  __int64 v40; // [rsp+0h] [rbp-60h] BYREF
  PULONG ReturnLength; // [rsp+20h] [rbp-40h]
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-38h]
  __int64 v43; // [rsp+30h] [rbp-30h]
  ULONG *v44; // [rsp+60h] [rbp+0h] BYREF
  ULONG v45; // [rsp+68h] [rbp+8h] BYREF
  PUCHAR v46; // [rsp+70h] [rbp+10h] BYREF
  __int64 v47; // [rsp+78h] [rbp+18h] BYREF
  int v48; // [rsp+80h] [rbp+20h] BYREF
  __int64 v49; // [rsp+88h] [rbp+28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+90h] [rbp+30h] BYREF
  _QWORD v51[2]; // [rsp+A0h] [rbp+40h] BYREF
  __int128 v52; // [rsp+B0h] [rbp+50h]
  __int128 v53; // [rsp+C0h] [rbp+60h]
  __int128 v54; // [rsp+D0h] [rbp+70h]
  _DWORD ProcessInformation[44]; // [rsp+E0h] [rbp+80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v56; // [rsp+190h] [rbp+130h] BYREF
  char *v57; // [rsp+1A0h] [rbp+140h]
  unsigned int v58; // [rsp+1A8h] [rbp+148h]
  int v59; // [rsp+1ACh] [rbp+14Ch]
  __int64 *v60; // [rsp+1B0h] [rbp+150h]
  _QWORD v61[8]; // [rsp+1B8h] [rbp+158h]
  int v62; // [rsp+1F8h] [rbp+198h]
  int v63; // [rsp+1FCh] [rbp+19Ch]
  int *v64; // [rsp+200h] [rbp+1A0h]
  int v65; // [rsp+208h] [rbp+1A8h]
  int v66; // [rsp+20Ch] [rbp+1ACh]

  v7 = 0;
  v48 = 0;
  v8 = 0;
  v45 = cbHash;
  v9 = (__int64)pPaddingInfo;
  v46 = pbHash;
  v47 = (__int64)pPaddingInfo;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqqdqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      pbHash,
      hKey,
      pPaddingInfo,
      pbHash,
      cbHash,
      pbSignature,
      cbSignature,
      dwFlags);
    v11 = WPP_GLOBAL_Control;
    v9 = v47;
    LODWORD(pbHash) = (_DWORD)v46;
  }
  if ( !hKey || *(_DWORD *)hKey < 0x20u || *((_DWORD *)hKey + 1) != 1431655762 )
  {
    v12 = -1073741816;
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
    {
      LODWORD(v43) = 6866;
      UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
      LODWORD(ReturnLength) = -1073741816;
      goto LABEL_11;
    }
    goto LABEL_42;
  }
  if ( !pbSignature )
  {
    v12 = -1073741811;
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
    {
      LODWORD(v43) = 6873;
      UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
      LODWORD(ReturnLength) = -1073741811;
LABEL_11:
      WPP_SF_sDsd(
        *((_QWORD *)v11 + 2),
        (_DWORD)pPaddingInfo,
        (_DWORD)pbHash,
        (unsigned int)"Status",
        (char)ReturnLength,
        (__int64)UserData,
        v43);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v13 = *((_QWORD *)hKey + 1);
  LODWORD(pPaddingInfo) = *(_DWORD *)(v13 + 36);
  v8 = (int *)(v13 + 444);
  if ( (_DWORD)pPaddingInfo == 5 )
  {
    v14 = *(__int64 (__fastcall **)(__int64, __int64))(v13 + 112);
    goto LABEL_62;
  }
  if ( (_DWORD)pPaddingInfo != 3 )
  {
    v12 = -1073741637;
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
    {
      LODWORD(v43) = 6908;
      UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
      LODWORD(ReturnLength) = -1073741637;
      goto LABEL_11;
    }
    goto LABEL_42;
  }
  v15 = *(_DWORD *)(v13 + 440);
  if ( (v15 & 1) != 0 && ((dwFlags & 2) == 0 || (v15 & 4) == 0) && ((dwFlags & 8) == 0 || (v15 & 0x10) == 0) )
  {
    v16 = *(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD, _QWORD, _DWORD, ULONG *, ULONG, int *, _DWORD))(v13 + 104);
    v17 = 0;
    v44 = 0;
    if ( !cbSignature )
      goto LABEL_32;
    if ( cbSignature > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)cbSignature + g_ulAdditionalProbeSize + 8 < cbSignature )
    {
      v17 = v44;
      goto LABEL_32;
    }
    if ( (unsigned int)VerifyStackAvailable(cbSignature + g_ulAdditionalProbeSize + 8) )
    {
      v19 = cbSignature + 23LL;
      if ( v19 <= (unsigned __int64)cbSignature + 8 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      v17 = (ULONG *)&v44;
      v44 = (ULONG *)&v44;
      if ( &v40 != (__int64 *)-96LL )
      {
        v17 = &v45;
        v44 = &v45;
        if ( &v45 )
          goto LABEL_35;
        v11 = WPP_GLOBAL_Control;
LABEL_32:
        v18 = cbSignature + 8;
        if ( (unsigned __int64)cbSignature + 8 < cbSignature )
          goto LABEL_36;
        v23 = (ULONG *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(cbSignature + 8LL);
        v44 = v23;
        v17 = v23;
        if ( v23 )
        {
          v17 = v23 + 2;
          *v23 = 1885431112;
          v44 = v23 + 2;
        }
LABEL_35:
        v11 = WPP_GLOBAL_Control;
LABEL_36:
        if ( v17 )
        {
          if ( v16 )
          {
            v12 = v16(*((_QWORD *)hKey + 2), pbSignature, cbSignature, 0, 0, 0, v17, cbSignature, &v48, 0);
            if ( v12 >= 0 )
            {
              v12 = CheckSignaturePadding(dwFlags, v47, (_DWORD)v46, v45, (__int64)v17, cbSignature);
              if ( v12 >= 0 )
              {
                v7 = v44;
                goto LABEL_67;
              }
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
LABEL_41:
                v7 = v44;
                goto LABEL_42;
              }
              LODWORD(v43) = 6962;
            }
            else
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_41;
              }
              LODWORD(v43) = 6949;
            }
            UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
            LODWORD(ReturnLength) = v12;
          }
          else
          {
            v12 = -1073741595;
            if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || (v11[28] & 1) == 0 )
              goto LABEL_41;
            LODWORD(v43) = 6933;
            UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
            LODWORD(ReturnLength) = -1073741595;
          }
        }
        else
        {
          v12 = -1073741801;
          if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || (v11[28] & 1) == 0 )
            goto LABEL_41;
          LODWORD(v43) = 6926;
          UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
          LODWORD(ReturnLength) = -1073741801;
        }
        WPP_SF_sDsd(
          *((_QWORD *)v11 + 2),
          v18,
          (_DWORD)pbHash,
          (unsigned int)"Status",
          (char)ReturnLength,
          (__int64)UserData,
          v43);
        goto LABEL_41;
      }
    }
    else
    {
      v17 = v44;
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  v14 = *(__int64 (__fastcall **)(__int64, __int64))(v13 + 152);
LABEL_62:
  v26 = *((_QWORD *)hKey + 2);
  LODWORD(v43) = dwFlags;
  LODWORD(UserData) = cbSignature;
  ReturnLength = (PULONG)pbSignature;
  v12 = v14(v26, v9);
  if ( v12 >= 0 )
  {
LABEL_67:
    v12 = 0;
    goto LABEL_42;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LODWORD(v43) = 6977;
    UserData = (PEVENT_DATA_DESCRIPTOR)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(ReturnLength) = v12;
    goto LABEL_11;
  }
LABEL_42:
  LOBYTE(v24) = g_TrustedEnvironment;
  v25 = -1;
  if ( !g_TrustedEnvironment )
  {
    memset_0(ProcessInformation, 0, sizeof(ProcessInformation));
    if ( NtQueryInformationProcess(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           ProcessPriorityBoost|0x40,
           ProcessInformation,
           0xB0u,
           0) < 0 )
    {
      v51[1] = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      v51[0] = 64;
      if ( NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBasicInformation, v51, 0x40u, 0) < 0
        || (v24 = 4, (SBYTE8(v54) & 0x80u) == 0) )
      {
        v24 = 1;
      }
    }
    else if ( (unsigned int)(ProcessInformation[0] - 16) <= 1 )
    {
      v24 = 16;
    }
    else
    {
      v24 = 1;
      if ( ProcessInformation[0] == 1 )
        v24 = 8;
    }
    g_TrustedEnvironment = v24;
  }
  if ( (v24 & 1) != 0
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_180024050 > 5
    && (qword_180024060 & 0x400000000000LL) != 0
    && (qword_180024068 & 0x400000000000LL) == qword_180024068 )
  {
    v47 = 1;
    v60 = &v47;
    v61[0] = 8;
    v61[1] = &v49;
    v61[3] = &v45;
    v61[5] = &v46;
    v27 = -1;
    v49 = 0x1000000;
    v61[2] = 8;
    v45 = v12;
    v61[4] = 4;
    LODWORD(v46) = 0;
    v61[6] = 4;
    do
      v28 = g_processImageName[++v27] == 0;
    while ( !v28 );
    v61[7] = g_processImageName;
    v62 = 2 * v27 + 2;
    v63 = 0;
    if ( v8 )
    {
      do
        v28 = *((_WORD *)v8 + ++v25) == 0;
      while ( !v28 );
      v29 = 2 * v25 + 2;
    }
    else
    {
      v8 = &dword_18001E7A4;
      v29 = 2;
    }
    *(_DWORD *)&EventDescriptor.Level = 5;
    v56.Ptr = (ULONGLONG)off_180024058;
    v64 = v8;
    v65 = v29;
    v66 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x400000000000LL;
    v56.Size = *(unsigned __int16 *)off_180024058;
    v57 = byte_18001F763;
    v56.Reserved = 2;
    v58 = 102;
    v59 = 1;
    LODWORD(v44) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180024078 == TlgAggregateInternalRegisteredProviderEtwCallback )
    {
      v30 = 0;
      v31 = &v57[v58];
      v32 = v57 + 2;
      do
        v33 = *v32++;
      while ( v33 < 0 );
      while ( *v32++ )
        ;
      if ( v32 >= v31 )
        goto LABEL_106;
      while ( 1 )
      {
        while ( *v32++ )
          ;
        LODWORD(v36) = (unsigned __int8)*v32;
        if ( (v36 & 0x80u) == 0LL )
          break;
        LOBYTE(v36) = v36 & 0x7F;
        if ( v32[1] >= 0 )
          break;
        v37 = (unsigned __int8)v32[2];
        v32 += 2;
        if ( (v37 & 0x80u) != 0 )
        {
          while ( (_BYTE)v37 == 0x80 )
          {
            v37 = (unsigned __int8)*++v32;
            if ( (v37 & 0x80u) == 0 )
              goto LABEL_101;
          }
          break;
        }
LABEL_101:
        if ( (_BYTE)v36 == 9 )
        {
          LODWORD(v36) = v37 - 113;
          if ( (unsigned __int8)(v37 - 113) <= 2u )
          {
            v38 = v30++;
            v36 = 2 * v38;
            BYTE5(v61[v36]) = v37;
            if ( v32 < v31 )
              continue;
          }
        }
        break;
      }
      if ( v30 )
        InsertEventEntryInLookUpTable(v36, (unsigned int)&EventDescriptor, 8, (unsigned int)&v56, v30);
      else
LABEL_106:
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &v56);
    }
  }
  if ( v7 && *(v7 - 2) == 1885431112 )
    ((void (__fastcall *)(ULONG *))g_pfnFree)(v7 - 2);
  return v12;
}

```

## disassembly

```asm
0x180010680  push    rbp
0x180010682  push    rbx
0x180010683  push    rsi
0x180010684  push    rdi
0x180010685  push    r12
0x180010687  push    r13
0x180010689  push    r14
0x18001068b  push    r15
0x18001068d  sub     rsp, 228h
0x180010694  lea     rbp, [rsp+60h]
0x180010699  mov     rax, cs:__security_cookie
0x1800106a0  xor     rax, rbp
0x1800106a3  mov     [rbp+200h+var_50], rax
0x1800106aa  mov     r12, [rbp+200h+pbSignature]
0x1800106b1  xor     r14d, r14d
0x1800106b4  mov     [rbp+200h+var_1E0], r14d
0x1800106b8  xor     r13d, r13d
0x1800106bb  mov     [rbp+200h+var_1F8], r9d
0x1800106bf  mov     r10, rdx
0x1800106c2  mov     [rbp+200h+var_1F0], r8
0x1800106c6  mov     rdi, rcx
0x1800106c9  mov     [rbp+200h+var_1E8], rdx
0x1800106cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d4  lea     rbx, WPP_GLOBAL_Control
0x1800106db  mov     r15d, [rbp+200h+dwFlags]
0x1800106e2  mov     esi, [rbp+200h+cbSignature]
0x1800106e8  cmp     rcx, rbx
0x1800106eb  jz      short loc_180010734
0x1800106ed  test    byte ptr [rcx+1Ch], 4
0x1800106f1  jz      short loc_180010734
0x1800106f3  mov     rcx, [rcx+10h]
0x1800106f7  mov     edx, 27h ; '''
0x1800106fc  mov     [rsp+260h+var_218], r15d
0x180010701  mov     dword ptr [rsp+260h+var_220], esi
0x180010705  mov     [rsp+260h+var_228], r12
0x18001070a  mov     dword ptr [rsp+260h+var_230], r9d
0x18001070f  mov     r9, rdi
0x180010712  mov     [rsp+260h+UserData], r8
0x180010717  mov     [rsp+260h+ReturnLength], r10
0x18001071c  call    WPP_SF_qqqdqdD
0x180010721  mov     rcx, cs:WPP_GLOBAL_Control
0x180010728  mov     r10, [rbp+200h+var_1E8]
0x18001072c  mov     r8, [rbp+200h+var_1F0]
0x180010730  mov     r9d, [rbp+200h+var_1F8]
0x180010734  test    rdi, rdi
0x180010737  jz      loc_180010B4B
0x18001073d  cmp     dword ptr [rdi], 20h ; ' '
0x180010740  jb      loc_180010B4B
0x180010746  cmp     dword ptr [rdi+4], 55555552h
0x18001074d  jnz     loc_180010B4B
0x180010753  test    r12, r12
0x180010756  jnz     short loc_1800107A1
0x180010758  mov     edi, 0C000000Dh
0x18001075d  cmp     rcx, rbx
0x180010760  jz      loc_180010917
0x180010766  test    byte ptr [rcx+1Ch], 1
0x18001076a  jz      loc_180010917
0x180010770  mov     dword ptr [rsp+260h+var_230], 1AD9h
0x180010778  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001077f  mov     [rsp+260h+UserData], rax
0x180010784  mov     dword ptr [rsp+260h+ReturnLength], 0C000000Dh
0x18001078c  mov     rcx, [rcx+10h]
0x180010790  lea     r9, aStatus; "Status"
0x180010797  call    WPP_SF_sDsd
0x18001079c  jmp     loc_180010917
0x1800107a1  mov     rax, [rdi+8]
0x1800107a5  mov     edx, [rax+24h]
0x1800107a8  lea     r13, [rax+1BCh]
0x1800107af  cmp     edx, 5
0x1800107b2  jnz     short loc_1800107BD
0x1800107b4  mov     rax, [rax+70h]
0x1800107b8  jmp     loc_180010AB0
0x1800107bd  cmp     edx, 3
0x1800107c0  jnz     loc_180010B12
0x1800107c6  mov     edx, [rax+1B8h]
0x1800107cc  test    dl, 1
0x1800107cf  jz      loc_180010AA9
0x1800107d5  test    r15b, 2
0x1800107d9  jz      short loc_1800107E4
0x1800107db  test    dl, 4
0x1800107de  jnz     loc_180010AA9
0x1800107e4  test    r15b, 8
0x1800107e8  jz      short loc_1800107F3
0x1800107ea  test    dl, 10h
0x1800107ed  jnz     loc_180010AA9
0x1800107f3  mov     r14, [rax+68h]
0x1800107f7  xor     ebx, ebx
0x1800107f9  mov     [rbp+200h+var_200], rbx
0x1800107fd  test    esi, esi
0x1800107ff  jz      loc_18001088E
0x180010805  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18001080c  mov     rbx, rsi
0x18001080f  ja      short loc_18001088A
0x180010811  mov     rdx, cs:g_ulAdditionalProbeSize
0x180010818  add     rdx, 8
0x18001081c  add     rdx, rbx
0x18001081f  cmp     rdx, rbx
0x180010822  jb      short loc_18001088A
0x180010824  mov     rcx, rdx
0x180010827  call    VerifyStackAvailable
0x18001082c  test    eax, eax
0x18001082e  jz      short loc_18001087D
0x180010830  lea     rax, [rsi+8]
0x180010834  lea     rcx, [rax+0Fh]
0x180010838  cmp     rcx, rax
0x18001083b  ja      short loc_180010847
0x18001083d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180010847  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001084b  mov     rax, rcx
0x18001084e  call    __chkstk_0
0x180010853  sub     rsp, rcx
0x180010856  lea     rbx, [rsp+260h+var_200]
0x18001085b  mov     [rbp+200h+var_200], rbx
0x18001085f  test    rbx, rbx
0x180010862  jz      short loc_180010881
0x180010864  mov     dword ptr [rbx], 6B637453h
0x18001086a  add     rbx, 8
0x18001086e  mov     [rbp+200h+var_200], rbx
0x180010872  jnz     short loc_1800108C0
0x180010874  mov     rcx, cs:WPP_GLOBAL_Control
0x18001087b  jmp     short loc_18001088E
0x18001087d  mov     rbx, [rbp+200h+var_200]
0x180010881  mov     rcx, cs:WPP_GLOBAL_Control
0x180010888  jmp     short loc_18001088E
0x18001088a  mov     rbx, [rbp+200h+var_200]
0x18001088e  lea     rdx, [rsi+8]
0x180010892  cmp     rdx, rsi
0x180010895  jb      short loc_1800108C7
0x180010897  mov     rax, cs:g_pfnAllocate
0x18001089e  mov     rcx, rdx
0x1800108a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a6  mov     [rbp+200h+var_200], rax
0x1800108aa  mov     rbx, rax
0x1800108ad  test    rax, rax
0x1800108b0  jz      short loc_1800108C0
0x1800108b2  add     rbx, 8
0x1800108b6  mov     dword ptr [rax], 70616548h
0x1800108bc  mov     [rbp+200h+var_200], rbx
0x1800108c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108c7  test    rbx, rbx
0x1800108ca  jnz     loc_180010998
0x1800108d0  mov     edi, 0C0000017h
0x1800108d5  lea     rax, WPP_GLOBAL_Control
0x1800108dc  cmp     rcx, rax
0x1800108df  jz      short loc_180010913
0x1800108e1  test    byte ptr [rcx+1Ch], 1
0x1800108e5  jz      short loc_180010913
0x1800108e7  mov     dword ptr [rsp+260h+var_230], 1B0Eh
0x1800108ef  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800108f6  mov     [rsp+260h+UserData], rax
0x1800108fb  mov     dword ptr [rsp+260h+ReturnLength], 0C0000017h
0x180010903  mov     rcx, [rcx+10h]
0x180010907  lea     r9, aStatus; "Status"
0x18001090e  call    WPP_SF_sDsd
0x180010913  mov     r14, [rbp+200h+var_200]
0x180010917  mov     eax, cs:g_TrustedEnvironment
0x18001091d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180010924  mov     esi, 8
0x180010929  test    eax, eax
0x18001092b  jnz     loc_180010BEE
0x180010931  xor     edx, edx; Val
0x180010933  lea     rcx, [rbp+200h+ProcessInformation]; void *
0x18001093a  mov     r8d, 0B0h; Size
0x180010940  call    memset_0
0x180010945  mov     r9d, 0B0h; ProcessInformationLength
0x18001094b  mov     [rsp+260h+ReturnLength], 0; ReturnLength
0x180010954  lea     r8, [rbp+200h+ProcessInformation]; ProcessInformation
0x18001095b  mov     edx, 56h ; 'V'; ProcessInformationClass
0x180010960  mov     rcx, rbx; ProcessHandle
0x180010963  call    cs:__imp_NtQueryInformationProcess
0x18001096a  nop     dword ptr [rax+rax+00h]
0x18001096f  test    eax, eax
0x180010971  js      loc_180010B8B
0x180010977  mov     ecx, [rbp+200h+ProcessInformation]
0x18001097d  lea     eax, [rcx-10h]
0x180010980  cmp     eax, 1
0x180010983  jbe     loc_180010B84
0x180010989  mov     eax, 1
0x18001098e  cmp     ecx, eax
0x180010990  cmovz   eax, esi
0x180010993  jmp     loc_180010BE8
0x180010998  test    r14, r14
0x18001099b  jnz     short loc_1800109DD
0x18001099d  mov     edi, 0C00000E5h
0x1800109a2  lea     rax, WPP_GLOBAL_Control
0x1800109a9  cmp     rcx, rax
0x1800109ac  jz      loc_180010913
0x1800109b2  test    byte ptr [rcx+1Ch], 1
0x1800109b6  jz      loc_180010913
0x1800109bc  mov     dword ptr [rsp+260h+var_230], 1B15h
0x1800109c4  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800109cb  mov     [rsp+260h+UserData], rax
0x1800109d0  mov     dword ptr [rsp+260h+ReturnLength], 0C00000E5h
0x1800109d8  jmp     loc_180010903
0x1800109dd  xor     ecx, ecx
0x1800109df  lea     rax, [rbp+200h+var_1E0]
0x1800109e3  mov     [rsp+260h+var_218], ecx
0x1800109e7  xor     r9d, r9d
0x1800109ea  mov     [rsp+260h+var_220], rax
0x1800109ef  mov     r8d, esi
0x1800109f2  mov     dword ptr [rsp+260h+var_228], esi
0x1800109f6  mov     rdx, r12
0x1800109f9  mov     [rsp+260h+var_230], rbx
0x1800109fe  mov     rax, r14
0x180010a01  mov     dword ptr [rsp+260h+UserData], ecx
0x180010a05  mov     [rsp+260h+ReturnLength], rcx
0x180010a0a  mov     rcx, [rdi+10h]
0x180010a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a13  mov     edi, eax
0x180010a15  test    eax, eax
0x180010a17  jns     short loc_180010A57
0x180010a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a20  lea     rax, WPP_GLOBAL_Control
0x180010a27  cmp     rcx, rax
0x180010a2a  jz      loc_180010913
0x180010a30  test    byte ptr [rcx+1Ch], 1
0x180010a34  jz      loc_180010913
0x180010a3a  mov     dword ptr [rsp+260h+var_230], 1B25h
0x180010a42  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a49  mov     [rsp+260h+UserData], rax
0x180010a4e  mov     dword ptr [rsp+260h+ReturnLength], edi
0x180010a52  jmp     loc_180010903
0x180010a57  mov     r9d, [rbp+200h+var_1F8]
0x180010a5b  mov     ecx, r15d
0x180010a5e  mov     r8, [rbp+200h+var_1F0]
0x180010a62  mov     rdx, [rbp+200h+var_1E8]
0x180010a66  mov     dword ptr [rsp+260h+UserData], esi
0x180010a6a  mov     [rsp+260h+ReturnLength], rbx
0x180010a6f  call    CheckSignaturePadding
0x180010a74  mov     edi, eax
0x180010a76  test    eax, eax
0x180010a78  jns     loc_180010B07
0x180010a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a85  lea     rax, WPP_GLOBAL_Control
0x180010a8c  cmp     rcx, rax
0x180010a8f  jz      loc_180010913
0x180010a95  test    byte ptr [rcx+1Ch], 1
0x180010a99  jz      loc_180010913
0x180010a9f  mov     dword ptr [rsp+260h+var_230], 1B32h
0x180010aa7  jmp     short loc_180010A42
0x180010aa9  mov     rax, [rax+98h]
0x180010ab0  mov     rcx, [rdi+10h]
0x180010ab4  mov     rdx, r10
0x180010ab7  mov     dword ptr [rsp+260h+var_230], r15d
0x180010abc  mov     dword ptr [rsp+260h+UserData], esi
0x180010ac0  mov     [rsp+260h+ReturnLength], r12
0x180010ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aca  mov     edi, eax
0x180010acc  test    eax, eax
0x180010ace  jns     short loc_180010B0B
0x180010ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ad7  cmp     rcx, rbx
0x180010ada  jz      loc_180010917
0x180010ae0  test    byte ptr [rcx+1Ch], 1
0x180010ae4  jz      loc_180010917
0x180010aea  mov     dword ptr [rsp+260h+var_230], 1B41h
0x180010af2  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010af9  mov     [rsp+260h+UserData], rax
0x180010afe  mov     dword ptr [rsp+260h+ReturnLength], edi
0x180010b02  jmp     loc_18001078C
0x180010b07  mov     r14, [rbp+200h+var_200]
0x180010b0b  xor     edi, edi
0x180010b0d  jmp     loc_180010917
0x180010b12  mov     edi, 0C00000BBh
0x180010b17  cmp     rcx, rbx
0x180010b1a  jz      loc_180010917
0x180010b20  test    byte ptr [rcx+1Ch], 1
0x180010b24  jz      loc_180010917
0x180010b2a  mov     dword ptr [rsp+260h+var_230], 1AFCh
0x180010b32  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010b39  mov     [rsp+260h+UserData], rax
0x180010b3e  mov     dword ptr [rsp+260h+ReturnLength], 0C00000BBh
0x180010b46  jmp     loc_18001078C
0x180010b4b  mov     edi, 0C0000008h
0x180010b50  cmp     rcx, rbx
0x180010b53  jz      loc_180010917
0x180010b59  test    byte ptr [rcx+1Ch], 1
0x180010b5d  jz      loc_180010917
0x180010b63  mov     dword ptr [rsp+260h+var_230], 1AD2h
0x180010b6b  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010b72  mov     [rsp+260h+UserData], rax
0x180010b77  mov     dword ptr [rsp+260h+ReturnLength], 0C0000008h
0x180010b7f  jmp     loc_18001078C
0x180010b84  mov     eax, 10h
0x180010b89  jmp     short loc_180010BE8
0x180010b8b  xorps   xmm0, xmm0
0x180010b8e  mov     [rbp+200h+var_1B8], 0
0x180010b96  xorps   xmm1, xmm1
0x180010b99  movdqa  [rbp+200h+var_1B0], xmm0
0x180010b9e  mov     r9d, 40h ; '@'; ProcessInformationLength
0x180010ba4  movdqa  [rbp+200h+var_1A0], xmm1
0x180010ba9  lea     r8, [rbp+200h+var_1C0]; ProcessInformation
0x180010bad  movdqa  [rbp+200h+var_190], xmm0
0x180010bb2  xor     edx, edx; ProcessInformationClass
0x180010bb4  mov     [rbp+200h+var_1C0], 40h ; '@'
0x180010bbc  mov     rcx, rbx; ProcessHandle
0x180010bbf  mov     [rsp+260h+ReturnLength], 0; ReturnLength
0x180010bc8  call    cs:__imp_NtQueryInformationProcess
0x180010bcf  nop     dword ptr [rax+rax+00h]
0x180010bd4  test    eax, eax
  ... truncated ...
```
