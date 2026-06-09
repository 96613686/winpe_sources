# IkeQueueAcquireToSa

- ea: `0x180002e90`
- end: `0x1800037bb`
- name: `IkeQueueAcquireToSa`
- size: `2347`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a40`
- `0x1800bbdb0`

## callees

- `0x180002e90`
- `0x180008388`
- `0x180025d88`
- `0x180039408`
- `0x18004890c`
- `0x180050850`
- `0x1800bc8e0`
- `0x1800bcc48`
- `0x1800bd128`
- `0x1800bd180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002f40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002f87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003107`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003171`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800031b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800033f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000347e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800034c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003670`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800036b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002f40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002f87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003107`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003171`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800031b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800033f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000347e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800034c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003670`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800036b7`
- `ntdll!EtwEventWriteTransfer` at `0x180003054`
- `ntdll!EtwEventWriteTransfer` at `0x1800032a4`
- `ntdll!EtwEventWriteTransfer` at `0x180003374`
- `ntdll!EtwEventWriteTransfer` at `0x1800035e6`
- `ntdll!EtwEventWriteTransfer` at `0x180003783`
- `ntdll!EtwEventWriteTransfer` at `0x180003054`
- `ntdll!EtwEventWriteTransfer` at `0x1800032a4`
- `ntdll!EtwEventWriteTransfer` at `0x180003374`
- `ntdll!EtwEventWriteTransfer` at `0x1800035e6`
- `ntdll!EtwEventWriteTransfer` at `0x180003783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003384`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003384`

## pseudocode

```c
__int64 __fastcall IkeQueueAcquireToSa(__int64 a1, _DWORD *a2)
{
  __int64 v4; // r14
  LPCRITICAL_SECTION v5; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v8; // rcx
  DWORD v9; // ecx
  char *v10; // rax
  const WCHAR *v11; // rdx
  __int64 v12; // rax
  bool v13; // zf
  int v14; // eax
  __int64 v15; // rcx
  __int64 SaForAcquire; // r13
  __int64 v17; // rbx
  __int64 LockSemaphore_low; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rbx
  __int64 *v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v25; // rax
  DWORD v26; // ecx
  __int64 *v27; // rax
  __int64 v28; // rcx
  DWORD v29; // ecx
  char *v30; // rax
  const WCHAR *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  __int64 *v35; // rcx
  __int64 v36; // rcx
  _QWORD *v37; // rsi
  __int64 *v38; // rax
  __int64 v39; // r15
  int v40; // edi
  __int64 v41; // rsi
  __int64 v42; // rax
  LPCRITICAL_SECTION v43; // rax
  DWORD v44; // ecx
  __int64 *v45; // rax
  __int64 v46; // rcx
  DWORD v47; // ecx
  char *v48; // rax
  const WCHAR *v49; // rdx
  __int64 v50; // rax
  int v51; // eax
  LPCRITICAL_SECTION v52; // rax
  DWORD v53; // ecx
  __int64 *v54; // rax
  __int64 v55; // rcx
  DWORD v56; // ecx
  char *v57; // rax
  const WCHAR *v58; // rdx
  int v59; // r14d
  int v61; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v62; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v64; // [rsp+58h] [rbp-A8h]
  __int64 v65; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v66; // [rsp+68h] [rbp-98h] BYREF
  __int128 v67; // [rsp+78h] [rbp-88h] BYREF
  __int64 v68; // [rsp+88h] [rbp-78h] BYREF
  char *v69; // [rsp+90h] [rbp-70h] BYREF
  int v70; // [rsp+98h] [rbp-68h]
  int v71; // [rsp+9Ch] [rbp-64h]
  char *v72; // [rsp+A0h] [rbp-60h]
  int v73; // [rsp+A8h] [rbp-58h]
  int v74; // [rsp+ACh] [rbp-54h]
  __int64 *v75; // [rsp+B0h] [rbp-50h]
  __int64 v76; // [rsp+B8h] [rbp-48h]
  const WCHAR *v77; // [rsp+C0h] [rbp-40h]
  int v78; // [rsp+C8h] [rbp-38h]
  int v79; // [rsp+CCh] [rbp-34h]
  const char *v80; // [rsp+D0h] [rbp-30h]
  __int64 v81; // [rsp+D8h] [rbp-28h]
  __int64 *v82; // [rsp+E0h] [rbp-20h]
  __int64 v83; // [rsp+E8h] [rbp-18h]
  __int64 *v84; // [rsp+F0h] [rbp-10h]
  __int64 v85; // [rsp+F8h] [rbp-8h]
  int *v86; // [rsp+100h] [rbp+0h]
  __int64 v87; // [rsp+108h] [rbp+8h]
  __int64 v88; // [rsp+110h] [rbp+10h] BYREF
  __int64 v89; // [rsp+118h] [rbp+18h]
  int *v90; // [rsp+120h] [rbp+20h]
  __int64 v91; // [rsp+128h] [rbp+28h]

  *a2 = 0;
  v62 = 0;
  v4 = -1;
  v67 = 0;
  v66 = 0;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v5 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v5 = gIkeExtGlobals;
LABEL_9:
    v8 = 0;
    goto LABEL_10;
  }
  v8 = *Value;
  v5 = gIkeExtGlobals;
LABEL_10:
  v65 = v8;
  v75 = &v65;
  v76 = 8;
  if ( !v5 )
    goto LABEL_18;
  v9 = (DWORD)v5[86].LockSemaphore;
  if ( v9 == -1 )
    goto LABEL_18;
  v10 = (char *)TlsGetValue(v9);
  v11 = (const WCHAR *)(v10 + 8);
  if ( !v10 )
    v11 = 0;
  if ( v11 )
  {
    v12 = -1;
    do
      v13 = v11[++v12] == 0;
    while ( !v13 );
    v14 = 2 * v12 + 2;
  }
  else
  {
LABEL_18:
    v11 = &LocaleName;
    v14 = 2;
  }
  v78 = v14;
  v69 = off_180173280;
  v77 = v11;
  v79 = 0;
  v80 = "IkeQueueAcquireToSa";
  v81 = 20;
  v63 = 0x50B000000LL;
  v64 = 1;
  v70 = *(unsigned __int16 *)off_180173280;
  v72 = (char *)&dword_180166EA4;
  v71 = 2;
  v73 = 45;
  v74 = 1;
  v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v63, 0, 0, 5, &v69);
LABEL_20:
  if ( (*(_BYTE *)(a1 + 376) & 0x10) == 0 )
  {
    SaForAcquire = IkeFindSaForAcquire(a1, &v62);
    if ( SaForAcquire )
      goto LABEL_89;
    v17 = v62;
    if ( !v62 )
    {
      LockSemaphore_low = *(unsigned int *)(a1 + 372);
      if ( (_DWORD)LockSemaphore_low == 1 )
      {
        v19 = IkeTryExpireSAQueueAuthIp(a1, a2);
      }
      else
      {
        if ( (_DWORD)LockSemaphore_low != 2 )
          goto LABEL_29;
        v19 = IkeTryExhaustedSAQueueIkeV2(a1, a2);
      }
      SaForAcquire = v19;
      if ( v19 )
        goto LABEL_89;
LABEL_29:
      if ( !*a2 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          if ( gIkeExtGlobals
            && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
            && (v21 = (__int64 *)TlsGetValue(LockSemaphore_low), v20 = WPP_GLOBAL_Control, v21) )
          {
            v22 = *v21;
          }
          else
          {
            LODWORD(v22) = 0;
          }
          v23 = v20[2];
          TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
          WPP_SF_iSq(v23, 23, (unsigned int)WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids, v22, TlsPeerAddr, a1);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v25 = gIkeExtGlobals;
          if ( gIkeExtGlobals )
          {
            v26 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
            if ( v26 != -1 )
            {
              v27 = (__int64 *)TlsGetValue(v26);
              if ( v27 )
              {
                v28 = *v27;
                v25 = gIkeExtGlobals;
LABEL_46:
                v65 = v28;
                v75 = &v65;
                v76 = 8;
                if ( !v25 )
                  goto LABEL_54;
                v29 = (DWORD)v25[86].LockSemaphore;
                if ( v29 == -1 )
                  goto LABEL_54;
                v30 = (char *)TlsGetValue(v29);
                v31 = (const WCHAR *)(v30 + 8);
                if ( !v30 )
                  v31 = 0;
                if ( v31 )
                {
                  v32 = -1;
                  do
                    v13 = v31[++v32] == 0;
                  while ( !v13 );
                  v33 = 2 * v32 + 2;
                }
                else
                {
LABEL_54:
                  v31 = &LocaleName;
                  v33 = 2;
                }
                v78 = v33;
                v77 = v31;
                v80 = "Could not queue acquire to any MM SA";
                v79 = 0;
                v82 = &v62;
                v69 = off_180173280;
                v81 = 37;
                v62 = a1;
                v83 = 8;
                v63 = 0x40B000000LL;
                v64 = 0;
                v70 = *(unsigned __int16 *)off_180173280;
                v72 = &byte_18015AEFF;
                v71 = 2;
                v73 = 63;
                v74 = 1;
                v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EtwEventWriteTransfer(qword_180173298, &v63, 0, 0, 6, &v69);
                goto LABEL_89;
              }
              v25 = gIkeExtGlobals;
            }
          }
          v28 = 0;
          goto LABEL_46;
        }
      }
LABEL_89:
      if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
      {
LABEL_107:
        v15 = SaForAcquire;
        return IkeReturnError(v15, "IkeQueueAcquireToSa");
      }
      v52 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v53 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v53 != -1 )
        {
          v54 = (__int64 *)TlsGetValue(v53);
          if ( v54 )
          {
            v55 = *v54;
            v52 = gIkeExtGlobals;
LABEL_98:
            v63 = v55;
            v75 = &v63;
            v76 = 8;
            if ( !v52 )
              goto LABEL_105;
            v56 = (DWORD)v52[86].LockSemaphore;
            if ( v56 == -1 )
              goto LABEL_105;
            v57 = (char *)TlsGetValue(v56);
            v58 = (const WCHAR *)(v57 + 8);
            if ( !v57 )
              v58 = 0;
            if ( v58 )
            {
              do
                v13 = v58[++v4] == 0;
              while ( !v13 );
              v59 = 2 * v4 + 2;
            }
            else
            {
LABEL_105:
              v58 = &LocaleName;
              v59 = 2;
            }
            v69 = off_180173280;
            v77 = v58;
            v78 = v59;
            v79 = 0;
            v80 = "IkeQueueAcquireToSa";
            v81 = 20;
            v88 = 0x50B000000LL;
            v89 = 1;
            v70 = *(unsigned __int16 *)off_180173280;
            v72 = byte_180166E6B;
            v71 = 2;
            v73 = 45;
            v74 = 1;
            LODWORD(v62) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(qword_180173298, &v88, 0, 0, 5, &v69);
            goto LABEL_107;
          }
          v52 = gIkeExtGlobals;
        }
      }
      v55 = 0;
      goto LABEL_98;
    }
    v34 = *(_QWORD *)(a1 + 360);
    *((_QWORD *)&v67 + 1) = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&v67 = v34;
    *((_QWORD *)&v66 + 1) = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&v66 = v62;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v63 = ActivityTransfer;
      v61 = 0;
      v64 = 0x8000000000000001uLL;
      if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
      {
        v89 = 16;
        v88 = (__int64)&Microsoft_Windows_Networking_ProviderId;
        v90 = &v61;
        v91 = 4;
        EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &v63, &v67, &v66, 2, &v88);
      }
      else
      {
        EtwEventWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &v63, &v67, &v66, 0, 0);
      }
    }
    *a2 = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 48));
    v35 = *(__int64 **)(v17 + 120);
    if ( *v35 != v17 + 112 )
      __fastfail(3u);
    *(_QWORD *)(a1 + 8) = v35;
    *(_QWORD *)a1 = v17 + 112;
    *v35 = a1;
    *(_QWORD *)(v17 + 120) = a1;
    ++*(_DWORD *)(v17 + 184);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 48));
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals
        && (v36 = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)v36 != -1)
        && (v38 = (__int64 *)TlsGetValue(v36), v37 = WPP_GLOBAL_Control, v38) )
      {
        v39 = *v38;
      }
      else
      {
        LODWORD(v39) = 0;
      }
      v40 = *(_DWORD *)(v17 + 184) + *(_DWORD *)(v17 + 188);
      v41 = v37[2];
      v42 = IkeGetTlsPeerAddr(v36);
      WPP_SF_iSqqD(v41, 24, (unsigned int)WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids, v39, v42, a1, v17, v40);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
    {
      QueueAcquirePostponedWorkEntry(v17);
      goto LABEL_89;
    }
    v43 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v44 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v44 != -1 )
      {
        v45 = (__int64 *)TlsGetValue(v44);
        if ( v45 )
        {
          v46 = *v45;
          v43 = gIkeExtGlobals;
LABEL_78:
          v65 = v46;
          v75 = &v65;
          v76 = 8;
          if ( !v43 )
            goto LABEL_86;
          v47 = (DWORD)v43[86].LockSemaphore;
          if ( v47 == -1 )
            goto LABEL_86;
          v48 = (char *)TlsGetValue(v47);
          v49 = (const WCHAR *)(v48 + 8);
          if ( !v48 )
            v49 = 0;
          if ( v49 )
          {
            v50 = -1;
            do
              v13 = v49[++v50] == 0;
            while ( !v13 );
            v51 = 2 * v50 + 2;
          }
          else
          {
LABEL_86:
            v49 = &LocaleName;
            v51 = 2;
          }
          v78 = v51;
          v77 = v49;
          v80 = "IkeQueueAcquireToSa: Queue acquire to MMSA";
          v79 = 0;
          v82 = &v68;
          v81 = 43;
          v84 = &v63;
          v68 = a1;
          v83 = 8;
          v63 = v17;
          v85 = 8;
          v61 = *(_DWORD *)(v17 + 184) + *(_DWORD *)(v17 + 188);
          v86 = &v61;
          v69 = off_180173280;
          v87 = 4;
          v88 = 0x40B000000LL;
          v89 = 0;
          v70 = *(unsigned __int16 *)off_180173280;
          v72 = (char *)&word_18015AE9E;
          v71 = 2;
          v73 = 85;
          v74 = 1;
          LODWORD(v62) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v88, 0, 0, 8, &v69);
          QueueAcquirePostponedWorkEntry(v17);
          goto LABEL_89;
        }
        v43 = gIkeExtGlobals;
      }
    }
    v46 = 0;
    goto LABEL_78;
  }
  v15 = 0;
  return IkeReturnError(v15, "IkeQueueAcquireToSa");
}

```

## disassembly

```asm
0x180002e90  mov     [rsp-8+arg_10], rbx
0x180002e95  push    rbp
0x180002e96  push    rsi
0x180002e97  push    rdi
0x180002e98  push    r12
0x180002e9a  push    r13
0x180002e9c  push    r14
0x180002e9e  push    r15
0x180002ea0  lea     rbp, [rsp-40h]
0x180002ea5  sub     rsp, 140h
0x180002eac  mov     rax, cs:__security_cookie
0x180002eb3  xor     rax, rsp
0x180002eb6  mov     [rbp+70h+var_40], rax
0x180002eba  xor     esi, esi
0x180002ebc  lea     rbx, aIkequeueacquir; "IkeQueueAcquireToSa"
0x180002ec3  mov     [rdx], esi
0x180002ec5  lea     r15, _TraceLoggingMetadataEnd
0x180002ecc  mov     eax, cs:dword_180173278
0x180002ed2  lea     r13, _TraceLoggingMetadata
0x180002ed9  mov     [rsp+170h+var_128], rsi
0x180002ede  xorps   xmm0, xmm0
0x180002ee1  xorps   xmm1, xmm1
0x180002ee4  mov     rdi, rdx
0x180002ee7  mov     r12, rcx
0x180002eea  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180002ef1  movups  [rsp+170h+var_F8], xmm0
0x180002ef6  movups  [rsp+170h+var_108], xmm1
0x180002efb  cmp     eax, 5
0x180002efe  jbe     loc_18000305A
0x180002f04  mov     rcx, cs:qword_180173290
0x180002f0b  mov     rax, cs:qword_180173288
0x180002f12  test    al, 1
0x180002f14  jz      loc_18000305A
0x180002f1a  mov     rax, rcx
0x180002f1d  and     eax, 1
0x180002f20  cmp     rax, rcx
0x180002f23  jnz     loc_18000305A
0x180002f29  mov     rax, cs:gIkeExtGlobals
0x180002f30  test    rax, rax
0x180002f33  jz      short loc_180002F5E
0x180002f35  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180002f3b  cmp     ecx, 0FFFFFFFFh
0x180002f3e  jz      short loc_180002F5E
0x180002f40  call    cs:__imp_TlsGetValue
0x180002f46  test    rax, rax
0x180002f49  jz      short loc_180002F57
0x180002f4b  mov     rcx, [rax]
0x180002f4e  mov     rax, cs:gIkeExtGlobals
0x180002f55  jmp     short loc_180002F61
0x180002f57  mov     rax, cs:gIkeExtGlobals
0x180002f5e  mov     rcx, rsi
0x180002f61  mov     [rsp+170h+var_110], rcx
0x180002f66  lea     rcx, [rsp+170h+var_110]
0x180002f6b  mov     [rbp+70h+var_C0], rcx
0x180002f6f  mov     [rbp+70h+var_B8], 8
0x180002f77  test    rax, rax
0x180002f7a  jz      short loc_180002FB4
0x180002f7c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180002f82  cmp     ecx, 0FFFFFFFFh
0x180002f85  jz      short loc_180002FB4
0x180002f87  call    cs:__imp_TlsGetValue
0x180002f8d  test    rax, rax
0x180002f90  lea     rdx, [rax+8]
0x180002f94  cmovz   rdx, rsi
0x180002f98  test    rdx, rdx
0x180002f9b  jz      short loc_180002FB4
0x180002f9d  mov     rax, r14
0x180002fa0  cmp     [rdx+rax*2+2], si
0x180002fa5  lea     rax, [rax+1]
0x180002fa9  jnz     short loc_180002FA0
0x180002fab  lea     eax, ds:2[rax*2]
0x180002fb2  jmp     short loc_180002FC0
0x180002fb4  lea     rdx, LocaleName
0x180002fbb  mov     eax, 2
0x180002fc0  mov     [rbp+70h+var_A8], eax
0x180002fc3  xor     r9d, r9d
0x180002fc6  movzx   eax, cs:word_180166E9A
0x180002fcd  xor     r8d, r8d
0x180002fd0  mov     dword ptr [rsp+170h+var_120+4], eax
0x180002fd4  mov     rax, cs:off_180173280
0x180002fdb  mov     [rbp+70h+var_E0], rax
0x180002fdf  mov     [rbp+70h+var_B0], rdx
0x180002fe3  lea     rdx, [rsp+170h+var_120]
0x180002fe8  mov     [rbp+70h+var_A4], esi
0x180002feb  mov     [rbp+70h+var_A0], rbx
0x180002fef  mov     [rbp+70h+var_98], 14h
0x180002ff7  mov     dword ptr [rsp+170h+var_120], 0B000000h
0x180002fff  mov     [rsp+170h+var_118], 1
0x180003008  movzx   eax, word ptr [rax]
0x18000300b  mov     [rbp+70h+var_D8], eax
0x18000300e  lea     rax, dword_180166EA4
0x180003015  mov     [rbp+70h+var_D0], rax
0x180003019  mov     rax, r15
0x18000301c  sub     eax, r13d
0x18000301f  mov     [rbp+70h+var_D4], 2
0x180003026  mov     [rbp+70h+var_C8], 2Dh ; '-'
0x18000302d  mov     [rbp+70h+var_C4], 1
0x180003034  mov     [rsp+170h+var_130], eax
0x180003038  mov     eax, [rsp+170h+var_130]
0x18000303c  mov     rcx, cs:qword_180173298
0x180003043  lea     rax, [rbp+70h+var_E0]
0x180003047  mov     [rsp+170h+var_148], rax
0x18000304c  mov     dword ptr [rsp+170h+var_150], 5
0x180003054  call    cs:__imp_EtwEventWriteTransfer
0x18000305a  test    byte ptr [r12+178h], 10h
0x180003063  jz      short loc_18000306C
0x180003065  xor     ecx, ecx
0x180003067  jmp     loc_18000378C
0x18000306c  lea     rdx, [rsp+170h+var_128]
0x180003071  mov     rcx, r12
0x180003074  call    IkeFindSaForAcquire
0x180003079  mov     r13, rax
0x18000307c  test    rax, rax
0x18000307f  jnz     loc_18000361E
0x180003085  mov     rbx, [rsp+170h+var_128]
0x18000308a  test    rbx, rbx
0x18000308d  jnz     loc_1800032B6
0x180003093  mov     ecx, [r12+174h]
0x18000309b  cmp     ecx, 1
0x18000309e  jnz     short loc_1800030AD
0x1800030a0  mov     rdx, rdi
0x1800030a3  mov     rcx, r12
0x1800030a6  call    IkeTryExpireSAQueueAuthIp
0x1800030ab  jmp     short loc_1800030BD
0x1800030ad  cmp     ecx, 2
0x1800030b0  jnz     short loc_1800030C9
0x1800030b2  mov     rdx, rdi
0x1800030b5  mov     rcx, r12
0x1800030b8  call    IkeTryExhaustedSAQueueIkeV2
0x1800030bd  mov     r13, rax
0x1800030c0  test    rax, rax
0x1800030c3  jnz     loc_180003617
0x1800030c9  cmp     [rdi], esi
0x1800030cb  jnz     loc_180003617
0x1800030d1  mov     rbx, cs:WPP_GLOBAL_Control
0x1800030d8  lea     rax, WPP_GLOBAL_Control
0x1800030df  cmp     rbx, rax
0x1800030e2  jz      short loc_18000314B
0x1800030e4  cmp     byte ptr [rbx+19h], 4
0x1800030e8  jb      short loc_18000314B
0x1800030ea  test    byte ptr [rbx+1Ch], 10h
0x1800030ee  jz      short loc_18000314B
0x1800030f0  mov     rax, cs:gIkeExtGlobals
0x1800030f7  test    rax, rax
0x1800030fa  jz      short loc_18000311E
0x1800030fc  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180003102  cmp     ecx, 0FFFFFFFFh
0x180003105  jz      short loc_18000311E
0x180003107  call    cs:__imp_TlsGetValue
0x18000310d  mov     rbx, cs:WPP_GLOBAL_Control
0x180003114  test    rax, rax
0x180003117  jz      short loc_18000311E
0x180003119  mov     rdi, [rax]
0x18000311c  jmp     short loc_180003121
0x18000311e  mov     rdi, rsi
0x180003121  mov     rbx, [rbx+10h]
0x180003125  call    IkeGetTlsPeerAddr
0x18000312a  mov     edx, 17h
0x18000312f  mov     [rsp+170h+var_148], r12
0x180003134  mov     r9, rdi
0x180003137  mov     [rsp+170h+var_150], rax
0x18000313c  lea     r8, WPP_ee79efc748f53d5223c07ba2e232d700_Traceguids
0x180003143  mov     rcx, rbx
0x180003146  call    WPP_SF_iSq
0x18000314b  mov     eax, cs:dword_180173278
0x180003151  cmp     eax, 4
0x180003154  jbe     loc_180003617
0x18000315a  mov     rax, cs:gIkeExtGlobals
0x180003161  test    rax, rax
0x180003164  jz      short loc_18000318F
0x180003166  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18000316c  cmp     ecx, 0FFFFFFFFh
0x18000316f  jz      short loc_18000318F
0x180003171  call    cs:__imp_TlsGetValue
0x180003177  test    rax, rax
0x18000317a  jz      short loc_180003188
0x18000317c  mov     rcx, [rax]
0x18000317f  mov     rax, cs:gIkeExtGlobals
0x180003186  jmp     short loc_180003192
0x180003188  mov     rax, cs:gIkeExtGlobals
0x18000318f  mov     rcx, rsi
0x180003192  mov     [rsp+170h+var_110], rcx
0x180003197  lea     rcx, [rsp+170h+var_110]
0x18000319c  mov     [rbp+70h+var_C0], rcx
0x1800031a0  mov     [rbp+70h+var_B8], 8
0x1800031a8  test    rax, rax
0x1800031ab  jz      short loc_1800031E5
0x1800031ad  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800031b3  cmp     ecx, 0FFFFFFFFh
0x1800031b6  jz      short loc_1800031E5
0x1800031b8  call    cs:__imp_TlsGetValue
0x1800031be  test    rax, rax
0x1800031c1  lea     rdx, [rax+8]
0x1800031c5  cmovz   rdx, rsi
0x1800031c9  test    rdx, rdx
0x1800031cc  jz      short loc_1800031E5
0x1800031ce  mov     rax, r14
0x1800031d1  cmp     [rdx+rax*2+2], si
0x1800031d6  lea     rax, [rax+1]
0x1800031da  jnz     short loc_1800031D1
0x1800031dc  lea     eax, ds:2[rax*2]
0x1800031e3  jmp     short loc_1800031F1
0x1800031e5  lea     rdx, LocaleName
0x1800031ec  mov     eax, 2
0x1800031f1  mov     [rbp+70h+var_A8], eax
0x1800031f4  lea     rdi, _TraceLoggingMetadata
0x1800031fb  mov     [rbp+70h+var_B0], rdx
0x1800031ff  lea     rax, aCouldNotQueueA; "Could not queue acquire to any MM SA"
0x180003206  mov     [rbp+70h+var_A0], rax
0x18000320a  lea     rdx, [rsp+170h+var_120]
0x18000320f  lea     rax, [rsp+170h+var_128]
0x180003214  mov     [rbp+70h+var_A4], esi
0x180003217  mov     [rbp+70h+var_90], rax
0x18000321b  xor     r9d, r9d
0x18000321e  movzx   eax, cs:word_18015AEF5
0x180003225  xor     r8d, r8d
0x180003228  mov     dword ptr [rsp+170h+var_120+4], eax
0x18000322c  mov     rax, cs:off_180173280
0x180003233  mov     [rbp+70h+var_E0], rax
0x180003237  mov     [rbp+70h+var_98], 25h ; '%'
0x18000323f  mov     [rsp+170h+var_128], r12
0x180003244  mov     [rbp+70h+var_88], 8
0x18000324c  mov     dword ptr [rsp+170h+var_120], 0B000000h
0x180003254  mov     [rsp+170h+var_118], rsi
0x180003259  movzx   eax, word ptr [rax]
0x18000325c  mov     [rbp+70h+var_D8], eax
0x18000325f  lea     rax, byte_18015AEFF
0x180003266  mov     [rbp+70h+var_D0], rax
0x18000326a  mov     rax, r15
0x18000326d  sub     eax, edi
0x18000326f  mov     [rbp+70h+var_D4], 2
0x180003276  mov     [rbp+70h+var_C8], 3Fh ; '?'
0x18000327d  mov     [rbp+70h+var_C4], 1
0x180003284  mov     [rsp+170h+var_130], eax
0x180003288  mov     eax, [rsp+170h+var_130]
0x18000328c  mov     rcx, cs:qword_180173298
0x180003293  lea     rax, [rbp+70h+var_E0]
0x180003297  mov     [rsp+170h+var_148], rax
0x18000329c  mov     dword ptr [rsp+170h+var_150], 6
0x1800032a4  call    cs:__imp_EtwEventWriteTransfer
0x1800032aa  lea     rbx, aIkequeueacquir; "IkeQueueAcquireToSa"
0x1800032b1  jmp     loc_180003625
0x1800032b6  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x1800032bd  mov     rax, [r12+168h]
0x1800032c5  movups  [rsp+170h+var_F8], xmm0
0x1800032ca  mov     qword ptr [rsp+170h+var_F8], rax
0x1800032cf  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800032d5  movups  [rsp+170h+var_108], xmm0
0x1800032da  mov     qword ptr [rsp+170h+var_108], rbx
0x1800032df  test    eax, eax
0x1800032e1  jz      loc_18000337A
0x1800032e7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800032ed  test    eax, eax
0x1800032ef  jz      loc_18000337A
0x1800032f5  mov     rax, cs:ActivityTransfer
0x1800032fc  lea     r9, [rsp+170h+var_108]
0x180003301  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle
0x180003308  lea     r8, [rsp+170h+var_F8]
0x18000330d  mov     [rsp+170h+var_120], rax
0x180003312  lea     rdx, [rsp+170h+var_120]
0x180003317  mov     rax, 8000000000000001h
0x180003321  mov     [rsp+170h+var_130], esi
0x180003325  mov     [rsp+170h+var_118], rax
0x18000332a  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180003330  test    eax, eax
0x180003332  jz      short loc_18000336B
0x180003334  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18000333b  mov     [rbp+70h+var_58], 10h
0x180003343  mov     [rbp+70h+var_60], rax
0x180003347  lea     rax, [rsp+170h+var_130]
0x18000334c  mov     [rbp+70h+var_50], rax
0x180003350  lea     rax, [rbp+70h+var_60]
0x180003354  mov     [rsp+170h+var_148], rax
0x180003359  mov     dword ptr [rsp+170h+var_150], 2
0x180003361  mov     [rbp+70h+var_48], 4
0x180003369  jmp     short loc_180003374
0x18000336b  mov     [rsp+170h+var_148], rsi
0x180003370  mov     dword ptr [rsp+170h+var_150], esi
0x180003374  call    cs:__imp_EtwEventWriteTransfer
0x18000337a  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000337e  mov     dword ptr [rdi], 1
0x180003384  call    cs:__imp_EnterCriticalSection
0x18000338a  mov     rcx, [rbx+78h]
0x18000338e  lea     rax, [rbx+70h]
0x180003392  cmp     [rcx], rax
0x180003395  jz      short loc_18000339E
0x180003397  mov     ecx, 3
0x18000339c  int     29h; Win8: RtlFailFast(ecx)
0x18000339e  mov     [r12+8], rcx
0x1800033a3  mov     [r12], rax
0x1800033a7  mov     [rcx], r12
0x1800033aa  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800033ae  mov     [rax+8], r12
0x1800033b2  inc     dword ptr [rbx+0B8h]
0x1800033b8  call    cs:__imp_LeaveCriticalSection
0x1800033be  mov     rsi, cs:WPP_GLOBAL_Control
0x1800033c5  lea     rax, WPP_GLOBAL_Control
0x1800033cc  cmp     rsi, rax
0x1800033cf  jz      loc_180003458
0x1800033d5  cmp     byte ptr [rsi+19h], 4
  ... truncated ...
```
